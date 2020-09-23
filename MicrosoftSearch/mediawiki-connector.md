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
ms.openlocfilehash: d8aa4a99c353a80f7d3dcf768d8287200b17fdc6
ms.sourcegitcommit: be0c64845477127d73ee24dc727e4583ced3d0e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48206954"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="6200e-103">Conector MediaWiki</span><span class="sxs-lookup"><span data-stu-id="6200e-103">MediaWiki connector</span></span>

<span data-ttu-id="6200e-104">Con el conector MediaWiki, su organización puede detectar e indizar datos de un sitio wiki creado mediante software de MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="6200e-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="6200e-105">Este conector indiza contenido específico en Microsoft Search y admite rastreos periódicos para mantener actualizado el índice.</span><span class="sxs-lookup"><span data-stu-id="6200e-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="6200e-106">Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="6200e-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="6200e-107">Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="6200e-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="6200e-108">Conectarse a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="6200e-108">Connect to a data source</span></span>

<span data-ttu-id="6200e-109">Escriba la dirección URL de MediaWiki y las credenciales para autenticar la conexión.</span><span class="sxs-lookup"><span data-stu-id="6200e-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="6200e-110">Necesitará la siguiente información: **identificador de inquilino**, **identificador de recurso**, identificador de **cliente**y **secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="6200e-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="6200e-111">Administrar el esquema de búsqueda</span><span class="sxs-lookup"><span data-stu-id="6200e-111">Manage the search schema</span></span>

<span data-ttu-id="6200e-112">Una vez que se haya conectado correctamente, configure la asignación del esquema de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6200e-112">After successful connection, configure the search schema mapping.</span></span> <span data-ttu-id="6200e-113">Puede elegir las propiedades que se pueden **consultar**, realizar **búsquedas**y **recuperar**.</span><span class="sxs-lookup"><span data-stu-id="6200e-113">You can choose which properties to make **queryable**, **searchable**, and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="6200e-114">Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="6200e-114">Manage search permissions</span></span>

<span data-ttu-id="6200e-115">El conector de MediaWiki solo admite permisos de búsqueda visibles para **todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="6200e-115">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="6200e-116">Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="6200e-116">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="6200e-117">Establecer la programación de actualización</span><span class="sxs-lookup"><span data-stu-id="6200e-117">Set the refresh schedule</span></span>

<span data-ttu-id="6200e-118">Esta programación actualiza los datos indizados, por lo que los cambios en el sitio wiki se reflejan en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="6200e-118">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="6200e-119">Todas las páginas nuevas, las páginas eliminadas, el contenido de la página o los cambios de metadatos aparecen en los resultados de la búsqueda después del intervalo de actualización especificado.</span><span class="sxs-lookup"><span data-stu-id="6200e-119">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="6200e-120">El tiempo de rastreo depende del tamaño de la wiki.</span><span class="sxs-lookup"><span data-stu-id="6200e-120">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="6200e-121">Actualmente el conector rastrea alrededor de 50 páginas por minuto.</span><span class="sxs-lookup"><span data-stu-id="6200e-121">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="6200e-122">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="6200e-122">Limitations</span></span>

<span data-ttu-id="6200e-123">El conector de MediaWiki tiene estas limitaciones en la versión preliminar:</span><span class="sxs-lookup"><span data-stu-id="6200e-123">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="6200e-124">Solo admite wikis basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="6200e-124">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="6200e-125">Solo admite Basic o OAuth 2,0 con Azure Active Directory o Azure Authentication.</span><span class="sxs-lookup"><span data-stu-id="6200e-125">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="6200e-126">No admite la selección de espacio de nombres para la indización.</span><span class="sxs-lookup"><span data-stu-id="6200e-126">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="6200e-127">Solo indiza los espacios de nombres **principal**, de **categoría**y de **archivo** .</span><span class="sxs-lookup"><span data-stu-id="6200e-127">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="6200e-128">No es compatible con las listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="6200e-128">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="6200e-129">Por lo tanto, las páginas indizadas son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="6200e-129">Thus, indexed pages are visible to all users in the organization.</span></span>
