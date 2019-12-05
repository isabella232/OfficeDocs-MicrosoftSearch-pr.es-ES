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
ROBOTS: NoIndex
description: Obtenga sugerencias de búsqueda relevantes y busque resultados de trabajo más rápidos agregando un cuadro de búsqueda de Microsoft Search a un sitio o una página de intranet.
ms.openlocfilehash: bcf1c6890415fdd9ae22f28cdf6d3dec1ffcaac4
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948910"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="e5059-103">Agregar un cuadro de búsqueda a su sitio de intranet</span><span class="sxs-lookup"><span data-stu-id="e5059-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="e5059-104">Para acceder rápidamente a las sugerencias de búsqueda y resultados de trabajo relevantes, agregue un cuadro de búsqueda de Microsoft Search a cualquier página o sitio de intranet.</span><span class="sxs-lookup"><span data-stu-id="e5059-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="e5059-105">Agregar un cuadro de búsqueda a una página de intranet</span><span class="sxs-lookup"><span data-stu-id="e5059-105">Add a search box to an intranet page</span></span>

<span data-ttu-id="e5059-106">Necesita agregar dos elementos a la página: un contenedor para el cuadro de búsqueda y la secuencia de comandos que la potencia.</span><span class="sxs-lookup"><span data-stu-id="e5059-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="e5059-107">En un sitio de SharePoint clásico, agregue un elemento web de Script Editor y coloque el script en él.</span><span class="sxs-lookup"><span data-stu-id="e5059-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="e5059-108">Habilitar el cuadro de búsqueda para dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="e5059-108">Enable the search box for mobile</span></span>

<span data-ttu-id="e5059-109">Para sitios o páginas de intranet disponibles para usuarios móviles, agregue isMobile: true al objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="e5059-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="e5059-110">Colocar el foco en el cuadro de búsqueda de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="e5059-110">Put focus on the search box by default</span></span>

<span data-ttu-id="e5059-111">Para ayudar a los usuarios a buscar con mayor rapidez, coloque el cursor en el cuadro de búsqueda cuando se cargue la página o sitio agregando focus: true al objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="e5059-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="e5059-112">Personalizar la apariencia del cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="e5059-112">Customize the appearance of the search box</span></span> 

<span data-ttu-id="e5059-113">Para ayudar a que el cuadro de búsqueda se adapte mejor con el estilo de su intranet, hay una gran variedad de opciones de configuración que puede usar.</span><span class="sxs-lookup"><span data-stu-id="e5059-113">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="e5059-114">Mezcle y combine opciones para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="e5059-114">Mix and match options to suit your needs.</span></span>

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: true
        iconColor: "#067FA6",                   // default: #067FA6
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work and the web"
                                                // when specified, text will be "Search the web and [Contoso]"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="e5059-115">Use un iFrame para insertar un cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="e5059-115">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="e5059-116">Si incrustar una secuencia de comandos no es una opción para el sitio, use un iFrame para agregar el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e5059-116">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="e5059-117">No podrá personalizar la apariencia del cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e5059-117">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```