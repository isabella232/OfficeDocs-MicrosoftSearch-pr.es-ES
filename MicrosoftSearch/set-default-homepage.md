---
title: Establecer página de inicio predeterminada
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
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
ROBOTS: NOINDEX
description: Obtenga información sobre cómo establecer Bing como página principal predeterminada para su empresa con Microsoft Search.
ms.openlocfilehash: 457202ba8dbebf59c5ef6a4630aea98304b9acdb
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "34728000"
---
# <a name="set-default-homepage"></a><span data-ttu-id="2f96f-103">Establecer página de inicio predeterminada</span><span class="sxs-lookup"><span data-stu-id="2f96f-103">Set default homepage</span></span>

<span data-ttu-id="2f96f-104">La configuración de la página principal, motor de búsqueda y explorador predeterminados ayudará a los usuarios a descubrir las funciones de Microsoft Search, fomentar su uso y proporcionar una experiencia más fluida.</span><span class="sxs-lookup"><span data-stu-id="2f96f-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="2f96f-105">Para establecer la página principal predeterminada para su organización, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2f96f-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="2f96f-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="2f96f-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="2f96f-107">Internet Explorer 5.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="2f96f-107">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="2f96f-108">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="2f96f-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="2f96f-109">Vaya a **Configuración de usuario\Preferencias\Configuración del panel de control\Configuración de Internet**.</span><span class="sxs-lookup"><span data-stu-id="2f96f-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="2f96f-110">Haga clic derecho en **Configuración de Internet** y seleccione **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="2f96f-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2f96f-111">Debe seleccionar la opción de Internet Explorer 10 para aplicar la configuración de Internet Explorer 11 ya que en ambos se aplica la misma configuración.</span><span class="sxs-lookup"><span data-stu-id="2f96f-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="2f96f-p101">Las opciones de configuración que se subrayan en rojo no se configuran en el equipo de destino, mientras que las subrayadas en verde sí lo hacen. Para cambiar el subrayado, use las teclas de función siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f96f-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="2f96f-114">F5: habilitar todas las opciones en la pestaña actual</span><span class="sxs-lookup"><span data-stu-id="2f96f-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="2f96f-115">F6: habilitar la opción seleccionada</span><span class="sxs-lookup"><span data-stu-id="2f96f-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="2f96f-116">F7: deshabilitar la opción seleccionada</span><span class="sxs-lookup"><span data-stu-id="2f96f-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="2f96f-117">F8: deshabilitar todas las opciones en la pestaña actual</span><span class="sxs-lookup"><span data-stu-id="2f96f-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="2f96f-p102">Presione **F8** deshabilitar todas las opciones antes de configurar nada. La pantalla debe tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="2f96f-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Cuadro de diálogo Propiedades de Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="2f96f-121">Presione **F6** en la configuración de página principal y escriba `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="2f96f-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="2f96f-122">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2f96f-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2f96f-123">Los usuarios podrán cambiar la página principal después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="2f96f-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="2f96f-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2f96f-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="2f96f-125">Windows 10, versión 1511 o posteriores.</span><span class="sxs-lookup"><span data-stu-id="2f96f-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="2f96f-126">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="2f96f-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="2f96f-127">Vaya a **Plantillas administrativas\Componentes de Windows\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="2f96f-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="2f96f-128">Haga doble clic en **Configurar páginas de inicio**, establézcalo como **Habilitado** y escriba `https://www.bing.com/business`.</span><span class="sxs-lookup"><span data-stu-id="2f96f-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="2f96f-129">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2f96f-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="2f96f-130">Los usuarios no podrán cambiar el proveedor de búsqueda después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="2f96f-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="2f96f-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="2f96f-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="2f96f-132">Windows XP SP2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="2f96f-132">Windows XP SP2 or later</span></span>

<span data-ttu-id="2f96f-133">El artículo de soporte técnico de Windows sobre la administración de archivos ADMX y los archivos ADMX más recientes para diferentes versiones de Windows pueden encontrarse [en el Soporte técnico de Microsoft](https://support.microsoft.com/es-ES/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="2f96f-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="2f96f-134">También necesitará el archivo de directiva de Google más reciente, que puede encontrar en [ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="2f96f-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="2f96f-p103">Si la configuración descrita en esta sección no se encuentra dentro de la GPMC, descargue los ADMX adecuados y cópielos en el [almacén central](https://docs.microsoft.com/es-ES/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). El almacén central en el controlador es una carpeta con la convención de nomenclatura siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f96f-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="2f96f-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="2f96f-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="2f96f-p104">Todos los dominios que maneja el controlador deben obtener una carpeta diferente. El comando siguiente puede usarse para copiar el archivo ADMX desde el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="2f96f-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="2f96f-140">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="2f96f-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="2f96f-141">Asegúrese de que las carpetas siguientes aparecen en la sección de **Plantillas administrativas** en *Usuario/Configuración de equipo*: Google Chrome y Google Chrome: configuración predeterminada (los usuarios pueden invalidarlas).</span><span class="sxs-lookup"><span data-stu-id="2f96f-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="2f96f-142">La configuración de la primera sección es fija y el administrador local no puede cambiarla.</span><span class="sxs-lookup"><span data-stu-id="2f96f-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="2f96f-p105">Los usuarios pueden cambiar la configuración de la segunda sección de directivas en la configuración del explorador. Debe decidir si los usuarios pueden invalidar la configuración predeterminada. En los pasos siguientes, cambie la configuración en la carpeta para que corresponda con las necesidades y directivas de su organización. Los pasos siguientes utilizan por defecto Google Chrome: configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2f96f-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="2f96f-147">Vaya a **&lt;Equipo/Configuración de usuario&gt;\Plantillas administrativas\Google Chrome: configuración predeterminada\Página de inicio predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="2f96f-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="2f96f-148">Haga doble clic en **Usar la página de nueva pestaña como página de inicio** y establézcalo como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="2f96f-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="2f96f-149">Vaya a **&lt;Equipo/Configuración de usuario&gt;\Plantillas administrativas\Google Chrome: configuración predeterminada\Página de nueva pestaña**.</span><span class="sxs-lookup"><span data-stu-id="2f96f-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="2f96f-150">Haga doble clic en **Configurar URL de página de nueva pestaña**, establézcalo como **Habilitado** y escriba `https://www.bing.com/business?form=BFBSPR`.</span><span class="sxs-lookup"><span data-stu-id="2f96f-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="2f96f-151">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2f96f-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="2f96f-152">Los usuarios podrán cambiar la página de inicio después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="2f96f-152">Users will be able to change the home page after this policy is set.</span></span>