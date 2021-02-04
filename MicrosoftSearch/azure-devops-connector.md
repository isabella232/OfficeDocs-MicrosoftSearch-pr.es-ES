---
title: Conector de Azure DevOps Graph para Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de Azure DevOps Graph para Microsoft Search
ms.openlocfilehash: 8fe783c847c672223e051f4433af3e41678fe367
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097407"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="62053-103">Conector de Azure DevOps Graph (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="62053-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="62053-104">El conector de Azure DevOps Graph permite a su organización indizar elementos de trabajo en su instancia del servicio Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="62053-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="62053-105">Después de configurar el conector y el contenido de índice de Azure DevOps, los usuarios finales pueden buscar esos elementos en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="62053-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="62053-106">Lea el [**artículo sobre el programa de instalación del conector de Graph**](configure-connector.md) para comprender el proceso de configuración general de los conectores de Graph.</span><span class="sxs-lookup"><span data-stu-id="62053-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="62053-107">Este artículo está dirigido a cualquier persona que configure, ejecute y monitore un conector de Azure DevOps Graph.</span><span class="sxs-lookup"><span data-stu-id="62053-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="62053-108">Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de Azure DevOps Graph.</span><span class="sxs-lookup"><span data-stu-id="62053-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="62053-109">El conector de Azure DevOps solo admite el servicio en la nube de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="62053-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="62053-110">Este conector no admite Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 y TFS 2013.</span><span class="sxs-lookup"><span data-stu-id="62053-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="62053-111">Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62053-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="62053-112">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="62053-112">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="62053-113">Paso 2: Nombrar la conexión</span><span class="sxs-lookup"><span data-stu-id="62053-113">Step 2: Name the connection</span></span>

<span data-ttu-id="62053-114">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="62053-114">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="62053-115">Paso 3: Configurar las opciones de conexión</span><span class="sxs-lookup"><span data-stu-id="62053-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="62053-116">Para conectarse a la instancia de Azure [DevOps,](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) necesita el nombre de la organización de Azure DevOps, su id. de aplicación y el secreto de cliente para la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="62053-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="62053-117">Registrar una aplicación</span><span class="sxs-lookup"><span data-stu-id="62053-117">Register an app</span></span>

<span data-ttu-id="62053-118">Registra una aplicación en Azure DevOps para que la aplicación búsqueda de Microsoft pueda acceder a la instancia.</span><span class="sxs-lookup"><span data-stu-id="62053-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="62053-119">Para obtener más información, consulte la documentación de Azure DevOps sobre cómo [registrar una aplicación.](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="62053-119">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true).</span></span>

<span data-ttu-id="62053-120">En la tabla siguiente se proporcionan instrucciones sobre cómo rellenar el formulario de registro de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="62053-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="62053-121">Campos obligatorios</span><span class="sxs-lookup"><span data-stu-id="62053-121">Mandatory Fields</span></span> | <span data-ttu-id="62053-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="62053-122">Description</span></span> | <span data-ttu-id="62053-123">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="62053-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="62053-124">Nombre de la compañía</span><span class="sxs-lookup"><span data-stu-id="62053-124">Company Name</span></span>         | <span data-ttu-id="62053-125">El nombre de su empresa.</span><span class="sxs-lookup"><span data-stu-id="62053-125">The name of your company.</span></span> | <span data-ttu-id="62053-126">Usar un valor adecuado</span><span class="sxs-lookup"><span data-stu-id="62053-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="62053-127">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="62053-127">Application name</span></span>     | <span data-ttu-id="62053-128">Un valor único que identifica la aplicación que está autorizando.</span><span class="sxs-lookup"><span data-stu-id="62053-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="62053-129">Búsqueda de Microsoft</span><span class="sxs-lookup"><span data-stu-id="62053-129">Microsoft Search</span></span>     |
| <span data-ttu-id="62053-130">Sitio web de la aplicación</span><span class="sxs-lookup"><span data-stu-id="62053-130">Application website</span></span>  | <span data-ttu-id="62053-131">La dirección URL de la aplicación que solicitará acceso a la instancia de Azure DevOps durante la instalación del conector.</span><span class="sxs-lookup"><span data-stu-id="62053-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="62053-132">(Obligatorio).</span><span class="sxs-lookup"><span data-stu-id="62053-132">(Required).</span></span>  | <span data-ttu-id="62053-133"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="62053-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="62053-134">Url de devolución de llamada de autorización</span><span class="sxs-lookup"><span data-stu-id="62053-134">Authorization callback URL</span></span>        | <span data-ttu-id="62053-135">Dirección URL de devolución de llamada necesaria a la que redirige el servidor de autorización.</span><span class="sxs-lookup"><span data-stu-id="62053-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="62053-136"> https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="62053-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="62053-137">Ámbitos autorizados</span><span class="sxs-lookup"><span data-stu-id="62053-137">Authorized scopes</span></span> | <span data-ttu-id="62053-138">El ámbito de acceso de la aplicación</span><span class="sxs-lookup"><span data-stu-id="62053-138">The scope of access for the application</span></span> | <span data-ttu-id="62053-139">Seleccione los siguientes ámbitos: Identidad (lectura), Elementos de trabajo (lectura), Grupos de variables (lectura), Proyecto y equipo (lectura), Gráfico (lectura)</span><span class="sxs-lookup"><span data-stu-id="62053-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

