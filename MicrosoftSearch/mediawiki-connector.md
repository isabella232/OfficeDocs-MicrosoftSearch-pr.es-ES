---
title: Conector de MediaWiki Graph para Microsoft Search
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
description: Configurar el conector de MediaWiki Graph para Microsoft Search
ms.openlocfilehash: 5922cf76aa112430f9f6e857066acd054182058c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031696"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="7c70b-103">Conector de MediaWiki Graph</span><span class="sxs-lookup"><span data-stu-id="7c70b-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="7c70b-104">El conector de MediaWiki Graph permite a su organización detectar e indizar datos de un wiki creado mediante el software MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="7c70b-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="7c70b-105">Este conector indiza el contenido especificado en Microsoft Search y admite rastreos periódicos para mantener el índice actualizado.</span><span class="sxs-lookup"><span data-stu-id="7c70b-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="7c70b-106">Lea el [**artículo Setup for your Graph connector para**](configure-connector.md) comprender las instrucciones generales de configuración de los conectores de Graph.</span><span class="sxs-lookup"><span data-stu-id="7c70b-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="7c70b-107">Este artículo está dirigido a cualquier persona que configure, ejecute y monitore un conector de MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="7c70b-107">This article is for anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="7c70b-108">Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="7c70b-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="7c70b-109">En este artículo también se incluye información sobre [limitaciones](#limitations).</span><span class="sxs-lookup"><span data-stu-id="7c70b-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="7c70b-110">Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c70b-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="7c70b-111">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7c70b-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="7c70b-112">Paso 2: Nombrar la conexión</span><span class="sxs-lookup"><span data-stu-id="7c70b-112">Step 2: Name the connection</span></span>

<span data-ttu-id="7c70b-113">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7c70b-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="7c70b-114">Paso 3: Configurar las opciones de conexión</span><span class="sxs-lookup"><span data-stu-id="7c70b-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="7c70b-115">Escribe la **dirección URL wiki** y elige el tipo de **autenticación** en el menú desplegable de opciones.</span><span class="sxs-lookup"><span data-stu-id="7c70b-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="7c70b-116">Las opciones **son None**, **Basic** y **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="7c70b-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="7c70b-117">Si elige Básico **como** tipo de autenticación,  deberá proporcionar el nombre de usuario y **la contraseña** para el wiki.</span><span class="sxs-lookup"><span data-stu-id="7c70b-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="7c70b-118">Si elige **OAuth 2.0 AAD** como tipo de autenticación, deberá proporcionar el **id.** de recurso de la instalación wiki.</span><span class="sxs-lookup"><span data-stu-id="7c70b-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="7c70b-119">También deberá proporcionar el  identificador de cliente y el secreto de **cliente generados** en la página de registro de la aplicación de AAD.</span><span class="sxs-lookup"><span data-stu-id="7c70b-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="7c70b-120">Paso 4: Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="7c70b-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="7c70b-121">El conector de MediaWiki solo admite permisos de búsqueda visibles para **Todos**.</span><span class="sxs-lookup"><span data-stu-id="7c70b-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="7c70b-122">Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="7c70b-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="7c70b-123">Paso 5: Asignar etiquetas de propiedades</span><span class="sxs-lookup"><span data-stu-id="7c70b-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="7c70b-124">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7c70b-124">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="7c70b-125">Paso 6: Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="7c70b-125">Step 6: Manage schema</span></span>

<span data-ttu-id="7c70b-126">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7c70b-126">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="7c70b-127">Paso 7: Elegir la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="7c70b-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="7c70b-128">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7c70b-128">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="7c70b-129">Paso 8: Revisar la conexión</span><span class="sxs-lookup"><span data-stu-id="7c70b-129">Step 8: Review connection</span></span>

<span data-ttu-id="7c70b-130">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7c70b-130">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="7c70b-131">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="7c70b-131">Limitations</span></span>

<span data-ttu-id="7c70b-132">El conector de MediaWiki tiene estas limitaciones en la versión preliminar:</span><span class="sxs-lookup"><span data-stu-id="7c70b-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="7c70b-133">Solo admite wikis basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="7c70b-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="7c70b-134">Solo admite Basic o OAuth 2.0 con Azure Active Directory o la autenticación de Azure.</span><span class="sxs-lookup"><span data-stu-id="7c70b-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="7c70b-135">No admite la selección de espacios de nombres para la indización.</span><span class="sxs-lookup"><span data-stu-id="7c70b-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="7c70b-136">Indiza solo los espacios de nombres Main, Category y File.</span><span class="sxs-lookup"><span data-stu-id="7c70b-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="7c70b-137">No admite listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="7c70b-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="7c70b-138">Por lo tanto, las páginas indizadas son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="7c70b-138">Thus, indexed pages are visible to all users in the organization.</span></span>