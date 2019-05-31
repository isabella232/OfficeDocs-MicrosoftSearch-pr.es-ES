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
# <a name="set-default-search-engine"></a><span data-ttu-id="90dbc-103">Establecer motor de búsqueda predeterminado</span><span class="sxs-lookup"><span data-stu-id="90dbc-103">Set default search engine</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90dbc-104">Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing</span><span class="sxs-lookup"><span data-stu-id="90dbc-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="90dbc-105">Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se eliminará.</span><span class="sxs-lookup"><span data-stu-id="90dbc-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="90dbc-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="90dbc-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="90dbc-107">[Introducción a Microsoft Search (Búsqueda de Microsoft)](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="90dbc-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="90dbc-108">La configuración de la página principal, motor de búsqueda y explorador predeterminados ayudará a los usuarios a descubrir las funciones de Microsoft Search, fomentar su uso y proporcionar una experiencia más fluida.</span><span class="sxs-lookup"><span data-stu-id="90dbc-108">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="90dbc-109">Para establecer el motor de búsqueda predeterminado para su organización, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="90dbc-109">To set the default search engine for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="90dbc-110">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="90dbc-110">Internet Explorer</span></span>

### <a name="internet-explorer-11"></a><span data-ttu-id="90dbc-111">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="90dbc-111">Internet Explorer 11</span></span>

<span data-ttu-id="90dbc-112">Los usuarios podrán cambiar el proveedor de búsqueda después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="90dbc-112">Users will be able to change the search provider after this policy is set.</span></span>
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="90dbc-113">1. Configurar el equipo local que se usará para establecer el GPO</span><span class="sxs-lookup"><span data-stu-id="90dbc-113">1. Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="90dbc-114">Pegue el texto siguiente en un archivo de registro (\*.reg).</span><span class="sxs-lookup"><span data-stu-id="90dbc-114">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="90dbc-115">Windows Registry Editor Version 5.00</span><span class="sxs-lookup"><span data-stu-id="90dbc-115">Windows Registry Editor Version 5.00</span></span>
  
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
  
<span data-ttu-id="90dbc-p102">Haga doble clic en el archivo creado y siga los pasos para importar el archivo. Una importación correcta debe dar como resultado el cuadro de diálogo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90dbc-p102">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![Mensaje de importación correcta del Editor del registro](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="90dbc-119">2. Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva</span><span class="sxs-lookup"><span data-stu-id="90dbc-119">2. Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="90dbc-120">Vaya a **Configuración de usuario\Configuración\Directivas\Preferencias\Configuración de Windows**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-120">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="90dbc-p103">Haga clic derecho en **Registro\Nuevo** y seleccione **Asistente de registro**. En la ventana del Explorador de registro, seleccione **Equipo local** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-p103">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
3. <span data-ttu-id="90dbc-123">Vaya a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-123">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
    
