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
ROBOTS: NOINDEX
description: Incluya aplicaciones basadas en navegador en los resultados de marcadores de Búsqueda de Microsoft
ms.openlocfilehash: d818ab8149032b4664adb90098700d4432a6fbb7
ms.sourcegitcommit: a7ca4c38d37fbdec58e002e42d865188939d0483
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2019
ms.locfileid: "35003123"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="4874a-103">Integrar PowerApps</span><span class="sxs-lookup"><span data-stu-id="4874a-103">Integrate PowerApps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4874a-104">Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing</span><span class="sxs-lookup"><span data-stu-id="4874a-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="4874a-105">Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se quitará.</span><span class="sxs-lookup"><span data-stu-id="4874a-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="4874a-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="4874a-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="4874a-107">[Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="4874a-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="4874a-108">Ayude a los usuarios a realizar tareas, como marcar las fechas de las vacaciones o registrar informes de gastos, integrando PowerApps existentes con los marcadores.</span><span class="sxs-lookup"><span data-stu-id="4874a-108">Help your users complete tasks, such as entering vacation time or reporting expenses, by adding existing PowerApps to your bookmarks.</span></span> <span data-ttu-id="4874a-109">Las PowerApps integradas aparecen en un resultado de marcador, por lo que no es necesario ir a otro sitio o abrir otra herramienta, lo que ahorra tiempo y esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="4874a-109">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="4874a-110">¿Qué son las PowerApps?</span><span class="sxs-lookup"><span data-stu-id="4874a-110">What are PowerApps?</span></span>

<span data-ttu-id="4874a-111">PowerApps es un servicio que le permite crear aplicaciones empresariales que funcionan en un explorador o en una tableta o teléfono sin necesidad de tener conocimientos de programación.</span><span class="sxs-lookup"><span data-stu-id="4874a-111">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="4874a-112">Más información:</span><span class="sxs-lookup"><span data-stu-id="4874a-112">Learn more:</span></span>
  
- <span data-ttu-id="4874a-113">
  [Aprendizaje guiado](https://docs.microsoft.com/es-ES/learn/browse/?products=powerapps)</span><span class="sxs-lookup"><span data-stu-id="4874a-113">[Guided Learning](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)</span></span>
    
- <span data-ttu-id="4874a-114">
  [Documentación](https://docs.microsoft.com/es-ES/powerapps/)</span><span class="sxs-lookup"><span data-stu-id="4874a-114">[Documentation](https://docs.microsoft.com/en-us/powerapps/)</span></span>
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="4874a-115">Agregar una PowerApp a un marcador</span><span class="sxs-lookup"><span data-stu-id="4874a-115">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="4874a-116">Las PowerApps funcionan en cualquier explorador y en cualquier dispositivo, y se agregan en menos de un minuto.</span><span class="sxs-lookup"><span data-stu-id="4874a-116">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="4874a-117">
  [Busque el Id. de aplicación para la PowerApp](https://docs.microsoft.com/es-ES/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que quiere integrar</span><span class="sxs-lookup"><span data-stu-id="4874a-117">Find the [App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) that you want to add.</span></span> 
    
2. <span data-ttu-id="4874a-118">En el portal de administración de Búsqueda de Microsoft, vaya a **Marcadores**</span><span class="sxs-lookup"><span data-stu-id="4874a-118">In the Microsoft Search Admin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="4874a-119">Agregue un marcador o busque un marcador existente al que quiere agregar una PowerApp</span><span class="sxs-lookup"><span data-stu-id="4874a-119">Add a bookmark or find an existing bookmark that you want to add a PowerApp to.</span></span>
    
4. <span data-ttu-id="4874a-120">En la configuración del marcador, haga clic en **PowerApp** y, después, haga clic en **Agregar una PowerApp**</span><span class="sxs-lookup"><span data-stu-id="4874a-120">In Bookmark settings, select Power App, and then Add a Power App.</span></span>
    
5. <span data-ttu-id="4874a-121">Escriba o pegue el Id. de la aplicación</span><span class="sxs-lookup"><span data-stu-id="4874a-121">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="4874a-122">Se agregan automáticamente el alto y ancho.</span><span class="sxs-lookup"><span data-stu-id="4874a-122">The height and width are automatically adjusted.</span></span> <span data-ttu-id="4874a-123">Los marcadores admiten la orientación vertical y horizontal, pero, de momento, no se puede cambiar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="4874a-123">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="4874a-124">La vista previa del marcador indica cómo se mostrará la PowerApp en el resultado de marcador</span><span class="sxs-lookup"><span data-stu-id="4874a-124">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="4874a-125">La PowerApp en la vista previa es completamente funcional para que sea fácil de probar y usar.</span><span class="sxs-lookup"><span data-stu-id="4874a-125">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="4874a-126">Haga clic en **Publicar**</span><span class="sxs-lookup"><span data-stu-id="4874a-126">Click **Publish**.</span></span>
    
<span data-ttu-id="4874a-127">Cuando un usuario de Búsqueda de Microsoft autorizado busca cualquiera de las palabras clave o palabras clave reservadas del marcador en Bing, la PowerApp aparecerá en el resultado del marcador.</span><span class="sxs-lookup"><span data-stu-id="4874a-127">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>
