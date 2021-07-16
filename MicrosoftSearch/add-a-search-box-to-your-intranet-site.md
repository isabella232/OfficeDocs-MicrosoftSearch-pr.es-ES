---
title: Agregar un cuadro de búsqueda a su sitio de intranet
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
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: Obtenga sugerencias de búsqueda relevantes y busque resultados de trabajo más rápido agregando un cuadro de Búsqueda de Microsoft de búsqueda a su sitio o página de intranet.
ms.openlocfilehash: 7d9ca4be8d3be27a7549ffb940d6dc55b3763baf
ms.sourcegitcommit: 38a0f09596c2bca0e12bf4cada7b4c64fd4c48e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53449065"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="1afe8-103">Agregar un cuadro de búsqueda a su sitio de intranet</span><span class="sxs-lookup"><span data-stu-id="1afe8-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="1afe8-104">Para proporcionar a los usuarios un acceso fácil a los resultados de su organización, agregue un Búsqueda de Microsoft en el Bing de búsqueda a cualquier sitio o página de intranet.</span><span class="sxs-lookup"><span data-stu-id="1afe8-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="1afe8-105">Estos son algunos de los beneficios:</span><span class="sxs-lookup"><span data-stu-id="1afe8-105">These are some of the benefits:</span></span>

- <span data-ttu-id="1afe8-106">Un cuadro de búsqueda en el portal SharePoint intranet proporciona un punto de entrada familiar y de confianza para empezar a buscar</span><span class="sxs-lookup"><span data-stu-id="1afe8-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="1afe8-107">Admite todos los exploradores web principales, incluidos Google Chrome y Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1afe8-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="1afe8-108">Solo aparecen sugerencias de búsqueda de su organización, las sugerencias web nunca se incluyen</span><span class="sxs-lookup"><span data-stu-id="1afe8-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="1afe8-109">Lleva a los usuarios a un Búsqueda de Microsoft en Bing de resultados de trabajo, que excluye anuncios y resultados web</span><span class="sxs-lookup"><span data-stu-id="1afe8-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="1afe8-110">Puede controlar la apariencia y el comportamiento del cuadro de búsqueda, incluida la capacidad de desembarco de usuarios en una vertical predeterminada o una vertical personalizada que haya creado.</span><span class="sxs-lookup"><span data-stu-id="1afe8-110">You control the appearance and behavior of the search box, including the ability to land users on a default vertical or a custom vertical you've created</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="1afe8-111">Agregar un cuadro de búsqueda a una página de intranet</span><span class="sxs-lookup"><span data-stu-id="1afe8-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="1afe8-112">Necesita agregar dos elementos a la página: un contenedor para el cuadro de búsqueda y la secuencia de comandos que la potencia.</span><span class="sxs-lookup"><span data-stu-id="1afe8-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="1afe8-113">En un sitio de SharePoint clásico, agregue un elemento web de Script Editor y coloque el script en él.</span><span class="sxs-lookup"><span data-stu-id="1afe8-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="1afe8-114">Habilitar el cuadro de búsqueda para dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="1afe8-114">Enable the search box for mobile</span></span>

<span data-ttu-id="1afe8-115">Para sitios o páginas de intranet disponibles para usuarios móviles, agregue isMobile: true al objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="1afe8-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="1afe8-116">Colocar el foco en el cuadro de búsqueda de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="1afe8-116">Put focus on the search box by default</span></span>

<span data-ttu-id="1afe8-117">Para ayudar a los usuarios a buscar con mayor rapidez, coloque el cursor en el cuadro de búsqueda cuando se cargue la página o sitio agregando focus: true al objeto de configuración:</span><span class="sxs-lookup"><span data-stu-id="1afe8-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="1afe8-118">Personalizar la apariencia del cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1afe8-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="1afe8-119">Para ayudar a que el cuadro de búsqueda se adapte mejor con el estilo de su intranet, hay una gran variedad de opciones de configuración que puede usar.</span><span class="sxs-lookup"><span data-stu-id="1afe8-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="1afe8-120">Mezcle y combine opciones para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="1afe8-120">Mix and match options to suit your needs.</span></span>

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: false
        iconColor: "#067FA6",                   // default: #067FA6
        title: "Search box",                    // default: "Search box"
        vertical: "Person-people",              // default: not specified, search box directs to the All vertical on the WORK results page
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="direct-users-to-a-default-or-custom-vertical"></a><span data-ttu-id="1afe8-121">Dirigir a los usuarios a una vertical predeterminada o personalizada</span><span class="sxs-lookup"><span data-stu-id="1afe8-121">Direct users to a default or custom vertical</span></span>

