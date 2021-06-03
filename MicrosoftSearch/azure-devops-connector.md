---
title: Azure DevOps Graph para Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector Azure DevOps Graph para Microsoft Search
ms.openlocfilehash: bfe04a022360a968424b673ad03ba05f27c8c333
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720956"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="b97e3-103">Azure DevOps Graph (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b97e3-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="b97e3-104">El Azure DevOps Graph permite a la organización indizar elementos de trabajo en su instancia del servicio Azure DevOps trabajo.</span><span class="sxs-lookup"><span data-stu-id="b97e3-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="b97e3-105">Después de configurar el conector y el contenido de índice Azure DevOps, los usuarios finales pueden buscar esos elementos en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="b97e3-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="b97e3-106">Lea el [**artículo Setup for your Graph connector para**](configure-connector.md) comprender las instrucciones generales Graph de configuración de conectores.</span><span class="sxs-lookup"><span data-stu-id="b97e3-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="b97e3-107">Este artículo está para cualquier persona que configure, ejecute y monitore un Azure DevOps Graph conector.</span><span class="sxs-lookup"><span data-stu-id="b97e3-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="b97e3-108">Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al Azure DevOps Graph conector.</span><span class="sxs-lookup"><span data-stu-id="b97e3-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b97e3-109">El Azure DevOps solo admite el Azure DevOps en la nube.</span><span class="sxs-lookup"><span data-stu-id="b97e3-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="b97e3-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 y TFS 2013 no son compatibles con este conector.</span><span class="sxs-lookup"><span data-stu-id="b97e3-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b97e3-111">Paso 1: Agregar un conector de Graph en el centro Microsoft 365 administración</span><span class="sxs-lookup"><span data-stu-id="b97e3-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b97e3-112">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b97e3-112">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="b97e3-113">Paso 2: Nombrar la conexión</span><span class="sxs-lookup"><span data-stu-id="b97e3-113">Step 2: Name the connection</span></span>

<span data-ttu-id="b97e3-114">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b97e3-114">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="b97e3-115">Paso 3: Configurar las opciones de conexión</span><span class="sxs-lookup"><span data-stu-id="b97e3-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="b97e3-116">Para conectarse a la instancia Azure DevOps, necesita [](/azure/devops/organizations/accounts/create-organization) el nombre Azure DevOps organización, su identificador de aplicación y el secreto de cliente para la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="b97e3-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="b97e3-117">Registrar una aplicación</span><span class="sxs-lookup"><span data-stu-id="b97e3-117">Register an app</span></span>

<span data-ttu-id="b97e3-118">Registra una aplicación en Azure DevOps para que la aplicación de Búsqueda de Microsoft pueda tener acceso a la instancia.</span><span class="sxs-lookup"><span data-stu-id="b97e3-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="b97e3-119">Para obtener más información, consulta Azure DevOps documentación sobre cómo [registrar una aplicación](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).</span><span class="sxs-lookup"><span data-stu-id="b97e3-119">To learn more, see Azure DevOps documentation on how to [register an app](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="b97e3-120">En la siguiente tabla se proporcionan instrucciones sobre cómo rellenar el formulario de registro de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b97e3-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="b97e3-121">Campos obligatorios</span><span class="sxs-lookup"><span data-stu-id="b97e3-121">Mandatory Fields</span></span> | <span data-ttu-id="b97e3-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="b97e3-122">Description</span></span> | <span data-ttu-id="b97e3-123">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="b97e3-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="b97e3-124">Nombre de la compañía</span><span class="sxs-lookup"><span data-stu-id="b97e3-124">Company Name</span></span>         | <span data-ttu-id="b97e3-125">El nombre de su empresa.</span><span class="sxs-lookup"><span data-stu-id="b97e3-125">The name of your company.</span></span> | <span data-ttu-id="b97e3-126">Usar un valor adecuado</span><span class="sxs-lookup"><span data-stu-id="b97e3-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="b97e3-127">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b97e3-127">Application name</span></span>     | <span data-ttu-id="b97e3-128">Valor único que identifica la aplicación que está autorizando.</span><span class="sxs-lookup"><span data-stu-id="b97e3-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="b97e3-129">Búsqueda de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b97e3-129">Microsoft Search</span></span>     |
| <span data-ttu-id="b97e3-130">Sitio web de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b97e3-130">Application website</span></span>  | <span data-ttu-id="b97e3-131">La dirección URL de la aplicación que solicitará acceso a la instancia Azure DevOps durante la instalación del conector.</span><span class="sxs-lookup"><span data-stu-id="b97e3-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="b97e3-132">(Obligatorio).</span><span class="sxs-lookup"><span data-stu-id="b97e3-132">(Required).</span></span>  | <span data-ttu-id="b97e3-133"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="b97e3-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="b97e3-134">Url de devolución de llamada de autorización</span><span class="sxs-lookup"><span data-stu-id="b97e3-134">Authorization callback URL</span></span>        | <span data-ttu-id="b97e3-135">Dirección URL de devolución de llamada necesaria a la que redirige el servidor de autorización.</span><span class="sxs-lookup"><span data-stu-id="b97e3-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="b97e3-136"> https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="b97e3-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="b97e3-137">Ámbitos autorizados</span><span class="sxs-lookup"><span data-stu-id="b97e3-137">Authorized scopes</span></span> | <span data-ttu-id="b97e3-138">El ámbito de acceso de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b97e3-138">The scope of access for the application</span></span> | <span data-ttu-id="b97e3-139">Seleccione los siguientes ámbitos: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span><span class="sxs-lookup"><span data-stu-id="b97e3-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

