---
title: Establecer motor de búsqueda predeterminado
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Obtenga información sobre cómo configurar Bing como motor de búsqueda predeterminado de su empresa con Microsoft Search.
ms.openlocfilehash: 1ac2f23a8263c01901e252e7dd830e7373380669
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508674"
---
# <a name="make-bing-the-default-search-engine"></a><span data-ttu-id="e0662-103">Establezca Bing como el motor de búsqueda predeterminado</span><span class="sxs-lookup"><span data-stu-id="e0662-103">Make Bing the default search engine</span></span>
  
<span data-ttu-id="e0662-104">Este artículo explica cómo puede hacer de Bing el motor de búsqueda predeterminado para Microsoft Edge, Google Chrome e Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e0662-104">This article explains how you can make Bing the default search engine for Microsoft Edge, Google Chrome, and Internet Explorer.</span></span> 
  
## <a name="microsoft-edge-on-windows-10-version-1703-or-later"></a><span data-ttu-id="e0662-105">Microsoft Edge en Windows 10, versión 1703 o posterior</span><span class="sxs-lookup"><span data-stu-id="e0662-105">Microsoft Edge on Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="e0662-106">Aunque usted va a configurar Bing como motor de búsqueda predeterminado, Microsoft Edge permite a los usuarios cambiar su configuración para usar un motor de búsqueda diferente.</span><span class="sxs-lookup"><span data-stu-id="e0662-106">Although you'll set Bing as the default search engine, Microsoft Edge allows users to change their settings to use a different search engine.</span></span>
  
