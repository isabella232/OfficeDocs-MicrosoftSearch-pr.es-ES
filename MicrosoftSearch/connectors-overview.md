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
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367527"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="adfe0-103">Información general sobre los conectores de Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="adfe0-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="adfe0-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indiza todos los datos de [Microsoft 365](https://www.microsoft.com/microsoft-365) para permitir que los usuarios puedan buscar en ellos.</span><span class="sxs-lookup"><span data-stu-id="adfe0-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="adfe0-105">Con los conectores de Microsoft Graph, su organización puede indizar datos de terceros para que aparezcan en los resultados de la búsqueda de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="adfe0-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="adfe0-106">Esto amplía los tipos de orígenes de contenido que se pueden buscar en las aplicaciones de productividad de Microsoft 365 y el más amplio ecosistema de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="adfe0-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="adfe0-107">Los datos de terceros pueden hospedarse localmente o en nubes públicas o privadas.</span><span class="sxs-lookup"><span data-stu-id="adfe0-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="adfe0-108">El resto de este artículo está pensado para ayudar a los administradores de Microsoft 365 a encontrar los recursos que están disponible para responder las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="adfe0-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are avaiable to answer the following questions:</span></span>

* [<span data-ttu-id="adfe0-109">¿Qué orígenes de datos se pueden conectar a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="adfe0-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="adfe0-110">¿Cómo se administran las conexiones?</span><span class="sxs-lookup"><span data-stu-id="adfe0-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="adfe0-111">¿Cuáles son los requisitos de licencia y los términos de uso de los conectores de Graph?</span><span class="sxs-lookup"><span data-stu-id="adfe0-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="adfe0-112">¿Cómo se personalizan y configuran los resultados de la búsqueda?</span><span class="sxs-lookup"><span data-stu-id="adfe0-112">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="adfe0-113">¿Cómo se busca en los datos de los conectores de una aplicación personalizada?</span><span class="sxs-lookup"><span data-stu-id="adfe0-113">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> <span data-ttu-id="adfe0-114">Los conectores de Microsoft Graph y las API de Microsoft Search ahora están disponibles para el público en general.</span><span class="sxs-lookup"><span data-stu-id="adfe0-114">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="adfe0-115">Las primeras implementaciones serán a los clientes configurados para la versión dirigida.</span><span class="sxs-lookup"><span data-stu-id="adfe0-115">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="adfe0-116">Si desea usar un conector de Graph en su espacio empresarial, los usuarios y administradores deben optar por la [versión dirigida](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="adfe0-116">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="adfe0-117">¿Qué orígenes de datos se pueden conectar a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="adfe0-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="adfe0-118">Microsoft proporciona diez conectores de Graph y nuestros socios de ecosistemas han creado más de 100 conectores de gráficos adicionales.</span><span class="sxs-lookup"><span data-stu-id="adfe0-118">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="adfe0-119">También puede crear su propio conector para gráficos.</span><span class="sxs-lookup"><span data-stu-id="adfe0-119">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="adfe0-120">Conectores de Graph de Microsoft</span><span class="sxs-lookup"><span data-stu-id="adfe0-120">Graph connectors by Microsoft</span></span>

<span data-ttu-id="adfe0-121">Puede conectarse a los siguientes orígenes de datos mediante conectores de Graph creados por Microsoft:</span><span class="sxs-lookup"><span data-stu-id="adfe0-121">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="adfe0-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="adfe0-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="adfe0-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="adfe0-123">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="adfe0-124">SQL de Azure</span><span class="sxs-lookup"><span data-stu-id="adfe0-124">Azure SQL</span></span>
* [<span data-ttu-id="adfe0-125">Sitios web de la empresa</span><span class="sxs-lookup"><span data-stu-id="adfe0-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="adfe0-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="adfe0-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="adfe0-127">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="adfe0-127">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="adfe0-128">Compartir archivos</span><span class="sxs-lookup"><span data-stu-id="adfe0-128">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="adfe0-129">Oracle (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="adfe0-129">Oracle (preview)</span></span>
* [<span data-ttu-id="adfe0-130">Salesforce (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="adfe0-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="adfe0-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="adfe0-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="adfe0-132">La [Galería de conectores de Graph](connectors-gallery.md) contiene una breve descripción de cada uno de estos conectores de Graph.</span><span class="sxs-lookup"><span data-stu-id="adfe0-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="adfe0-133">Si está listo para conectar uno de estos orígenes de datos al espacio empresarial, asegúrese de leer la [información general del programa de instalación](configure-connector.md) y los artículos de la sección Setup Connectors by Microsoft que se aplican a su origen de datos.</span><span class="sxs-lookup"><span data-stu-id="adfe0-133">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="adfe0-134">Conectores de gráficos por nuestros partners</span><span class="sxs-lookup"><span data-stu-id="adfe0-134">Graph connectors by our partners</span></span>

<span data-ttu-id="adfe0-135">La [Galería de conectores de Microsoft Graph](connectors-gallery.md) incluye una breve descripción de cada uno de los conectores de gráficos creados por nuestros socios y un vínculo al sitio web de cada socio.</span><span class="sxs-lookup"><span data-stu-id="adfe0-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="adfe0-136">Póngase en contacto con cada socio directamente para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="adfe0-136">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="adfe0-137">Crear su propio conector para gráficos</span><span class="sxs-lookup"><span data-stu-id="adfe0-137">Build your own Graph connector</span></span>

<span data-ttu-id="adfe0-138">Si tiene previsto crear su propio conector para gráficos, vea la información [General de la API de búsqueda de Microsoft en Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="adfe0-138">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="adfe0-139">¿Cómo se administran las conexiones?</span><span class="sxs-lookup"><span data-stu-id="adfe0-139">How do I manage my connections?</span></span>

<span data-ttu-id="adfe0-140">Puede administrar las conexiones desde la [pestaña conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) del centro de [administración de Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="adfe0-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="adfe0-141">Para obtener más información, vea [administrar las conexiones](manage-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="adfe0-141">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="adfe0-142">¿Cuáles son los requisitos de licencia y los términos de uso de los conectores de Graph?</span><span class="sxs-lookup"><span data-stu-id="adfe0-142">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="adfe0-143">Necesita una licencia válida de Microsoft 365 o de Office 365 y suficientes conectores de gráficos para que los usuarios de la organización puedan ver los datos de los conectores en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="adfe0-143">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="adfe0-144">Para obtener más información, consulte [requisitos de licencia y precios](licensing.md) y [condiciones de uso](terms-of-use.md).</span><span class="sxs-lookup"><span data-stu-id="adfe0-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="adfe0-145">¿Cómo se personalizan y configuran los resultados de la búsqueda?</span><span class="sxs-lookup"><span data-stu-id="adfe0-145">How do I customize and configure search results?</span></span>

<span data-ttu-id="adfe0-146">Hay varias formas de personalizar y configurar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="adfe0-146">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="adfe0-147">Consulte los siguientes artículos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="adfe0-147">See the following articles to learn more:</span></span>

* [<span data-ttu-id="adfe0-148">Administrar los sectores verticales y los tipos de resultados</span><span class="sxs-lookup"><span data-stu-id="adfe0-148">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="adfe0-149">Administre los diseños de resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="adfe0-149">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="adfe0-150">Administrar clúster de resultados</span><span class="sxs-lookup"><span data-stu-id="adfe0-150">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="adfe0-151">Administrar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="adfe0-151">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="adfe0-152">¿Cómo se busca en los datos de los conectores de una aplicación personalizada?</span><span class="sxs-lookup"><span data-stu-id="adfe0-152">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="adfe0-153">Una vez indizados los datos personalizados, los desarrolladores pueden [consultar estos datos](https://docs.microsoft.com/graph/search-concept-custom-types).</span><span class="sxs-lookup"><span data-stu-id="adfe0-153">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="adfe0-154">Puede ver los datos en cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="adfe0-154">You can view your data in any application.</span></span> <span data-ttu-id="adfe0-155">Para obtener más información, vea la [información general de la API de búsqueda de Microsoft en Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="adfe0-155">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>
