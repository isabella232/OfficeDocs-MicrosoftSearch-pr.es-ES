---
title: Introducción a los conectores
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Introducción a los conectores de Microsoft Graph para Microsoft Search
ms.openlocfilehash: 677c91f121185faa6dc96f80c517917f429a3ab0
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847523"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="a8842-103">Introducción a los conectores de Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="a8842-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="a8842-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indiza todos los [datos de Microsoft 365](https://www.microsoft.com/microsoft-365) para que los usuarios puedan realizar búsquedas.</span><span class="sxs-lookup"><span data-stu-id="a8842-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="a8842-105">Con los conectores de Microsoft Graph, su organización puede indizar datos de terceros para que aparezcan en los resultados de Búsqueda de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8842-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="a8842-106">Esto expande los tipos de orígenes de contenido que se pueden buscar en las aplicaciones de productividad de Microsoft 365 y en el ecosistema más amplio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8842-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="a8842-107">Los datos de terceros se pueden hospedar de forma local o en las nubes públicas o privadas.</span><span class="sxs-lookup"><span data-stu-id="a8842-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="a8842-108">El resto de este artículo está pensado para ayudar a los administradores de Microsoft 365 a localizar los recursos disponibles para responder a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="a8842-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="a8842-109">¿Qué orígenes de datos se pueden conectar a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="a8842-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="a8842-110">¿Cómo puedo administrar mis conexiones?</span><span class="sxs-lookup"><span data-stu-id="a8842-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="a8842-111">¿Cuáles son los requisitos de licencia y los términos de uso de los conectores de Graph?</span><span class="sxs-lookup"><span data-stu-id="a8842-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="a8842-112">¿Cómo personalice y configure los resultados de la búsqueda?</span><span class="sxs-lookup"><span data-stu-id="a8842-112">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="a8842-113">¿Cómo puedo buscar datos del conector desde una aplicación personalizada?</span><span class="sxs-lookup"><span data-stu-id="a8842-113">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> <span data-ttu-id="a8842-114">Los conectores de Microsoft Graph y las API de Búsqueda de Microsoft ya están disponibles en general.</span><span class="sxs-lookup"><span data-stu-id="a8842-114">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="a8842-115">Los primeros lanzamientos se realizarán a los clientes configurados para la versión dirigida.</span><span class="sxs-lookup"><span data-stu-id="a8842-115">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="a8842-116">Si desea usar un conector de Graph en su espacio empresarial, los usuarios y administradores deben participar en [la versión dirigida.](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="a8842-116">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="a8842-117">¿Qué orígenes de datos se pueden conectar a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="a8842-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="a8842-118">Microsoft proporciona diez conectores de Graph y nuestros socios del ecosistema han creado más de 100 conectores de Graph adicionales.</span><span class="sxs-lookup"><span data-stu-id="a8842-118">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="a8842-119">También puede crear su propio conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="a8842-119">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="a8842-120">Conectores de Graph por Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8842-120">Graph connectors by Microsoft</span></span>

