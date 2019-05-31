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
ROBOTS: NOINDEX
description: Obtenga información sobre cómo configurar Bing como motor de búsqueda predeterminado de su empresa con Microsoft Search.
ms.openlocfilehash: 77a8ea884f4df26fc8f7661fb9a9b8791b2f0f18
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591120"
---
# <a name="set-default-search-engine"></a>Establecer motor de búsqueda predeterminado

> [!IMPORTANT]
> Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se eliminará. Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar. [Introducción a Microsoft Search (Búsqueda de Microsoft)](overview-microsoft-search.md).
    
La configuración de la página principal, motor de búsqueda y explorador predeterminados ayudará a los usuarios a descubrir las funciones de Microsoft Search, fomentar su uso y proporcionar una experiencia más fluida.
  
Para establecer el motor de búsqueda predeterminado para su organización, siga los pasos siguientes.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-11"></a>Internet Explorer 11

Los usuarios podrán cambiar el proveedor de búsqueda después de establecer esta directiva.
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>1. Configurar el equipo local que se usará para establecer el GPO

Pegue el texto siguiente en un archivo de registro (\*.reg).
  
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
  
Haga doble clic en el archivo creado y siga los pasos para importar el archivo. Una importación correcta debe dar como resultado el cuadro de diálogo siguiente:
  
![Mensaje de importación correcta del Editor del registro](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>2. Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva

1. Vaya a **Configuración de usuario\Configuración\Directivas\Preferencias\Configuración de Windows**.
    
2. Haga clic derecho en **Registro\Nuevo** y seleccione **Asistente de registro**. En la ventana del Explorador de registro, seleccione **Equipo local** y haga clic en **Siguiente**.
    
3. Vaya a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.
    
4. En esta clave, asegúrese de seleccionar DefaultScope.
    
    ![Explorador de registro con DefaultScope seleccionado](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. Compruebe todas las subclaves que contienen el GUID de Microsoft Search en Bing y todos los valores de la clave excepto las rutas de acceso a los perfiles de usuario. Desplácese hacia abajo para seleccionar otros elementos.
    
    ![Explorador de registro con valores adicionales seleccionados](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. Haga clic en Finalizar para terminar la configuración.
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>3. Configurar las Preferencias de usuario para ayudar a eliminar una advertencia que puede aparecer para el usuario cuando se aplica la búsqueda DefaultScope

Esta advertencia es intencionada y alerta a los usuarios de un programa que intentan modificar la configuración.
  
1. En el mismo GPO, haga clic derecho en **Registro\Nuevo** y seleccione **Asistente de registro**.
    
2. Vaya a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.
    
3. Seleccione la clave **User Preference**.
    
4. Haga clic en **Finalizar**.
    
5. Haga clic en el objeto recién creado. En el panel de la derecha, haga doble clic en el objeto User Preferences y cambie la **Acción** a **Eliminar y guardar**.
    
Aplique el GPO resultante vinculándolo al dominio correspondiente.
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1703-or-later"></a>Windows 10, versión 1703 o posteriores.

Los usuarios podrán cambiar el proveedor de búsqueda después de establecer esta directiva.
  
Para los archivos ADMX más recientes para diferentes versiones de Windows, vea [Cómo crear y administrar el almacén central de plantillas administrativas de directiva de grupo en Windows](https://support.microsoft.com/es-ES/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).
  
Si la configuración descrita en esta sección no se encuentra dentro de la GPMC, descargue los ADMX adecuados y cópielos en el almacén central. Para obtener más información, vea [Editar GPO basados en dominios mediante archivos ADMX](https://docs.microsoft.com/es-ES/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). El almacén central en el controlador es una carpeta con la convención de nomenclatura siguiente:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Todos los dominios que maneja el controlador deben obtener una carpeta diferente. El comando siguiente puede usarse para copiar el archivo ADMX desde el símbolo del sistema:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.
    
2. Vaya a **&lt;Equipo/Configuración de usuario&gt;\Plantillas administrativas\Componentes de Windows\Microsoft Edge**.
    
1. Haga doble clic en **Establecer motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://www.bing.com/sa/osd/bfb.xml`
    
3. Aplique el GPO resultante vinculándolo al dominio correspondiente.
    
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 o versiones posteriores

Los usuarios no podrán cambiar el proveedor de búsqueda después de establecer esta directiva.
  
Chrome incluye su propio conjunto de configuración de directiva de grupo, que puede descargarse en forma de archivo ADMX desde Chrome [Ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202). Si se usan los sistemas operativos Windows Vista/Server 2008 o versiones posteriores para administrar los GPO del dominio, el archivo ADMX proporcionado en este paquete se encarga de la configuración de Chrome en Windows XP SP2 o versiones posteriores.
  
Copie el archivo de plantilla en un almacén central para archivos ADMX en el controlador del dominio. Para obtener más información, vea [Editar GPO basados en dominios mediante archivos ADMX](https://docs.microsoft.com/es-ES/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). El almacén central en el controlador es una carpeta con la convención de nomenclatura siguiente:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Todos los dominios que maneja el controlador deben obtener una carpeta diferente. El comando siguiente puede usarse para copiar el archivo ADMX desde el símbolo del sistema:
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.
    
2. Asegúrese de que las carpetas siguientes aparecen en la sección de Plantillas administrativas en Usuario/Configuración de equipo: Google Chrome y Google Chrome: configuración predeterminada.
    
  - La configuración de la primera sección es fija y los administradores locales no pueden cambiarla en el explorador.
    
  - Los usuarios pueden cambiar la configuración de la segunda sección de directivas en la configuración del explorador.
    
3. Vaya a **\<Equipo/Configuración de usuario\>\Plantillas administrativas\Google Chrome\Motor de búsqueda predeterminado**.
    
4. Haga doble clic en **Habilitar el motor de búsqueda predeterminado** y establézcalo como **Habilitado**.
    
5. Haga doble clic en el **icono de Motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://www.bing.com/sa/simg/bb.ico`.
    
6. Haga doble clic en el **URL instantánea del motor de búsqueda predeterminado** y escriba `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`.
    
7. Haga doble clic en el **nombre del motor de búsqueda predeterminado**, establézcalo como Habilitado y escriba "Microsoft Search en Bing".
    
8. Haga doble clic en el **URL de búsqueda del motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`.
    
9. Haga doble clic en el **URL de sugerencia del motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`.
    
10. Aplique el GPO resultante vinculándolo al dominio correspondiente.
    
Al establecer el motor de búsqueda predeterminado se agregará la característica de sugerencias de búsqueda de Microsoft Search en la barra de direcciones del explorador. Actualmente solo admite marcadores. Los usuarios verán las sugerencias de los dos marcadores principales por encima de las sugerencias web públicas mientras escribe en la barra de direcciones.