>[!IMPORTANT]
><span data-ttu-id="b97e3-140">Los ámbitos autorizados que selecciones para la aplicación deben coincidir exactamente con los ámbitos indicados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b97e3-140">The authorized scopes that you select for the app should match the scopes exactly as listed above.</span></span> <span data-ttu-id="b97e3-141">Si omite uno de los ámbitos autorizados de la lista o agrega otro ámbito, se producirá un error en la autorización.</span><span class="sxs-lookup"><span data-stu-id="b97e3-141">If you omit one of the authorized scopes in the list, or add another scope, the authorization will fail.</span></span>

<span data-ttu-id="b97e3-142">Al registrar la aplicación con los detalles anteriores, tendrás  el identificador de la aplicación y el secreto de cliente que se usarán para configurar el conector. </span><span class="sxs-lookup"><span data-stu-id="b97e3-142">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="b97e3-143">Para revocar el acceso a cualquier aplicación registrada en Azure DevOps, ve a Configuración de usuario en la parte superior derecha de la Azure DevOps instancia.</span><span class="sxs-lookup"><span data-stu-id="b97e3-143">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="b97e3-144">Seleccione Perfil y, a continuación, seleccione Autorizaciones en la sección Seguridad del panel lateral.</span><span class="sxs-lookup"><span data-stu-id="b97e3-144">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="b97e3-145">Mantenga el mouse sobre una aplicación OAuth autorizada para ver el botón Revocar en la esquina de los detalles de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b97e3-145">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="b97e3-146">Configuración de conexión</span><span class="sxs-lookup"><span data-stu-id="b97e3-146">Connection settings</span></span>

<span data-ttu-id="b97e3-147">Después de registrar la aplicación de Microsoft Search con Azure DevOps, puedes completar el paso de configuración de conexión.</span><span class="sxs-lookup"><span data-stu-id="b97e3-147">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="b97e3-148">Escriba el nombre de la organización, el identificador de la aplicación y el secreto de cliente.</span><span class="sxs-lookup"><span data-stu-id="b97e3-148">Enter your organization name, App ID, and Client secret.</span></span>

![Aplicación de conexión Configuración](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="b97e3-150">Configurar datos: seleccionar proyectos y campos</span><span class="sxs-lookup"><span data-stu-id="b97e3-150">Configure data: select projects and fields</span></span>

<span data-ttu-id="b97e3-151">Puede elegir la conexión para indizar toda la organización o proyectos específicos.</span><span class="sxs-lookup"><span data-stu-id="b97e3-151">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="b97e3-152">Si elige indizar toda la organización, los elementos de todos los proyectos de la organización se indizarán.</span><span class="sxs-lookup"><span data-stu-id="b97e3-152">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="b97e3-153">Los nuevos proyectos y elementos se indizarán durante el siguiente rastreo después de su creación.</span><span class="sxs-lookup"><span data-stu-id="b97e3-153">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="b97e3-154">Si elige proyectos individuales, solo se indizarán los elementos de trabajo de esos proyectos.</span><span class="sxs-lookup"><span data-stu-id="b97e3-154">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Configurar datos](media/ADO_Configure_data.png)

