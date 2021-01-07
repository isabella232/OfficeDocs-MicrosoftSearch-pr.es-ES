---
title: Clúster de resultados de conectores
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Detalles del resultado de los conectores experiencia de clúster
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773031"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="3614e-103">Clúster de resultados de conectores de Graph</span><span class="sxs-lookup"><span data-stu-id="3614e-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="3614e-104">Información general sobre el clúster de resultados de conectores de Graph (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="3614e-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="3614e-105">Con los clústeres de resultados de conectores de Graph, las empresas pueden buscar contenido de orígenes de datos de terceros en su vista predeterminada, en la pestaña **todos** , en SharePoint, Office.com y Microsoft Search en Bing.</span><span class="sxs-lookup"><span data-stu-id="3614e-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="3614e-106">Los clústeres de resultados ayudan a los usuarios a descubrir todo el contenido de terceros en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="3614e-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="3614e-107">Los resultados que se muestran en un clúster de resultados se agrupan en función de la configuración vertical de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3614e-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="3614e-108">Cómo se seleccionan y se muestran los resultados de los conectores</span><span class="sxs-lookup"><span data-stu-id="3614e-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="3614e-109">Los resultados de conectores proporcionados en el clúster de resultados se derivan de presentaciones verticales de búsqueda individuales con contenido de conector.</span><span class="sxs-lookup"><span data-stu-id="3614e-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="3614e-110">Cada presentación vertical de búsqueda proporciona un conjunto de resultados relevantes que se convierten en un clúster de resultados candidatos.</span><span class="sxs-lookup"><span data-stu-id="3614e-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="3614e-111">Los resultados relevantes se eligen en función de la propiedad "título" y de la propiedad "Content" de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="3614e-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="3614e-112">La propiedad de contenido se marca como *isContent = true* en el esquema.</span><span class="sxs-lookup"><span data-stu-id="3614e-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="3614e-113">Para garantizar la detección del contenido de las presentaciones verticales de búsqueda, le recomendamos que proporcione títulos significativos para los elementos.</span><span class="sxs-lookup"><span data-stu-id="3614e-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="3614e-114">Esto afecta positivamente el arbitraje de los candidatos del clúster de resultados y la probabilidad de que el contenido aparezca en un clúster de resultados.</span><span class="sxs-lookup"><span data-stu-id="3614e-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="3614e-115">Por ejemplo, evite el uso de identificadores como valores para la propiedad "título" a menos que los usuarios estén usando identificadores para buscar contenido.</span><span class="sxs-lookup"><span data-stu-id="3614e-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="3614e-116">La frecuencia con la que se muestra un clúster de resultados varía en factores como el número de presentaciones verticales de búsqueda que se configuran y el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="3614e-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="3614e-117">Mediante la interacción o la omisión de un clúster de resultados, los usuarios proporcionarán implícitamente sugerencias que ajustarán su activación a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="3614e-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="3614e-118">La experiencia de resultados de búsqueda para los elementos de conector que se muestran en el clúster de resultados usa [tipos de resultado](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3614e-118">The search result experience for connector items shown in your result cluster uses [result types](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="3614e-119">Si no se ha configurado ningún tipo de resultado, se usa un [diseño generado](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) por el sistema.</span><span class="sxs-lookup"><span data-stu-id="3614e-119">If no result type is configured, a [system generated layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="3614e-120">Se recomienda usar la propiedad "title" como título del resultado de la búsqueda y la propiedad "Content" como la descripción de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3614e-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="3614e-121">Esto proporcionará la mejor experiencia para los usuarios mediante la activación precisa del clúster de resultados y los resultados más relevantes en el clúster.</span><span class="sxs-lookup"><span data-stu-id="3614e-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="3614e-122">Habilitar clústeres de resultados</span><span class="sxs-lookup"><span data-stu-id="3614e-122">Enable result clusters</span></span>
  
<span data-ttu-id="3614e-123">La experiencia del clúster de resultados está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3614e-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="3614e-124">Siga estos pasos para activar la experiencia en el nivel de organización:</span><span class="sxs-lookup"><span data-stu-id="3614e-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="3614e-125">En el [centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**verticales**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="3614e-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="3614e-126">Seleccione **todos** los resultados en vertical y, a continuación, habilite **Mostrar los resultados del conector**.</span><span class="sxs-lookup"><span data-stu-id="3614e-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="3614e-127">Siga estos pasos para activar la experiencia en el nivel de sitio de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="3614e-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="3614e-128">En el sitio de SharePoint en el que desea la experiencia del clúster de resultados, vaya a **configuración**.</span><span class="sxs-lookup"><span data-stu-id="3614e-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="3614e-129">Vaya a **información del sitio** para > **ver toda la configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="3614e-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="3614e-130">Vaya a la sección de Microsoft Search y, a continuación, seleccione **configurar Microsoft Search para esta colección de sitios**.</span><span class="sxs-lookup"><span data-stu-id="3614e-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="3614e-131">En el panel de navegación, vaya a **experiencia personalizada** y, a continuación, seleccione **vertical**.</span><span class="sxs-lookup"><span data-stu-id="3614e-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="3614e-132">Seleccione **todos** los resultados en vertical y, a continuación, habilite **Mostrar los resultados del conector**.</span><span class="sxs-lookup"><span data-stu-id="3614e-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="3614e-133">Ver la experiencia de clúster de resultados una vez habilitada</span><span class="sxs-lookup"><span data-stu-id="3614e-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="3614e-134">Después de activar la experiencia del clúster de resultados, puede tardar unos minutos antes de poder verlo.</span><span class="sxs-lookup"><span data-stu-id="3614e-134">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="3614e-135">Si quiere la experiencia inmediatamente, puede anexar *cacheClear = true* a la dirección URL en SharePoint y Office.</span><span class="sxs-lookup"><span data-stu-id="3614e-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
