---
title: Agente local
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Agente local
ms.openlocfilehash: 5dbca392fefdcc11de253fd244cc98a6adcee68a
ms.sourcegitcommit: e8d770fa72ac83e074a5de57098cb55d06d8db07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588371"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="7d6a1-103">Agente de conector de Graph</span><span class="sxs-lookup"><span data-stu-id="7d6a1-103">Graph connector agent</span></span>

<span data-ttu-id="7d6a1-104">El uso de conectores de gráficos locales requiere la instalación del software del *agente de conector de Graph* .</span><span class="sxs-lookup"><span data-stu-id="7d6a1-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="7d6a1-105">Permite una transferencia de datos segura entre los datos locales y las API de conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="7d6a1-106">Este artículo le guiará a través de la instalación y configuración del agente.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="7d6a1-107">Instalación</span><span class="sxs-lookup"><span data-stu-id="7d6a1-107">Installation</span></span>

<span data-ttu-id="7d6a1-108">Descargue la última versión [del agente de](https://aka.ms/gcadownload) conector de Graph y instale el software mediante el Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="7d6a1-109">Mediante el uso de la configuración recomendada del equipo que se describe a continuación, el software puede administrar hasta tres conexiones.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="7d6a1-110">Cualquier conexión posterior podría degradar el rendimiento de todas las conexiones en el agente.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="7d6a1-111">Configuración recomendada:</span><span class="sxs-lookup"><span data-stu-id="7d6a1-111">Recommended configuration:</span></span>

* <span data-ttu-id="7d6a1-112">Windows 10, Windows Server 2016 R2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7d6a1-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="7d6a1-113">.NET Core Desktop Runtime de 3,1 (x64)</span><span class="sxs-lookup"><span data-stu-id="7d6a1-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="7d6a1-114">8 núcleos, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="7d6a1-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="7d6a1-115">16 GB de RAM, 2 GB de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="7d6a1-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="7d6a1-116">Acceso de red a origen de datos e Internet mediante 443</span><span class="sxs-lookup"><span data-stu-id="7d6a1-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="7d6a1-117">Crear y configurar una aplicación para el agente</span><span class="sxs-lookup"><span data-stu-id="7d6a1-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="7d6a1-118">Antes de usar el agente, debe crear una aplicación y configurar los detalles de autenticación.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-118">Before using the agent, you must create an app and configure the authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="7d6a1-119">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="7d6a1-119">Create an app</span></span>

1. <span data-ttu-id="7d6a1-120">Vaya a [Azure portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-120">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="7d6a1-121">Navegue a **Azure Active Directory**  ->  **registros de aplicaciones** de Azure Active Directory desde el panel de navegación y seleccione **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-121">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="7d6a1-122">Especifique un nombre para la aplicación y seleccione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-122">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="7d6a1-123">Anote el identificador de la aplicación (cliente).</span><span class="sxs-lookup"><span data-stu-id="7d6a1-123">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="7d6a1-124">Abra **permisos de API** en el panel de navegación y seleccione **Agregar un permiso**.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-124">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="7d6a1-125">Seleccione **Microsoft Graph** y, a continuación, permisos de la **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-125">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="7d6a1-126">Busque "ExternalItem. ReadWrite. All" y "Directory. Read. All" desde los permisos y seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-126">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="7d6a1-127">Seleccione **conceder consentimiento de administrador para [TenantName]** y confirme seleccionando **sí**.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-127">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="7d6a1-128">Compruebe que los permisos estén en el estado "concedido".</span><span class="sxs-lookup"><span data-stu-id="7d6a1-128">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="7d6a1-129">![Permisos que se muestran como concedidos en verde en la columna derecha.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="7d6a1-129">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="7d6a1-130">Configurar la autenticación</span><span class="sxs-lookup"><span data-stu-id="7d6a1-130">Configure Authentication</span></span>

<span data-ttu-id="7d6a1-131">Se pueden proporcionar detalles de autenticación mediante un secreto de cliente o un certificado.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-131">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="7d6a1-132">Siga los pasos que desee.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-132">Follow the steps for your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="7d6a1-133">Configuración del secreto de cliente para la autenticación</span><span class="sxs-lookup"><span data-stu-id="7d6a1-133">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="7d6a1-134">Vaya a [Azure portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-134">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="7d6a1-135">Abra el **registro de aplicaciones** en el panel de navegación y vaya a la aplicación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-135">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="7d6a1-136">En **administrar**, seleccione **certificados y secretos**.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-136">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="7d6a1-137">Seleccione **nuevo secreto de cliente** y seleccione un período de expiración para el secreto.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-137">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="7d6a1-138">Copie el secreto generado y guárdelo porque no se volverá a mostrar.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-138">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="7d6a1-139">Use este secreto de cliente junto con el identificador de aplicación para configurar el agente.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-139">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="7d6a1-140">No puede usar espacios en blanco en el campo **nombre** del agente.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-140">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="7d6a1-141">Se aceptan los caracteres alfanuméricos alfanuméricos.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-141">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="7d6a1-142">Uso de un certificado para la autenticación</span><span class="sxs-lookup"><span data-stu-id="7d6a1-142">Using a certificate for authentication</span></span>

<span data-ttu-id="7d6a1-143">Hay tres pasos sencillos para usar la autenticación basada en certificados:</span><span class="sxs-lookup"><span data-stu-id="7d6a1-143">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="7d6a1-144">Creación u obtención de un certificado</span><span class="sxs-lookup"><span data-stu-id="7d6a1-144">Create or obtain a certificate</span></span>
1. <span data-ttu-id="7d6a1-145">Cargar el certificado en el portal de Azure</span><span class="sxs-lookup"><span data-stu-id="7d6a1-145">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="7d6a1-146">Asignar el certificado al agente</span><span class="sxs-lookup"><span data-stu-id="7d6a1-146">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="7d6a1-147">Paso 1: obtener un certificado</span><span class="sxs-lookup"><span data-stu-id="7d6a1-147">Step 1: Get a certificate</span></span>

<span data-ttu-id="7d6a1-148">El script siguiente se puede usar para generar un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-148">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="7d6a1-149">Es posible que su organización no permita certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-149">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="7d6a1-150">En ese caso, use esta información para comprender los requisitos y adquirir un certificado de acuerdo con las directivas de la organización.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-150">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

```Powershell
$dnsName = "<TenantDomain like agent.onmicrosoft.com>" # Your DNS name
$password = "<password>" # Certificate password
$folderPath = "D:\New folder\" # Where do you want the files to get saved to? The folder needs to exist.
$fileName = "agentcert" # What do you want to call the cert files? without the file extension
$yearsValid = 10 # Number of years until you need to renew the certificate
$certStoreLocation = "cert:\LocalMachine\My"
$expirationDate = (Get-Date).AddYears($yearsValid)
$certificate = New-SelfSignedCertificate -DnsName $dnsName -CertStoreLocation $certStoreLocation -NotAfter $expirationDate -KeyExportPolicy Exportable -KeySpec Signature
$certificatePath = $certStoreLocation + '\' + $certificate.Thumbprint
$filePath = $folderPath + '\' + $fileName
$securePassword = ConvertTo-SecureString -String $password -Force -AsPlainText
Export-Certificate -Cert $certificatePath -FilePath ($filePath + '.cer')
Export-PfxCertificate -Cert $certificatePath -FilePath ($filePath + '.pfx') -Password $securePassword
```

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="7d6a1-151">Paso 2: cargar el certificado en Azure portal</span><span class="sxs-lookup"><span data-stu-id="7d6a1-151">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="7d6a1-152">Abra la aplicación y vaya a la sección certificados y secretos del panel izquierdo</span><span class="sxs-lookup"><span data-stu-id="7d6a1-152">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="7d6a1-153">Seleccione "cargar certificado" y cargue el archivo. cer</span><span class="sxs-lookup"><span data-stu-id="7d6a1-153">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="7d6a1-154">Abra el **registro de aplicaciones** y seleccione **certificados y secretos** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-154">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="7d6a1-155">Copie la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-155">Copy the certificate thumbprint.</span></span>

![Lista de certificados de thumbrint cuando se selecciona certificados y secretos en el panel izquierdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="7d6a1-157">Paso 3: asignar el certificado al agente</span><span class="sxs-lookup"><span data-stu-id="7d6a1-157">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="7d6a1-158">Si usó el script de ejemplo para generar un certificado, el archivo PFX puede encontrarse en la ubicación identificada en el script.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-158">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="7d6a1-159">Descargue el archivo PFX de certificado en el equipo del agente.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-159">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="7d6a1-160">Haga doble clic en el archivo PFX para iniciar el cuadro de diálogo de instalación de certificado.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-160">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="7d6a1-161">Seleccione "equipo local" para la ubicación del almacén mientras instala el certificado.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-161">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="7d6a1-162">Después de instalar el certificado, abra "administrar certificados de equipo" a través del menú Inicio</span><span class="sxs-lookup"><span data-stu-id="7d6a1-162">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="7d6a1-163">Seleccione el certificado recién instalado en ' ' personal '-> ' certificados '</span><span class="sxs-lookup"><span data-stu-id="7d6a1-163">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="7d6a1-164">Haga clic con el botón secundario en el certificado y seleccione "todas las tareas"-> "administrar claves privadas..."</span><span class="sxs-lookup"><span data-stu-id="7d6a1-164">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="7d6a1-165">Opción</span><span class="sxs-lookup"><span data-stu-id="7d6a1-165">Option</span></span>
1. <span data-ttu-id="7d6a1-166">En el cuadro de diálogo permisos, seleccione Agregar opción.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-166">In the permissions dialog, select add option.</span></span> <span data-ttu-id="7d6a1-167">En el cuadro de diálogo de selección del usuario, escriba: "NT Service\GcaHostService" y haga clic en "Aceptar".</span><span class="sxs-lookup"><span data-stu-id="7d6a1-167">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="7d6a1-168">No haga clic en el botón Comprobar nombres.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-168">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="7d6a1-169">Haga clic en aceptar en el cuadro de diálogo permisos.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-169">Click okay on the permissions dialog.</span></span> <span data-ttu-id="7d6a1-170">El equipo del agente ya está configurado para que el agente genere los tokens con el certificado.</span><span class="sxs-lookup"><span data-stu-id="7d6a1-170">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
