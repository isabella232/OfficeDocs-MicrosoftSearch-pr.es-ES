---
title: Establecer motor de búsqueda predeterminado
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Obtenga información sobre cómo establecer a Bing como motor de búsqueda predeterminado de su empresa con Microsoft Search.
ms.openlocfilehash: a0798da94f4433bb754c71b9e0d00e09ba5a543b
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612533"
---
# <a name="set-default-search-engine"></a>Establecer motor de búsqueda predeterminado

Configurar el explorador predeterminado, el motor de búsqueda predeterminado y la página principal predeterminada le ayudará a los usuarios a descubrir las capacidades de Microsoft Search, fomentar el uso más y proporcionar una experiencia más suave.
  
Para establecer el motor de búsqueda predeterminado para la organización, siga los pasos siguientes.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-11"></a>Internet Explorer 11

Los usuarios podrán cambiar el proveedor de búsqueda después de establece esta directiva.
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>1. configurar el equipo local que se usará para establecer el GPO

Pegue el siguiente texto en un reg (\*. reg) archivo.
  
Windows Registry Editor Version 5.00
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"SuggestionsURL_JSON"="https://business.ing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA"
"ShowSearchSuggestions"=dword:00000001
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
Haga doble clic en el archivo creado y siga los pasos para importar el archivo. Debe dar como resultado una importación correcta en el cuadro de diálogo siguiente:
  
![Mensaje de importación correcta del Editor del registro](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>2. Abra la consola de administración de directiva de grupo (gpmc.msc) y cambie a editar una directiva existente o crear uno nuevo

1. Vaya a **Configuración del usuario Configuration\Policies\Preferences\Windows**.
    
2. El botón secundario en **Registry\New** y seleccione **Asistente para el registro**. Desde la ventana del explorador de registro, seleccione **Equipo Local** y haga clic en **siguiente**.
    
3. Vaya a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.
    
4. En esta clave, asegúrese de que seleccionar DefaultScope.
    
    ![Explorador del registro con DefaultScope seleccionado](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. Compruebe todas las subclaves que contiene el GUID para Microsoft Search en Bing y cada valor en la clave, excepto cualquier ruta de acceso a los perfiles de usuario. Desplácese hacia abajo para seleccionar otros elementos.
    
    ![Explorador del registro con valores adicionales seleccionados](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. Haga clic en Finalizar para completar esta configuración.
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>3. configurar las preferencias del usuario para ayudar a eliminar una advertencia que el usuario puede obtener cuando se aplica la búsqueda de DefaultScope

Esta advertencia es por diseño y avisa a los usuarios de un programa intenta modificar su configuración.
  
1. En el mismo GPO, haga clic con el botón secundario en **Registry\New** y seleccione **Asistente para el registro**.
    
2. Vaya a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User preferencias**.
    
3. Seleccione la clave de **Preferencia de usuario** .
    
4. Haga clic en **Finalizar**.
    
5. Haga clic en el objeto recién creado. En el panel del lado derecho, haga doble clic en el objeto de las preferencias del usuario, cambie la **acción** **eliminar y guardar**.
    
Aplicar el GPO resultante mediante la vinculación al dominio apropiado.
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1703-or-later"></a>10 de Windows, versión 1703 o posterior

Los usuarios podrán cambiar el proveedor de búsqueda después de establece esta directiva.
  
Para los archivos ADMX más recientes para las distintas versiones de Windows, vea [cómo crear y administrar el almacén Central de plantillas administrativas de directiva de grupo en Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).
  
Si la configuración que se describen en esta sección no se encuentra dentro de GPMC, descargue el ADMX adecuado y copiarlos en el almacén central. Para obtener más información, vea [Los archivos de descripción los GPO utilizando ADMX](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Almacén central en el controlador de es una carpeta con la convención de nomenclatura siguiente:
  
 **%SystemRoot%\Sysvol\\<domain\>\policies\PolicyDefinitions**
  
Cada dominio que controla el controlador debería obtener una carpeta independiente. El siguiente comando se puede usar para copiar el archivo ADMX desde el símbolo del sistema:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra la consola de administración de directiva de grupo (gpmc.msc) y cambie a editar una directiva existente o crear uno nuevo.
    
2. Vaya a ** &lt;configuración de usuario o equipo&gt;\Administrative Templates\Windows Windows\Microsoft perimetral**.
    
1. Haga doble clic en **establecer motor de búsqueda predeterminado**, establezca en **habilitado**y escriba`https://www.bing.com/sa/osd/bfb.xml`
    
3. Aplicar el GPO resultante mediante la vinculación al dominio apropiado.
    
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 o posterior

Los usuarios no podrán cambiar el proveedor de búsqueda después de establece esta directiva.
  
Cromo viene con su propio conjunto de configuración de directiva de grupo que se puede descargar en el formato de archivo de [Ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202)ADMX. Si Windows Vista de sistemas operativos/Server 2008 o posterior se usan para administrar los GPO para el dominio, el archivo ADMX proporcionado en este paquete se ocupa de la configuración de Chrome en Windows XP SP2 o posterior.
  
Copie el archivo de plantilla en un almacén central para los archivos ADMX en el controlador de dominio. Para obtener más información, vea [Los archivos de descripción los GPO utilizando ADMX](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Almacén central en el controlador de es una carpeta con la convención de nomenclatura siguiente:
  
 **%SystemRoot%\Sysvol\\<domain\>\policies\PolicyDefinitions**
  
Cada dominio que controla el controlador debería obtener una carpeta independiente. El siguiente comando se puede usar para copiar el archivo ADMX desde el símbolo del sistema:
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra la consola de administración de directiva de grupo (gpmc.msc) y cambie a editar cualquier directiva existente o crear uno nuevo.
    
2. Asegúrese de que las carpetas siguientes aparecen en la sección Plantillas administrativas de configuración del usuario/equipo: Google Chrome y Google Chrome - la configuración predeterminada.
    
  - La configuración de la primera sección se corrigen y los administradores locales no puedan cambiarlas en el explorador.
    
  - La configuración de la sección de directivas de este última se puede cambiar por los usuarios de la configuración del explorador.
    
3. Vaya a ** \<usuario o equipo\> proveedor de búsqueda de configuración de usuario\Plantillas Templates\Google Chrome\Default**
    
4. Haga doble clic en **Habilitar al proveedor de búsqueda predeterminado**y establecerla en **habilitado**.
    
5. Haga doble clic en el **valor predeterminado de icono de proveedor de búsqueda**, establecida en **habilitado**y escriba`https://www.bing.com/sa/simg/bb.ico`
    
6. Haga doble clic en **dirección URL de instantánea de proveedor de búsqueda predeterminada**y escriba`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
7. Haga doble clic en el **nombre de proveedor de búsqueda predeterminado**, establezca en habilitado y escriba 'Microsoft Search en Bing'
    
8. Haga doble clic en **dirección URL de búsqueda de proveedor de búsqueda predeterminada**, establecida en **habilitado**y escriba`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
9. Haga doble clic en el **proveedor de búsqueda predeterminado sugerir la dirección URL**, establecida en **habilitado**y escriba`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`
    
10. Aplicar el GPO resultante mediante la vinculación al dominio apropiado.
    
El motor de búsqueda predeterminado va a agregar la característica de sugerencias de búsqueda de Microsoft Search en la barra de direcciones del explorador. Esto admite actualmente, sólo los marcadores. Los usuarios verán las sugerencias de dos marcador superior por encima de las sugerencias de web públicos mientras escribe en la barra de direcciones.