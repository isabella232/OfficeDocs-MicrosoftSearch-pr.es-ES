---
title: Establecer página de inicio predeterminada
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: Obtenga información sobre cómo establecer Bing como página principal predeterminada para su empresa con Microsoft Search.
ms.openlocfilehash: 745e4a81e4b53ff88b612cd19295cb89dc041ddc
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973696"
---
# <a name="make-bingcom-the-default-home-page"></a>Convertir Bing.com en la Página principal predeterminada

Este artículo explica cómo establecer Bing como página principal predeterminada para los exploradores Microsoft Edge, Google Chrome e Internet Explorer. 
  
 
## <a name="microsoft-edge-on-windows-10-version-1511-or-later"></a>Microsoft Edge en Windows 10, versión 1511 o posterior

Los usuarios no podrán cambiarlo después de establecer esta directiva. 

1. Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva. 
1. Vaya a **Plantillas administrativas\Componentes de Windows\Microsoft Edge**.    
1. Haga doble clic en **Configurar páginas de inicio**, establézcalo como **Habilitado** y escriba `https://www.bing.com/business`.
1.  Aplique el GPO resultante vinculándolo al dominio correspondiente.

  
## <a name="google-chrome-on-windows-xp-sp2-or-later"></a>Google Chrome en Windows XP SP2 o posterior


El artículo de soporte técnico de Windows sobre la administración de archivos ADMX y los archivos ADMX más recientes para diferentes versiones de Windows pueden encontrarse [en el Soporte técnico de Microsoft](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).

También necesitará el archivo de directiva de Google más reciente, que puede encontrar en [ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).
  
Si la configuración descrita en esta sección no se encuentra dentro de la GPMC, descargue los ADMX adecuados y cópielos en el [almacén central](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). El almacén central en el controlador es una carpeta con la convención de nomenclatura siguiente:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Todos los dominios que maneja el controlador deben obtener una carpeta diferente. El comando siguiente puede usarse para copiar el archivo ADMX desde el símbolo del sistema:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.
1. Asegúrese de que las carpetas siguientes aparecen en la sección de **Plantillas administrativas** en *Usuario/Configuración de equipo*: Google Chrome y Google Chrome: configuración predeterminada (los usuarios pueden invalidarlas).
   - La configuración de la primera sección es fija y el administrador local no puede cambiarla.
   - Los usuarios pueden cambiar la configuración de la segunda sección de directivas en la configuración del explorador. Debe decidir si los usuarios pueden invalidar la configuración predeterminada. En los pasos siguientes, cambie la configuración en la carpeta para que corresponda con las necesidades y directivas de su organización. Los pasos siguientes utilizan por defecto Google Chrome: configuración predeterminada.

1. Vaya a **&lt;Equipo/Configuración de usuario&gt;\Plantillas administrativas\Google Chrome: configuración predeterminada\Página de inicio predeterminada**. 
1. Haga doble clic en **Usar la página de nueva pestaña como página de inicio** y establézcalo como **Habilitado**. 
1. Vaya a **&lt;Equipo/Configuración de usuario&gt;\Plantillas administrativas\Google Chrome: configuración predeterminada\Página de nueva pestaña**. 
1. Haga doble clic en **Configurar URL de página de nueva pestaña**, establézcalo como **Habilitado** y escriba `https://www.bing.com/business?form=BFBSPR`. 
1. Aplique el GPO resultante vinculándolo al dominio correspondiente.

## <a name="internet-explorer-50-or-later"></a>Internet Explorer 5.0 o posterior
Los usuarios podrán cambiar la página principal después de establecer esta directiva. 

1. Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.
    
2. Vaya a **Configuración de usuario\Preferencias\Configuración del panel de control\Configuración de Internet**.
    
3. Haga clic derecho en **Configuración de Internet** y seleccione **Internet Explorer 10**.
    
    > [!NOTE]
    > Debe seleccionar la opción de Internet Explorer 10 para aplicar la configuración de Internet Explorer 11 ya que en ambos se aplica la misma configuración. 
  
4. Las opciones de configuración que se subrayan en rojo no se configuran en el equipo de destino, mientras que las subrayadas en verde sí lo hacen. Para cambiar el subrayado, use las teclas de función siguientes:
    
    F5: habilitar todas las opciones en la pestaña actual
    
    F6: habilitar la opción seleccionada
    
    F7: deshabilitar la opción seleccionada
    
    F8: deshabilitar todas las opciones en la pestaña actual
    
5. Presione **F8** deshabilitar todas las opciones antes de configurar nada. La pantalla debe tener este aspecto: 
    
    ![Internet Explorer 10 Cuadro de diálogo Propiedades.](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. Presione **F6** en la configuración de página principal y escriba `https://www.bing.com/business?form=BFBSPR`
    
7. Aplique el GPO resultante vinculándolo al dominio correspondiente.