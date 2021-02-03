---
title: Conector mediaWiki Graph para Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector mediaWiki Graph para Microsoft Search
ms.openlocfilehash: 9d9d7a1ef9aeaba079f8cccef1ec4a4836768e8d
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084987"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="d927c-103">Conector de MediaWiki Graph</span><span class="sxs-lookup"><span data-stu-id="d927c-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="d927c-104">El conector mediaWiki Graph permite a su organización detectar e indizar datos de un sitio wiki creado mediante el software MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="d927c-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="d927c-105">Este conector indiza el contenido especificado en Microsoft Search y admite rastreos periódicos para mantener el índice actualizado.</span><span class="sxs-lookup"><span data-stu-id="d927c-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="d927c-106">Lea el [**artículo sobre el programa de instalación del conector de Graph**](configure-connector.md) para comprender el proceso de configuración general de los conectores de Graph.</span><span class="sxs-lookup"><span data-stu-id="d927c-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="d927c-107">Este artículo está dirigido a cualquier persona que configure, ejecute y monitore un conector de ServiceNow Graph.</span><span class="sxs-lookup"><span data-stu-id="d927c-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="d927c-108">Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="d927c-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="d927c-109">En este artículo también se incluye información sobre [limitaciones.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="d927c-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="d927c-110">Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d927c-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="d927c-111">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="d927c-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="d927c-112">Paso 2: Nombrar la conexión</span><span class="sxs-lookup"><span data-stu-id="d927c-112">Step 2: Name the connection</span></span>

<span data-ttu-id="d927c-113">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="d927c-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="d927c-114">Paso 3: Configurar las opciones de conexión</span><span class="sxs-lookup"><span data-stu-id="d927c-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="d927c-115">Escriba su **dirección URL wiki** y elija el tipo de **autenticación** en el menú desplegable de opciones.</span><span class="sxs-lookup"><span data-stu-id="d927c-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="d927c-116">Las opciones son **None**, **Basic** y **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="d927c-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="d927c-117">Si elige **Básico como** tipo de autenticación,  deberá proporcionar el nombre de usuario y la contraseña **para** el sitio wiki.</span><span class="sxs-lookup"><span data-stu-id="d927c-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="d927c-118">Si elige **OAuth 2.0 AAD** como tipo de autenticación, deberá proporcionar el id. de recurso **de** la instalación wiki.</span><span class="sxs-lookup"><span data-stu-id="d927c-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="d927c-119">También deberá proporcionar el  identificador de cliente y el secreto de **cliente** generados en la página de registro de la aplicación AAD.</span><span class="sxs-lookup"><span data-stu-id="d927c-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="d927c-120">Paso 4: Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="d927c-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="d927c-121">El conector MediaWiki solo admite permisos de búsqueda visibles para **Todos.**</span><span class="sxs-lookup"><span data-stu-id="d927c-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="d927c-122">Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="d927c-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="d927c-123">Paso 5: Asignar etiquetas de propiedad</span><span class="sxs-lookup"><span data-stu-id="d927c-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="d927c-124">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="d927c-124">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="d927c-125">Paso 6: Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="d927c-125">Step 6: Manage schema</span></span>

<span data-ttu-id="d927c-126">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="d927c-126">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="d927c-127">Paso 7: Elegir la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="d927c-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="d927c-128">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="d927c-128">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="d927c-129">Paso 8: Revisar la conexión</span><span class="sxs-lookup"><span data-stu-id="d927c-129">Step 8: Review connection</span></span>

<span data-ttu-id="d927c-130">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="d927c-130">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="d927c-131">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="d927c-131">Limitations</span></span>

<span data-ttu-id="d927c-132">El conector MediaWiki tiene estas limitaciones en la versión preliminar:</span><span class="sxs-lookup"><span data-stu-id="d927c-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="d927c-133">Solo admite wikis basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="d927c-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="d927c-134">Solo admite Basic u OAuth 2.0 con Azure Active Directory o la autenticación de Azure.</span><span class="sxs-lookup"><span data-stu-id="d927c-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="d927c-135">No admite la selección de espacios de nombres para la indización.</span><span class="sxs-lookup"><span data-stu-id="d927c-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="d927c-136">Indiza solo los espacios de nombres Main, Category y File.</span><span class="sxs-lookup"><span data-stu-id="d927c-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="d927c-137">No admite listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="d927c-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="d927c-138">Por lo tanto, las páginas indizadas son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="d927c-138">Thus, indexed pages are visible to all users in the organization.</span></span>
