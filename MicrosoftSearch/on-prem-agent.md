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
ms.openlocfilehash: 487c5b179e09fd99fa26ae7a237e89ca38b7be4d
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408946"
---
# <a name="on-prem-agent"></a><span data-ttu-id="940eb-103">Agente local</span><span class="sxs-lookup"><span data-stu-id="940eb-103">On-Prem Agent</span></span>

## <a name="graph-connector-agent"></a><span data-ttu-id="940eb-104">Agente de conector de Graph</span><span class="sxs-lookup"><span data-stu-id="940eb-104">Graph connector agent</span></span>

<span data-ttu-id="940eb-105">Los conectores de gráficos locales requieren la instalación del software del *agente de conector de Graph* .</span><span class="sxs-lookup"><span data-stu-id="940eb-105">On-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="940eb-106">Permite una transferencia de datos rápida y segura entre los datos locales y los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="940eb-106">It allows quick and secure data transfer between on-premises data and cloud services.</span></span> <span data-ttu-id="940eb-107">Este artículo le guiará por los pasos necesarios para instalar y configurar el software.</span><span class="sxs-lookup"><span data-stu-id="940eb-107">This article guides you through the steps of installing and configuring the software.</span></span> <span data-ttu-id="940eb-108">Una vez configurada, estará disponible para crear conexiones a los orígenes de datos locales desde el [centro de administración de Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="940eb-108">Once configured, it will be available for creating connections to your on-prem data sources from the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

## <a name="installation"></a><span data-ttu-id="940eb-109">Instalación</span><span class="sxs-lookup"><span data-stu-id="940eb-109">Installation</span></span>

<span data-ttu-id="940eb-110">Descargue la versión más reciente del agente de conector de Graph con [este vínculo](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) e instale el software mediante el Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="940eb-110">Download the latest version of Graph connector agent using [this link](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) and install the software using the installation wizard.</span></span> <span data-ttu-id="940eb-111">Con la configuración recomendada del equipo que se describe a continuación, el software puede controlar fácilmente hasta tres conexiones.</span><span class="sxs-lookup"><span data-stu-id="940eb-111">With the recommended configuration of the machine described below, the software can seamlessly handle up to three connections.</span></span> <span data-ttu-id="940eb-112">Cualquier conexión posterior podría degradar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="940eb-112">Any connections beyond that might degrade the performance.</span></span>

<span data-ttu-id="940eb-113">Configuración recomendada:</span><span class="sxs-lookup"><span data-stu-id="940eb-113">Recommended configuration:</span></span>

* <span data-ttu-id="940eb-114">Windows 10, Windows Server 2012 R2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="940eb-114">Windows 10, Windows Server 2012 R2 and above</span></span>
* <span data-ttu-id="940eb-115">8 núcleos, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="940eb-115">8 cores, 3GHz</span></span>
* <span data-ttu-id="940eb-116">16 GB de RAM, 1 GB de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="940eb-116">16GB RAM, 1GB Disk Space</span></span>
* <span data-ttu-id="940eb-117">Acceso de red a origen de datos e Internet mediante 443</span><span class="sxs-lookup"><span data-stu-id="940eb-117">Network access to data source and internet through 443</span></span>

## <a name="creating-app-for-the-agent"></a><span data-ttu-id="940eb-118">Creación de la aplicación para el agente</span><span class="sxs-lookup"><span data-stu-id="940eb-118">Creating App for the agent</span></span>  

<span data-ttu-id="940eb-119">La instancia del agente debe alimentarse con algunos parámetros críticos antes de crear conexiones.</span><span class="sxs-lookup"><span data-stu-id="940eb-119">The agent instance needs to be fed few critical parameters before you create connections.</span></span> <span data-ttu-id="940eb-120">Estos parámetros incluyen los detalles de autenticación necesarios para usar las API de recopilación de gráficos.</span><span class="sxs-lookup"><span data-stu-id="940eb-120">These parameters include authentication details required for using Graph ingestion APIs.</span></span>  

<span data-ttu-id="940eb-121">Pasos para crear aplicaciones para el agente.</span><span class="sxs-lookup"><span data-stu-id="940eb-121">Steps for creating App for the agent.</span></span>

1. <span data-ttu-id="940eb-122">Vaya a [Azure portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="940eb-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="940eb-123">Navegue a **Azure Active Directory**  ->  **registros de aplicaciones** de Azure Active Directory desde el panel de navegación y seleccione **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="940eb-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="940eb-124">Especifique un nombre para la aplicación y seleccione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="940eb-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="940eb-125">Anote el identificador de la aplicación (cliente).</span><span class="sxs-lookup"><span data-stu-id="940eb-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="940eb-126">Abra **permisos de API** en el panel de navegación y seleccione **Agregar un permiso**.</span><span class="sxs-lookup"><span data-stu-id="940eb-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="940eb-127">Seleccione **Microsoft Graph** y, a continuación, permisos de la **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="940eb-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="940eb-128">Busque "ExternalItem. ReadWrite. All" y "Directory. Read. All" desde los permisos y seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="940eb-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="940eb-129">Seleccione **conceder consentimiento de administrador para [TenantName]** y confirme seleccionando **sí**.</span><span class="sxs-lookup"><span data-stu-id="940eb-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="940eb-130">Compruebe que los permisos se encuentran en el estado concedido.</span><span class="sxs-lookup"><span data-stu-id="940eb-130">Check that the permissions are in the granted state.</span></span>
     <span data-ttu-id="940eb-131">![Permisos que se muestran como concedidos en verde en la columna derecha.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="940eb-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

## <a name="configuring-graph-connector-agent"></a><span data-ttu-id="940eb-132">Configuración del agente de conector de Graph</span><span class="sxs-lookup"><span data-stu-id="940eb-132">Configuring Graph connector agent</span></span>

<span data-ttu-id="940eb-133">Una vez que haya creado la aplicación para el agente, debe configurar el agente con los detalles de autenticación adecuados.</span><span class="sxs-lookup"><span data-stu-id="940eb-133">Once you have created the App for the agent, you must configure the agent with appropriate authentication details.</span></span>

<span data-ttu-id="940eb-134">Los detalles de autenticación se pueden proporcionar en una de las siguientes formas.</span><span class="sxs-lookup"><span data-stu-id="940eb-134">Authentication details can be provided in one of the following forms.</span></span>

### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="940eb-135">Configuración del secreto de cliente para la autenticación</span><span class="sxs-lookup"><span data-stu-id="940eb-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="940eb-136">Vaya a [Azure portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="940eb-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="940eb-137">Abra el **registro de aplicaciones** en el panel de navegación y vaya a la aplicación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="940eb-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="940eb-138">En **administrar**, seleccione **certificados y secretos**.</span><span class="sxs-lookup"><span data-stu-id="940eb-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="940eb-139">Seleccione **nuevo secreto de cliente** y seleccione un período de expiración para el secreto.</span><span class="sxs-lookup"><span data-stu-id="940eb-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="940eb-140">Copie el secreto generado y guárdelo porque no se volverá a mostrar.</span><span class="sxs-lookup"><span data-stu-id="940eb-140">Copy the generated secret and save it because it will not be shown again.</span></span>
4. <span data-ttu-id="940eb-141">Use este secreto de cliente junto con el identificador de aplicación para configurar el agente.</span><span class="sxs-lookup"><span data-stu-id="940eb-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="940eb-142">No use espacios en blanco en el campo **nombre** del agente.</span><span class="sxs-lookup"><span data-stu-id="940eb-142">Do not use any blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="940eb-143">Se aceptan los caracteres alfanuméricos alfanuméricos.</span><span class="sxs-lookup"><span data-stu-id="940eb-143">Alpha numeric characters are accepted.</span></span>

## <a name="using-thumbprint-certificate-for-authentication"></a><span data-ttu-id="940eb-144">Uso del certificado de huella digital para la autenticación</span><span class="sxs-lookup"><span data-stu-id="940eb-144">Using thumbprint certificate for authentication</span></span>

<span data-ttu-id="940eb-145">Si ya ha configurado los detalles de autenticación mediante [la configuración del secreto de cliente para la autenticación](#configuring-the-client-secret-for-authentication) , puede ir directamente a la introducción a la [instalación](configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="940eb-145">If you have already configured the authentication details by following [Configuring the client secret for authentication](#configuring-the-client-secret-for-authentication) , then you can jump directly to [Setup overview](configure-connector.md).</span></span>

1. <span data-ttu-id="940eb-146">Abra el **registro de aplicaciones** y seleccione **certificados y secretos** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="940eb-146">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="940eb-147">Copie la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="940eb-147">Copy the certificate thumbprint.</span></span>
<span data-ttu-id="940eb-148">![Lista de certificados de thumbrint cuando se selecciona certificados y secretos en el panel izquierdo](media/onprem-agent/certificates.png)</span><span class="sxs-lookup"><span data-stu-id="940eb-148">![List of thumbrint certificates when Certificates and secrets is selected in the left pane](media/onprem-agent/certificates.png)</span></span>
2. <span data-ttu-id="940eb-149">Use el secreto de cliente o la huella digital para registrar el agente de conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="940eb-149">Use either the client secret or thumbprint to register the Graph connector agent.</span></span>
<span data-ttu-id="940eb-150">![Registro del formulario donde se pide el nombre, el identificador de la aplicación, el tipo de credencial y el certificado](media/onprem-agent/register.png)</span><span class="sxs-lookup"><span data-stu-id="940eb-150">![Register form asking for name, app id, credential type, and certificate](media/onprem-agent/register.png)</span></span>
