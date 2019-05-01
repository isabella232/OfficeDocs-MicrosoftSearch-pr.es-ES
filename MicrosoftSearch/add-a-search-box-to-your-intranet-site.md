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
ms.openlocfilehash: a66c0cea71cf637209d298f49542864755e92ec9
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508525"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Agregar un cuadro de búsqueda a su sitio de intranet

Para acceder rápidamente a las sugerencias de búsqueda y resultados de trabajo relevantes, agregue un cuadro de búsqueda de Microsoft Search a cualquier página o sitio de intranet.
  
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
                                                // when absent, ghost text will be "Search work and the web"
                                                // when specified, text will be "Search the web and [Contoso]"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a>Use un iFrame para insertar un cuadro de búsqueda

Si incrustar una secuencia de comandos no es una opción para el sitio, use un iFrame para agregar el cuadro de búsqueda. No podrá personalizar la apariencia del cuadro de búsqueda.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```