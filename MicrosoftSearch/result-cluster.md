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
ms.openlocfilehash: fa6ac2dc720ed43e40454b952526734accd45ea4
ms.sourcegitcommit: a328b9764abf5cd0c1c0a8c7def0c6e334da9a1d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477117"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="2dd7f-103">Clúster de resultados de conectores de Graph</span><span class="sxs-lookup"><span data-stu-id="2dd7f-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="2dd7f-104">Información general sobre el clúster de resultados de conectores de Graph (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="2dd7f-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="2dd7f-105">Con los clústeres de resultados de conectores de Graph, las empresas pueden buscar contenido de orígenes de datos de terceros en su vista predeterminada (la pestaña todos) en SharePoint y Office.com.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view (the All tab) in SharePoint and Office.com.</span></span>

<span data-ttu-id="2dd7f-106">Los clústeres de resultados ayudan a los usuarios a descubrir todo el contenido de terceros (previoulsy ligado a un único conector y al vertical) en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-106">Result clusters help users discover all third party content (previoulsy tied to a single connector and vertical) in one place.</span></span> <span data-ttu-id="2dd7f-107">Los resultados que se muestran en un clúster de resultados se agrupan en función de cómo el administrador del inquilino los configura en una presentación vertical de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-107">The results shown in a result cluster are grouped together based on how the tenant administrator configures them in a search vertical.</span></span>  

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="2dd7f-108">Cómo se seleccionan y se muestran los resultados de los conectores</span><span class="sxs-lookup"><span data-stu-id="2dd7f-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="2dd7f-109">Los resultados de conectores proporcionados en el clúster de resultados se derivan de presentaciones verticales de búsqueda individuales con contenido de conector.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="2dd7f-110">Cada presentación vertical de búsqueda proporciona un conjunto de resultados relevantes que se convierten en un clúster de resultados candidatos.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="2dd7f-111">Los resultados relevantes se eligen en función de la propiedad "title", el fragmento de código de resultado y el componente de contenido de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-111">Relevant results are chosen based on the "title" property, result snippet, and content component of each item.</span></span>

<span data-ttu-id="2dd7f-112">Para garantizar la detección del contenido de las presentaciones verticales de búsqueda, le recomendamos que proporcione títulos significativos para los elementos.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-112">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="2dd7f-113">Esto afecta positivamente el arbitraje de los candidatos del clúster de resultados y la probabilidad de que el contenido aparezca en un clúster de resultados.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-113">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="2dd7f-114">Por ejemplo, evite el uso de identificadores como valores para la propiedad "título" a menos que los usuarios estén usando identificadores para buscar contenido.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-114">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="2dd7f-115">La frecuencia con la que se muestra un clúster de resultados varía en factores como el número de presentaciones verticales de búsqueda que se configuran y el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-115">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="2dd7f-116">Al seleccionar o ignorar los resultados del clúster de resultados, se proporcionan implícitamente sugerencias que ajustarán la activación de los clústeres de resultados a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-116">By either selecting or ignoring result cluster results, you will implicitly provide hints that will adjust the triggering of result clusters over time.</span></span>

<span data-ttu-id="2dd7f-117">La experiencia de resultados de búsqueda para los elementos de conector que se muestran en el clúster de resultados es generada por el sistema y no utiliza diseños de resultados personalizados.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-117">The search result experience for connector items shown in your result cluster is system generated and does not use custom result layouts.</span></span> <span data-ttu-id="2dd7f-118">Debe declarar la propiedad "title" y el contenido del elemento durante el registro de conexión si desea que los resultados aparezcan en el clúster de resultados.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-118">You must declare the "title" property and item content during connection registration if you want results to appear in your result cluster.</span></span>

## <a name="enable-result-clusters"></a><span data-ttu-id="2dd7f-119">Habilitar clústeres de resultados</span><span class="sxs-lookup"><span data-stu-id="2dd7f-119">Enable result clusters</span></span>
  
<span data-ttu-id="2dd7f-120">La experiencia del clúster de resultados está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-120">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="2dd7f-121">Siga estos pasos para activar la experiencia en el nivel de organización:</span><span class="sxs-lookup"><span data-stu-id="2dd7f-121">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="2dd7f-122">En el [centro de administración de Microsoft 365](https://admin.microsoft.com/), vaya a **configuración**  >  **Buscar &**  >  vertical de **Personalización** de inteligencia  >  **Verticals**.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-122">In the [Microsoft 365 admin center](https://admin.microsoft.com/), go to **Settings** > **Search & intelligence** > **Customization** > **Verticals**.</span></span>  
2. <span data-ttu-id="2dd7f-123">Seleccione **todos** los resultados en vertical y, a continuación, habilite **Mostrar los resultados del conector**.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-123">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="2dd7f-124">Siga estos pasos para activar la experiencia en el nivel de sitio:</span><span class="sxs-lookup"><span data-stu-id="2dd7f-124">Follow these steps to turn on the experience at the site level:</span></span>

1. <span data-ttu-id="2dd7f-125">En el sitio de SharePoint en el que desea la experiencia del clúster de resultados, vaya a **configuración**.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-125">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="2dd7f-126">Vaya a **información del sitio** para > **ver toda la configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-126">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="2dd7f-127">Vaya a la sección de Microsoft Search y, a continuación, seleccione **configurar Microsoft Search para esta colección de sitios**.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-127">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="2dd7f-128">En el panel de navegación, vaya a **experiencia personalizada** y, a continuación, seleccione **vertical**.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-128">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="2dd7f-129">Seleccione **todos** los resultados en vertical y, a continuación, habilite **Mostrar los resultados del conector**.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-129">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="2dd7f-130">Ver la experiencia de clúster de resultados una vez habilitada</span><span class="sxs-lookup"><span data-stu-id="2dd7f-130">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="2dd7f-131">Después de activar la experiencia del clúster de resultados, puede tardar unos minutos antes de poder verlo.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-131">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="2dd7f-132">Si quiere la experiencia inmediatamente, puede anexar *cacheClear = true* a la dirección URL en SharePoint y Office.</span><span class="sxs-lookup"><span data-stu-id="2dd7f-132">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
