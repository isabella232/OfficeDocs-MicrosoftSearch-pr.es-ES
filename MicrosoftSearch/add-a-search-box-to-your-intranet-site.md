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
description: Obtener sugerencias de búsqueda relevantes y busque los resultados de trabajo más rápido mediante la adición de un cuadro de búsqueda de Microsoft Search a un sitio de la intranet o página.
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612421"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Agregar un cuadro de búsqueda a su sitio de intranet

Para agilizar el acceso a las sugerencias de búsqueda relevantes y los resultados del trabajo, agregue un cuadro de búsqueda de Microsoft Search a cualquier sitio de la intranet o página.
  
## <a name="add-a-search-box-to-an-intranet-page"></a>Agregar un cuadro de búsqueda a una página de intranet

Es necesario agregar dos elementos a la página: un contenedor para el cuadro de búsqueda y la secuencia de comandos que se enciende.
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

En un sitio de SharePoint clásico, agregue un elemento Web Editor de secuencias de comandos y colocar la secuencia de comandos en ella.
  
## <a name="enable-the-search-box-for-mobile"></a>Habilitar el cuadro de búsqueda para mobile

Para sitios de intranet o páginas disponibles para los usuarios móviles, agregar isMobile: True para el objeto de configuración:
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>Poner el foco en el cuadro de búsqueda de forma predeterminada

Para ayudar a los usuarios a buscar con mayor rapidez, cuando las cargas de página o sitio sitúe el cursor en el cuadro de búsqueda mediante la adición de foco: True para el objeto de configuración:
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a>Use un iFrame para insertar un cuadro de búsqueda

Si la incrustación de una secuencia de comandos no es una opción para el sitio, use un iFrame para agregar el cuadro de búsqueda:
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
