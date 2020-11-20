---
title: Conector de MediaWiki para Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de MediaWiki para Microsoft Search
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367644"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="e7345-103">Conector MediaWiki</span><span class="sxs-lookup"><span data-stu-id="e7345-103">MediaWiki connector</span></span>

<span data-ttu-id="e7345-104">Con el conector MediaWiki, su organización puede detectar e indizar datos de un sitio wiki creado mediante software de MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="e7345-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="e7345-105">Este conector indiza contenido específico en Microsoft Search y admite rastreos periódicos para mantener actualizado el índice.</span><span class="sxs-lookup"><span data-stu-id="e7345-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="e7345-106">Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="e7345-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="e7345-107">Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="e7345-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="e7345-108">Conectarse a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="e7345-108">Connect to a data source</span></span>

<span data-ttu-id="e7345-109">Escriba la dirección URL de MediaWiki y las credenciales para autenticar la conexión.</span><span class="sxs-lookup"><span data-stu-id="e7345-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="e7345-110">Necesitará la siguiente información: **identificador de inquilino**, **identificador de recurso**, identificador de **cliente** y **secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="e7345-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="e7345-111">Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="e7345-111">Manage search permissions</span></span>

<span data-ttu-id="e7345-112">El conector de MediaWiki solo admite permisos de búsqueda visibles para **todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e7345-112">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="e7345-113">Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="e7345-113">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="e7345-114">Asignar etiquetas de propiedad</span><span class="sxs-lookup"><span data-stu-id="e7345-114">Assign property labels</span></span>

<span data-ttu-id="e7345-115">Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones.</span><span class="sxs-lookup"><span data-stu-id="e7345-115">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="e7345-116">Aunque este paso no es obligatorio, tener algunas etiquetas de propiedades mejorará la relevancia de la búsqueda y garantizará resultados de búsqueda más precisos para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="e7345-116">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="e7345-117">Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="e7345-117">Manage schema</span></span>

<span data-ttu-id="e7345-118">En la pantalla **administrar esquema** , tiene la opción de cambiar los atributos de esquema (**consultable**, **búsquedas**, **recuperables** y **refinables**) asociados con las propiedades, agregar alias opcionales y elegir la propiedad de **contenido** .</span><span class="sxs-lookup"><span data-stu-id="e7345-118">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="e7345-119">Establecer la programación de actualización</span><span class="sxs-lookup"><span data-stu-id="e7345-119">Set the refresh schedule</span></span>

<span data-ttu-id="e7345-120">Esta programación actualiza los datos indizados, por lo que los cambios en el sitio wiki se reflejan en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="e7345-120">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="e7345-121">Todas las páginas nuevas, las páginas eliminadas, el contenido de la página o los cambios de metadatos aparecen en los resultados de la búsqueda después del intervalo de actualización especificado.</span><span class="sxs-lookup"><span data-stu-id="e7345-121">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="e7345-122">El tiempo de rastreo depende del tamaño de la wiki.</span><span class="sxs-lookup"><span data-stu-id="e7345-122">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="e7345-123">Actualmente el conector rastrea alrededor de 50 páginas por minuto.</span><span class="sxs-lookup"><span data-stu-id="e7345-123">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="e7345-124">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="e7345-124">Limitations</span></span>

<span data-ttu-id="e7345-125">El conector de MediaWiki tiene estas limitaciones en la versión preliminar:</span><span class="sxs-lookup"><span data-stu-id="e7345-125">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="e7345-126">Solo admite wikis basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="e7345-126">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="e7345-127">Solo admite Basic o OAuth 2,0 con Azure Active Directory o Azure Authentication.</span><span class="sxs-lookup"><span data-stu-id="e7345-127">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="e7345-128">No admite la selección de espacio de nombres para la indización.</span><span class="sxs-lookup"><span data-stu-id="e7345-128">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="e7345-129">Solo indiza los espacios de nombres **principal**, de **categoría** y de **archivo** .</span><span class="sxs-lookup"><span data-stu-id="e7345-129">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="e7345-130">No es compatible con las listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="e7345-130">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="e7345-131">Por lo tanto, las páginas indizadas son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="e7345-131">Thus, indexed pages are visible to all users in the organization.</span></span>
