---
title: Establecer explorador predeterminado
ms.author: anfowler
author: adefowler
manager: shohara
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
description: Configure Microsoft Edge o Internet Explorer como explorador predeterminado para los usuarios de Búsqueda de Microsoft.
ms.openlocfilehash: ed145a1811aba0b58158ed04dd3bf8dc089a0682
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639743"
---
# <a name="make-microsoft-edge-the-default-browser"></a><span data-ttu-id="01c05-103">Hacer de Microsoft Edge el explorador predeterminado</span><span class="sxs-lookup"><span data-stu-id="01c05-103">Make Microsoft Edge the default browser</span></span>
  
<span data-ttu-id="01c05-104">Para proporcionar a los usuarios la mejor experiencia con Búsqueda de Microsoft, puede hacer de Microsoft Edge el explorador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="01c05-104">To give your users the best experience with Microsoft Search, you can make Microsoft Edge the default browser.</span></span> <span data-ttu-id="01c05-105">Esto solo establece Microsoft Edge como explorador predeterminado para los usuarios en su organización; los usuarios pueden seleccionar individualmente un explorador diferente.</span><span class="sxs-lookup"><span data-stu-id="01c05-105">This will only set Microsoft Edge as the default browser for users in your org, individual users can still select a different browser.</span></span>
  
  
## <a name="windows-8-and-later"></a><span data-ttu-id="01c05-106">Windows 8 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="01c05-106">Windows 8 and above</span></span>

<span data-ttu-id="01c05-107">Estas instrucciones muestran cómo establecer Microsoft Edge o Internet Explorer como explorador predeterminado para equipos que ejecutan Windows 8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="01c05-107">These instructions show you how to make Microsoft Edge or Internet Explorer as the default browser for computers running Windows 8 or later.</span></span> <span data-ttu-id="01c05-108">Los usuarios podrán cambiar el explorador después de establecer esta directiva.</span><span class="sxs-lookup"><span data-stu-id="01c05-108">Users will be able to change the browser after this policy is set.</span></span>
  
### <a name="step-1-create-the-default-associations-file"></a><span data-ttu-id="01c05-109">PASO 1: Cree el archivo de asociaciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="01c05-109">STEP 1: Create the default associations file</span></span>
<span data-ttu-id="01c05-110">Cree el archivo de asociaciones predeterminadas en la carpeta SYSVOL del controlador del dominio.</span><span class="sxs-lookup"><span data-stu-id="01c05-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>

1. <span data-ttu-id="01c05-111">Abra una consola de administración de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01c05-111">Open an administrative PowerShell console.</span></span>
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a><span data-ttu-id="01c05-112">PASO 2.</span><span class="sxs-lookup"><span data-stu-id="01c05-112">Step 2</span></span> <span data-ttu-id="01c05-113">Agregue o edite el archivo de asociaciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="01c05-113">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. <span data-ttu-id="01c05-114">Edite las siguientes entradas (.htm, .html, http, https) y quite otras entradas si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="01c05-114">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
  - <span data-ttu-id="01c05-115">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="01c05-115">**Microsoft Edge**</span></span>
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="01c05-116">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="01c05-116">**Internet Explorer**</span></span>
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a><span data-ttu-id="01c05-117">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="01c05-117">Step 3.</span></span> <span data-ttu-id="01c05-118">Edite la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="01c05-118">Edit the Group Policy</span></span>

1. <span data-ttu-id="01c05-119">Abra la **Consola de administración de directivas de grupo (gpmc.msc)** y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="01c05-119">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="01c05-120">Vaya a **Configuración del equipo\Plantillas administrativas\Componentes de Windows\Explorador de archivos**.</span><span class="sxs-lookup"><span data-stu-id="01c05-120">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
1. <span data-ttu-id="01c05-121">Haga doble clic en **Establecer un archivo de configuración de asociaciones predeterminadas**, establézcalo en **Habilitado** y especifique la ruta de acceso a AppAssoc.xml (por ejemplo: %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Aplique el GPO resultante vinculándolo al dominio apropiado.</span><span class="sxs-lookup"><span data-stu-id="01c05-121">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="windows-7"></a><span data-ttu-id="01c05-122">Windows 7</span><span class="sxs-lookup"><span data-stu-id="01c05-122">Windows 7</span></span>

1. <span data-ttu-id="01c05-123">Configure el equipo local que se usará para establecer el GPO</span><span class="sxs-lookup"><span data-stu-id="01c05-123">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="01c05-124">Abra **Panel de control\Programas\Programas predeterminados\Establecer programas predeterminados** y establezca Internet Explorer como predeterminado.</span><span class="sxs-lookup"><span data-stu-id="01c05-124">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="01c05-125">Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="01c05-125">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="01c05-126">Vaya a **\<Equipo/Configuración\> de usuario\Directivas\Preferencias\Configuración de Windows**.</span><span class="sxs-lookup"><span data-stu-id="01c05-126">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="01c05-127">Haga clic derecho en **Registro\Nuevo** y seleccione **Asistente de registro**.</span><span class="sxs-lookup"><span data-stu-id="01c05-127">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="01c05-128">En la ventana del Explorador de registro, seleccione **Equipo local** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="01c05-128">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="01c05-p105">Vaya a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** y seleccione el valor ProgId. Asegúrese de que el valor tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="01c05-p105">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Seleccione el valor ProgId en Editar cadena](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="01c05-p106">Vaya a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** y seleccione el valor ProgId. Asegúrese de que el valor tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="01c05-p106">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Seleccione ProgId para HTTPS en Editar cadena](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="01c05-135">Aplique el GPO resultante vinculándolo al dominio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="01c05-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
