---
title: Integrar Power Apps
ms.author: dawholl
author: dawholl
manager: kellis
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
ms.openlocfilehash: 52fa78c54ab6db74ef1e3679d3d32151a3f5ac10
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031705"
---
# <a name="integrate-power-apps-in-microsoft-search-bookmarks"></a><span data-ttu-id="6c0c6-103">Integrar Power Apps en marcadores de Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="6c0c6-103">Integrate Power Apps in Microsoft Search bookmarks</span></span>
   
<span data-ttu-id="6c0c6-104">Ayude a los usuarios a completar tareas, como especificar el tiempo de vacaciones o informar de los gastos, integrando las [Aplicaciones de Microsoft Power existentes](https://products.office.com/business/microsoft-powerapps) en los marcadores de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-104">Help your users complete tasks, like entering vacation time or reporting expenses, by integrating existing [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) into your Microsoft Search bookmarks.</span></span> <span data-ttu-id="6c0c6-105">Power Apps integradas aparecen dentro de un resultado de marcador, lo que elimina la necesidad de ir a un sitio diferente o abrir una herramienta independiente, lo que ahorra tiempo y esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-105">Integrated Power Apps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-power-apps"></a><span data-ttu-id="6c0c6-106">¿Qué son Power Apps?</span><span class="sxs-lookup"><span data-stu-id="6c0c6-106">What are Power Apps?</span></span>

<span data-ttu-id="6c0c6-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) es un servicio que te permite crear aplicaciones empresariales que se ejecutan en un explorador o en un teléfono o tableta sin necesidad de experiencia de codificación.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="6c0c6-108">Más información:</span><span class="sxs-lookup"><span data-stu-id="6c0c6-108">Learn more:</span></span>
  
- [<span data-ttu-id="6c0c6-109">Aprendizaje guiado</span><span class="sxs-lookup"><span data-stu-id="6c0c6-109">Guided Learning</span></span>](/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="6c0c6-110">Documentación</span><span class="sxs-lookup"><span data-stu-id="6c0c6-110">Documentation</span></span>](/powerapps/)
    
## <a name="add-a-power-app-to-a-bookmark"></a><span data-ttu-id="6c0c6-111">Agregar una power app a un marcador</span><span class="sxs-lookup"><span data-stu-id="6c0c6-111">Add a Power App to a bookmark</span></span>

<span data-ttu-id="6c0c6-112">[Power Apps( https://products.office.com/business/microsoft-powerapps) trabajar en cualquier explorador y en cualquier dispositivo y tardar menos de un minuto en agregarse.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-112">[Power Apps(https://products.office.com/business/microsoft-powerapps) work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="6c0c6-113">[Busca el id. de la aplicación para power app](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que quieres integrar.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-113">[Find the App ID for the Power App](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate.</span></span>
    
2. <span data-ttu-id="6c0c6-114">En el Centro de [](https://admin.microsoft.com)administración de Microsoft 365, vaya a **Marcadores**.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-114">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Bookmarks**.</span></span>
    
3. <span data-ttu-id="6c0c6-115">Agrega un marcador o busca un marcador existente al que quieras agregar una Power App.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-115">Add a bookmark or find an existing bookmark that you want to add a Power App to.</span></span>
    
4. <span data-ttu-id="6c0c6-116">En la configuración del marcador, **seleccione Power App** y, a continuación, seleccione Agregar una aplicación **power**.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-116">In the bookmark settings, select **Power App**, and then select **Add a Power App**.</span></span>
    
5. <span data-ttu-id="6c0c6-117">Escriba o pegue el App ID.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-117">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="6c0c6-118">El alto y el ancho se agregan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-118">The height and width are automatically added.</span></span> <span data-ttu-id="6c0c6-119">Los marcadores admite la orientación vertical y horizontal, pero, de momento, no se puede cambiar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="6c0c6-120">La vista previa del marcador muestra cómo aparecerá Power App en el resultado del marcador.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-120">The bookmark preview shows how the Power App will appear in the bookmark result.</span></span>
    
    <span data-ttu-id="6c0c6-121">Power App en la vista previa es totalmente funcional para que sea fácil de probar y usar.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-121">The Power App in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="6c0c6-122">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-122">Select **Publish**.</span></span>
    
<span data-ttu-id="6c0c6-123">Cuando un usuario autorizado de Microsoft Search busca en [Bing](https://Bing.com) alguna de las palabras clave o palabras clave reservadas del marcador, Power App aparecerá en el resultado del marcador.</span><span class="sxs-lookup"><span data-stu-id="6c0c6-123">When an authorized Microsoft Search user searches on [Bing](https://Bing.com) for any of the bookmark's keywords or reserved keywords, the Power App will appear in the bookmark result.</span></span>