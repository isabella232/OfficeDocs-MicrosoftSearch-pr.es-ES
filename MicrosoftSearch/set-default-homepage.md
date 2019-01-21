---
title: Página principal predeterminada de conjunto
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: Obtenga información sobre cómo establecer a Bing como la página principal predeterminada para su empresa con Microsoft Search.
ms.openlocfilehash: 9190e607f5e17a0b898ab131886de12cb300a74c
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379243"
---
# <a name="set-default-homepage"></a>Página principal predeterminada de conjunto

Configurar el explorador predeterminado, el motor de búsqueda predeterminado y la página principal predeterminada le ayudará a los usuarios a descubrir las capacidades de Microsoft Search, fomentar el uso más y proporcionar una experiencia más suave.
  
Para establecer la página principal predeterminada para su organización, siga los pasos siguientes.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-50-or-later"></a>Internet Explorer 5.0 o posterior

1. Abra la consola de administración de directiva de grupo (gpmc.msc) y cambie a editar cualquier directiva existente o crear uno nuevo.
    
2. Vaya a **configuración de Windows\Mantenimiento de Internet del Panel de Configuration\Preferences\Control de usuario**.
    
3. Haga clic en **Configuración de Internet** y seleccione **Internet Explorer 10**.
    
    > [!NOTE]
    > Es necesario seleccionar la opción de Internet Explorer 10 para aplicar la configuración de Internet Explorer 11 como la misma configuración se aplica a Internet Explorer 11. 
  
4. Configuración que está subrayados en rojo no está configurados en el equipo de destino, mientras que la configuración de subrayado en verde se configura en el equipo de destino. Para cambiar el formato de subrayado, use las teclas de función siguientes:
    
    F5 - habilitar todas las opciones en la ficha actual
    
    F6 - habilitar el valor seleccionado actualmente
    
    F7 - deshabilitar el valor seleccionado actualmente
    
    F8 - deshabilitar todas las opciones en la ficha actual
    
5. Presione la tecla **F8** para deshabilitar a todas las opciones antes de configurar nada. La pantalla debe tener este aspecto: 
    
    ![Cuadro de diálogo Propiedades de Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. En la configuración de la página principal, presione **F6** y escriba`https://www.bing.com/business?form=BFBSPR`
    
7. Aplicar el GPO resultante mediante la vinculación al dominio apropiado.
    
> [!NOTE]
> Los usuarios todavía pueden cambiar la página principal de una vez establecida esta directiva. 
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1511-or-later"></a>10 de Windows, versión 1511 o posterior

1. Abra la consola de administración de directiva de grupo (gpmc.msc) y cambie a editar cualquier directiva existente o crear uno nuevo.
    
2. Navegue al **borde de Windows\Microsoft administrativas\Componentes administrativas**
    
1. Haga doble clic en **las páginas de configuración de inicio**, establecida en **habilitado**y escriba`https://www.bing.com/business`
    
3. Aplicar el GPO resultante mediante la vinculación al dominio apropiado.
    
> [!CAUTION]
> Los usuarios no podrán cambiar el proveedor de búsqueda después de establece esta directiva. 
  
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 o posterior

El artículo de soporte técnico de Windows en administración de archivos ADMX y los archivos ADMX más recientes para las diferentes versiones de Windows puede encontrarse [en soporte técnico de Microsoft](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).

También necesitará el archivo de directiva de Google más reciente, que puede encontrar en la [Ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).
  
Si la configuración que se describen en esta sección no se encuentra dentro de GPMC, descargar el ADMX adecuado y copiarlos en el [almacén central](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Almacén central en el controlador de es una carpeta con la convención de nomenclatura siguiente:
  
 **%SystemRoot%\Sysvol\\<domain\>\policies\PolicyDefinitions**
  
Cada dominio de los identificadores de controlador deberían obtener una carpeta independiente. El siguiente comando se puede usar para copiar el archivo ADMX desde el símbolo del sistema:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra la consola de administración de directiva de grupo (gpmc.msc) y cambie a editar cualquier directiva existente o crear uno nuevo.
    
2. Asegúrese de que las carpetas siguientes aparecen en la sección **Plantillas administrativas** de ambos *Configuración del usuario o equipo*: Google Chrome y Google Chrome - Default Settings (los usuarios pueden invalidar).
    
   - La configuración de la primera sección se fija y el administrador local no podrá cambiarla.
    
   - La configuración de la sección de directivas de este última se puede cambiar por los usuarios de su configuración del explorador. Debe decidir si los usuarios pueden invalidar la configuración predeterminada. En los siguientes pasos, cambiar en la opción en la carpeta que corresponde a sus necesidades y la directiva de la organización. Los pasos siguientes usan Google Chrome - configuración predeterminada como el valor predeterminado.
    
3. Vaya a ** &lt;configuración de usuario o equipo&gt;\Administrative Templates\Google cromo - página de Settings\Home predeterminada**.
    
4. Haga doble clic en **Usar la nueva ficha página como página principal**y establecerla en **habilitado**.
    
5. Vaya a ** &lt;configuración de usuario o equipo&gt;\Administrative Templates\Google cromo - página de ficha predeterminada Settings\New**.
    
6. Haga doble clic en **Configurar la nueva dirección URL de página de ficha**, establecida en **habilitado**y escriba`https://www.bing.com/business?form=BFBSPR`
    
7. Aplicar el GPO resultante mediante la vinculación al dominio apropiado.
    
Los usuarios podrán cambiar la página principal, una vez establecida esta directiva.