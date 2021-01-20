---
title: Conector MediaWiki para Microsoft Search
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
description: Configurar el conector MediaWiki para Microsoft Search
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905960"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="ffe23-103">Conector MediaWiki</span><span class="sxs-lookup"><span data-stu-id="ffe23-103">MediaWiki connector</span></span>

<span data-ttu-id="ffe23-104">Con el conector MediaWiki, su organización puede detectar e indizar datos de un sitio wiki creado mediante el software MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="ffe23-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="ffe23-105">Este conector indiza el contenido especificado en Microsoft Search y admite rastreos periódicos para mantener el índice actualizado.</span><span class="sxs-lookup"><span data-stu-id="ffe23-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="ffe23-106">Este artículo está dirigido a administradores de Microsoft 365 o a cualquier persona que configure, ejecute y monitore un conector de MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="ffe23-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="ffe23-107">Complementa las instrucciones generales proporcionadas en el artículo [Configurar el conector de Graph.](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="ffe23-107">It supplements the general instructions provided in the [Set up your Graph connector](configure-connector.md) article.</span></span> <span data-ttu-id="ffe23-108">Si aún no lo ha hecho, lea todo el artículo Configurar el conector de Graph para comprender el proceso de configuración general.</span><span class="sxs-lookup"><span data-stu-id="ffe23-108">If you have not already done so, read the entire Set up your Graph connector article to understand the general setup process.</span></span>

<span data-ttu-id="ffe23-109">Cada paso del proceso de configuración se muestra a continuación junto con una nota que indica que debe seguir las instrucciones generales de configuración u otras instrucciones que se aplican solo a conectores de MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="ffe23-109">Each step in the setup process is listed below along with either a note that indicates you should follow the general setup instructions OR other instructions that apply to only MediaWiki Graph connectors.</span></span> <span data-ttu-id="ffe23-110">En este artículo también se incluye información [sobre las limitaciones](#limitations) de los conectores de MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="ffe23-110">This article also includes information about [Limitations](#limitations) for MediaWiki Graph connectors.</span></span> 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ffe23-111">Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffe23-111">Step 1: Add a Graph connector in the Microsoft 365 admin center.</span></span>
<span data-ttu-id="ffe23-112">Siga las instrucciones generales de configuración.</span><span class="sxs-lookup"><span data-stu-id="ffe23-112">Follow the general setup instructions.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="ffe23-113">Paso 2: Asigne un nombre a la conexión.</span><span class="sxs-lookup"><span data-stu-id="ffe23-113">Step 2: Name the connection.</span></span>
<span data-ttu-id="ffe23-114">Siga las instrucciones generales de configuración.</span><span class="sxs-lookup"><span data-stu-id="ffe23-114">Follow the general setup instructions.</span></span>
 
## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="ffe23-115">Paso 3: Configurar las opciones de conexión.</span><span class="sxs-lookup"><span data-stu-id="ffe23-115">Step 3: Configure the connection settings.</span></span>
<span data-ttu-id="ffe23-116">Escriba su **dirección URL wiki** y elija el tipo de **autenticación** en el menú desplegable de opciones.</span><span class="sxs-lookup"><span data-stu-id="ffe23-116">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="ffe23-117">Las opciones son **None**, **Basic** y **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="ffe23-117">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="ffe23-118">Si elige **Básico como** tipo de autenticación,  deberá proporcionar el nombre de usuario y la contraseña **para** el sitio wiki.</span><span class="sxs-lookup"><span data-stu-id="ffe23-118">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="ffe23-119">Si elige **OAuth 2.0 AAD** como tipo de autenticación, deberá proporcionar el id. de recurso **de** la instalación wiki.</span><span class="sxs-lookup"><span data-stu-id="ffe23-119">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="ffe23-120">También deberá proporcionar el  identificador de cliente y el secreto de **cliente** generados en la página de registro de la aplicación de AAD.</span><span class="sxs-lookup"><span data-stu-id="ffe23-120">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span> 

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="ffe23-121">Paso 4: Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="ffe23-121">Step 4: Manage search permissions</span></span>
<span data-ttu-id="ffe23-122">El conector MediaWiki solo admite permisos de búsqueda visibles para **Todos.**</span><span class="sxs-lookup"><span data-stu-id="ffe23-122">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="ffe23-123">Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="ffe23-123">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="ffe23-124">Paso 5: Asignar etiquetas de propiedad</span><span class="sxs-lookup"><span data-stu-id="ffe23-124">Step 5: Assign property labels</span></span>
<span data-ttu-id="ffe23-125">Siga las instrucciones generales de configuración.</span><span class="sxs-lookup"><span data-stu-id="ffe23-125">Follow the general setup instructions.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="ffe23-126">Paso 6: Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="ffe23-126">Step 6: Manage schema</span></span>
<span data-ttu-id="ffe23-127">Siga las instrucciones generales de configuración.</span><span class="sxs-lookup"><span data-stu-id="ffe23-127">Follow the general setup instructions.</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="ffe23-128">Paso 7: Elegir la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="ffe23-128">Step 7: Choose refresh settings</span></span>
<span data-ttu-id="ffe23-129">Siga las instrucciones generales de configuración.</span><span class="sxs-lookup"><span data-stu-id="ffe23-129">Follow the general setup instructions.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="ffe23-130">Paso 8: Revisar la conexión</span><span class="sxs-lookup"><span data-stu-id="ffe23-130">Step 8: Review connection</span></span>
<span data-ttu-id="ffe23-131">Siga las instrucciones generales de configuración.</span><span class="sxs-lookup"><span data-stu-id="ffe23-131">Follow the general setup instructions.</span></span>

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="ffe23-132">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="ffe23-132">Limitations</span></span>
<span data-ttu-id="ffe23-133">El conector MediaWiki tiene estas limitaciones en la versión preliminar:</span><span class="sxs-lookup"><span data-stu-id="ffe23-133">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="ffe23-134">Solo admite wikis basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="ffe23-134">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="ffe23-135">Solo admite Basic u OAuth 2.0 con Azure Active Directory o la autenticación de Azure.</span><span class="sxs-lookup"><span data-stu-id="ffe23-135">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="ffe23-136">No admite la selección de espacios de nombres para la indización.</span><span class="sxs-lookup"><span data-stu-id="ffe23-136">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="ffe23-137">Indiza solo los espacios de nombres Main, Category y File.</span><span class="sxs-lookup"><span data-stu-id="ffe23-137">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="ffe23-138">No admite listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="ffe23-138">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="ffe23-139">Por lo tanto, las páginas indizadas son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="ffe23-139">Thus, indexed pages are visible to all users in the organization.</span></span>
