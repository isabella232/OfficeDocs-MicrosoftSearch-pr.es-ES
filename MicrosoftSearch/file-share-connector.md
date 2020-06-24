---
title: Conector de recurso compartido de archivos para Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de recursos compartidos de archivos para Microsoft Search.
ms.openlocfilehash: 2349ad753508d5f19a70648d9cbf1df495b27108
ms.sourcegitcommit: 7eda9b621def0659d7e7bc8b989f8adc929cce93
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "44861098"
---
# <a name="file-share-connector"></a>Conector de uso compartido de archivos

Con el conector de recursos compartidos de archivos, los usuarios de la organización pueden buscar recursos compartidos de archivos locales. Los resultados de la búsqueda de estos recursos compartidos se combinan con los resultados de [SharePoint](http://sharepoint.com/) y [Microsoft OneDrive para la empresa](https://onedrive.live.com/about/business/).

Este artículo está destinado a los administradores de [Microsoft 365](https://www.microsoft.com/microsoft-365) o a cualquiera que configure, ejecute y supervise un conector de recursos compartidos de archivos. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.

## <a name="install-a-data-gateway"></a>Instalar una puerta de enlace de datos
Para obtener acceso a los datos de terceros, debe instalar y configurar una puerta de enlace de [Microsoft Power BI](https://msit.powerbi.com/) . Consulte [instalar una puerta de enlace local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) para obtener más información.  

## <a name="content-requirements"></a>Requisitos de contenido
**Tipos de archivo**. Solo se pueden indizar y buscar los archivos en estos formatos: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, DAB, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS y ZIP. Solo se indiza el contenido textual de estos formatos. Se omite todo el contenido multimedia.
 
**Límites de tamaño de archivo**. El tamaño máximo de archivo admitido es 100 MB. Los archivos que superan los 100 MB se omiten de la indización. El límite de tamaño posterior al proceso es de 4 MB. El procesamiento se detiene cuando el tamaño de un archivo alcanza 4 MB. Como resultado, es posible que algunas frases presentes en el archivo no funcionen para la búsqueda.

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos
En la página **conectar con origen de datos** , seleccione **recurso compartido de archivos** y proporcione el nombre, el identificador de conexión y la descripción. En la página siguiente, especifique la ruta de acceso al recurso compartido de archivos y seleccione la puerta de enlace instalada previamente. Escriba las credenciales de una cuenta de usuario de [Microsoft Windows](https://microsoft.com/windows) con acceso de lectura a todos los archivos del recurso compartido. Recorra el resto de la configuración y publique la conexión.

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización
El intervalo de programación de actualización predeterminada recomendado es de 15 minutos, pero puede cambiarlo a otro intervalo que prefiera.

## <a name="set-up-your-search-results-page"></a>Configurar la página de resultados de la búsqueda
Para mostrar distintos resultados de conexión de archivos en las pestañas **todos** y **archivos** , debe configurar una página de resultados del motor de búsqueda de [SharePoint](http://sharepoint.com/) :
- La tabla **All** muestra los resultados combinados de las conexiones de archivos, archivos de SharePoint, archivos de [OneDrive](https://onedrive.live.com/about/business/) y sitios de SharePoint. 
- Los **archivos** verticales muestran todos los resultados de los archivos de las conexiones, SharePoint y OneDrive.
Los resultados de las conexiones de archivos se agregan a los resultados ya existentes en los verticales de **todos** los **archivos** y.

Para configurar la página de resultados de la búsqueda, siga estos pasos:
1. Cree una colección de sitios de SharePoint con una página de búsqueda moderna.

2. Instale un [Shell de administración de SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).

3. Abra el shell de administración de SharePoint Online como administrador e importe el módulo **Microsoft.SharePoint.Client.dll** presente en `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll` .

> [!NOTE]
> Esta ruta de acceso puede no ser la misma para todos los usuarios.

Para importar el módulo, ejecute este comando en el [Shell de administración de SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588):
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. Ahora, ejecute este script:
```bash
$orgName = Read-Host -prompt 'Please enter your org name'
$userName = Read-Host -prompt 'Enter user name'
$userCreds = Get-Credential -UserName $userName -Message "Type the password"
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCreds

$url = Read-Host -Prompt 'Please enter the site url'
$site = Get-SPOSite -Identity $url
Set-SPOSite $url -DenyAddAndCustomizePages 0

$pwd = Read-Host -AsSecureString 'type the password'
$context = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credential = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $pwd)
$context.Credentials = $credential
$web = $context.Web
$context.Load($web)
$web.AllProperties["AllVerticalContent"] = "Combined"
$web.Update()
$context.ExecuteQuery()
$web.AllProperties["FilesVerticalContent"] = "ConnectorsOnly"
$web.Update()
$context.ExecuteQuery()
Set-SPOSite $url -DenyAddAndCustomizePages 1

Write-Host "Success" -ForegroundColor Cyan
Read-Host -Prompt 'Press enter to exit'
```

5. Escriba los valores necesarios en [Microsoft PowerShell](https://microsoft.com/powershell), como el nombre de la organización, el nombre de usuario, la contraseña y la dirección URL del sitio. Por **ejemplo**, si las credenciales de administrador son `admin@a830edad9050849823J19081300.onmicrosoft.com` , el nombre de la organización es **a830edad9050849823J19081300**y la dirección URL del sitio es `https:// a830edad9050849823J19081300.sharepoint.com` .

> [!NOTE]
> La configuración **AllProperties** solo puede realizarse en un nivel de colección de sitios (Teams/commes).

6. Ahora puede buscar archivos indizados y ver los resultados en las pestañas **todos** y **archivos** .

## <a name="search-for-file-share-content-in-the-search-results-page"></a>Buscar contenido de recurso compartido de archivos en la página de resultados de búsqueda
Para buscar contenido indizado, vaya a la Página principal de [SharePoint](http://sharepoint.com/) de su inquilino de prueba. Los resultados se mostrarán en las pestañas **todos** y **archivos** .

Debido a las restricciones del explorador, no puede seleccionar un resultado de archivo para ver o abrir archivos en las búsquedas de recursos compartidos de archivos locales. Para abrir estos archivos, copie el vínculo del resultado del archivo y péguelo en la barra de direcciones del explorador del sistema. Para [Windows](https://microsoft.com/windows), use el explorador de Windows. A continuación, puede abrir el archivo en el sistema.

![Búsqueda de SharePoint con el cuadro de diálogo Copiar vínculo abierto.](media/fileshare-search.png)

## <a name="troubleshooting"></a>Solución de problemas
Si algo es muy incorrecto en una conexión, su estado indica que **ha fallado**. Para obtener más información acerca de los tres tipos de errores, vaya a la página de **detalles del error** y seleccione la conexión con error. Consulte [administrar el conector](manage-connector.md) para obtener más información.
1. **No se puede obtener acceso a la puerta de enlace (código de error: 11)**. La máquina de la puerta de enlace para la conexión está inactiva. Compruebe si el proceso de [Power BI](https://msit.powerbi.com/) se ejecuta en la máquina de la puerta de enlace.
2. **Error de autenticación (código de error: 12)**. Las credenciales usadas para crear la conexión expiraron o ya no son válidas. Para resolver este error, escriba credenciales válidas.
3. **Error interno (código de error: cualquier cosa que no sea 11 o 12)**. Hay un error en la infraestructura del conector. Vea el artículo de comentarios para obtener [información](connectors-feedback.md) sobre cómo informar de estos errores.

## <a name="limitations"></a>Limitaciones
El conector de recursos compartidos de archivos tiene estas limitaciones en la versión preliminar:
* Solo se pueden Indizar archivos con propiedades fijas, no con propiedades personalizadas.
* Actualmente no se admiten las listas de control de acceso (ACL) del recurso compartido de archivos. Solo se admiten las ACL de archivos NTFS.
* Las identidades externas no son compatibles. Deben estar asignados a identidades de [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) .