<span data-ttu-id="62053-140">Al registrar la aplicación con los detalles anteriores, recibirá  el identificador de aplicación y el secreto de cliente que se usarán para configurar el conector. </span><span class="sxs-lookup"><span data-stu-id="62053-140">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="62053-141">Para revocar el acceso a cualquier aplicación registrada en Azure DevOps, ve a Configuración de usuario en la parte superior derecha de la instancia de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="62053-141">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="62053-142">Seleccione Perfil y, a continuación, seleccione Autorizaciones en la sección Seguridad del panel lateral.</span><span class="sxs-lookup"><span data-stu-id="62053-142">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="62053-143">Mantenga el puntero sobre una aplicación de OAuth autorizada para ver el botón Revocar en la esquina de los detalles de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="62053-143">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="62053-144">Configuración de conexión</span><span class="sxs-lookup"><span data-stu-id="62053-144">Connection settings</span></span>

<span data-ttu-id="62053-145">Después de registrar la aplicación DevOps de Microsoft Search con Azure DevOps, puede completar el paso de configuración de conexión.</span><span class="sxs-lookup"><span data-stu-id="62053-145">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="62053-146">Escribe el nombre de la organización, el id. de aplicación y el secreto de cliente.</span><span class="sxs-lookup"><span data-stu-id="62053-146">Enter your organization name, App ID, and Client secret.</span></span>

![Configuración de la aplicación de conexión](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="62053-148">Configurar datos: seleccionar proyectos y campos</span><span class="sxs-lookup"><span data-stu-id="62053-148">Configure data: select projects and fields</span></span>

<span data-ttu-id="62053-149">Puede elegir que la conexión indexe toda la organización o proyectos específicos.</span><span class="sxs-lookup"><span data-stu-id="62053-149">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="62053-150">Si decide indizar toda la organización, se indizarán los elementos de todos los proyectos de la organización.</span><span class="sxs-lookup"><span data-stu-id="62053-150">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="62053-151">Los nuevos proyectos y elementos se indizarán durante el siguiente rastreo después de crearlos.</span><span class="sxs-lookup"><span data-stu-id="62053-151">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="62053-152">Si elige proyectos individuales, solo se indizarán los elementos de trabajo de esos proyectos.</span><span class="sxs-lookup"><span data-stu-id="62053-152">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Configurar datos](media/ADO_Configure_data.png)

<span data-ttu-id="62053-154">A continuación, seleccione los campos que desea que la conexión indexe y obtenga una vista previa de los datos de estos campos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="62053-154">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Elegir propiedades](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="62053-156">Paso 4: Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="62053-156">Step 4: Manage search permissions</span></span>

<span data-ttu-id="62053-157">El conector de Azure DevOps admite permisos de búsqueda visibles solo para las personas con  **acceso a este** origen de datos o **todos.**</span><span class="sxs-lookup"><span data-stu-id="62053-157">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="62053-158">Si elige solo las personas con acceso a este origen de **datos,** los datos indizados aparecerán en los resultados de la búsqueda para los usuarios que tengan acceso a ellos en función de los permisos para usuarios o grupos en el nivel de ruta de acceso organización, proyecto o área en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="62053-158">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="62053-159">Si elige **Todos, los** datos indizados aparecerán en los resultados de búsqueda de todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="62053-159">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="62053-160">Paso 5: Asignar etiquetas de propiedad</span><span class="sxs-lookup"><span data-stu-id="62053-160">Step 5: Assign property labels</span></span>

<span data-ttu-id="62053-161">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="62053-161">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="62053-162">Paso 6: Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="62053-162">Step 6: Manage schema</span></span>

<span data-ttu-id="62053-163">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="62053-163">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="62053-164">Paso 7: Elegir la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="62053-164">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="62053-165">El conector de Azure DevOps admite programaciones de actualización para rastreos completos e incrementales.</span><span class="sxs-lookup"><span data-stu-id="62053-165">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="62053-166">La programación recomendada es una hora para un rastreo incremental y un día para un rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="62053-166">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="62053-167">Paso 8: Revisar la conexión</span><span class="sxs-lookup"><span data-stu-id="62053-167">Step 8: Review connection</span></span>

<span data-ttu-id="62053-168">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="62053-168">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
