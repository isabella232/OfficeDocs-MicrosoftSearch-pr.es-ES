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
ms.openlocfilehash: bd5212d42fe21583aa6a4e0dc8060d5e191a7292
ms.sourcegitcommit: 35b4246cb3e38c6fe21540686e28fe54154b33f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2021
ms.locfileid: "50259433"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="41332-103">Agente de conector de Graph</span><span class="sxs-lookup"><span data-stu-id="41332-103">Graph connector agent</span></span>

<span data-ttu-id="41332-104">El uso de conectores de Graph locales requiere instalar el software *del agente de conector de Graph.*</span><span class="sxs-lookup"><span data-stu-id="41332-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="41332-105">Permite la transferencia segura de datos entre los datos locales y las API del conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="41332-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="41332-106">Este artículo le guiará a través de la instalación y configuración del agente.</span><span class="sxs-lookup"><span data-stu-id="41332-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="41332-107">Instalación</span><span class="sxs-lookup"><span data-stu-id="41332-107">Installation</span></span>

<span data-ttu-id="41332-108">Descargue aquí la versión más reciente del agente del conector de Graph [e](https://aka.ms/gcadownload) instale el software con el asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="41332-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="41332-109">Con la configuración recomendada de la máquina que se describe a continuación, el software puede controlar hasta tres conexiones.</span><span class="sxs-lookup"><span data-stu-id="41332-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="41332-110">Las conexiones posteriores pueden degradar el rendimiento de todas las conexiones en el agente.</span><span class="sxs-lookup"><span data-stu-id="41332-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="41332-111">Configuración recomendada:</span><span class="sxs-lookup"><span data-stu-id="41332-111">Recommended configuration:</span></span>

* <span data-ttu-id="41332-112">Windows 10, Windows Server 2016 R2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="41332-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="41332-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="41332-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="41332-114">8 núcleos, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="41332-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="41332-115">16 GB de RAM, 2 GB de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="41332-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="41332-116">Acceso de red al origen de datos e Internet a través del 443</span><span class="sxs-lookup"><span data-stu-id="41332-116">Network access to data source and internet through 443</span></span>

<span data-ttu-id="41332-117">Después de instalar el agente, si los servidores proxy o firewalls de su organización bloquean la comunicación con dominios desconocidos, agregue los siguientes a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="41332-117">After you install the agent, if your organization's proxy servers or firewalls block communication to unknown domains, please add below ones to the allow list.</span></span>

1. <span data-ttu-id="41332-118">\*.servicebus.windows.net</span><span class="sxs-lookup"><span data-stu-id="41332-118">\*.servicebus.windows.net</span></span>
2. <span data-ttu-id="41332-119">\*.events.data.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="41332-119">\*.events.data.microsoft.com</span></span>
3. <span data-ttu-id="41332-120"> https://<span>login.microsoftonline.</span>com</span><span class="sxs-lookup"><span data-stu-id="41332-120">https://<span>login.microsoftonline.</span>com</span></span>
4. <span data-ttu-id="41332-121"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="41332-121">https://<span>gcs.office.</span>com/</span></span>
5. <span data-ttu-id="41332-122"> https://<span>graph.microsoft.</span> com/</span><span class="sxs-lookup"><span data-stu-id="41332-122">https://<span>graph.microsoft.</span>com/</span></span>


## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="41332-123">Crear y configurar una aplicación para el agente</span><span class="sxs-lookup"><span data-stu-id="41332-123">Create and configure an App for the agent</span></span>  

<span data-ttu-id="41332-124">En primer lugar, inicie sesión y tenga en cuenta que el privilegio mínimo requerido en la cuenta es el administrador de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="41332-124">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="41332-125">A continuación, el agente le pedirá que proporcione detalles de autenticación.</span><span class="sxs-lookup"><span data-stu-id="41332-125">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="41332-126">Siga los pasos siguientes para crear una aplicación y generar los detalles de autenticación necesarios.</span><span class="sxs-lookup"><span data-stu-id="41332-126">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="41332-127">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="41332-127">Create an app</span></span>

1. <span data-ttu-id="41332-128">Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con las credenciales de administrador del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="41332-128">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="41332-129">Vaya a **Registros de aplicaciones de Azure Active Directory** desde el panel de navegación y seleccione Nuevo  ->   **registro.**</span><span class="sxs-lookup"><span data-stu-id="41332-129">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="41332-130">Proporcione un nombre para la aplicación y seleccione **Registrar.**</span><span class="sxs-lookup"><span data-stu-id="41332-130">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="41332-131">Anote el id. de aplicación (cliente).</span><span class="sxs-lookup"><span data-stu-id="41332-131">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="41332-132">Abra **los permisos de** api en el panel de navegación y seleccione Agregar un **permiso.**</span><span class="sxs-lookup"><span data-stu-id="41332-132">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="41332-133">Seleccione **Microsoft Graph y,** a continuación, **permisos de aplicación.**</span><span class="sxs-lookup"><span data-stu-id="41332-133">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="41332-134">Busque "ExternalItem.ReadWrite.All" y "Directory.Read.All" en los permisos y seleccione **Agregar permisos.**</span><span class="sxs-lookup"><span data-stu-id="41332-134">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="41332-135">Seleccione **Conceder consentimiento de administrador para [TenantName]** y confirme **seleccionando Sí**.</span><span class="sxs-lookup"><span data-stu-id="41332-135">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="41332-136">Compruebe que los permisos están en el estado "concedido".</span><span class="sxs-lookup"><span data-stu-id="41332-136">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="41332-137">![Permisos que se muestran en verde en la columna de la derecha.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="41332-137">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="41332-138">Configurar la autenticación</span><span class="sxs-lookup"><span data-stu-id="41332-138">Configure Authentication</span></span>

<span data-ttu-id="41332-139">Los detalles de autenticación se pueden proporcionar mediante un secreto de cliente o un certificado.</span><span class="sxs-lookup"><span data-stu-id="41332-139">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="41332-140">Siga los pasos que desee.</span><span class="sxs-lookup"><span data-stu-id="41332-140">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="41332-141">Configuración del secreto de cliente para la autenticación</span><span class="sxs-lookup"><span data-stu-id="41332-141">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="41332-142">Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="41332-142">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="41332-143">Abra **Registro de aplicaciones** desde el panel de navegación y vaya a la aplicación adecuada.</span><span class="sxs-lookup"><span data-stu-id="41332-143">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="41332-144">En **Administrar,** seleccione **Certificados y secretos.**</span><span class="sxs-lookup"><span data-stu-id="41332-144">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="41332-145">Seleccione **nuevo secreto de cliente** y seleccione un período de expiración para el secreto.</span><span class="sxs-lookup"><span data-stu-id="41332-145">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="41332-146">Copie el secreto generado y guárdelo porque no se volverá a mostrar.</span><span class="sxs-lookup"><span data-stu-id="41332-146">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="41332-147">Use este secreto de cliente junto con el id. de aplicación para configurar el agente.</span><span class="sxs-lookup"><span data-stu-id="41332-147">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="41332-148">No puede usar espacios en blanco en el **campo Nombre** del agente.</span><span class="sxs-lookup"><span data-stu-id="41332-148">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="41332-149">Se aceptan caracteres numéricos alfa.</span><span class="sxs-lookup"><span data-stu-id="41332-149">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="41332-150">Uso de un certificado para la autenticación</span><span class="sxs-lookup"><span data-stu-id="41332-150">Using a certificate for authentication</span></span>

<span data-ttu-id="41332-151">Hay tres pasos sencillos para usar la autenticación basada en certificados:</span><span class="sxs-lookup"><span data-stu-id="41332-151">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="41332-152">Crear u obtener un certificado</span><span class="sxs-lookup"><span data-stu-id="41332-152">Create or obtain a certificate</span></span>
1. <span data-ttu-id="41332-153">Cargar el certificado en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="41332-153">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="41332-154">Asignar el certificado al agente</span><span class="sxs-lookup"><span data-stu-id="41332-154">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="41332-155">Paso 1: Obtener un certificado</span><span class="sxs-lookup"><span data-stu-id="41332-155">Step 1: Get a certificate</span></span>

<span data-ttu-id="41332-156">El script siguiente se puede usar para generar un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="41332-156">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="41332-157">Es posible que su organización no permita certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="41332-157">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="41332-158">En ese caso, use esta información para comprender los requisitos y adquirir un certificado de acuerdo con las directivas de su organización.</span><span class="sxs-lookup"><span data-stu-id="41332-158">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="41332-159">Paso 2: Cargar el certificado en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="41332-159">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="41332-160">Abra la aplicación y vaya a la sección certificados y secretos desde el panel izquierdo</span><span class="sxs-lookup"><span data-stu-id="41332-160">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="41332-161">Seleccione "Cargar certificado" y cargue el archivo .cer</span><span class="sxs-lookup"><span data-stu-id="41332-161">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="41332-162">Abra **el registro de la** aplicación y seleccione Certificados y **secretos** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="41332-162">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="41332-163">Copie la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="41332-163">Copy the certificate thumbprint.</span></span>

![Lista de certificados en miniatura cuando se seleccionan certificados y secretos en el panel izquierdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="41332-165">Paso 3: Asignar el certificado al agente</span><span class="sxs-lookup"><span data-stu-id="41332-165">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="41332-166">Si usó el script de ejemplo para generar un certificado, el archivo PFX se puede encontrar en la ubicación identificada en el script.</span><span class="sxs-lookup"><span data-stu-id="41332-166">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="41332-167">Descarga el archivo pfx del certificado en el equipo del agente.</span><span class="sxs-lookup"><span data-stu-id="41332-167">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="41332-168">Haz doble clic en el archivo pfx para iniciar el cuadro de diálogo de instalación del certificado.</span><span class="sxs-lookup"><span data-stu-id="41332-168">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="41332-169">Selecciona "Equipo local" para la ubicación del almacén mientras instalas el certificado.</span><span class="sxs-lookup"><span data-stu-id="41332-169">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="41332-170">Después de instalar el certificado, abra "Administrar certificados de equipo" a través del menú Inicio</span><span class="sxs-lookup"><span data-stu-id="41332-170">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="41332-171">Seleccione el certificado recién instalado en "Personal" -> "Certificados"</span><span class="sxs-lookup"><span data-stu-id="41332-171">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="41332-172">Haga clic con el botón secundario en el certificado y seleccione "Todas las tareas" -> "Administrar claves privadas..."</span><span class="sxs-lookup"><span data-stu-id="41332-172">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="41332-173">Opción</span><span class="sxs-lookup"><span data-stu-id="41332-173">Option</span></span>
1. <span data-ttu-id="41332-174">En el cuadro de diálogo de permisos, seleccione la opción Agregar.</span><span class="sxs-lookup"><span data-stu-id="41332-174">In the permissions dialog, select add option.</span></span> <span data-ttu-id="41332-175">En el cuadro de diálogo de selección de usuario, escriba: "Servicio NT\GcaHostService" y haga clic en "Aceptar".</span><span class="sxs-lookup"><span data-stu-id="41332-175">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="41332-176">No haga clic en el botón "Comprobar nombres".</span><span class="sxs-lookup"><span data-stu-id="41332-176">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="41332-177">Haga clic bien en el cuadro de diálogo de permisos.</span><span class="sxs-lookup"><span data-stu-id="41332-177">Click okay on the permissions dialog.</span></span> <span data-ttu-id="41332-178">La máquina de agente ahora está configurada para que el agente genere tokens mediante el certificado.</span><span class="sxs-lookup"><span data-stu-id="41332-178">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="41332-179">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="41332-179">Troubleshooting</span></span>
1. <span data-ttu-id="41332-180">Si se produce un error en una conexión con el error "1011: el agente del conector de Graph no es accesible ni está sin conexión", inicie sesión en el equipo donde está instalado el agente e inicie la aplicación de agente si aún no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="41332-180">If a connection fails with the error '1011: The Graph connector agent is not reachable or offline.', log in to the machine where agent is installed and start the agent application if it isn't running already.</span></span> <span data-ttu-id="41332-181">Si la conexión continúa fallando, compruebe que el certificado o secreto de cliente proporcionado al agente durante el registro no ha expirado y tiene los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="41332-181">If the connection continues to fail, verify that the certificate or client secret provided to the agent during registration hasn't expired and has required permissions.</span></span>