<span data-ttu-id="a8842-121">Puede conectarse a los siguientes orígenes de datos mediante conectores de Graph creados por Microsoft:</span><span class="sxs-lookup"><span data-stu-id="a8842-121">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="a8842-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="a8842-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="a8842-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="a8842-123">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="a8842-124">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="a8842-124">Azure SQL</span></span>
* [<span data-ttu-id="a8842-125">Sitios web de la empresa</span><span class="sxs-lookup"><span data-stu-id="a8842-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="a8842-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="a8842-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="a8842-127">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8842-127">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="a8842-128">Compartir archivos</span><span class="sxs-lookup"><span data-stu-id="a8842-128">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="a8842-129">Oracle (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="a8842-129">Oracle (preview)</span></span>
* [<span data-ttu-id="a8842-130">Salesforce (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="a8842-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="a8842-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="a8842-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="a8842-132">La [galería de conectores de Graph](connectors-gallery.md) contiene una breve descripción de cada uno de estos conectores de Graph.</span><span class="sxs-lookup"><span data-stu-id="a8842-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="a8842-133">Si está listo para conectar uno de estos orígenes de [](configure-connector.md) datos a su espacio empresarial, asegúrese de leer la introducción al programa de instalación y cualquier otro artículo de la sección Conectores de instalación de Microsoft que se aplique al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a8842-133">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="a8842-134">Conectores de Graph de nuestros socios</span><span class="sxs-lookup"><span data-stu-id="a8842-134">Graph connectors by our partners</span></span>

<span data-ttu-id="a8842-135">La [galería de conectores](connectors-gallery.md) de Microsoft Graph incluye una breve descripción de cada uno de los conectores de Graph creados por nuestros asociados y un vínculo al sitio web de cada asociado.</span><span class="sxs-lookup"><span data-stu-id="a8842-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="a8842-136">Póngase en contacto con cada partner directamente para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a8842-136">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="a8842-137">Crear su propio conector de Graph</span><span class="sxs-lookup"><span data-stu-id="a8842-137">Build your own Graph connector</span></span>

<span data-ttu-id="a8842-138">Si planea crear su propio conector de Graph, vea la información general de la API de Búsqueda de Microsoft en [Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a8842-138">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="a8842-139">¿Cómo puedo administrar mis conexiones?</span><span class="sxs-lookup"><span data-stu-id="a8842-139">How do I manage my connections?</span></span>

<span data-ttu-id="a8842-140">Puede administrar las conexiones desde la [pestaña Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) en el [Centro de administración de Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="a8842-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="a8842-141">Vea [Administrar las conexiones](manage-connector.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a8842-141">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="a8842-142">¿Cuáles son los requisitos de licencia y los términos de uso de los conectores de Graph?</span><span class="sxs-lookup"><span data-stu-id="a8842-142">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="a8842-143">Necesita una licencia válida de Microsoft 365 u Office 365 y una cuota suficiente de conectores de Graph para que los usuarios de su organización puedan ver los datos de los conectores en sus resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a8842-143">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="a8842-144">Para obtener más información, consulte [Requisitos de licencia, precios](licensing.md) y [términos de uso.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="a8842-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="a8842-145">¿Cómo personalice y configure los resultados de la búsqueda?</span><span class="sxs-lookup"><span data-stu-id="a8842-145">How do I customize and configure search results?</span></span>

<span data-ttu-id="a8842-146">Hay varias maneras de personalizar y configurar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a8842-146">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="a8842-147">Vea los siguientes artículos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="a8842-147">See the following articles to learn more:</span></span>

* [<span data-ttu-id="a8842-148">Administrar los sectores verticales y los tipos de resultados</span><span class="sxs-lookup"><span data-stu-id="a8842-148">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="a8842-149">Administrar los diseños de resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="a8842-149">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="a8842-150">Administrar el clúster de resultados</span><span class="sxs-lookup"><span data-stu-id="a8842-150">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="a8842-151">Administrar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="a8842-151">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="a8842-152">¿Cómo puedo buscar datos del conector desde una aplicación personalizada?</span><span class="sxs-lookup"><span data-stu-id="a8842-152">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="a8842-153">Después de indizar los datos personalizados, los desarrolladores [pueden consultar estos datos.](https://docs.microsoft.com/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="a8842-153">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="a8842-154">Puede ver los datos en cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8842-154">You can view your data in any application.</span></span> <span data-ttu-id="a8842-155">Para obtener más información, vea [la información general de la API de Búsqueda de Microsoft en Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="a8842-155">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="limitations"></a><span data-ttu-id="a8842-156">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="a8842-156">Limitations</span></span>

* <span data-ttu-id="a8842-157">Al publicar **un** conector creado por Microsoft, la conexión puede tardar unos minutos en crearse.</span><span class="sxs-lookup"><span data-stu-id="a8842-157">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="a8842-158">Durante ese tiempo, la conexión mostrará su estado como pendiente.</span><span class="sxs-lookup"><span data-stu-id="a8842-158">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="a8842-159">El Centro de administración de [Microsoft 365](https://admin.microsoft.com) no admite la edición del esquema de búsqueda **después** de publicar una conexión.</span><span class="sxs-lookup"><span data-stu-id="a8842-159">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="a8842-160">Para editar el esquema de búsqueda, elimine la conexión y, a continuación, cree una nueva.</span><span class="sxs-lookup"><span data-stu-id="a8842-160">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="a8842-161">El rendimiento de ingesta se limita a unos cuatro elementos por segundo.</span><span class="sxs-lookup"><span data-stu-id="a8842-161">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="a8842-162">No se admiten actualizaciones de esquema.</span><span class="sxs-lookup"><span data-stu-id="a8842-162">There is no support for schema updates.</span></span> <span data-ttu-id="a8842-163">Después de crear una configuración de conexión, no hay ninguna forma de actualizar el esquema.</span><span class="sxs-lookup"><span data-stu-id="a8842-163">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="a8842-164">Solo puede eliminar y volver a crear la conexión.</span><span class="sxs-lookup"><span data-stu-id="a8842-164">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="a8842-165">Hay un límite de conexiones.</span><span class="sxs-lookup"><span data-stu-id="a8842-165">There is a connections limit.</span></span> <span data-ttu-id="a8842-166">Cada inquilino puede crear hasta 10 conexiones.</span><span class="sxs-lookup"><span data-stu-id="a8842-166">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="a8842-167">La compatibilidad de edición para la conexión no está disponible.</span><span class="sxs-lookup"><span data-stu-id="a8842-167">Edit support for connection is not available.</span></span> <span data-ttu-id="a8842-168">Una vez creada la conexión, no podrá editarla ni cambiarla.</span><span class="sxs-lookup"><span data-stu-id="a8842-168">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="a8842-169">Si necesita cambiar algún detalle, debe eliminar y volver a crear la conexión.</span><span class="sxs-lookup"><span data-stu-id="a8842-169">If you need to change any details, you must delete and recreate the connection.</span></span>
