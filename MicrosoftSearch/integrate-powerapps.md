---
title: Integrar PowerApps
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
description: Incluya aplicaciones basadas en navegador en los resultados de marcadores de Búsqueda de Microsoft
ms.openlocfilehash: 96b409274e3fa06cef7dcc6f1c43360a3e6b9d34
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968390"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="0d6f2-103">Integrar PowerApps</span><span class="sxs-lookup"><span data-stu-id="0d6f2-103">Integrate PowerApps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d6f2-104">Búsqueda de Microsoft en la configuración de Bing ya está disponible en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d6f2-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0d6f2-105">Empiece por [asignar administradores de búsqueda](https://docs.microsoft.com/es-ES/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="0d6f2-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="0d6f2-106">Ayude a los usuarios a realizar tareas, como marcar las fechas de las vacaciones o registrar informes de gastos, integrando PowerApps existentes con los marcadores.</span><span class="sxs-lookup"><span data-stu-id="0d6f2-106">Help your users complete tasks, such as entering vacation time or reporting expenses, by adding existing PowerApps to your bookmarks.</span></span> <span data-ttu-id="0d6f2-107">Las PowerApps integradas aparecen en un resultado de marcador, por lo que no es necesario ir a otro sitio o abrir otra herramienta, lo que ahorra tiempo y esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="0d6f2-107">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="0d6f2-108">¿Qué son las PowerApps?</span><span class="sxs-lookup"><span data-stu-id="0d6f2-108">What are PowerApps?</span></span>

<span data-ttu-id="0d6f2-109">PowerApps es un servicio que le permite crear aplicaciones empresariales que funcionan en un explorador o en una tableta o teléfono sin necesidad de tener conocimientos de programación.</span><span class="sxs-lookup"><span data-stu-id="0d6f2-109">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="0d6f2-110">Más información:</span><span class="sxs-lookup"><span data-stu-id="0d6f2-110">Learn more:</span></span>
  
- <span data-ttu-id="0d6f2-111">
  [Aprendizaje guiado](https://docs.microsoft.com/es-ES/learn/browse/?products=powerapps)</span><span class="sxs-lookup"><span data-stu-id="0d6f2-111">[Guided Learning](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)</span></span>
    
- <span data-ttu-id="0d6f2-112">
  [Documentación](https://docs.microsoft.com/es-ES/powerapps/)</span><span class="sxs-lookup"><span data-stu-id="0d6f2-112">[Documentation](https://docs.microsoft.com/en-us/powerapps/)</span></span>
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="0d6f2-113">Agregar una PowerApp a un marcador</span><span class="sxs-lookup"><span data-stu-id="0d6f2-113">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="0d6f2-114">Las PowerApps funcionan en cualquier explorador y en cualquier dispositivo, y se agregan en menos de un minuto.</span><span class="sxs-lookup"><span data-stu-id="0d6f2-114">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="0d6f2-115">
  [Busque el Id. de aplicación para la PowerApp](https://docs.microsoft.com/es-ES/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que quiere integrar</span><span class="sxs-lookup"><span data-stu-id="0d6f2-115">Find the [App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) that you want to add.</span></span> 
    
2. <span data-ttu-id="0d6f2-116">En el portal de administración de Búsqueda de Microsoft, vaya a **Marcadores**</span><span class="sxs-lookup"><span data-stu-id="0d6f2-116">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="0d6f2-117">Agregue un marcador o busque un marcador existente al que quiere agregar una PowerApp</span><span class="sxs-lookup"><span data-stu-id="0d6f2-117">Add a bookmark or find an existing bookmark that you want to add a PowerApp to.</span></span>
    
4. <span data-ttu-id="0d6f2-118">En la configuración del marcador, haga clic en **PowerApp** y, después, haga clic en **Agregar una PowerApp**</span><span class="sxs-lookup"><span data-stu-id="0d6f2-118">In Bookmark settings, select Power App, and then Add a Power App.</span></span>
    
5. <span data-ttu-id="0d6f2-119">Escriba o pegue el Id. de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0d6f2-119">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="0d6f2-120">Se agregan automáticamente el alto y ancho.</span><span class="sxs-lookup"><span data-stu-id="0d6f2-120">The height and width are automatically adjusted.</span></span> <span data-ttu-id="0d6f2-121">Los marcadores admiten la orientación vertical y horizontal, pero, de momento, no se puede cambiar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="0d6f2-121">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="0d6f2-122">La vista previa del marcador indica cómo se mostrará la PowerApp en el resultado de marcador</span><span class="sxs-lookup"><span data-stu-id="0d6f2-122">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="0d6f2-123">La PowerApp en la vista previa es completamente funcional para que sea fácil de probar y usar.</span><span class="sxs-lookup"><span data-stu-id="0d6f2-123">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="0d6f2-124">Haga clic en **Publicar**</span><span class="sxs-lookup"><span data-stu-id="0d6f2-124">Click **Publish**.</span></span>
    
<span data-ttu-id="0d6f2-125">Cuando un usuario de Búsqueda de Microsoft autorizado busca cualquiera de las palabras clave o palabras clave reservadas del marcador en Bing, la PowerApp aparecerá en el resultado del marcador.</span><span class="sxs-lookup"><span data-stu-id="0d6f2-125">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

