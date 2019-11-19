---
title: Personalizar el diseño de los resultados de búsqueda
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Mediante tarjetas adaptables, cree un diseño para ver los resultados de la búsqueda personalizados
ms.openlocfilehash: 6f406bb32a18678f1ca0546e37edb8013e2ba450
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699570"
---
# <a name="create-a-layout-to-customize-search-results"></a>Crear un diseño para personalizar los resultados de la búsqueda

Puede diseñar el diseño de los resultados de una vertical personalizada mediante el diseñador de diseño de búsqueda. Puede empezar a diseñar el diseño si elige plantillas que se ofrecen en el diseñador de diseño y las usa si se ajustan a sus necesidades. También puede optar por editar estas plantillas de varias formas para ajustarse a sus necesidades. Por ejemplo, agregar o quitar imágenes, agregar o quitar texto y modificar texto. Si ninguna de las plantillas cumple los requisitos, puede optar por empezar a diseñar el diseño con una plantilla en blanco.  

 

Una vez que el diseño esté listo, use el [lenguaje de plantilla tarjetas adaptables](https://docs.microsoft.com/adaptive-cards/templating/language) para crear una JSON de diseño de resultados que se usa para definir un tipo de resultado. Las propiedades de resultado se asignan al diseño mediante el paso de asignación del diseñador de diseño.  

## <a name="create-a-layout-on-your-own"></a>Crear un diseño por su cuenta
La creación de un diseño propio requiere conocimientos de [tarjetas adaptables](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) y su [esquema](https://adaptivecards.io/explorer/). El diseño de resultados de búsqueda usa un subconjunto de los elementos ofrecidos por tarjetas adaptables y puede usar el diseñador de diseño para obtener información sobre el conjunto de elementos admitidos.  

Al crear su propio diseño, cree el diseño de la tarjeta adaptable con los datos del conector y, a continuación, finalice el diseño.
Existen dos pasos principales para crear su propio diseño:
- Diseñar el diseño.
- Separe los datos de la plantilla.

#### <a name="design-the-layout"></a>Edite el diseño.

En este ejemplo, se muestra un diseño con un encabezado, un vínculo y un texto descriptivo.

![Ejemplo de un diseño con un encabezado, un vínculo y una descripción.](media/Verts-ExampleLayout.png)

Y este es el archivo JSON asociado al diseño:


```json
{ 
    "type": "AdaptiveCard", 
    "version": "1.0", 
     "body": [ 
{ 

            "type": "ColumnSet", 
             "columns": [ 
                 { 
                     "type": "Column", 
                     "width": 8, 
                     "items": [ 
                         { 
                             "type": "TextBlock", 
                             "text": "Contoso Marketing Analysis - Q3 FY18", 
                             "color": "Accent", 
                             "size": "Medium", 
                             "spacing": "None", 
                             "$when": "{title != \"\"}", 
                             "weight": "Bolder" 
                        }, 
                        { 
                        "type": "TextBlock",  
                        "text": "https://contoso.com/hr/link", 
                        "spacing": "None",  
                        "color": "Dark", 
                        "weight": "Bolder" 

                        }, 

                        {  
                        "type": "TextBlock", 
                        "text": "Marketing team at Contoso.., and looking at the Contoso Marketing documents on the team site. This contains the data from FY20 and will taken over to FY21...Marketing Planning is ongoing for FY20..",  
                        "wrap": true, 
                        "maxLines": 2, 
                        "spacing": "Medium" 
                        } 
                        ], 

                    "horizontalAlignment": "Center", 
                    "spacing": "None" 

                } 

            ] 

        } 
        ], 

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json" 
}
```

#### <a name="separate-the-data-from-the-layout"></a>Separar los datos del diseño

Puede separar los datos del diseño y enlazar los datos. 

Este es el JSON de diseño después de enlazar los datos:


```json
{ 

    "type": "AdaptiveCard", 
    "version": "1.0", 
    "body": [ 
    { 
    "type": "ColumnSet", 
"columns": [ 

                { 
                "type": "Column", 
                "width": 8, 
                "items": [ 
                { 
                "type": "TextBlock", 
                "text": "[{title}]({titleUrl})", 
                "color": "Accent", 
                "size": "Medium",
                "spacing": "None", 
                "weight": "Bolder" 

                 }, 
                 { 
                 "type": "TextBlock", 
                 "text": "{link}",
                 "spacing": "None", 
                 "color": "Dark",
                 "weight": "Bolder" 
                 }, 
                 { 
                 "type": "TextBlock",
                 "text": "{description}",
                 "wrap": true,
                 "maxLines": 2, 
                 "spacing": "Medium" 
                 } 
                 ], 
                 "horizontalAlignment": "Center", 
                 "spacing": "None" 
                 } 
                 ] 

        } 

    ], 

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json" 
}
```

Datos de ejemplo: especifique datos de ejemplo en el **Editor de datos de ejemplo** para ver la tarjeta enlazada a datos en modo de **vista previa**.

```json
{ 

    "title": "Contoso Marketing Analysis - Q3 FY18", 
    "titleUrl": "https://contoso.com/hr/link", 
    "link": "https://contoso.com/hr/link", 
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?" 

} 
```

## <a name="map-the-layout-to-the-result-properties"></a>Asignar el diseño a las propiedades del resultado

Debe asignar cada campo del diseño a una propiedad de resultado o a una propiedad de conector para generar el JSON del diseño de resultados.

![Captura de pantalla de un diseño de ejemplo en la página del diseñador de diseño de búsqueda con un campo seleccionado y el panel de propiedades abierto.](media/Verts-SearchLayoutDesigner.png)

Seleccione un campo en el diseño para resaltar las variables que se deben asignar. Puede usar varias variables para un solo campo y todos los campos deben asignarse a las propiedades del resultado.

## <a name="things-to-consider"></a>Aspectos que tener en cuenta...

Antes de empezar, hay algunas cosas que debe hacer y algunas cosas que debe evitar para asegurarse de que los diseños se realicen correctamente.

### <a name="do"></a>Correcto

- Edite una plantilla para proporcionar el vínculo del logotipo en el diseño si está usando vínculos estáticos para los logotipos y no las propiedades de los resultados.   
- Validar el diseño de los resultados de los escenarios en los que no se devuelven datos para una propiedad de resultado usada en el JSON del resultado. Use la `$when` condición para ocultar un elemento si la propiedad no contiene datos.  
- Asegúrese de que los tipos de datos `$when` de la condición y la propiedad result coinciden. Por ejemplo, no compare `Number` con `Text` en la `$when` condición.  
- Piense en los requisitos de tema al diseñar un diseño de resultados.  
- Asegúrese de que el `Textblock`  elemento puede controlar el contenido dinámico. Puede usar las propiedades `wrap` del `maxLines` elemento y para este propósito. 
- Dar formato adecuado a la fecha `{DATE()}` al usar en Markdown.  

### <a name="dont"></a>Incorrecto

- No defina tipos de datos no válidos al enlazar valores. Para obtener más información acerca de los tipos de datos, consulte [administrar el esquema de búsqueda](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).
- Evite recortar el resultado en la página de resultados mediante el alto máximo de la JSON del diseño de resultados. Si supera el alto máximo del diseño de los resultados, el resultado se recortará en la página de resultados.
- No use `px` valores en las propiedades del elemento.


## <a name="resources"></a>Recursos
[Página personalizar resultados de búsqueda](customize-search-page.md)

[Tarjetas adaptables](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[Idioma de plantilla de tarjetas adaptables](https://docs.microsoft.com/adaptive-cards/templating/language)

[Esquema de tarjeta adaptable](https://adaptivecards.io/explorer/)
