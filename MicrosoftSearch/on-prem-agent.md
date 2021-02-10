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
description: Agente on-prem
ms.openlocfilehash: 7aef2ea57c92929d4d4f45e1a738c84e6a3f4bba
ms.sourcegitcommit: ab4f81ded967168689e6e81c90e115b94719335c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "50173066"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="ef7b6-103">Agente de conector de Graph</span><span class="sxs-lookup"><span data-stu-id="ef7b6-103">Graph connector agent</span></span>

<span data-ttu-id="ef7b6-104">El uso de conectores de Graph locales requiere instalar el software *del agente de conector de Graph.*</span><span class="sxs-lookup"><span data-stu-id="ef7b6-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="ef7b6-105">Permite la transferencia segura de datos entre los datos locales y las API del conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="ef7b6-106">Este artículo le guiará a través de la instalación y configuración del agente.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="ef7b6-107">Instalación</span><span class="sxs-lookup"><span data-stu-id="ef7b6-107">Installation</span></span>

<span data-ttu-id="ef7b6-108">Descargue aquí la versión más reciente del agente del conector de Graph [e](https://aka.ms/gcadownload) instale el software con el asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="ef7b6-109">Con la configuración recomendada de la máquina que se describe a continuación, el software puede controlar hasta tres conexiones.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="ef7b6-110">Las conexiones posteriores pueden degradar el rendimiento de todas las conexiones en el agente.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="ef7b6-111">Configuración recomendada:</span><span class="sxs-lookup"><span data-stu-id="ef7b6-111">Recommended configuration:</span></span>

* <span data-ttu-id="ef7b6-112">Windows 10, Windows Server 2016 R2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="ef7b6-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="ef7b6-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="ef7b6-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="ef7b6-114">8 núcleos, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="ef7b6-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="ef7b6-115">16 GB de RAM, 2 GB de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="ef7b6-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="ef7b6-116">Acceso de red al origen de datos e Internet a través del 443</span><span class="sxs-lookup"><span data-stu-id="ef7b6-116">Network access to data source and internet through 443</span></span>

<span data-ttu-id="ef7b6-117">Después de instalar el agente, si los servidores proxy o firewalls de su organización bloquean la comunicación con dominios desconocidos, agregue los siguientes a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-117">After you install the agent, if your organization's proxy servers or firewalls block communication to unknown domains, please add below ones to the allow list.</span></span>

1. <span data-ttu-id="ef7b6-118">\*.servicebus.windows.net</span><span class="sxs-lookup"><span data-stu-id="ef7b6-118">\*.servicebus.windows.net</span></span>
2. <span data-ttu-id="ef7b6-119">\*.events.data.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ef7b6-119">\*.events.data.microsoft.com</span></span>
3. https://login.microsoftonline.com
4. https://gcs.office.com
5. https://graph.microsoft.com/


## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="ef7b6-120">Crear y configurar una aplicación para el agente</span><span class="sxs-lookup"><span data-stu-id="ef7b6-120">Create and configure an App for the agent</span></span>  

<span data-ttu-id="ef7b6-121">En primer lugar, inicie sesión y tenga en cuenta que el privilegio mínimo requerido en la cuenta es el administrador de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-121">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="ef7b6-122">A continuación, el agente le pedirá que proporcione detalles de autenticación.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-122">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="ef7b6-123">Siga los pasos siguientes para crear una aplicación y generar los detalles de autenticación necesarios.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-123">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="ef7b6-124">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="ef7b6-124">Create an app</span></span>

1. <span data-ttu-id="ef7b6-125">Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con las credenciales de administrador del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-125">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="ef7b6-126">Vaya a **Registros de aplicaciones de Azure Active Directory** desde el panel de navegación y seleccione Nuevo  ->   **registro.**</span><span class="sxs-lookup"><span data-stu-id="ef7b6-126">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="ef7b6-127">Proporcione un nombre para la aplicación y seleccione **Registrar.**</span><span class="sxs-lookup"><span data-stu-id="ef7b6-127">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="ef7b6-128">Anote el id. de aplicación (cliente).</span><span class="sxs-lookup"><span data-stu-id="ef7b6-128">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="ef7b6-129">Abra **los permisos de** api en el panel de navegación y seleccione Agregar un **permiso.**</span><span class="sxs-lookup"><span data-stu-id="ef7b6-129">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="ef7b6-130">Seleccione **Microsoft Graph y,** a continuación, **permisos de aplicación.**</span><span class="sxs-lookup"><span data-stu-id="ef7b6-130">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="ef7b6-131">Busque "ExternalItem.ReadWrite.All" y "Directory.Read.All" en los permisos y seleccione **Agregar permisos.**</span><span class="sxs-lookup"><span data-stu-id="ef7b6-131">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="ef7b6-132">Seleccione **Conceder consentimiento de administrador para [TenantName]** y confirme **seleccionando Sí**.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-132">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="ef7b6-133">Compruebe que los permisos están en el estado "concedido".</span><span class="sxs-lookup"><span data-stu-id="ef7b6-133">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="ef7b6-134">![Permisos que se muestran en verde en la columna de la derecha.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="ef7b6-134">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="ef7b6-135">Configurar la autenticación</span><span class="sxs-lookup"><span data-stu-id="ef7b6-135">Configure Authentication</span></span>

<span data-ttu-id="ef7b6-136">Los detalles de autenticación se pueden proporcionar mediante un secreto de cliente o un certificado.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-136">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="ef7b6-137">Siga los pasos que desee.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-137">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="ef7b6-138">Configuración del secreto de cliente para la autenticación</span><span class="sxs-lookup"><span data-stu-id="ef7b6-138">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="ef7b6-139">Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con las credenciales de administrador del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-139">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="ef7b6-140">Abra **Registro de aplicaciones** desde el panel de navegación y vaya a la aplicación adecuada.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-140">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="ef7b6-141">En **Administrar,** seleccione **Certificados y secretos.**</span><span class="sxs-lookup"><span data-stu-id="ef7b6-141">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="ef7b6-142">Seleccione **nuevo secreto de** cliente y seleccione un período de expiración para el secreto.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-142">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="ef7b6-143">Copie el secreto generado y guárdelo porque no se volverá a mostrar.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-143">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="ef7b6-144">Use este secreto de cliente junto con el id. de aplicación para configurar el agente.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-144">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="ef7b6-145">No puede usar espacios en blanco en el **campo Nombre** del agente.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-145">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="ef7b6-146">Se aceptan caracteres numéricos alfa.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-146">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="ef7b6-147">Uso de un certificado para la autenticación</span><span class="sxs-lookup"><span data-stu-id="ef7b6-147">Using a certificate for authentication</span></span>

<span data-ttu-id="ef7b6-148">Hay tres pasos sencillos para usar la autenticación basada en certificados:</span><span class="sxs-lookup"><span data-stu-id="ef7b6-148">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="ef7b6-149">Crear u obtener un certificado</span><span class="sxs-lookup"><span data-stu-id="ef7b6-149">Create or obtain a certificate</span></span>
1. <span data-ttu-id="ef7b6-150">Cargar el certificado en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="ef7b6-150">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="ef7b6-151">Asignar el certificado al agente</span><span class="sxs-lookup"><span data-stu-id="ef7b6-151">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="ef7b6-152">Paso 1: Obtener un certificado</span><span class="sxs-lookup"><span data-stu-id="ef7b6-152">Step 1: Get a certificate</span></span>

<span data-ttu-id="ef7b6-153">El script siguiente se puede usar para generar un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-153">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="ef7b6-154">Es posible que su organización no permita certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-154">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="ef7b6-155">En ese caso, use esta información para comprender los requisitos y adquirir un certificado de acuerdo con las directivas de su organización.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-155">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="ef7b6-156">Paso 2: Cargar el certificado en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="ef7b6-156">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="ef7b6-157">Abra la aplicación y vaya a la sección certificados y secretos desde el panel izquierdo</span><span class="sxs-lookup"><span data-stu-id="ef7b6-157">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="ef7b6-158">Seleccione "Cargar certificado" y cargue el archivo .cer</span><span class="sxs-lookup"><span data-stu-id="ef7b6-158">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="ef7b6-159">Abra **el registro de la** aplicación y seleccione Certificados y **secretos** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-159">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="ef7b6-160">Copie la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-160">Copy the certificate thumbprint.</span></span>

![Lista de certificados en miniatura cuando se seleccionan certificados y secretos en el panel izquierdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="ef7b6-162">Paso 3: Asignar el certificado al agente</span><span class="sxs-lookup"><span data-stu-id="ef7b6-162">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="ef7b6-163">Si usó el script de ejemplo para generar un certificado, el archivo PFX se puede encontrar en la ubicación identificada en el script.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-163">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="ef7b6-164">Descarga el archivo pfx del certificado en el equipo del agente.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-164">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="ef7b6-165">Haz doble clic en el archivo pfx para iniciar el cuadro de diálogo de instalación del certificado.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-165">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="ef7b6-166">Selecciona "Equipo local" para la ubicación del almacén mientras instalas el certificado.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-166">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="ef7b6-167">Después de instalar el certificado, abra "Administrar certificados de equipo" a través del menú Inicio</span><span class="sxs-lookup"><span data-stu-id="ef7b6-167">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="ef7b6-168">Seleccione el certificado recién instalado en "Personal" -> "Certificados"</span><span class="sxs-lookup"><span data-stu-id="ef7b6-168">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="ef7b6-169">Haga clic con el botón secundario en el certificado y seleccione "Todas las tareas" -> "Administrar claves privadas..."</span><span class="sxs-lookup"><span data-stu-id="ef7b6-169">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="ef7b6-170">Opción</span><span class="sxs-lookup"><span data-stu-id="ef7b6-170">Option</span></span>
1. <span data-ttu-id="ef7b6-171">En el cuadro de diálogo de permisos, seleccione la opción Agregar.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-171">In the permissions dialog, select add option.</span></span> <span data-ttu-id="ef7b6-172">En el cuadro de diálogo de selección de usuario, escriba: "Servicio NT\GcaHostService" y haga clic en "Aceptar".</span><span class="sxs-lookup"><span data-stu-id="ef7b6-172">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="ef7b6-173">No haga clic en el botón "Comprobar nombres".</span><span class="sxs-lookup"><span data-stu-id="ef7b6-173">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="ef7b6-174">Haga clic bien en el cuadro de diálogo de permisos.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-174">Click okay on the permissions dialog.</span></span> <span data-ttu-id="ef7b6-175">La máquina de agente ahora está configurada para que el agente genere tokens mediante el certificado.</span><span class="sxs-lookup"><span data-stu-id="ef7b6-175">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
