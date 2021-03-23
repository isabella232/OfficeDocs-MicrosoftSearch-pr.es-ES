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
description: Detalles de la experiencia del clúster de resultados de conectores
ms.openlocfilehash: ae5528f2e12c9e331b66e821f2a9c03947d788df
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031777"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="03a85-103">Clúster de resultados de conectores de Graph</span><span class="sxs-lookup"><span data-stu-id="03a85-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="03a85-104">Información general sobre el clúster de resultados de conectores de Graph (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="03a85-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="03a85-105">Con los clústeres de resultados de los conectores de Graph,  las empresas pueden buscar contenido de orígenes de datos de terceros en su vista predeterminada, la pestaña Todo, en SharePoint, Office.com y Microsoft Search en Bing.</span><span class="sxs-lookup"><span data-stu-id="03a85-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="03a85-106">Los clústeres de resultados ayudan a los usuarios a descubrir todo el contenido de terceros en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="03a85-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="03a85-107">Los resultados que se muestran en un clúster de resultados se agrupan en función de la configuración vertical de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="03a85-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="03a85-108">Cómo se seleccionan y muestran los resultados del conector</span><span class="sxs-lookup"><span data-stu-id="03a85-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="03a85-109">Los resultados del conector proporcionados en el clúster de resultados se derivan de verticales de búsqueda individuales con contenido de conector.</span><span class="sxs-lookup"><span data-stu-id="03a85-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="03a85-110">Cada vertical de búsqueda proporciona un conjunto de resultados relevantes que se convierte en un clúster de resultados candidato.</span><span class="sxs-lookup"><span data-stu-id="03a85-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="03a85-111">Los resultados relevantes se eligen en función de la propiedad "title" y la propiedad "content" de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="03a85-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="03a85-112">La propiedad content se marca como *isContent=true* en el esquema.</span><span class="sxs-lookup"><span data-stu-id="03a85-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="03a85-113">Para garantizar la detección de contenido de las verticales de búsqueda, se recomienda proporcionar títulos significativos para los elementos.</span><span class="sxs-lookup"><span data-stu-id="03a85-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="03a85-114">Esto afecta positivamente al arbitraje de los candidatos del clúster de resultados y a la probabilidad de que el contenido se muestre en un clúster de resultados.</span><span class="sxs-lookup"><span data-stu-id="03a85-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="03a85-115">Por ejemplo, evite el uso de los IDs como valores de la propiedad "title" a menos que los usuarios usen los IDs para buscar contenido.</span><span class="sxs-lookup"><span data-stu-id="03a85-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="03a85-116">La frecuencia con la que se muestra un clúster de resultados varía según factores como el número de verticales de búsqueda que configure y el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="03a85-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="03a85-117">Al interactuar o ignorar un clúster de resultados, los usuarios proporcionarán implícitamente sugerencias que ajustarán su desencadenamiento con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="03a85-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="03a85-118">La experiencia de resultados de búsqueda de los elementos de conector que se muestran en el clúster de [resultados](./customize-search-page.md#create-your-own-result-type) usa tipos de resultados definidos por usted.</span><span class="sxs-lookup"><span data-stu-id="03a85-118">The search result experience for connector items shown in your result cluster uses [result types](./customize-search-page.md#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="03a85-119">Si no se configura ningún tipo de resultado, [se usa un diseño generado por](./customize-search-page.md#default-search-result-layout) el sistema.</span><span class="sxs-lookup"><span data-stu-id="03a85-119">If no result type is configured, a [system generated layout](./customize-search-page.md#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="03a85-120">Se recomienda usar la propiedad "title" como título del resultado de la búsqueda y la propiedad "content" como descripción de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="03a85-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="03a85-121">Esto proporcionará la mejor experiencia para los usuarios mediante la activación precisa del clúster de resultados y los resultados más relevantes en el clúster.</span><span class="sxs-lookup"><span data-stu-id="03a85-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="03a85-122">Habilitar clústeres de resultados</span><span class="sxs-lookup"><span data-stu-id="03a85-122">Enable result clusters</span></span>
  
<span data-ttu-id="03a85-123">La experiencia del clúster de resultados está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="03a85-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="03a85-124">Siga estos pasos para activar la experiencia en el nivel de la organización:</span><span class="sxs-lookup"><span data-stu-id="03a85-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="03a85-125">En el [Centro de administración de Microsoft 365,](https://admin.microsoft.com)vaya a [**Verticales**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="03a85-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="03a85-126">Seleccione la **vertical Todo** y, a continuación, habilite **Mostrar resultados del conector**.</span><span class="sxs-lookup"><span data-stu-id="03a85-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="03a85-127">Siga estos pasos para activar la experiencia en el nivel de sitio de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="03a85-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="03a85-128">En el sitio de SharePoint donde desea la experiencia del clúster de resultados, vaya a **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="03a85-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="03a85-129">Vaya a **Información del sitio** Ver toda la configuración del > **sitio**.</span><span class="sxs-lookup"><span data-stu-id="03a85-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="03a85-130">Vaya a la sección Búsqueda de Microsoft y, a continuación, **seleccione Configurar Microsoft Search para esta colección de sitios.**</span><span class="sxs-lookup"><span data-stu-id="03a85-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="03a85-131">En el panel de navegación, vaya **a Experiencia personalizada** y, a continuación, seleccione **Verticales**.</span><span class="sxs-lookup"><span data-stu-id="03a85-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="03a85-132">Seleccione la **vertical Todo** y, a continuación, habilite **Mostrar resultados del conector**.</span><span class="sxs-lookup"><span data-stu-id="03a85-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="03a85-133">Ver la experiencia del clúster de resultados después de habilitarla</span><span class="sxs-lookup"><span data-stu-id="03a85-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="03a85-134">Después de activar la experiencia del clúster de resultados, puede tardar hasta 12 horas antes de poder verlo.</span><span class="sxs-lookup"><span data-stu-id="03a85-134">After you turn on the result cluster experience, it can take up to 12 hours before you can view it.</span></span> <span data-ttu-id="03a85-135">Si desea la experiencia inmediatamente, puede anexar *cacheClear=true* a la dirección URL en SharePoint y Office.</span><span class="sxs-lookup"><span data-stu-id="03a85-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>