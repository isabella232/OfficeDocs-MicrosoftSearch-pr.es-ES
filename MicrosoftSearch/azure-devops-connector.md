---
title: Conector de Azure DevOps para Microsoft Search
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de Azure DevOps para Microsoft Search
ms.openlocfilehash: a0028c3b336c2b5e3d01bb14006ee0debb4524f2
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927193"
---
# <a name="azure-devops-connector"></a><span data-ttu-id="0f7c3-103">Conector de Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="0f7c3-103">Azure DevOps connector</span></span>

<span data-ttu-id="0f7c3-104">Con el conector de Azure DevOps, su organización puede indizar los elementos de trabajo en su instancia del servicio de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-104">With the Azure DevOps connector, your organization can index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="0f7c3-105">Después de configurar el conector y el contenido de índice desde Azure DevOps, los usuarios finales pueden buscar esos elementos en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

<span data-ttu-id="0f7c3-106">Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Azure DevOps connector.</span></span> <span data-ttu-id="0f7c3-107">Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="0f7c3-108">El conector de Azure DevOps solo admite el servicio en la nube de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-108">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="0f7c3-109">El conector no admite Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 y TFS 2013.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-109">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="0f7c3-110">Conectarse a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="0f7c3-110">Connect to a data source</span></span>

<span data-ttu-id="0f7c3-111">Para conectarse a la instancia de DevOps de Azure, necesita el nombre de la [organización](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) de Azure DevOps, su identificador de aplicación y el secreto de cliente para la autenticación OAuth.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-111">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="0f7c3-112">Registrar una aplicación</span><span class="sxs-lookup"><span data-stu-id="0f7c3-112">Register an app</span></span>

<span data-ttu-id="0f7c3-113">Debe registrar una aplicación en Azure DevOps para que la aplicación Microsoft Search pueda tener acceso a la instancia.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-113">You must register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="0f7c3-114">Para obtener más información, consulte la documentación de Azure DevOps sobre cómo [registrar una aplicación](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span><span class="sxs-lookup"><span data-stu-id="0f7c3-114">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="0f7c3-115">La siguiente tabla proporciona instrucciones sobre cómo rellenar el formulario de registro de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="0f7c3-115">The following table provides guidance on how to fill out the app registration form:</span></span>

 <span data-ttu-id="0f7c3-116">**Campos obligatorios**</span><span class="sxs-lookup"><span data-stu-id="0f7c3-116">**Mandatory Fields**</span></span> | <span data-ttu-id="0f7c3-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0f7c3-117">**Description**</span></span>      | <span data-ttu-id="0f7c3-118">**Valor recomendado**</span><span class="sxs-lookup"><span data-stu-id="0f7c3-118">**Recommended Value**</span></span>
--- | --- | ---
| <span data-ttu-id="0f7c3-119">Nombre de la compañía</span><span class="sxs-lookup"><span data-stu-id="0f7c3-119">Company Name</span></span>         | <span data-ttu-id="0f7c3-120">Este es el nombre de su compañía.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-120">This is the name of your company.</span></span> | <span data-ttu-id="0f7c3-121">Use un valor apropiado</span><span class="sxs-lookup"><span data-stu-id="0f7c3-121">Use an appropriate value</span></span>   |
| <span data-ttu-id="0f7c3-122">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0f7c3-122">Application name</span></span>     | <span data-ttu-id="0f7c3-123">Este valor único identifica la aplicación que está autorizando.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-123">This unique value identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="0f7c3-124">Búsqueda de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0f7c3-124">Microsoft Search</span></span>     |
| <span data-ttu-id="0f7c3-125">Sitio web de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0f7c3-125">Application website</span></span>  | <span data-ttu-id="0f7c3-126">Este campo obligatorio es la dirección URL de la aplicación que solicitará acceso a la instancia de Azure DevOps durante la instalación del conector.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-126">This required field is the URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span>  | <https://gcs.office.com/>                |
| <span data-ttu-id="0f7c3-127">Dirección URL de devolución de llamada de autorización</span><span class="sxs-lookup"><span data-stu-id="0f7c3-127">Authorization callback URL</span></span>        | <span data-ttu-id="0f7c3-128">Una dirección URL de devolución de llamada obligatoria a la que redirige el servidor de autorización.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-128">A required callback URL that the authorization server redirects to.</span></span> | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| <span data-ttu-id="0f7c3-129">Ámbitos autorizados</span><span class="sxs-lookup"><span data-stu-id="0f7c3-129">Authorized scopes</span></span> | <span data-ttu-id="0f7c3-130">Este es el ámbito de acceso para la aplicación</span><span class="sxs-lookup"><span data-stu-id="0f7c3-130">This is the scope of access for the application</span></span> | <span data-ttu-id="0f7c3-131">Seleccione los siguientes ámbitos: identidad (lectura), elementos de trabajo (lectura), grupos de variables (lectura), proyecto y equipo (lectura), gráfico (lectura)</span><span class="sxs-lookup"><span data-stu-id="0f7c3-131">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

