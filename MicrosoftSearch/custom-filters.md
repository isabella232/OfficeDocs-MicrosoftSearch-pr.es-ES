---
title: Administrar filtros personalizados
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Administrar filtros personalizados
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927390"
---
# <a name="create-custom-filters"></a><span data-ttu-id="cbe23-103">Crear filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="cbe23-103">Create custom Filters</span></span>

<span data-ttu-id="cbe23-104">Puede crear filtros para personalizar la experiencia de búsqueda que los usuarios ven cuando buscan en Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com)y Microsoft Search en [Bing](https://bing.com).</span><span class="sxs-lookup"><span data-stu-id="cbe23-104">You can create filters to customize the search experience that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="cbe23-105">Filtros permite a los usuarios refinar rápidamente el conjunto de resultados de la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cbe23-105">Filters lets users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="cbe23-106">Se puede crear un filtro personalizado dentro de un vertical basado en una propiedad de conexión.</span><span class="sxs-lookup"><span data-stu-id="cbe23-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="cbe23-107">Por ejemplo, puede crear un filtro **publicado en** para la conexión de ServiceNow dentro de una vertical personalizada.</span><span class="sxs-lookup"><span data-stu-id="cbe23-107">For example, you can create a **Published On** filter for ServiceNow connection inside a custom vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="cbe23-108">Consideraciones que se deben tener en cuenta</span><span class="sxs-lookup"><span data-stu-id="cbe23-108">Things to consider</span></span>

1. <span data-ttu-id="cbe23-109">Para crear un filtro personalizado en el origen de contenido de conexión, se proporcionan algunas funciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="cbe23-109">For creating custom filter on connection content source, some additional capabilities are provided:</span></span>
- <span data-ttu-id="cbe23-110">También puede crear un filtro en un alias para las propiedades de origen del conector</span><span class="sxs-lookup"><span data-stu-id="cbe23-110">You can also create filter on an alias to connector source properties</span></span>
- <span data-ttu-id="cbe23-111">En caso de que la vertical tenga varias conexiones, puede crear un filtro común a través de estas conexiones.</span><span class="sxs-lookup"><span data-stu-id="cbe23-111">In case your vertical has multiple connections then you can create a common filter across these connections.</span></span> <span data-ttu-id="cbe23-112">Para ello, cree el filtro en un alias común que contenga los alias de las propiedades de origen en distintas conexiones.</span><span class="sxs-lookup"><span data-stu-id="cbe23-112">This can be done by creating the filter on an common alias which aliases source properties across across different connections.</span></span> <span data-ttu-id="cbe23-113">Por ejemplo, puede crear un filtro de **autor** en un ServiceNow & una conexión JIRA mediante la creación de alias de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="cbe23-113">For example you can create an **Author** filter across a ServiceNow & a Jira connection by creating aliases as follows:</span></span>

| <span data-ttu-id="cbe23-114">Connection</span><span class="sxs-lookup"><span data-stu-id="cbe23-114">Connection</span></span> | <span data-ttu-id="cbe23-115">Propiedad</span><span class="sxs-lookup"><span data-stu-id="cbe23-115">Property</span></span> | <span data-ttu-id="cbe23-116">Alias</span><span class="sxs-lookup"><span data-stu-id="cbe23-116">Alias</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cbe23-117">Servicio ahora</span><span class="sxs-lookup"><span data-stu-id="cbe23-117">Service Now</span></span> | <span data-ttu-id="cbe23-118">Owner</span><span class="sxs-lookup"><span data-stu-id="cbe23-118">Owner</span></span> | <span data-ttu-id="cbe23-119">Autor</span><span class="sxs-lookup"><span data-stu-id="cbe23-119">Author</span></span> |
| <span data-ttu-id="cbe23-120">Jira</span><span class="sxs-lookup"><span data-stu-id="cbe23-120">Jira</span></span> | <span data-ttu-id="cbe23-121">Publisher</span><span class="sxs-lookup"><span data-stu-id="cbe23-121">Publisher</span></span> | <span data-ttu-id="cbe23-122">Autor</span><span class="sxs-lookup"><span data-stu-id="cbe23-122">Author</span></span> |

2. <span data-ttu-id="cbe23-123">Existen filtros en el ámbito de la vertical.</span><span class="sxs-lookup"><span data-stu-id="cbe23-123">Filters exist within the scope of the vertical.</span></span> <span data-ttu-id="cbe23-124">Ello</span><span class="sxs-lookup"><span data-stu-id="cbe23-124">Hence,</span></span>  
- <span data-ttu-id="cbe23-125">Si un filtro se crea en un vertical que se encuentra en el nivel de organización, el filtro solo estaría visible en el nivel de organización.</span><span class="sxs-lookup"><span data-stu-id="cbe23-125">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
- <span data-ttu-id="cbe23-126">Si un filtro se crea en un nivel vertical que se encuentra en el nivel del sitio, el filtro solo estaría visible en el nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="cbe23-126">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="steps-to-create-custom-filter"></a><span data-ttu-id="cbe23-127">Pasos para crear un filtro personalizado</span><span class="sxs-lookup"><span data-stu-id="cbe23-127">Steps to Create custom filter</span></span>

### <a name="create-filter-in-organizational-level-vertical"></a><span data-ttu-id="cbe23-128">Crear filtro a nivel de organización vertical:</span><span class="sxs-lookup"><span data-stu-id="cbe23-128">Create filter in organizational level vertical:</span></span>

<span data-ttu-id="cbe23-129">Para crear un filtro en Microsoft Search, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cbe23-129">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="cbe23-130">En el centro de administración de Microsoft 365, vaya a la página [vertical](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .</span><span class="sxs-lookup"><span data-stu-id="cbe23-130">In the Microsoft 365 admin center, go to the [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) page.</span></span>
2. <span data-ttu-id="cbe23-131">Crear o editar el vertical en el que desea crear el filtro</span><span class="sxs-lookup"><span data-stu-id="cbe23-131">Create/Edit the vertical in which you want to create the filter</span></span>
3. <span data-ttu-id="cbe23-132">Vaya al paso "filtros" del asistente.</span><span class="sxs-lookup"><span data-stu-id="cbe23-132">Navigate to the 'Filters' step in the wizard</span></span>
4. <span data-ttu-id="cbe23-133">Haga clic en "agregar filtro" y empiece después de agregar filtros, puede revisar y guardar el vertical.</span><span class="sxs-lookup"><span data-stu-id="cbe23-133">Click on 'Add Filter' and get started After adding filters, you can review and save the vertical.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cbe23-134">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="cbe23-134">Known Limitations</span></span>

1. <span data-ttu-id="cbe23-135">Actualmente, solo se pueden crear filtros en las propiedades administradas de tipo de fecha & cadena.</span><span class="sxs-lookup"><span data-stu-id="cbe23-135">You can currently create filters only on String & Date type managed properties.</span></span>
2. <span data-ttu-id="cbe23-136">No puede crear filtros jerárquicos</span><span class="sxs-lookup"><span data-stu-id="cbe23-136">You cannot create hierarchical filters</span></span>

## <a name="resources"></a><span data-ttu-id="cbe23-137">Recursos</span><span class="sxs-lookup"><span data-stu-id="cbe23-137">Resources</span></span>

[<span data-ttu-id="cbe23-138">Página personalizar resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="cbe23-138">Customize search result page</span></span>](customize-search-page.md)