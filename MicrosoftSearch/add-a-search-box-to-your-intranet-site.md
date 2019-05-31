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
ROBOTS: NoIndex
description: Obtenga sugerencias de búsqueda relevantes y busque resultados de trabajo más rápidos agregando un cuadro de búsqueda de Microsoft Search a un sitio o una página de intranet.
ms.openlocfilehash: 867282393c7a4bffa63363a3455e4f1543c7f8a1
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590697"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="b8ac3-103">Agregar un cuadro de búsqueda a su sitio de intranet</span><span class="sxs-lookup"><span data-stu-id="b8ac3-103">Add a search box to your intranet site</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8ac3-104">Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing</span><span class="sxs-lookup"><span data-stu-id="b8ac3-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="b8ac3-105">Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se eliminará.</span><span class="sxs-lookup"><span data-stu-id="b8ac3-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="b8ac3-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="b8ac3-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="b8ac3-107">[Introducción a Microsoft Search (Búsqueda de Microsoft)](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="b8ac3-107">Overview of Microsoft Search</span></span>

<span data-ttu-id="b8ac3-108">Para acceder rápidamente a las sugerencias de búsqueda y resultados de trabajo relevantes, agregue un cuadro de búsqueda de Microsoft Search a cualquier página o sitio de intranet.</span><span class="sxs-lookup"><span data-stu-id="b8ac3-108">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="b8ac3-109">Agregar un cuadro de búsqueda a una página de intranet</span><span class="sxs-lookup"><span data-stu-id="b8ac3-109">Add a search box to an intranet page</span></span>

<span data-ttu-id="b8ac3-110">Necesita agregar dos elementos a la página: un contenedor para el cuadro de búsqueda y la secuencia de comandos que la potencia.</span><span class="sxs-lookup"><span data-stu-id="b8ac3-110">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="b8ac3-111">En un sitio de SharePoint clásico, agregue un elemento web de Script Editor y coloque el script en él.</span><span class="sxs-lookup"><span data-stu-id="b8ac3-111">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="b8ac3-112">Habilitar el cuadro de búsqueda para dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="b8ac3-112">Enable the search box for mobile</span></span>

<span data-ttu-id="b8ac3-113">Para sitios o páginas de intranet disponibles para usuarios móviles, agregue isMobile: true al objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="b8ac3-113">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="b8ac3-114">Colocar el foco en el cuadro de búsqueda de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="b8ac3-114">Put focus on the search box by default</span></span>

<span data-ttu-id="b8ac3-115">Para ayudar a los usuarios a buscar con mayor rapidez, coloque el cursor en el cuadro de búsqueda cuando se cargue la página o sitio agregando focus: true al objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="b8ac3-115">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="b8ac3-116">Personalizar la apariencia del cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="b8ac3-116">Customize the appearance of the search box</span></span> 

<span data-ttu-id="b8ac3-117">Para ayudar a que el cuadro de búsqueda se adapte mejor con el estilo de su intranet, hay una gran variedad de opciones de configuración que puede usar.</span><span class="sxs-lookup"><span data-stu-id="b8ac3-117">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="b8ac3-118">Mezcle y combine opciones para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="b8ac3-118">Mix and match options to suit your needs.</span></span>

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

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="b8ac3-119">Use un iFrame para insertar un cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="b8ac3-119">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="b8ac3-120">Si incrustar una secuencia de comandos no es una opción para el sitio, use un iFrame para agregar el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b8ac3-120">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="b8ac3-121">No podrá personalizar la apariencia del cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b8ac3-121">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```