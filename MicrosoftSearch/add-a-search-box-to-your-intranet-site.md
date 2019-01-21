---
title: Agregar un cuadro de búsqueda a su sitio de intranet
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
description: Obtener sugerencias de búsqueda relevantes y busque los resultados de trabajo más rápido mediante la adición de un cuadro de búsqueda de Microsoft Search a un sitio de la intranet o página.
ms.openlocfilehash: a27b4d79e8795cdd2749c12119709f97710061e7
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379344"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="91cbf-103">Agregar un cuadro de búsqueda a su sitio de intranet</span><span class="sxs-lookup"><span data-stu-id="91cbf-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="91cbf-104">Para agilizar el acceso a las sugerencias de búsqueda relevantes y los resultados del trabajo, agregue un cuadro de búsqueda de Microsoft Search a cualquier sitio de la intranet o página.</span><span class="sxs-lookup"><span data-stu-id="91cbf-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="91cbf-105">Agregar un cuadro de búsqueda a una página de intranet</span><span class="sxs-lookup"><span data-stu-id="91cbf-105">Add a search box to an intranet page</span></span>

<span data-ttu-id="91cbf-106">Es necesario agregar dos elementos a la página: un contenedor para el cuadro de búsqueda y la secuencia de comandos que se enciende.</span><span class="sxs-lookup"><span data-stu-id="91cbf-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="91cbf-107">En un sitio de SharePoint clásico, agregue un elemento Web Editor de secuencias de comandos y colocar la secuencia de comandos en ella.</span><span class="sxs-lookup"><span data-stu-id="91cbf-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="91cbf-108">Habilitar el cuadro de búsqueda para mobile</span><span class="sxs-lookup"><span data-stu-id="91cbf-108">Enable the search box for mobile</span></span>

<span data-ttu-id="91cbf-109">Para sitios de intranet o páginas disponibles para los usuarios móviles, agregar isMobile: True para el objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="91cbf-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox", 
        isMobile: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="91cbf-110">Poner el foco en el cuadro de búsqueda de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="91cbf-110">Put focus on the search box by default</span></span>

<span data-ttu-id="91cbf-111">Para ayudar a los usuarios a buscar con mayor rapidez, cuando las cargas de página o sitio sitúe el cursor en el cuadro de búsqueda mediante la adición de foco: True para el objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="91cbf-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        focus: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="91cbf-112">Use un iFrame para insertar un cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="91cbf-112">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="91cbf-113">Si la incrustación de una secuencia de comandos no es una opción para el sitio, use un iFrame para agregar el cuadro de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="91cbf-113">If embedding a script isn't an option for the site, use an iFrame to add the search box:</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