<span data-ttu-id="1afe8-122">Para facilitar la integración entre las aplicaciones de línea de negocio o los sitios de intranet y los resultados del trabajo, también puede personalizar el cuadro de búsqueda especificando una vertical predeterminada o personalizada en la que los usuarios deben aterrizar cuando hacen clic en una sugerencia de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1afe8-122">To provide easy integration between your line-of-business apps or intranet sites and your work results, you can also customize the search box by specifying a default or custom vertical that users should land on when they click a search suggestion.</span></span>

<span data-ttu-id="1afe8-123">Use la opción vertical en bfbSearchBoxConfig para definir la vertical que desee.</span><span class="sxs-lookup"><span data-stu-id="1afe8-123">Use the vertical option in bfbSearchBoxConfig to define the vertical you want.</span></span> <span data-ttu-id="1afe8-124">Por ejemplo, si desea que los usuarios siempre aterrice en la vertical Sitios, una de las verticales predeterminadas, use el valor "Site-sites".</span><span class="sxs-lookup"><span data-stu-id="1afe8-124">For example, if you want users to always land on the Sites vertical, one of the default verticals, use the value "Site-sites".</span></span>

:::image type="content" alt-text="Captura de pantalla de la página de resultados del trabajo Búsqueda de Microsoft en Bing muestra los resultados verticales de sitios y la dirección URL." source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

<span data-ttu-id="1afe8-126">Para verticales personalizados, use el hash al final de la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="1afe8-126">For custom verticals, use the hash at the end of the URL.</span></span> <span data-ttu-id="1afe8-127">Puede encontrar estos valores buscando en la página de trabajo de Bing, haciendo clic en una etiqueta vertical y copiando el valor después del signo de número (#).</span><span class="sxs-lookup"><span data-stu-id="1afe8-127">You can find these values by searching from the work page on Bing, clicking a vertical label, and copying the value after the number sign (#).</span></span>

:::image type="content" alt-text="Captura de pantalla de la página de resultados del trabajo Búsqueda de Microsoft en Bing muestra una dirección URL y resultados verticales de presentación personalizados." source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="1afe8-129">Use un iFrame para insertar un cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="1afe8-129">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="1afe8-130">Si incrustar una secuencia de comandos no es una opción para el sitio, use un iFrame para agregar el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1afe8-130">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="1afe8-131">No podrá personalizar el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1afe8-131">You won't be able to customize the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a><span data-ttu-id="1afe8-132">Modo InPrivate y acceso condicional</span><span class="sxs-lookup"><span data-stu-id="1afe8-132">InPrivate mode and Conditional Access</span></span>

<span data-ttu-id="1afe8-133">Si la página o el sitio se abre en una ventana de InPrivate, se deshabilitará un cuadro de búsqueda incrustado.</span><span class="sxs-lookup"><span data-stu-id="1afe8-133">An embedded search box will be disabled if the page or site is opened in an InPrivate window.</span></span> <span data-ttu-id="1afe8-134">Además, con la compatibilidad con acceso condicional de Azure AD en Microsoft Edge, Bing.com no admite el inicio de sesión de AAD al usar el modo InPrivate.</span><span class="sxs-lookup"><span data-stu-id="1afe8-134">Also, with Azure AD Conditional Access support in Microsoft Edge, Bing.com doesn't support AAD sign in when using InPrivate mode.</span></span> <span data-ttu-id="1afe8-135">Para obtener más información acerca del acceso condicional en edge, [vea Microsoft Edge y Conditional Access](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge).</span><span class="sxs-lookup"><span data-stu-id="1afe8-135">For more information about Conditional Access in Edge, see [Microsoft Edge and Conditional Access](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge).</span></span> 
