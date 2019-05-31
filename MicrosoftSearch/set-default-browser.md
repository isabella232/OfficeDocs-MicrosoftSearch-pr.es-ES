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
ROBOTS: NOINDEX
description: Obtenga información sobre cómo configurar un explorador predeterminado para su empresa con Microsoft Search.
ms.openlocfilehash: daff7f66bd38bdd56179e44c36092a2c4fd42b42
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591165"
---
# <a name="set-default-browser"></a><span data-ttu-id="fa454-103">Establecer explorador predeterminado</span><span class="sxs-lookup"><span data-stu-id="fa454-103">Set default browser</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa454-104">Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing</span><span class="sxs-lookup"><span data-stu-id="fa454-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="fa454-105">Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se eliminará.</span><span class="sxs-lookup"><span data-stu-id="fa454-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="fa454-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="fa454-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="fa454-107">[Introducción a Microsoft Search (Búsqueda de Microsoft)](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="fa454-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="fa454-108">La configuración de la página principal, motor de búsqueda y explorador predeterminados ayudará a los usuarios a descubrir las funciones de Microsoft Search, fomentar su uso y proporcionar una experiencia más fluida.</span><span class="sxs-lookup"><span data-stu-id="fa454-108">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="fa454-109">Para establecer el explorador predeterminado para su organización, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="fa454-109">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="fa454-110">Windows 8 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="fa454-110">Windows 8 and above</span></span>

<span data-ttu-id="fa454-111">Para configurar Internet Explorer o Microsoft Edge como explorador predeterminado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fa454-111">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="fa454-112">Cree el archivo de asociaciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="fa454-112">Create default associations file</span></span>

1. <span data-ttu-id="fa454-113">Abra una consola de administración de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa454-113">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="fa454-114">Estos pasos intentan crear el archivo de asociaciones predeterminadas en la carpeta SYSVOL del controlador del dominio.</span><span class="sxs-lookup"><span data-stu-id="fa454-114">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="fa454-115">Agregue o edite el archivo de asociaciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="fa454-115">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="fa454-116">Edite las siguientes entradas (.htm, .html, http, https) y quite otras entradas si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="fa454-116">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="fa454-117">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="fa454-117">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="fa454-118">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="fa454-118">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="fa454-119">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="fa454-119">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="fa454-120">Vaya a **Configuración del equipo\Plantillas administrativas\Componentes de Windows\Explorador de archivos**.</span><span class="sxs-lookup"><span data-stu-id="fa454-120">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="fa454-121">Haga doble clic en **Establecer un archivo de configuración de asociaciones predeterminadas**, establézcalo en **Habilitado** y especifique la ruta de acceso a AppAssoc.xml (por ejemplo: %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span><span class="sxs-lookup"><span data-stu-id="fa454-121">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="fa454-122">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="fa454-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="fa454-123">Los usuarios podrán cambiar el explorador después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="fa454-123">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="fa454-124">Windows 7</span><span class="sxs-lookup"><span data-stu-id="fa454-124">Windows 7</span></span>

1. <span data-ttu-id="fa454-125">Configure el equipo local que se usará para establecer el GPO</span><span class="sxs-lookup"><span data-stu-id="fa454-125">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="fa454-126">Abra **Panel de control\Programas\Programas predeterminados\Establecer programas predeterminados** y establezca Internet Explorer como predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fa454-126">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="fa454-127">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="fa454-127">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="fa454-128">Vaya a **\<Equipo/Configuración\> de usuario\Directivas\Preferencias\Configuración de Windows**.</span><span class="sxs-lookup"><span data-stu-id="fa454-128">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="fa454-129">Haga clic derecho en **Registro\Nuevo** y seleccione **Asistente de registro**.</span><span class="sxs-lookup"><span data-stu-id="fa454-129">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="fa454-130">En la ventana del Explorador de registro, seleccione **Equipo local** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fa454-130">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="fa454-p102">Vaya a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** y seleccione el valor ProgId. Asegúrese de que el valor tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa454-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Seleccione el valor ProgId en Editar cadena](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="fa454-p103">Vaya a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** y seleccione el valor ProgId. Asegúrese de que el valor tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa454-p103">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Seleccione ProgId para HTTPS en Editar cadena](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="fa454-137">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="fa454-137">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="fa454-138">Los usuarios podrán cambiar el explorador después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="fa454-138">Users will be able to change the browser after this policy is set.</span></span>