4. <span data-ttu-id="90dbc-124">En esta clave, asegúrese de seleccionar DefaultScope.</span><span class="sxs-lookup"><span data-stu-id="90dbc-124">From this key, make sure to select DefaultScope.</span></span>
    
    ![Explorador de registro con DefaultScope seleccionado](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. <span data-ttu-id="90dbc-p104">Compruebe todas las subclaves que contienen el GUID de Microsoft Search en Bing y todos los valores de la clave excepto las rutas de acceso a los perfiles de usuario. Desplácese hacia abajo para seleccionar otros elementos.</span><span class="sxs-lookup"><span data-stu-id="90dbc-p104">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
    
    ![Explorador de registro con valores adicionales seleccionados](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. <span data-ttu-id="90dbc-129">Haga clic en Finalizar para terminar la configuración.</span><span class="sxs-lookup"><span data-stu-id="90dbc-129">Click Finish to complete this configuration.</span></span>
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="90dbc-130">3. Configurar las Preferencias de usuario para ayudar a eliminar una advertencia que puede aparecer para el usuario cuando se aplica la búsqueda DefaultScope</span><span class="sxs-lookup"><span data-stu-id="90dbc-130">3. Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="90dbc-131">Esta advertencia es intencionada y alerta a los usuarios de un programa que intentan modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="90dbc-131">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="90dbc-132">En el mismo GPO, haga clic derecho en **Registro\Nuevo** y seleccione **Asistente de registro**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-132">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
    
2. <span data-ttu-id="90dbc-133">Vaya a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-133">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
    
3. <span data-ttu-id="90dbc-134">Seleccione la clave **User Preference**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-134">Select the **User Preference** key.</span></span>
    
4. <span data-ttu-id="90dbc-135">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-135">Click **Finish**.</span></span>
    
5. <span data-ttu-id="90dbc-p105">Haga clic en el objeto recién creado. En el panel de la derecha, haga doble clic en el objeto User Preferences y cambie la **Acción** a **Eliminar y guardar**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-p105">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
    
<span data-ttu-id="90dbc-138">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="90dbc-138">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
  
## <a name="microsoft-edge"></a><span data-ttu-id="90dbc-139">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="90dbc-139">Microsoft Edge</span></span>

### <a name="windows-10-version-1703-or-later"></a><span data-ttu-id="90dbc-140">Windows 10, versión 1703 o posteriores.</span><span class="sxs-lookup"><span data-stu-id="90dbc-140">Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="90dbc-141">Los usuarios podrán cambiar el proveedor de búsqueda después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="90dbc-141">Users will be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="90dbc-142">Para los archivos ADMX más recientes para diferentes versiones de Windows, vea [Cómo crear y administrar el almacén central de plantillas administrativas de directiva de grupo en Windows](https://support.microsoft.com/es-ES/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="90dbc-142">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="90dbc-p106">Si la configuración descrita en esta sección no se encuentra dentro de la GPMC, descargue los ADMX adecuados y cópielos en el almacén central. Para obtener más información, vea [Editar GPO basados en dominios mediante archivos ADMX](https://docs.microsoft.com/es-ES/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). El almacén central en el controlador es una carpeta con la convención de nomenclatura siguiente:</span><span class="sxs-lookup"><span data-stu-id="90dbc-p106">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="90dbc-146">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="90dbc-146">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="90dbc-p107">Todos los dominios que maneja el controlador deben obtener una carpeta diferente. El comando siguiente puede usarse para copiar el archivo ADMX desde el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="90dbc-p107">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="90dbc-149">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="90dbc-149">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="90dbc-150">Vaya a **&lt;Equipo/Configuración de usuario&gt;\Plantillas administrativas\Componentes de Windows\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-150">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
    
1. <span data-ttu-id="90dbc-151">Haga doble clic en **Establecer motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="90dbc-151">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
    
3. <span data-ttu-id="90dbc-152">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="90dbc-152">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
## <a name="google-chrome"></a><span data-ttu-id="90dbc-153">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="90dbc-153">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="90dbc-154">Windows XP SP2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="90dbc-154">Windows XP SP2 or later</span></span>

<span data-ttu-id="90dbc-155">Los usuarios no podrán cambiar el proveedor de búsqueda después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="90dbc-155">Users won't be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="90dbc-p108">Chrome incluye su propio conjunto de configuración de directiva de grupo, que puede descargarse en forma de archivo ADMX desde Chrome [Ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202). Si se usan los sistemas operativos Windows Vista/Server 2008 o versiones posteriores para administrar los GPO del dominio, el archivo ADMX proporcionado en este paquete se encarga de la configuración de Chrome en Windows XP SP2 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="90dbc-p108">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). If operating systems Windows Vista/Server 2008 or later are used to manage GPO's for the domain, the ADMX file provided in this package takes care of Chrome settings on Windows XP SP2 or later.</span></span>
  
<span data-ttu-id="90dbc-p109">Copie el archivo de plantilla en un almacén central para archivos ADMX en el controlador del dominio. Para obtener más información, vea [Editar GPO basados en dominios mediante archivos ADMX](https://docs.microsoft.com/es-ES/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). El almacén central en el controlador es una carpeta con la convención de nomenclatura siguiente:</span><span class="sxs-lookup"><span data-stu-id="90dbc-p109">Copy the template file to a central store for ADMX files on the domain controller. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="90dbc-161">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="90dbc-161">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="90dbc-p110">Todos los dominios que maneja el controlador deben obtener una carpeta diferente. El comando siguiente puede usarse para copiar el archivo ADMX desde el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="90dbc-p110">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="90dbc-164">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="90dbc-164">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="90dbc-165">Asegúrese de que las carpetas siguientes aparecen en la sección de Plantillas administrativas en Usuario/Configuración de equipo: Google Chrome y Google Chrome: configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="90dbc-165">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>
    
  - <span data-ttu-id="90dbc-166">La configuración de la primera sección es fija y los administradores locales no pueden cambiarla en el explorador.</span><span class="sxs-lookup"><span data-stu-id="90dbc-166">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    
  - <span data-ttu-id="90dbc-167">Los usuarios pueden cambiar la configuración de la segunda sección de directivas en la configuración del explorador.</span><span class="sxs-lookup"><span data-stu-id="90dbc-167">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>
    
3. <span data-ttu-id="90dbc-168">Vaya a **\<Equipo/Configuración de usuario\>\Plantillas administrativas\Google Chrome\Motor de búsqueda predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-168">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
    
4. <span data-ttu-id="90dbc-169">Haga doble clic en **Habilitar el motor de búsqueda predeterminado** y establézcalo como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="90dbc-169">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="90dbc-170">Haga doble clic en el **icono de Motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://www.bing.com/sa/simg/bb.ico`.</span><span class="sxs-lookup"><span data-stu-id="90dbc-170">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
    
6. <span data-ttu-id="90dbc-171">Haga doble clic en el **URL instantánea del motor de búsqueda predeterminado** y escriba `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`.</span><span class="sxs-lookup"><span data-stu-id="90dbc-171">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
7. <span data-ttu-id="90dbc-172">Haga doble clic en el **nombre del motor de búsqueda predeterminado**, establézcalo como Habilitado y escriba "Microsoft Search en Bing".</span><span class="sxs-lookup"><span data-stu-id="90dbc-172">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
    
8. <span data-ttu-id="90dbc-173">Haga doble clic en el **URL de búsqueda del motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`.</span><span class="sxs-lookup"><span data-stu-id="90dbc-173">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
9. <span data-ttu-id="90dbc-174">Haga doble clic en el **URL de sugerencia del motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`.</span><span class="sxs-lookup"><span data-stu-id="90dbc-174">Double-click **Default search provider suggest URL**, set it to **Enabled**, and enter `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span></span>
    
10. <span data-ttu-id="90dbc-175">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="90dbc-175">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="90dbc-p111">Al establecer el motor de búsqueda predeterminado se agregará la característica de sugerencias de búsqueda de Microsoft Search en la barra de direcciones del explorador. Actualmente solo admite marcadores. Los usuarios verán las sugerencias de los dos marcadores principales por encima de las sugerencias web públicas mientras escribe en la barra de direcciones.</span><span class="sxs-lookup"><span data-stu-id="90dbc-p111">Setting the default search engine will add the Microsoft Search search suggestions feature in the browser address bar. Currently, this supports bookmarks only. Users will see the top two bookmark suggestions above public web suggestions as they type in the address bar.</span></span>