<span data-ttu-id="b97e3-156">A continuación, seleccione los campos que desea que la conexión indexe y obtenga una vista previa de los datos de estos campos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b97e3-156">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Elegir propiedades](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="b97e3-158">Paso 4: Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="b97e3-158">Step 4: Manage search permissions</span></span>

<span data-ttu-id="b97e3-159">El Azure DevOps admite permisos de búsqueda visibles para solo personas con  **acceso a este origen de datos** o **todos**.</span><span class="sxs-lookup"><span data-stu-id="b97e3-159">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="b97e3-160">Si elige Solo personas con acceso a este origen de **datos,** los datos indizados aparecerán en los resultados de búsqueda para los usuarios que tengan acceso a ellos en función de los permisos para usuarios o grupos en el nivel de ruta de acceso de la organización, Project o Área en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="b97e3-160">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="b97e3-161">Si elige **Todos, los** datos indizados aparecerán en los resultados de la búsqueda para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b97e3-161">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="b97e3-162">Paso 5: Asignar etiquetas de propiedades</span><span class="sxs-lookup"><span data-stu-id="b97e3-162">Step 5: Assign property labels</span></span>

<span data-ttu-id="b97e3-163">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b97e3-163">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="b97e3-164">Paso 6: Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="b97e3-164">Step 6: Manage schema</span></span>

<span data-ttu-id="b97e3-165">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b97e3-165">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="b97e3-166">Paso 7: Elegir la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="b97e3-166">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="b97e3-167">El Azure DevOps admite programaciones de actualización para rastreos completos e incrementales.</span><span class="sxs-lookup"><span data-stu-id="b97e3-167">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="b97e3-168">La programación recomendada es de una hora para un rastreo incremental y un día para un rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="b97e3-168">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="b97e3-169">Paso 8: Revisar la conexión</span><span class="sxs-lookup"><span data-stu-id="b97e3-169">Step 8: Review connection</span></span>

<span data-ttu-id="b97e3-170">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b97e3-170">Follow the general [setup instructions](./configure-connector.md).</span></span>

>[!TIP]
><span data-ttu-id="b97e3-171">**Tipo de resultado predeterminado**</span><span class="sxs-lookup"><span data-stu-id="b97e3-171">**Default Result type**</span></span>
>* <span data-ttu-id="b97e3-172">El Azure DevOps registra automáticamente un tipo [de resultado](./customize-search-page.md#step-2-create-the-result-types) una vez que se publica el conector.</span><span class="sxs-lookup"><span data-stu-id="b97e3-172">The Azure DevOps connector automatically registers a [result type](./customize-search-page.md#step-2-create-the-result-types) once the connector is published.</span></span> <span data-ttu-id="b97e3-173">El tipo de resultado usa un diseño de resultados generado [dinámicamente](./customize-results-layout.md) en función de los campos seleccionados en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="b97e3-173">The result type uses a dynamically generated [result layout](./customize-results-layout.md) based on the fields selected in step 3.</span></span> 
>* <span data-ttu-id="b97e3-174">Para administrar el tipo de resultado, vaya a [**Tipos de resultados**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) en el [centro Microsoft 365 administración.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b97e3-174">You can manage the result type by navigating to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="b97e3-175">El tipo de resultado predeterminado se denominará `ConnectionId` "Predeterminado".</span><span class="sxs-lookup"><span data-stu-id="b97e3-175">The default result type will be named as "`ConnectionId`Default".</span></span> <span data-ttu-id="b97e3-176">Por ejemplo, si el identificador de conexión es , el diseño `AzureDevOps` de resultados se denominará: "AzureDevOpsDefault"</span><span class="sxs-lookup"><span data-stu-id="b97e3-176">For example, if your connection id is `AzureDevOps`, your result layout will be named: "AzureDevOpsDefault"</span></span>
>* <span data-ttu-id="b97e3-177">Además, puede elegir crear su propio tipo de resultado si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b97e3-177">Also, you can choose to create your own result type if needed.</span></span>

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->