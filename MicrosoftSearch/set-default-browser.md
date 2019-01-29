---
title: Establecer explorador predeterminado
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
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Obtenga información sobre cómo configurar un explorador predeterminado para su empresa con Microsoft Search.
ms.openlocfilehash: 160dbbef9981127b74c51f54f86428667ecd4471
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612477"
---
# <a name="set-default-browser"></a><span data-ttu-id="12db8-103">Establecer explorador predeterminado</span><span class="sxs-lookup"><span data-stu-id="12db8-103">Set default browser</span></span>

<span data-ttu-id="12db8-104">Configurar el explorador predeterminado, el motor de búsqueda predeterminado y la página principal predeterminada le ayudará a los usuarios a descubrir las capacidades de Microsoft Search, fomentar el uso más y proporcionar una experiencia más suave.</span><span class="sxs-lookup"><span data-stu-id="12db8-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="12db8-105">Para establecer el explorador predeterminado para la organización, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="12db8-105">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="12db8-106">Windows 8 y anterior</span><span class="sxs-lookup"><span data-stu-id="12db8-106">Windows 8 and above</span></span>

<span data-ttu-id="12db8-107">Para configurar Internet Explorer o Microsoft Edge como el explorador predeterminado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="12db8-107">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="12db8-108">Crear el archivo de asociaciones predeterminado</span><span class="sxs-lookup"><span data-stu-id="12db8-108">Create default associations file</span></span>

1. <span data-ttu-id="12db8-109">Abra una consola administrativa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12db8-109">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="12db8-110">Estos pasos probar y creación el archivo de asociaciones de forma predeterminada en la carpeta SYSVOL del controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="12db8-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="12db8-111">Agregar o editar el archivo de asociaciones predeterminado</span><span class="sxs-lookup"><span data-stu-id="12db8-111">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="12db8-112">Editar las siguientes entradas (.htm, .html, http, https) y quitar otras entradas si no se necesitan.</span><span class="sxs-lookup"><span data-stu-id="12db8-112">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="12db8-113">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="12db8-113">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="12db8-114">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="12db8-114">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="12db8-115">Abra la consola de administración de directivas de grupo (gpmc.msc) y cambie a la edición de cualquier directiva existente o crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="12db8-115">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="12db8-116">Vaya a **configuración de usuario\Plantillas administrativas\Componentes Components\File Explorer de equipo**</span><span class="sxs-lookup"><span data-stu-id="12db8-116">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="12db8-117">Haga doble clic en **establecer un archivo de configuración de asociaciones de forma predeterminada**, establecida en **habilitado**y escriba la ruta de acceso a AppAssoc.xml (por ejemplo %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span><span class="sxs-lookup"><span data-stu-id="12db8-117">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="12db8-118">Aplicar el GPO resultante mediante la vinculación al dominio apropiado.</span><span class="sxs-lookup"><span data-stu-id="12db8-118">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="12db8-119">Los usuarios podrán cambiar el explorador una vez establecida esta directiva.</span><span class="sxs-lookup"><span data-stu-id="12db8-119">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="12db8-120">Windows 7</span><span class="sxs-lookup"><span data-stu-id="12db8-120">Windows 7</span></span>

1. <span data-ttu-id="12db8-121">Configurar el equipo local que se usará para establecer el GPO.</span><span class="sxs-lookup"><span data-stu-id="12db8-121">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="12db8-122">Abra **Programas de Control Panel\Programs\Default Programs\Set predeterminados** y configurar Internet Explorer como el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="12db8-122">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="12db8-123">Abra la consola de administración de directivas de grupo (gpmc.msc) y cambie a la edición de cualquier directiva existente o crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="12db8-123">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="12db8-124">Vaya a \*\* \<usuario o equipo\> configuración de Configuration\Policies\Preferences\Windows\*\*.</span><span class="sxs-lookup"><span data-stu-id="12db8-124">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="12db8-125">El botón secundario en **Registry\New** y seleccione **Asistente para el registro**.</span><span class="sxs-lookup"><span data-stu-id="12db8-125">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="12db8-126">Desde la ventana del explorador de registro, seleccione **Equipo Local** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="12db8-126">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="12db8-p101">Vaya a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** y seleccione el valor ProgId. Asegúrese de que el valor tiene el aspecto como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="12db8-p101">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Seleccione el valor ProgID en Editar cadena](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="12db8-p102">Vaya a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** y seleccione el valor ProgId. Asegúrese de que el valor tiene el aspecto como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="12db8-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Seleccione ProgId para HTTPS en la cadena de edición](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="12db8-133">Aplicar el GPO resultante mediante la vinculación al dominio apropiado.</span><span class="sxs-lookup"><span data-stu-id="12db8-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="12db8-134">Los usuarios podrán cambiar el explorador una vez establecida esta directiva.</span><span class="sxs-lookup"><span data-stu-id="12db8-134">Users will be able to change the browser after this policy is set.</span></span>