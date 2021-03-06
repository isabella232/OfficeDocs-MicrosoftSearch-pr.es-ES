---
title: Introducción a Microsoft Graph Connectors
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
description: Información general sobre los conectores de Microsoft Graph para Microsoft Search
ms.openlocfilehash: 1b3ea74cf571b1b5a048695633f6b9f698a21bf5
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508917"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="d0bfd-103">Información general sobre los conectores de Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="d0bfd-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="d0bfd-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indiza todos los [datos de Microsoft 365](https://www.microsoft.com/microsoft-365) para que puedan realizar búsquedas para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="d0bfd-105">Con los conectores de Microsoft Graph, su organización puede indizar datos de terceros para que aparezcan en los resultados de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="d0bfd-106">Esta característica amplía los tipos de orígenes de contenido que se pueden buscar en las aplicaciones de productividad de Microsoft 365 y en el ecosistema más amplio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="d0bfd-107">Los datos de terceros se pueden hospedar localmente o en las nubes públicas o privadas.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="d0bfd-108">Este artículo está pensado para ayudar a los administradores de Microsoft 365 a localizar los recursos disponibles para responder a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="d0bfd-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="d0bfd-109">¿Qué orígenes de datos se pueden conectar a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="d0bfd-110">¿Cómo puedo administrar mis conexiones?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="d0bfd-111">¿Cuáles son los requisitos de licencia y los términos de uso de los conectores de Graph?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="d0bfd-112">¿Cuáles son las características de vista previa?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="d0bfd-113">¿Cómo puedo personalizar y configurar los resultados de búsqueda?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="d0bfd-114">¿Cómo puedo buscar los datos del conector desde una aplicación personalizada?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="d0bfd-115">¿Cómo puedo personalizar los resultados de búsqueda?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="d0bfd-116">Cuáles son las limitaciones del conector</span><span class="sxs-lookup"><span data-stu-id="d0bfd-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="d0bfd-117">Los conectores de Microsoft Graph y las API de Microsoft Search ahora están disponibles en general.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-117">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="d0bfd-118">Los primeros lanzamientos serán para los clientes configurados para la versión dirigida.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-118">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="d0bfd-119">Si desea usar un conector de Graph en el inquilino, los usuarios y administradores deben optar por [la versión dirigida](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="d0bfd-119">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="d0bfd-120">¿Qué orígenes de datos se pueden conectar a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-120">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="d0bfd-121">Microsoft proporciona 9 conectores de Graph y nuestros socios del ecosistema han creado más de 100 conectores de Graph más.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-121">Microsoft provides 9 Graph connectors and our ecosystem partners have created over 100 more Graph connectors.</span></span> <span data-ttu-id="d0bfd-122">También puede crear su propio conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-122">You can also build your own Graph connector.</span></span>

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="d0bfd-123">Conectores de Graph por Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0bfd-123">Graph connectors by Microsoft</span></span>

