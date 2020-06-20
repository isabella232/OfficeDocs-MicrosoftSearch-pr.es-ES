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
# <a name="add-a-search-box-to-your-intranet-site"></a>Agregar un cuadro de búsqueda a su sitio de intranet

Para proporcionar a los usuarios un acceso sencillo a los resultados de su organización, agregue un cuadro de búsqueda de Microsoft Search en Bing a cualquier sitio o página de la intranet. Estas son algunas de las ventajas:

- Un cuadro de búsqueda en el portal de SharePoint o de intranet proporciona un punto de entrada de confianza conocido para iniciar la búsqueda
- Admite todos los exploradores Web principales, incluidos Google Chrome y Microsoft Edge
- Solo aparecen las sugerencias de búsqueda de la organización, las sugerencias web nunca se incluyen
- Lleva a los usuarios a una búsqueda de Microsoft en la página de resultados de trabajo de Bing, que excluye los anuncios y los resultados Web
- La apariencia y el comportamiento del cuadro de búsqueda se controla
  
## <a name="add-a-search-box-to-an-intranet-page"></a>Agregar un cuadro de búsqueda a una página de intranet

Necesita agregar dos elementos a la página: un contenedor para el cuadro de búsqueda y la secuencia de comandos que la potencia.
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

En un sitio de SharePoint clásico, agregue un elemento web de Script Editor y coloque el script en él.
  
## <a name="enable-the-search-box-for-mobile"></a>Habilitar el cuadro de búsqueda para dispositivos móviles

Para sitios o páginas de intranet disponibles para usuarios móviles, agregue isMobile: true al objeto de configuración:
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>Colocar el foco en el cuadro de búsqueda de forma predeterminada

Para ayudar a los usuarios a buscar con mayor rapidez, coloque el cursor en el cuadro de búsqueda cuando se cargue la página o sitio agregando focus: true al objeto de configuración:
  
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

## <a name="customize-the-appearance-of-the-search-box"></a>Personalizar la apariencia del cuadro de búsqueda 

Para ayudar a que el cuadro de búsqueda se adapte mejor con el estilo de su intranet, hay una gran variedad de opciones de configuración que puede usar. Mezcle y combine opciones para satisfacer sus necesidades.

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

## <a name="use-an-iframe-to-embed-a-search-box"></a>Use un iFrame para insertar un cuadro de búsqueda

Si incrustar una secuencia de comandos no es una opción para el sitio, use un iFrame para agregar el cuadro de búsqueda. No podrá personalizar la apariencia del cuadro de búsqueda.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