<span data-ttu-id="0f7c3-132">Al registrar la aplicación con los detalles anteriores, obtendrá el identificador de la **aplicación** y el **secreto de cliente** que se usará para configurar el conector.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-132">On registering the app with the details above, you will get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="0f7c3-133">Para revocar el acceso a cualquier aplicación registrada en Azure DevOps, vaya a configuración de usuario en la parte superior derecha de la instancia de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-133">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="0f7c3-134">Haga clic en perfil y, a continuación, haga clic en autorizaciones en la sección seguridad del panel lateral.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-134">Click on Profile and then click on Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="0f7c3-135">Mantenga el mouse sobre una aplicación de OAuth autorizada para ver el botón revocar en la esquina de los detalles de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-135">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="0f7c3-136">Configuración de conexión</span><span class="sxs-lookup"><span data-stu-id="0f7c3-136">Connection settings</span></span>

<span data-ttu-id="0f7c3-137">Después de registrar la aplicación Microsoft Search con Azure DevOps, puede completar el paso de configuración de la conexión.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-137">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="0f7c3-138">Escriba el nombre de la organización, el identificador de la aplicación y el secreto de cliente.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-138">Enter your organization name, App ID, and Client secret.</span></span>

![Configuración de la aplicación de conexión](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a><span data-ttu-id="0f7c3-140">Selección de proyectos y campos</span><span class="sxs-lookup"><span data-stu-id="0f7c3-140">Select projects and fields</span></span>

<span data-ttu-id="0f7c3-141">Puede elegir que la conexión se Indice en toda la organización o en proyectos específicos.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-141">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="0f7c3-142">Si elige indizar toda la organización, los elementos de todos los proyectos de la organización se indizarán.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-142">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="0f7c3-143">Los nuevos proyectos y elementos se indizarán durante el siguiente rastreo una vez que se hayan creado.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-143">New projects and items will be indexed during the next crawl after they are created.</span></span> <span data-ttu-id="0f7c3-144">Si elige proyectos individuales, solo se indizarán los elementos de trabajo en esos proyectos.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-144">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Configurar datos](media/ADO_Configure_data.png)

<span data-ttu-id="0f7c3-146">A continuación, seleccione los campos que desea que la conexión indexe y obtenga una vista previa de los datos de estos campos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-146">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Elegir propiedades](media/ADO_choose_properties.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="0f7c3-148">Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="0f7c3-148">Manage search permissions</span></span>

<span data-ttu-id="0f7c3-149">Actualmente, el conector de Azure DevOps solo admite permisos **de búsqueda visibles para todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-149">The Azure DevOps connector currently only supports search permissions **Visible to Everyone**.</span></span> <span data-ttu-id="0f7c3-150">Los datos indizados aparecerán en los resultados de la búsqueda para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-150">Indexed data will appear in the search results for all users.</span></span>

## <a name="manage-search-schema"></a><span data-ttu-id="0f7c3-151">Administrar el esquema de búsqueda</span><span class="sxs-lookup"><span data-stu-id="0f7c3-151">Manage search schema</span></span>

<span data-ttu-id="0f7c3-152">Configure la asignación del esquema de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-152">Configure the search schema mapping.</span></span> <span data-ttu-id="0f7c3-153">Puede elegir qué propiedades se pueden **consultar** , **Buscar** y **recuperar**.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-153">You can choose which properties to make **queryable** , **searchable** and **retrievable**.</span></span>


## <a name="set-refresh-schedule"></a><span data-ttu-id="0f7c3-154">Establecer programación de actualización</span><span class="sxs-lookup"><span data-stu-id="0f7c3-154">Set refresh schedule</span></span>

<span data-ttu-id="0f7c3-155">El conector de DevOps de Azure admite programaciones de actualización para rastreos completos e incrementales.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-155">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="0f7c3-156">Un rastreo completo busca elementos de trabajo eliminados que se sincronizaron previamente con el índice de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-156">A full crawl finds deleted work items that were previously synced to the Microsoft Search index.</span></span> <span data-ttu-id="0f7c3-157">Se ejecuta un rastreo completo para sincronizar todos los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-157">A full crawl runs to sync all the work items.</span></span> <span data-ttu-id="0f7c3-158">Para sincronizar los nuevos elementos de trabajo y las actualizaciones de los elementos de trabajo existentes, debe programar rastreos incrementales.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-158">To sync new work items and updates to existing work items, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="0f7c3-159">La programación recomendada es una hora para un rastreo incremental y un día para un rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="0f7c3-159">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>
