---
title: Agregar un cuadro de búsqueda a su sitio de intranet
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
description: Obtenga sugerencias de búsqueda relevantes y busque resultados de trabajo más rápidos agregando un cuadro de búsqueda de Microsoft Search a un sitio o una página de intranet.
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612421"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="23e0f-103">Agregar un cuadro de búsqueda a su sitio de intranet</span><span class="sxs-lookup"><span data-stu-id="23e0f-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="23e0f-104">Para acceder rápidamente a las sugerencias de búsqueda y resultados de trabajo relevantes, agregue un cuadro de búsqueda de Microsoft Search a cualquier página o sitio de intranet.</span><span class="sxs-lookup"><span data-stu-id="23e0f-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="23e0f-105">Agregar un cuadro de búsqueda a una página de intranet</span><span class="sxs-lookup"><span data-stu-id="23e0f-105">Add a search box to your intranet site</span></span>

<span data-ttu-id="23e0f-106">Necesita agregar dos elementos a la página: un contenedor para el cuadro de búsqueda y la secuencia de comandos que la potencia.</span><span class="sxs-lookup"><span data-stu-id="23e0f-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="23e0f-107">En un sitio de SharePoint clásico, agregue un elemento web de Script Editor y coloque el script en él.</span><span class="sxs-lookup"><span data-stu-id="23e0f-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="23e0f-108">Habilitar el cuadro de búsqueda para dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="23e0f-108">Enable the search box for mobile</span></span>

<span data-ttu-id="23e0f-109">Para sitios o páginas de intranet disponibles para usuarios móviles, agregue isMobile: true al objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="23e0f-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="23e0f-110">Colocar el foco en el cuadro de búsqueda de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="23e0f-110">Put focus on the search box by default</span></span>

<span data-ttu-id="23e0f-111">Para ayudar a los usuarios a buscar con mayor rapidez, coloque el cursor en el cuadro de búsqueda cuando se cargue la página o sitio agregando focus: true al objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="23e0f-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="23e0f-112">Usar un iFrame para insertar un cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="23e0f-112">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="23e0f-113">Si incrustar una secuencia de comandos no es una opción para el sitio, use un iFrame para agregar el cuadro de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="23e0f-113">If embedding a script isn't an option for the site, use an iFrame to add the search box:</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
