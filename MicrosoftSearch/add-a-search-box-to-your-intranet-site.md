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
# <a name="add-a-search-box-to-your-intranet-site"></a>Agregar un cuadro de búsqueda a su sitio de intranet

Para proporcionar a los usuarios un acceso fácil a los resultados de su organización, agregue un Búsqueda de Microsoft en el Bing de búsqueda a cualquier sitio o página de intranet. Estos son algunos de los beneficios:

- Un cuadro de búsqueda en el portal SharePoint intranet proporciona un punto de entrada familiar y de confianza para empezar a buscar
- Admite todos los exploradores web principales, incluidos Google Chrome y Microsoft Edge
- Solo aparecen sugerencias de búsqueda de su organización, las sugerencias web nunca se incluyen
- Lleva a los usuarios a un Búsqueda de Microsoft en Bing de resultados de trabajo, que excluye anuncios y resultados web
- Puede controlar la apariencia y el comportamiento del cuadro de búsqueda, incluida la capacidad de desembarco de usuarios en una vertical predeterminada o una vertical personalizada que haya creado.
  
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

## <a name="direct-users-to-a-default-or-custom-vertical"></a>Dirigir a los usuarios a una vertical predeterminada o personalizada

Para facilitar la integración entre las aplicaciones de línea de negocio o los sitios de intranet y los resultados del trabajo, también puede personalizar el cuadro de búsqueda especificando una vertical predeterminada o personalizada en la que los usuarios deben aterrizar cuando hacen clic en una sugerencia de búsqueda.

Use la opción vertical en bfbSearchBoxConfig para definir la vertical que desee. Por ejemplo, si desea que los usuarios siempre aterrice en la vertical Sitios, una de las verticales predeterminadas, use el valor "Site-sites".

:::image type="content" alt-text="Captura de pantalla de la página de resultados del trabajo Búsqueda de Microsoft en Bing muestra los resultados verticales de sitios y la dirección URL." source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

Para verticales personalizados, use el hash al final de la dirección URL. Puede encontrar estos valores buscando en la página de trabajo de Bing, haciendo clic en una etiqueta vertical y copiando el valor después del signo de número (#).

:::image type="content" alt-text="Captura de pantalla de la página de resultados del trabajo Búsqueda de Microsoft en Bing muestra una dirección URL y resultados verticales de presentación personalizados." source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a>Use un iFrame para insertar un cuadro de búsqueda

Si incrustar una secuencia de comandos no es una opción para el sitio, use un iFrame para agregar el cuadro de búsqueda. No podrá personalizar el cuadro de búsqueda.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a>Modo InPrivate y acceso condicional

Si la página o el sitio se abre en una ventana de InPrivate, se deshabilitará un cuadro de búsqueda incrustado. Además, con la compatibilidad con acceso condicional de Azure AD en Microsoft Edge, Bing.com no admite el inicio de sesión de AAD al usar el modo InPrivate. Para obtener más información acerca del acceso condicional en edge, [vea Microsoft Edge y Conditional Access](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge). 