<span data-ttu-id="d0bfd-124">Puede conectarse a los siguientes orígenes de datos mediante conectores de Graph creados por Microsoft:</span><span class="sxs-lookup"><span data-stu-id="d0bfd-124">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="d0bfd-125">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="d0bfd-125">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="d0bfd-126">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="d0bfd-126">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="d0bfd-127">Azure SQL y Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0bfd-127">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="d0bfd-128">Sitios web de la empresa</span><span class="sxs-lookup"><span data-stu-id="d0bfd-128">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="d0bfd-129">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="d0bfd-129">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="d0bfd-130">Compartir archivos</span><span class="sxs-lookup"><span data-stu-id="d0bfd-130">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="d0bfd-131">Oracle SQL (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d0bfd-131">Oracle SQL (preview)</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="d0bfd-132">Salesforce (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d0bfd-132">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="d0bfd-133">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d0bfd-133">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="d0bfd-134">La [galería de conectores de Graph](connectors-gallery.md) contiene una breve descripción de cada uno de estos conectores de Graph.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-134">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="d0bfd-135">Si está listo para conectar uno de estos orígenes de datos [](configure-connector.md) al inquilino, asegúrese de leer la introducción al programa de instalación y cualquier otro artículo de la sección Setup connectors by Microsoft que se aplican al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-135">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="d0bfd-136">Conectores de graph de nuestros partners</span><span class="sxs-lookup"><span data-stu-id="d0bfd-136">Graph connectors by our partners</span></span>

<span data-ttu-id="d0bfd-137">La [galería de conectores de Microsoft Graph](connectors-gallery.md) incluye una breve descripción de cada uno de los conectores de Graph creados por nuestros partners y un vínculo al sitio web de cada partner.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-137">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief description of each of the Graph connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="d0bfd-138">Para obtener más información, póngase en contacto con cada partner directamente.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-138">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="d0bfd-139">Crear su propio conector de Graph</span><span class="sxs-lookup"><span data-stu-id="d0bfd-139">Build your own Graph connector</span></span>

<span data-ttu-id="d0bfd-140">Puede crear su propio conector de Graph si lo prefiere.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-140">You can build your own Graph connector if you prefer.</span></span> <span data-ttu-id="d0bfd-141">Para obtener más información sobre la creación de conectores de Graph, vea [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="d0bfd-141">For more information on building Graph connectors, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="d0bfd-142">¿Cómo puedo administrar mis conexiones?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-142">How do I manage my connections?</span></span>

<span data-ttu-id="d0bfd-143">Puede administrar las conexiones desde la [pestaña Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) en el Centro de administración [de Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d0bfd-143">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="d0bfd-144">Para obtener más información acerca de la administración de conexiones, vea: [Administrar las conexiones](manage-connector.md).</span><span class="sxs-lookup"><span data-stu-id="d0bfd-144">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="d0bfd-145">¿Cuáles son los requisitos de licencia y los términos de uso de los conectores de Graph?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-145">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="d0bfd-146">Necesita una licencia válida de Microsoft 365 u Office 365 y una cuota suficiente de Conectores de Graph para que los usuarios de su organización puedan ver los datos de los conectores en sus resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-146">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="d0bfd-147">Para obtener más información, vea [Requisitos de licencia y precios](licensing.md) y [Términos de uso.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="d0bfd-147">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="d0bfd-148">¿Cuáles son las características de vista previa?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-148">What are the preview features?</span></span>

<span data-ttu-id="d0bfd-149">Aunque los conectores de Microsoft Graph y las API de Microsoft Search ahora están disponibles en general, hay varias características que están en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-149">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="d0bfd-150">El conjunto de conectores y características en versión preliminar incluyen:</span><span class="sxs-lookup"><span data-stu-id="d0bfd-150">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="d0bfd-151">Conector de Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="d0bfd-151">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="d0bfd-152">Conector de Salesforce</span><span class="sxs-lookup"><span data-stu-id="d0bfd-152">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="d0bfd-153">[Conector de ServiceNow](servicenow-connector.md) con permisos de búsqueda que usan ACL de origen</span><span class="sxs-lookup"><span data-stu-id="d0bfd-153">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="d0bfd-154">Administrar el clúster de resultados</span><span class="sxs-lookup"><span data-stu-id="d0bfd-154">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="d0bfd-155">¿Cómo puedo personalizar y configurar los resultados de búsqueda?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-155">How do I customize and configure search results?</span></span>

<span data-ttu-id="d0bfd-156">Hay muchas maneras de personalizar y configurar los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-156">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="d0bfd-157">Vea los siguientes artículos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="d0bfd-157">See the following articles to learn more:</span></span>

* [<span data-ttu-id="d0bfd-158">Administrar los sectores verticales y los tipos de resultados</span><span class="sxs-lookup"><span data-stu-id="d0bfd-158">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="d0bfd-159">Administrar los diseños de resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="d0bfd-159">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="d0bfd-160">Administrar el clúster de resultados</span><span class="sxs-lookup"><span data-stu-id="d0bfd-160">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="d0bfd-161">Administrar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="d0bfd-161">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="d0bfd-162">¿Cómo puedo buscar los datos del conector desde una aplicación personalizada?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-162">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="d0bfd-163">Una vez indizados los datos personalizados, los desarrolladores [pueden consultar estos datos](https://docs.microsoft.com/graph/search-concept-custom-types).</span><span class="sxs-lookup"><span data-stu-id="d0bfd-163">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="d0bfd-164">Puede ver los datos en cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-164">You can view your data in any application.</span></span> <span data-ttu-id="d0bfd-165">Para obtener más información, vea [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="d0bfd-165">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="d0bfd-166">¿Cómo puedo personalizar los resultados de búsqueda?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-166">How do I customize search results?</span></span>

<span data-ttu-id="d0bfd-167">El siguiente paso es personalizar los resultados de búsqueda según se recomienda en este artículo [¿Cómo puedo personalizar y configurar los resultados de búsqueda?](#how-do-i-customize-and-configure-search-results).</span><span class="sxs-lookup"><span data-stu-id="d0bfd-167">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="d0bfd-168">Para obtener más información sobre cómo personalizar los resultados de búsqueda, vea [Personalizar la página de resultados de búsqueda](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).</span><span class="sxs-lookup"><span data-stu-id="d0bfd-168">To learn more about customizing search results, see [Customize the search results page](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="d0bfd-169">¿Cuáles son las limitaciones del conector?</span><span class="sxs-lookup"><span data-stu-id="d0bfd-169">What are the connector limitations?</span></span>

* <span data-ttu-id="d0bfd-170">Al publicar **un** conector creado por Microsoft, la conexión puede tardar unos minutos en crearse.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-170">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="d0bfd-171">Durante ese tiempo, la conexión mostrará su estado como pendiente.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-171">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="d0bfd-172">El [Centro de administración de Microsoft 365](https://admin.microsoft.com) no admite la edición del esquema de búsqueda **después** de publicar una conexión.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-172">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="d0bfd-173">Para editar el esquema de búsqueda, elimine la conexión y, a continuación, cree una nueva.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-173">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="d0bfd-174">El rendimiento de la ingesta se limita a unos cuatro elementos por segundo.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-174">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="d0bfd-175">No hay compatibilidad con las actualizaciones de esquema.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-175">There is no support for schema updates.</span></span> <span data-ttu-id="d0bfd-176">Después de crear una configuración de conexión, no hay forma de actualizar el esquema.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-176">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="d0bfd-177">Solo puede eliminar y volver a crear la conexión.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-177">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="d0bfd-178">Hay un límite de conexión.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-178">There is a connection limit.</span></span> <span data-ttu-id="d0bfd-179">Cada espacio empresarial puede crear hasta 10 conexiones.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-179">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="d0bfd-180">La compatibilidad de edición para la conexión no está disponible.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-180">Edit support for connection is not available.</span></span> <span data-ttu-id="d0bfd-181">Una vez creada la conexión, no puede editarla ni cambiarla.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-181">Once the connection has been created, you can't edit or change it.</span></span> <span data-ttu-id="d0bfd-182">Si necesita cambiar algún detalle, debe eliminar y volver a crear la conexión.</span><span class="sxs-lookup"><span data-stu-id="d0bfd-182">If you need to change any details, you must delete and recreate the connection.</span></span>
