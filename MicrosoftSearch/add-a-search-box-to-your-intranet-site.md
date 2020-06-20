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
ms.openlocfilehash: af12ce4d17c2695e196f8e4d79ccd515f002f238
ms.sourcegitcommit: 92206ea179ec00b22496f6fd2866b5406449cf40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44798229"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="22c70-103">Agregar un cuadro de búsqueda a su sitio de intranet</span><span class="sxs-lookup"><span data-stu-id="22c70-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="22c70-104">Para proporcionar a los usuarios un acceso sencillo a los resultados de su organización, agregue un cuadro de búsqueda de Microsoft Search en Bing a cualquier sitio o página de la intranet.</span><span class="sxs-lookup"><span data-stu-id="22c70-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="22c70-105">Estas son algunas de las ventajas:</span><span class="sxs-lookup"><span data-stu-id="22c70-105">These are some of the benefits:</span></span>

- <span data-ttu-id="22c70-106">Un cuadro de búsqueda en el portal de SharePoint o de intranet proporciona un punto de entrada de confianza conocido para iniciar la búsqueda</span><span class="sxs-lookup"><span data-stu-id="22c70-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="22c70-107">Admite todos los exploradores Web principales, incluidos Google Chrome y Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="22c70-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="22c70-108">Solo aparecen las sugerencias de búsqueda de la organización, las sugerencias web nunca se incluyen</span><span class="sxs-lookup"><span data-stu-id="22c70-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="22c70-109">Lleva a los usuarios a una búsqueda de Microsoft en la página de resultados de trabajo de Bing, que excluye los anuncios y los resultados Web</span><span class="sxs-lookup"><span data-stu-id="22c70-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="22c70-110">La apariencia y el comportamiento del cuadro de búsqueda se controla</span><span class="sxs-lookup"><span data-stu-id="22c70-110">You control the appearance and behavior of the search box</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="22c70-111">Agregar un cuadro de búsqueda a una página de intranet</span><span class="sxs-lookup"><span data-stu-id="22c70-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="22c70-112">Necesita agregar dos elementos a la página: un contenedor para el cuadro de búsqueda y la secuencia de comandos que la potencia.</span><span class="sxs-lookup"><span data-stu-id="22c70-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="22c70-113">En un sitio de SharePoint clásico, agregue un elemento web de Script Editor y coloque el script en él.</span><span class="sxs-lookup"><span data-stu-id="22c70-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="22c70-114">Habilitar el cuadro de búsqueda para dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="22c70-114">Enable the search box for mobile</span></span>

<span data-ttu-id="22c70-115">Para sitios o páginas de intranet disponibles para usuarios móviles, agregue isMobile: true al objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="22c70-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="22c70-116">Colocar el foco en el cuadro de búsqueda de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="22c70-116">Put focus on the search box by default</span></span>

<span data-ttu-id="22c70-117">Para ayudar a los usuarios a buscar con mayor rapidez, coloque el cursor en el cuadro de búsqueda cuando se cargue la página o sitio agregando focus: true al objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="22c70-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="22c70-118">Personalizar la apariencia del cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="22c70-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="22c70-119">Para ayudar a que el cuadro de búsqueda se adapte mejor con el estilo de su intranet, hay una gran variedad de opciones de configuración que puede usar.</span><span class="sxs-lookup"><span data-stu-id="22c70-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="22c70-120">Mezcle y combine opciones para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="22c70-120">Mix and match options to suit your needs.</span></span>

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
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="22c70-121">Use un iFrame para insertar un cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="22c70-121">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="22c70-122">Si incrustar una secuencia de comandos no es una opción para el sitio, use un iFrame para agregar el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="22c70-122">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="22c70-123">No podrá personalizar la apariencia del cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="22c70-123">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