<span data-ttu-id="e0662-107">Para los archivos ADMX más recientes para diferentes versiones de Windows, vea [Cómo crear y administrar el almacén central de plantillas administrativas de directiva de grupo en Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="e0662-107">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="e0662-108">Si no se encuentra la configuración descrita en esta sección dentro de GPMC, descargue el ADMX adecuado y cópielos en el almacén central.</span><span class="sxs-lookup"><span data-stu-id="e0662-108">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store.</span></span> <span data-ttu-id="e0662-109">Para obtener más información, [vea Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span><span class="sxs-lookup"><span data-stu-id="e0662-109">For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span></span> <span data-ttu-id="e0662-110">El almacén central en el controlador es una carpeta con la siguiente convención de nomenclatura: **%systemroot%\sysvol \\<dominio \> \policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="e0662-110">Central store on the controller is a folder with the following naming convention: **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="e0662-p102">Todos los dominios que maneja el controlador deben obtener una carpeta diferente. El comando siguiente puede usarse para copiar el archivo ADMX desde el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="e0662-p102">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="e0662-113">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="e0662-113">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
2. <span data-ttu-id="e0662-114">Vaya a **&lt;Equipo/Configuración de usuario&gt;\Plantillas administrativas\Componentes de Windows\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="e0662-114">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
3. <span data-ttu-id="e0662-115">Haga doble clic en **Establecer motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="e0662-115">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
4. <span data-ttu-id="e0662-116">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e0662-116">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>


## <a name="google-chrome-on-windows-10-version-1507-or-later"></a><span data-ttu-id="e0662-117">Google Chrome en Windows 10, versión 1507 o posterior</span><span class="sxs-lookup"><span data-stu-id="e0662-117">Google Chrome on Windows 10, Version 1507 or later</span></span>

<span data-ttu-id="e0662-118">Los usuarios no podrán cambiar el motor de búsqueda predeterminado después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="e0662-118">Users won't be able to change the default search engine after this policy is set.</span></span>
  
<span data-ttu-id="e0662-119">Chrome viene con su propio conjunto de configuraciones de directiva de grupo que se pueden descargar en forma de archivo ADMX de [la Ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="e0662-119">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="e0662-120">Copie el archivo de plantilla en un almacén central para archivos ADMX en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="e0662-120">Copy the template file to a central store for ADMX files on the domain controller.</span></span> <span data-ttu-id="e0662-121">Para obtener más información, [vea Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span><span class="sxs-lookup"><span data-stu-id="e0662-121">For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span></span> <span data-ttu-id="e0662-122">El almacén central en el controlador es una carpeta con la siguiente convención de nomenclatura: **%systemroot%\sysvol \\<dominio \> \policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="e0662-122">Central store on the controller is a folder with the following naming convention: **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="e0662-p104">Todos los dominios que maneja el controlador deben obtener una carpeta diferente. El comando siguiente puede usarse para copiar el archivo ADMX desde el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="e0662-p104">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="e0662-125">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="e0662-125">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
2. <span data-ttu-id="e0662-126">Asegúrese de que las carpetas siguientes aparecen en la sección de Plantillas administrativas en Usuario/Configuración de equipo: Google Chrome y Google Chrome: configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e0662-126">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>

    - <span data-ttu-id="e0662-127">La configuración de la primera sección es fija y los administradores locales no pueden cambiarla en el explorador.</span><span class="sxs-lookup"><span data-stu-id="e0662-127">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    - <span data-ttu-id="e0662-128">Los usuarios pueden cambiar la configuración de la segunda sección de directivas en la configuración del explorador.</span><span class="sxs-lookup"><span data-stu-id="e0662-128">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>

3. <span data-ttu-id="e0662-129">Vaya a **\<Computer/User\> Configuración\Plantillas administrativas\Google Chrome\Proveedor de búsqueda predeterminado**</span><span class="sxs-lookup"><span data-stu-id="e0662-129">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
4. <span data-ttu-id="e0662-130">Haga doble clic en **Habilitar el motor de búsqueda predeterminado** y establézcalo como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="e0662-130">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
5. <span data-ttu-id="e0662-131">Haga doble clic en el **icono de Motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://www.bing.com/sa/simg/bb.ico`.</span><span class="sxs-lookup"><span data-stu-id="e0662-131">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
6. <span data-ttu-id="e0662-132">Haga doble clic en el **URL instantánea del motor de búsqueda predeterminado** y escriba `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`.</span><span class="sxs-lookup"><span data-stu-id="e0662-132">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
7. <span data-ttu-id="e0662-133">Haga doble clic en el **nombre del motor de búsqueda predeterminado**, establézcalo como Habilitado y escriba "Microsoft Search en Bing".</span><span class="sxs-lookup"><span data-stu-id="e0662-133">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
8. <span data-ttu-id="e0662-134">Haga doble clic en el **URL de búsqueda del motor de búsqueda predeterminado**, establézcalo como **Habilitado** y escriba `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`.</span><span class="sxs-lookup"><span data-stu-id="e0662-134">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
9. <span data-ttu-id="e0662-135">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e0662-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

## <a name="internet-explorer-11-or-later"></a><span data-ttu-id="e0662-136">Internet Explorer 11 o posterior</span><span class="sxs-lookup"><span data-stu-id="e0662-136">Internet Explorer 11 or later</span></span>

<span data-ttu-id="e0662-137">Los usuarios podrán cambiar el proveedor de búsqueda después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="e0662-137">Users will be able to change the search provider after this policy is set.</span></span>
  
### <a name="step-1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="e0662-138">PASO 1.</span><span class="sxs-lookup"><span data-stu-id="e0662-138">STEP 1.</span></span> <span data-ttu-id="e0662-139">Configure el equipo local que se usará para establecer el GPO</span><span class="sxs-lookup"><span data-stu-id="e0662-139">Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="e0662-140">Pegue el texto siguiente en un archivo de registro (\*.reg).</span><span class="sxs-lookup"><span data-stu-id="e0662-140">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="e0662-141">Windows Registry Editor Version 5.00</span><span class="sxs-lookup"><span data-stu-id="e0662-141">Windows Registry Editor Version 5.00</span></span>
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
<span data-ttu-id="e0662-p106">Haga doble clic en el archivo creado y siga los pasos para importar el archivo. Una importación correcta debe dar como resultado el cuadro de diálogo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0662-p106">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![Mensaje de importación correcta del Editor del registro](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
### <a name="step-2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="e0662-145">PASO 2.</span><span class="sxs-lookup"><span data-stu-id="e0662-145">STEP 2.</span></span> <span data-ttu-id="e0662-146">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="e0662-146">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="e0662-147">Vaya a **Configuración de usuario\Configuración\Directivas\Preferencias\Configuración de Windows**.</span><span class="sxs-lookup"><span data-stu-id="e0662-147">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
2. <span data-ttu-id="e0662-p108">Haga clic derecho en **Registro\Nuevo** y seleccione **Asistente de registro**. En la ventana del Explorador de registro, seleccione **Equipo local** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e0662-p108">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
3. <span data-ttu-id="e0662-150">Vaya a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span><span class="sxs-lookup"><span data-stu-id="e0662-150">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
4. <span data-ttu-id="e0662-151">En esta clave, asegúrese de seleccionar DefaultScope.</span><span class="sxs-lookup"><span data-stu-id="e0662-151">From this key, make sure to select DefaultScope.</span></span>

    ![Explorador de registro con DefaultScope seleccionado](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
5. <span data-ttu-id="e0662-p109">Compruebe todas las subclaves que contienen el GUID de Microsoft Search en Bing y todos los valores de la clave excepto las rutas de acceso a los perfiles de usuario. Desplácese hacia abajo para seleccionar otros elementos.</span><span class="sxs-lookup"><span data-stu-id="e0662-p109">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
6. <span data-ttu-id="e0662-155">Haga clic en Finalizar para terminar la configuración.</span><span class="sxs-lookup"><span data-stu-id="e0662-155">Click Finish to complete this configuration.</span></span>

### <a name="step-3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="e0662-156">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="e0662-156">STEP 3.</span></span> <span data-ttu-id="e0662-157">Configurar las Preferencias de usuario para ayudar a eliminar la advertencia que posiblemente reciba el usuario cuando se aplique la búsqueda DefaultScope</span><span class="sxs-lookup"><span data-stu-id="e0662-157">Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="e0662-158">Esta advertencia es intencionada y alerta a los usuarios de un programa que intentan modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="e0662-158">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="e0662-159">En el mismo GPO, haga clic derecho en **Registro\Nuevo** y seleccione **Asistente de registro**.</span><span class="sxs-lookup"><span data-stu-id="e0662-159">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
2. <span data-ttu-id="e0662-160">Vaya a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span><span class="sxs-lookup"><span data-stu-id="e0662-160">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
3. <span data-ttu-id="e0662-161">Seleccione la clave **User Preference**.</span><span class="sxs-lookup"><span data-stu-id="e0662-161">Select the **User Preference** key.</span></span>
4. <span data-ttu-id="e0662-162">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e0662-162">Click **Finish**.</span></span>
5. <span data-ttu-id="e0662-p111">Haga clic en el objeto recién creado. En el panel de la derecha, haga doble clic en el objeto User Preferences y cambie la **Acción** a **Eliminar y guardar**.</span><span class="sxs-lookup"><span data-stu-id="e0662-p111">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
6. <span data-ttu-id="e0662-165">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e0662-165">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
