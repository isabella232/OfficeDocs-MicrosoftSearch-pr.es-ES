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
description: Obtenga información sobre cómo establecer a Bing como la página principal predeterminada para su empresa con Microsoft Search.
ms.openlocfilehash: db0611ebd7f4a8344664825bbb42025f3bb36486
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612493"
---
# <a name="set-default-homepage"></a><span data-ttu-id="9be39-103">Establecer página de inicio predeterminada</span><span class="sxs-lookup"><span data-stu-id="9be39-103">Set default homepage</span></span>

<span data-ttu-id="9be39-104">Configurar el explorador predeterminado, el motor de búsqueda predeterminado y la página principal predeterminada le ayudará a los usuarios a descubrir las capacidades de Microsoft Search, fomentar el uso más y proporcionar una experiencia más suave.</span><span class="sxs-lookup"><span data-stu-id="9be39-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="9be39-105">Para establecer la página principal predeterminada para su organización, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="9be39-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="9be39-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="9be39-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="9be39-107">Internet Explorer 5.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="9be39-107">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="9be39-108">Abra la consola de administración de directiva de grupo (gpmc.msc) y cambie a editar cualquier directiva existente o crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="9be39-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="9be39-109">Vaya a **configuración de Windows\Mantenimiento de Internet del Panel de Configuration\Preferences\Control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="9be39-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="9be39-110">Haga clic en **Configuración de Internet** y seleccione **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="9be39-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9be39-111">Es necesario seleccionar la opción de Internet Explorer 10 para aplicar la configuración de Internet Explorer 11 como la misma configuración se aplica a Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="9be39-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="9be39-p101">Configuración que está subrayados en rojo no está configurados en el equipo de destino, mientras que la configuración de subrayado en verde se configura en el equipo de destino. Para cambiar el formato de subrayado, use las teclas de función siguientes:</span><span class="sxs-lookup"><span data-stu-id="9be39-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="9be39-114">F5 - habilitar todas las opciones en la ficha actual</span><span class="sxs-lookup"><span data-stu-id="9be39-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="9be39-115">F6 - habilitar el valor seleccionado actualmente</span><span class="sxs-lookup"><span data-stu-id="9be39-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="9be39-116">F7 - deshabilitar el valor seleccionado actualmente</span><span class="sxs-lookup"><span data-stu-id="9be39-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="9be39-117">F8 - deshabilitar todas las opciones en la ficha actual</span><span class="sxs-lookup"><span data-stu-id="9be39-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="9be39-p102">Presione la tecla **F8** para deshabilitar a todas las opciones antes de configurar nada. La pantalla debe tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="9be39-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Cuadro de diálogo Propiedades de Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="9be39-121">En la configuración de la página principal, presione **F6** y escriba`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="9be39-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="9be39-122">Aplicar el GPO resultante mediante la vinculación al dominio apropiado.</span><span class="sxs-lookup"><span data-stu-id="9be39-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9be39-123">Los usuarios todavía pueden cambiar la página principal de una vez establecida esta directiva.</span><span class="sxs-lookup"><span data-stu-id="9be39-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="9be39-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9be39-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="9be39-125">10 de Windows, versión 1511 o posterior</span><span class="sxs-lookup"><span data-stu-id="9be39-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="9be39-126">Abra la consola de administración de directiva de grupo (gpmc.msc) y cambie a editar cualquier directiva existente o crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="9be39-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="9be39-127">Navegue al **borde de Windows\Microsoft administrativas\Componentes administrativas**</span><span class="sxs-lookup"><span data-stu-id="9be39-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="9be39-128">Haga doble clic en **las páginas de configuración de inicio**, establecida en **habilitado**y escriba`https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="9be39-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="9be39-129">Aplicar el GPO resultante mediante la vinculación al dominio apropiado.</span><span class="sxs-lookup"><span data-stu-id="9be39-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="9be39-130">Los usuarios no podrán cambiar el proveedor de búsqueda después de establece esta directiva.</span><span class="sxs-lookup"><span data-stu-id="9be39-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="9be39-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="9be39-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="9be39-132">Windows XP SP2 o posterior</span><span class="sxs-lookup"><span data-stu-id="9be39-132">Windows XP SP2 or later</span></span>

<span data-ttu-id="9be39-133">El artículo de soporte técnico de Windows en administración de archivos ADMX y los archivos ADMX más recientes para las diferentes versiones de Windows puede encontrarse [en soporte técnico de Microsoft](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="9be39-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="9be39-134">También necesitará el archivo de directiva de Google más reciente, que puede encontrar en la [Ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="9be39-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="9be39-p103">Si la configuración que se describen en esta sección no se encuentra dentro de GPMC, descargar el ADMX adecuado y copiarlos en el [almacén central](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Almacén central en el controlador de es una carpeta con la convención de nomenclatura siguiente:</span><span class="sxs-lookup"><span data-stu-id="9be39-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="9be39-137">**%SystemRoot%\Sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="9be39-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="9be39-p104">Cada dominio de los identificadores de controlador deberían obtener una carpeta independiente. El siguiente comando se puede usar para copiar el archivo ADMX desde el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="9be39-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="9be39-140">Abra la consola de administración de directiva de grupo (gpmc.msc) y cambie a editar cualquier directiva existente o crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="9be39-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="9be39-141">Asegúrese de que las carpetas siguientes aparecen en la sección **Plantillas administrativas** de ambos *Configuración del usuario o equipo*: Google Chrome y Google Chrome - Default Settings (los usuarios pueden invalidar).</span><span class="sxs-lookup"><span data-stu-id="9be39-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="9be39-142">La configuración de la primera sección se fija y el administrador local no podrá cambiarla.</span><span class="sxs-lookup"><span data-stu-id="9be39-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="9be39-p105">La configuración de la sección de directivas de este última se puede cambiar por los usuarios de su configuración del explorador. Debe decidir si los usuarios pueden invalidar la configuración predeterminada. En los siguientes pasos, cambiar en la opción en la carpeta que corresponde a sus necesidades y la directiva de la organización. Los pasos siguientes usan Google Chrome - configuración predeterminada como el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9be39-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="9be39-147">Vaya a \*\* &lt;configuración de usuario o equipo&gt;\Administrative Templates\Google cromo - página de Settings\Home predeterminada\*\*.</span><span class="sxs-lookup"><span data-stu-id="9be39-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="9be39-148">Haga doble clic en **Usar la nueva ficha página como página principal**y establecerla en **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="9be39-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="9be39-149">Vaya a \*\* &lt;configuración de usuario o equipo&gt;\Administrative Templates\Google cromo - página de ficha predeterminada Settings\New\*\*.</span><span class="sxs-lookup"><span data-stu-id="9be39-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="9be39-150">Haga doble clic en **Configurar la nueva dirección URL de página de ficha**, establecida en **habilitado**y escriba`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="9be39-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="9be39-151">Aplicar el GPO resultante mediante la vinculación al dominio apropiado.</span><span class="sxs-lookup"><span data-stu-id="9be39-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="9be39-152">Los usuarios podrán cambiar la página principal, una vez establecida esta directiva.</span><span class="sxs-lookup"><span data-stu-id="9be39-152">Users will be able to change the home page after this policy is set.</span></span>