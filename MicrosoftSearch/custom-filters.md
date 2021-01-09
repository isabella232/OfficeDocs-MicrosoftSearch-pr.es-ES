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
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790338"
---
# <a name="manage-custom-filters"></a><span data-ttu-id="1ae05-103">Administrar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="1ae05-103">Manage custom filters</span></span>

<span data-ttu-id="1ae05-104">Puede usar filtros para personalizar la experiencia de Búsqueda de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ae05-104">You can use filters to customize the Microsoft Search experience.</span></span> <span data-ttu-id="1ae05-105">Los filtros permiten a los usuarios refinar rápidamente el conjunto de resultados de su consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1ae05-105">Filters let users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="1ae05-106">Se puede crear un filtro personalizado dentro de una vertical en función de una propiedad de conexión.</span><span class="sxs-lookup"><span data-stu-id="1ae05-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="1ae05-107">Por ejemplo, puede crear un filtro **Publicado en** para la conexión ServiceNow dentro de una vertical.</span><span class="sxs-lookup"><span data-stu-id="1ae05-107">For example, you can create a **Published On** filter for ServiceNow connection inside a vertical.</span></span>

## <a name="create-a-filter-in-an-organizational-level-vertical"></a><span data-ttu-id="1ae05-108">Crear un filtro en una vertical de nivel organizativo</span><span class="sxs-lookup"><span data-stu-id="1ae05-108">Create a filter in an organizational level vertical</span></span>

<span data-ttu-id="1ae05-109">Para crear un filtro en la búsqueda de Microsoft, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1ae05-109">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="1ae05-110">En el Centro de administración de Microsoft 365, vaya [a Verticales.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)</span><span class="sxs-lookup"><span data-stu-id="1ae05-110">In the Microsoft 365 admin center, go to [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
1. <span data-ttu-id="1ae05-111">Crear o editar la vertical en la que desea crear el filtro</span><span class="sxs-lookup"><span data-stu-id="1ae05-111">Create/Edit the vertical in which you want to create the filter</span></span>
1. <span data-ttu-id="1ae05-112">Vaya al paso "Filtros" en el asistente</span><span class="sxs-lookup"><span data-stu-id="1ae05-112">Navigate to the 'Filters' step in the wizard</span></span>
1. <span data-ttu-id="1ae05-113">Haz clic en "Agregar filtro" y empieza a trabajar</span><span class="sxs-lookup"><span data-stu-id="1ae05-113">Click on 'Add Filter' and get started</span></span>
1. <span data-ttu-id="1ae05-114">Después de agregar filtros, puede revisar y guardar la vertical.</span><span class="sxs-lookup"><span data-stu-id="1ae05-114">After adding filters, you can review and save the vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="1ae05-115">Consideraciones que se deben tener en cuenta</span><span class="sxs-lookup"><span data-stu-id="1ae05-115">Things to consider</span></span>

1. <span data-ttu-id="1ae05-116">Existen capacidades de filtro adicionales en el contenido de la conexión.</span><span class="sxs-lookup"><span data-stu-id="1ae05-116">Additional filter capabilities exist on connection content.</span></span>

    - <span data-ttu-id="1ae05-117">También puede crear un filtro en un alias para las propiedades de origen del conector</span><span class="sxs-lookup"><span data-stu-id="1ae05-117">You can also create filter on an alias to connector source properties</span></span>
    - <span data-ttu-id="1ae05-118">Si una vertical tiene varias conexiones, puede crear un filtro común en estas conexiones.</span><span class="sxs-lookup"><span data-stu-id="1ae05-118">If a vertical has multiple connections, you can create a common filter across these connections.</span></span> <span data-ttu-id="1ae05-119">Esto se puede hacer creando el filtro en un alias común que aliase las propiedades de origen en las distintas conexiones.</span><span class="sxs-lookup"><span data-stu-id="1ae05-119">This can be done by creating the filter on an common alias which aliases source properties across across the different connections.</span></span> <span data-ttu-id="1ae05-120">Por ejemplo, puede crear un filtro **De** autor a través de una conexión ServiceNow y Jira mediante la creación de alias de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1ae05-120">For example you can create an **Author** filter across a ServiceNow and a Jira connection by creating aliases as follows:</span></span>

    | <span data-ttu-id="1ae05-121">Connection</span><span class="sxs-lookup"><span data-stu-id="1ae05-121">Connection</span></span> | <span data-ttu-id="1ae05-122">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1ae05-122">Property</span></span> | <span data-ttu-id="1ae05-123">Alias</span><span class="sxs-lookup"><span data-stu-id="1ae05-123">Alias</span></span> |
    | --- | --- | --- |
    | <span data-ttu-id="1ae05-124">Servicio ahora</span><span class="sxs-lookup"><span data-stu-id="1ae05-124">Service Now</span></span> | <span data-ttu-id="1ae05-125">Owner</span><span class="sxs-lookup"><span data-stu-id="1ae05-125">Owner</span></span> | <span data-ttu-id="1ae05-126">Autor</span><span class="sxs-lookup"><span data-stu-id="1ae05-126">Author</span></span> |
    | <span data-ttu-id="1ae05-127">Jira</span><span class="sxs-lookup"><span data-stu-id="1ae05-127">Jira</span></span> | <span data-ttu-id="1ae05-128">Publisher</span><span class="sxs-lookup"><span data-stu-id="1ae05-128">Publisher</span></span> | <span data-ttu-id="1ae05-129">Autor</span><span class="sxs-lookup"><span data-stu-id="1ae05-129">Author</span></span> |

1. <span data-ttu-id="1ae05-130">Los filtros existen en el ámbito de una vertical.</span><span class="sxs-lookup"><span data-stu-id="1ae05-130">Filters exist within the scope of a vertical.</span></span>

    - <span data-ttu-id="1ae05-131">Si se crea un filtro en una vertical que se encuentra en el nivel organizativo, el filtro solo será visible en el nivel de la organización.</span><span class="sxs-lookup"><span data-stu-id="1ae05-131">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
    - <span data-ttu-id="1ae05-132">Si se crea un filtro en una vertical que se encuentra en el nivel de sitio, el filtro solo será visible en el nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="1ae05-132">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1ae05-133">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="1ae05-133">Known Limitations</span></span>

1. <span data-ttu-id="1ae05-134">Actualmente, solo puede crear filtros en cadenas & propiedades administradas de tipo de fecha.</span><span class="sxs-lookup"><span data-stu-id="1ae05-134">You can currently create filters only on string & date type managed properties.</span></span>
1. <span data-ttu-id="1ae05-135">No puede crear filtros jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="1ae05-135">You cannot create hierarchical filters.</span></span>

## <a name="resources"></a><span data-ttu-id="1ae05-136">Recursos</span><span class="sxs-lookup"><span data-stu-id="1ae05-136">Resources</span></span>

[<span data-ttu-id="1ae05-137">Administrar los sectores verticales y los tipos de resultados</span><span class="sxs-lookup"><span data-stu-id="1ae05-137">Manage verticals and result types</span></span>](customize-search-page.md)
