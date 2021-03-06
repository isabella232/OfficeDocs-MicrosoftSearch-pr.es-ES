---
title: Agente local
ms.author: rusamai
author: rsamai
manager: jameslau
audience: Admin
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
ms.openlocfilehash: 5134c0c4459f9d38825451f274e67469956756d2
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508809"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="a94f5-103">Agente de conector de Graph</span><span class="sxs-lookup"><span data-stu-id="a94f5-103">Graph connector agent</span></span>

<span data-ttu-id="a94f5-104">El uso de conectores de Graph locales requiere instalar software de *agente de conector de Graph.*</span><span class="sxs-lookup"><span data-stu-id="a94f5-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="a94f5-105">Permite la transferencia de datos segura entre los datos locales y las API del conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="a94f5-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="a94f5-106">Este artículo le guía a través de la instalación y configuración del agente.</span><span class="sxs-lookup"><span data-stu-id="a94f5-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="a94f5-107">Instalación</span><span class="sxs-lookup"><span data-stu-id="a94f5-107">Installation</span></span>

<span data-ttu-id="a94f5-108">Descargue la versión más reciente del agente de conector de Graph [aquí](https://aka.ms/gcadownload) e instale el software con el asistente de instalación.</span><span class="sxs-lookup"><span data-stu-id="a94f5-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="a94f5-109">Con la configuración recomendada de la máquina que se describe a continuación, el software puede controlar hasta tres conexiones.</span><span class="sxs-lookup"><span data-stu-id="a94f5-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="a94f5-110">Las conexiones posteriores podrían degradar el rendimiento de todas las conexiones del agente.</span><span class="sxs-lookup"><span data-stu-id="a94f5-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="a94f5-111">Configuración recomendada:</span><span class="sxs-lookup"><span data-stu-id="a94f5-111">Recommended configuration:</span></span>

* <span data-ttu-id="a94f5-112">Windows 10, Windows Server 2016 R2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="a94f5-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="a94f5-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="a94f5-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="a94f5-114">8 núcleos, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="a94f5-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="a94f5-115">16 GB de RAM, 2 GB de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="a94f5-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="a94f5-116">Acceso de red al origen de datos e Internet a través de 443</span><span class="sxs-lookup"><span data-stu-id="a94f5-116">Network access to data source and internet through 443</span></span>

<span data-ttu-id="a94f5-117">Después de instalar el agente, si los servidores proxy o firewalls de la organización bloquean la comunicación con dominios desconocidos, agregue los siguientes a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="a94f5-117">After you install the agent, if your organization's proxy servers or firewalls block communication to unknown domains, please add below ones to the allow list.</span></span>

1. <span data-ttu-id="a94f5-118">\*.servicebus.windows.net</span><span class="sxs-lookup"><span data-stu-id="a94f5-118">\*.servicebus.windows.net</span></span>
2. <span data-ttu-id="a94f5-119">\*.events.data.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a94f5-119">\*.events.data.microsoft.com</span></span>
3. <span data-ttu-id="a94f5-120"> https://<span>login.microsoftonline.</span>com</span><span class="sxs-lookup"><span data-stu-id="a94f5-120">https://<span>login.microsoftonline.</span>com</span></span>
4. <span data-ttu-id="a94f5-121"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="a94f5-121">https://<span>gcs.office.</span>com/</span></span>
5. <span data-ttu-id="a94f5-122"> https://<span>graph.microsoft.</span> com/</span><span class="sxs-lookup"><span data-stu-id="a94f5-122">https://<span>graph.microsoft.</span>com/</span></span>


## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="a94f5-123">Crear y configurar una aplicación para el agente</span><span class="sxs-lookup"><span data-stu-id="a94f5-123">Create and configure an App for the agent</span></span>  

<span data-ttu-id="a94f5-124">En primer lugar, inicie sesión y tenga en cuenta que el privilegio mínimo requerido en la cuenta es el administrador de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a94f5-124">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="a94f5-125">A continuación, el agente le pedirá que proporcione detalles de autenticación.</span><span class="sxs-lookup"><span data-stu-id="a94f5-125">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="a94f5-126">Sigue los pasos siguientes para crear una aplicación y generar los detalles de autenticación necesarios.</span><span class="sxs-lookup"><span data-stu-id="a94f5-126">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="a94f5-127">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="a94f5-127">Create an app</span></span>

1. <span data-ttu-id="a94f5-128">Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="a94f5-128">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="a94f5-129">Vaya a **Registros de aplicaciones de Azure Active Directory** desde el panel de navegación y seleccione Nuevo  ->   **registro**.</span><span class="sxs-lookup"><span data-stu-id="a94f5-129">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="a94f5-130">Proporcione un nombre para la aplicación y seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="a94f5-130">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="a94f5-131">Anote el identificador de aplicación (cliente).</span><span class="sxs-lookup"><span data-stu-id="a94f5-131">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="a94f5-132">Abra **los permisos de** api desde el panel de navegación y seleccione Agregar un **permiso**.</span><span class="sxs-lookup"><span data-stu-id="a94f5-132">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="a94f5-133">Seleccione **Microsoft Graph** y, a continuación, Permisos de **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="a94f5-133">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="a94f5-134">Busque "ExternalItem.ReadWrite.All" y "Directory.Read.All" en los permisos y seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="a94f5-134">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="a94f5-135">Seleccione **Conceder consentimiento de administrador para [TenantName]** y confirme **seleccionando Sí**.</span><span class="sxs-lookup"><span data-stu-id="a94f5-135">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="a94f5-136">Compruebe que los permisos están en el estado "concedido".</span><span class="sxs-lookup"><span data-stu-id="a94f5-136">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="a94f5-137">![Permisos que se muestran como concedidos en verde en la columna de la derecha.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="a94f5-137">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="a94f5-138">Configurar la autenticación</span><span class="sxs-lookup"><span data-stu-id="a94f5-138">Configure Authentication</span></span>

<span data-ttu-id="a94f5-139">Los detalles de autenticación se pueden proporcionar mediante un secreto de cliente o un certificado.</span><span class="sxs-lookup"><span data-stu-id="a94f5-139">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="a94f5-140">Sigue los pasos que prefieras.</span><span class="sxs-lookup"><span data-stu-id="a94f5-140">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="a94f5-141">Configuración del secreto de cliente para la autenticación</span><span class="sxs-lookup"><span data-stu-id="a94f5-141">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="a94f5-142">Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="a94f5-142">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="a94f5-143">Abre **Registro de aplicaciones** desde el panel de navegación y ve a la aplicación adecuada.</span><span class="sxs-lookup"><span data-stu-id="a94f5-143">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="a94f5-144">En **Administrar**, seleccione **Certificados y secretos**.</span><span class="sxs-lookup"><span data-stu-id="a94f5-144">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="a94f5-145">Seleccione **Nuevo secreto de cliente** y seleccione un período de expiración para el secreto.</span><span class="sxs-lookup"><span data-stu-id="a94f5-145">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="a94f5-146">Copie el secreto generado y guárdelo porque no se volverá a mostrar.</span><span class="sxs-lookup"><span data-stu-id="a94f5-146">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="a94f5-147">Use este secreto de cliente junto con el identificador de aplicación para configurar el agente.</span><span class="sxs-lookup"><span data-stu-id="a94f5-147">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="a94f5-148">No puede usar espacios en blanco en el **campo Nombre** del agente.</span><span class="sxs-lookup"><span data-stu-id="a94f5-148">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="a94f5-149">Se aceptan caracteres numéricos alfa.</span><span class="sxs-lookup"><span data-stu-id="a94f5-149">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="a94f5-150">Uso de un certificado para la autenticación</span><span class="sxs-lookup"><span data-stu-id="a94f5-150">Using a certificate for authentication</span></span>

<span data-ttu-id="a94f5-151">Hay tres pasos sencillos para usar la autenticación basada en certificados:</span><span class="sxs-lookup"><span data-stu-id="a94f5-151">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="a94f5-152">Crear u obtener un certificado</span><span class="sxs-lookup"><span data-stu-id="a94f5-152">Create or obtain a certificate</span></span>
1. <span data-ttu-id="a94f5-153">Cargar el certificado en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="a94f5-153">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="a94f5-154">Asignar el certificado al agente</span><span class="sxs-lookup"><span data-stu-id="a94f5-154">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="a94f5-155">Paso 1: Obtener un certificado</span><span class="sxs-lookup"><span data-stu-id="a94f5-155">Step 1: Get a certificate</span></span>

<span data-ttu-id="a94f5-156">El siguiente script se puede usar para generar un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="a94f5-156">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="a94f5-157">Es posible que su organización no permita certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="a94f5-157">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="a94f5-158">En ese caso, use esta información para comprender los requisitos y adquirir un certificado de acuerdo con las directivas de su organización.</span><span class="sxs-lookup"><span data-stu-id="a94f5-158">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="a94f5-159">Paso 2: Cargar el certificado en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="a94f5-159">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="a94f5-160">Abra la aplicación y vaya a la sección certificados y secretos desde el panel izquierdo</span><span class="sxs-lookup"><span data-stu-id="a94f5-160">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="a94f5-161">Seleccione "Cargar certificado" y cargue el archivo .cer</span><span class="sxs-lookup"><span data-stu-id="a94f5-161">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="a94f5-162">Abra **Registro de aplicaciones** y seleccione Certificados y **secretos** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="a94f5-162">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="a94f5-163">Copie la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="a94f5-163">Copy the certificate thumbprint.</span></span>

![Lista de certificados thumbrint cuando se seleccionan certificados y secretos en el panel izquierdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="a94f5-165">Paso 3: Asignar el certificado al agente</span><span class="sxs-lookup"><span data-stu-id="a94f5-165">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="a94f5-166">Si usó el script de ejemplo para generar un certificado, el archivo PFX se puede encontrar en la ubicación identificada en el script.</span><span class="sxs-lookup"><span data-stu-id="a94f5-166">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="a94f5-167">Descargue el archivo pfx del certificado en el equipo agente.</span><span class="sxs-lookup"><span data-stu-id="a94f5-167">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="a94f5-168">Haga doble clic en el archivo pfx para iniciar el cuadro de diálogo de instalación del certificado.</span><span class="sxs-lookup"><span data-stu-id="a94f5-168">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="a94f5-169">Seleccione "Máquina local" para la ubicación del almacén al instalar el certificado.</span><span class="sxs-lookup"><span data-stu-id="a94f5-169">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="a94f5-170">Después de instalar el certificado, abra "Administrar certificados de equipo" a través del menú Inicio</span><span class="sxs-lookup"><span data-stu-id="a94f5-170">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="a94f5-171">Seleccione el certificado recién instalado en 'Personal' -> 'Certificados'</span><span class="sxs-lookup"><span data-stu-id="a94f5-171">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="a94f5-172">Haga clic con el botón secundario en el certificado y seleccione "Todas las tareas" -> 'Administrar claves privadas...'</span><span class="sxs-lookup"><span data-stu-id="a94f5-172">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="a94f5-173">Opción</span><span class="sxs-lookup"><span data-stu-id="a94f5-173">Option</span></span>
1. <span data-ttu-id="a94f5-174">En el cuadro de diálogo permisos, seleccione agregar opción.</span><span class="sxs-lookup"><span data-stu-id="a94f5-174">In the permissions dialog, select add option.</span></span> <span data-ttu-id="a94f5-175">En el cuadro de diálogo de selección de usuario, escriba: 'NT Service\GcaHostService' y haga clic en 'Aceptar'.</span><span class="sxs-lookup"><span data-stu-id="a94f5-175">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="a94f5-176">No haga clic en el botón "Comprobar nombres".</span><span class="sxs-lookup"><span data-stu-id="a94f5-176">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="a94f5-177">Haga clic en Aceptar en el cuadro de diálogo permisos.</span><span class="sxs-lookup"><span data-stu-id="a94f5-177">Click okay on the permissions dialog.</span></span> <span data-ttu-id="a94f5-178">La máquina del agente ahora está configurada para que el agente genere tokens con el certificado.</span><span class="sxs-lookup"><span data-stu-id="a94f5-178">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a94f5-179">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="a94f5-179">Troubleshooting</span></span>
1. <span data-ttu-id="a94f5-180">Si se produce un error en una conexión con el error '1011: el agente del conector de Graph no es accesible ni sin conexión', inicie sesión en el equipo donde está instalado el agente e inicie la aplicación de agente si aún no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="a94f5-180">If a connection fails with the error '1011: The Graph connector agent is not reachable or offline.', log in to the machine where agent is installed and start the agent application if it isn't running already.</span></span> <span data-ttu-id="a94f5-181">Si la conexión sigue fallando, compruebe que el certificado o secreto de cliente proporcionado al agente durante el registro no ha expirado y tiene permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="a94f5-181">If the connection continues to fail, verify that the certificate or client secret provided to the agent during registration hasn't expired and has required permissions.</span></span>
