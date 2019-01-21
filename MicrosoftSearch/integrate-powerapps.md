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
description: Incluir aplicaciones basadas en explorador en los resultados de marcadores para Microsoft Search
ms.openlocfilehash: d8d9d099848e719c86e0f3cadee330263566d243
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379262"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="46d8b-103">Integrar PowerApps</span><span class="sxs-lookup"><span data-stu-id="46d8b-103">Integrate PowerApps</span></span>

<span data-ttu-id="46d8b-p101">Ayudar a los usuarios completar tareas, como especificar el tiempo de vacaciones o los informes de gastos mediante la integración de PowerApps existente en sus marcadores. PowerApps integradas aparecen dentro de un resultado de marcador, lo que elimina la necesidad de ir a un sitio diferente o para abrir una herramienta independiente, los tiempos de guardados y esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="46d8b-p101">Help your users complete tasks, such as entering vacation time or reporting expenses by integrating existing PowerApps into your bookmarks. Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="46d8b-106">¿Qué PowerApps?</span><span class="sxs-lookup"><span data-stu-id="46d8b-106">What are PowerApps?</span></span>

<span data-ttu-id="46d8b-p102">PowerApps es un servicio que le permite crear aplicaciones empresariales que se ejecutan en un explorador o en un teléfono o tableta con ninguna experiencia en codificación necesaria. Aprende más:</span><span class="sxs-lookup"><span data-stu-id="46d8b-p102">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required. Learn more:</span></span>
  
- [<span data-ttu-id="46d8b-109">Autoaprendizaje</span><span class="sxs-lookup"><span data-stu-id="46d8b-109">Guided Learning</span></span>](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="46d8b-110">Documentación</span><span class="sxs-lookup"><span data-stu-id="46d8b-110">Documentation</span></span>](https://docs.microsoft.com/en-us/powerapps/)
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="46d8b-111">Agregar un PowerApp a un marcador</span><span class="sxs-lookup"><span data-stu-id="46d8b-111">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="46d8b-112">PowerApps trabajar en cualquier explorador y en cualquier dispositivo y tardar menos de un minuto para agregar.</span><span class="sxs-lookup"><span data-stu-id="46d8b-112">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="46d8b-113">[Busque el identificador de la aplicación para la PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que desea integrar</span><span class="sxs-lookup"><span data-stu-id="46d8b-113">[Find the App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate</span></span> 
    
2. <span data-ttu-id="46d8b-114">En el portal de Microsoft SearchAdmin, vaya a **marcadores**</span><span class="sxs-lookup"><span data-stu-id="46d8b-114">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="46d8b-115">Agregar un marcador o buscar un marcador existente que desee agregar un PowerApp a</span><span class="sxs-lookup"><span data-stu-id="46d8b-115">Add a bookmark or find an existing bookmark that you want to add a PowerApp to</span></span>
    
4. <span data-ttu-id="46d8b-116">En la configuración de marcador, haga clic en **Aplicación Power**y, a continuación, haga clic en **Agregar una aplicación de alimentación**</span><span class="sxs-lookup"><span data-stu-id="46d8b-116">In the bookmark settings, click **Power App**, and then click **Add a Power App**</span></span>
    
5. <span data-ttu-id="46d8b-117">Escriba o pegue el identificador de aplicación</span><span class="sxs-lookup"><span data-stu-id="46d8b-117">Enter or paste the App ID</span></span>
    
    <span data-ttu-id="46d8b-p103">El alto y el ancho se agregan automáticamente. Marcadores pueden admitir la orientación vertical y horizontal, pero actualmente no se puede cambiar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="46d8b-p103">The height and width are automatically added. Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="46d8b-120">La vista previa del marcador muestra cómo aparecerá la PowerApp en el resultado de marcador</span><span class="sxs-lookup"><span data-stu-id="46d8b-120">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="46d8b-121">Es totalmente funcional para que sea fácil probar y usar el PowerApp en la vista previa.</span><span class="sxs-lookup"><span data-stu-id="46d8b-121">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="46d8b-122">Haga clic en **Publicar**</span><span class="sxs-lookup"><span data-stu-id="46d8b-122">Click **Publish**</span></span>
    
<span data-ttu-id="46d8b-123">Cuando un usuario autorizado de Microsoft Search busca en Bing para cualquiera de las palabras clave o palabras clave reservadas del marcador, el PowerApp aparecerá en el resultado de marcador.</span><span class="sxs-lookup"><span data-stu-id="46d8b-123">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

