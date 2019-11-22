---
title: Personalizar el diseño de los resultados de búsqueda
ms.author: anfowler
author: jeffkizn
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
ms.openlocfilehash: 6d1409eaf070275a4c6dbc713b1ec7914e09e541
ms.sourcegitcommit: b28d7f4dfc71ecd7edc28c964a3da2180e1f4c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793554"
---
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="e5600-103">Crear un diseño para personalizar los resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="e5600-103">Create a layout to customize search results</span></span>

<span data-ttu-id="e5600-104">Puede diseñar el diseño de los resultados de una vertical personalizada mediante el diseñador de diseño de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e5600-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="e5600-105">Puede empezar a diseñar el diseño si elige plantillas que se ofrecen en el diseñador de diseño y las usa si se ajustan a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="e5600-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="e5600-106">También puede optar por editar estas plantillas de varias formas para ajustarse a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="e5600-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="e5600-107">Por ejemplo, agregar o quitar imágenes, agregar o quitar texto y modificar texto.</span><span class="sxs-lookup"><span data-stu-id="e5600-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="e5600-108">Si ninguna de las plantillas cumple los requisitos, puede optar por empezar a diseñar el diseño con una plantilla en blanco.</span><span class="sxs-lookup"><span data-stu-id="e5600-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

 

<span data-ttu-id="e5600-109">Una vez que el diseño esté listo, use el [lenguaje de plantilla tarjetas adaptables](https://docs.microsoft.com/adaptive-cards/templating/language) para crear una JSON de diseño de resultados que se usa para definir un tipo de resultado.</span><span class="sxs-lookup"><span data-stu-id="e5600-109">After the layout is ready, use the [Adaptive Cards Template language](https://docs.microsoft.com/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="e5600-110">Las propiedades de resultado se asignan al diseño mediante el paso de asignación del diseñador de diseño.</span><span class="sxs-lookup"><span data-stu-id="e5600-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="e5600-111">Crear un diseño por su cuenta</span><span class="sxs-lookup"><span data-stu-id="e5600-111">Create a layout on your own</span></span>
<span data-ttu-id="e5600-112">La creación de un diseño propio requiere conocimientos de [tarjetas adaptables](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) y su [esquema](https://adaptivecards.io/explorer/).</span><span class="sxs-lookup"><span data-stu-id="e5600-112">Creating a layout on your own requires knowledge of [adaptive cards](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="e5600-113">El diseño de resultados de búsqueda usa un subconjunto de los elementos ofrecidos por tarjetas adaptables y puede usar el diseñador de diseño para obtener información sobre el conjunto de elementos admitidos.</span><span class="sxs-lookup"><span data-stu-id="e5600-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="e5600-114">Al crear su propio diseño, cree el diseño de la tarjeta adaptable con los datos del conector y, a continuación, finalice el diseño.</span><span class="sxs-lookup"><span data-stu-id="e5600-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="e5600-115">Existen dos pasos principales para crear su propio diseño:</span><span class="sxs-lookup"><span data-stu-id="e5600-115">There are two main steps in creating your own layout:</span></span>
- <span data-ttu-id="e5600-116">Diseñar el diseño.</span><span class="sxs-lookup"><span data-stu-id="e5600-116">Design the layout.</span></span>
- <span data-ttu-id="e5600-117">Separe los datos de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="e5600-117">Separate the data from the template.</span></span>

#### <a name="design-the-layout"></a><span data-ttu-id="e5600-118">Edite el diseño.</span><span class="sxs-lookup"><span data-stu-id="e5600-118">Design the layout</span></span>

<span data-ttu-id="e5600-119">En este ejemplo, se muestra un diseño con un encabezado, un vínculo y un texto descriptivo.</span><span class="sxs-lookup"><span data-stu-id="e5600-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![Ejemplo de un diseño con un encabezado, un vínculo y una descripción.](media/Verts-ExampleLayout.png)

<span data-ttu-id="e5600-121">Y este es el archivo JSON asociado al diseño:</span><span class="sxs-lookup"><span data-stu-id="e5600-121">And here's the layout's associated JSON file:</span></span>


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

#### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="e5600-122">Separar los datos del diseño</span><span class="sxs-lookup"><span data-stu-id="e5600-122">Separate the data from the layout</span></span>

<span data-ttu-id="e5600-123">Puede separar los datos del diseño y enlazar los datos.</span><span class="sxs-lookup"><span data-stu-id="e5600-123">You can separate the data from the layout and bind the data.</span></span> 

<span data-ttu-id="e5600-124">Este es el JSON de diseño después de enlazar los datos:</span><span class="sxs-lookup"><span data-stu-id="e5600-124">Here's Layout JSON after binding the data:</span></span>


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

<span data-ttu-id="e5600-125">Datos de ejemplo: especifique datos de ejemplo en el **Editor de datos de ejemplo** para ver la tarjeta enlazada a datos en modo de **vista previa**.</span><span class="sxs-lookup"><span data-stu-id="e5600-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{ 

    "title": "Contoso Marketing Analysis - Q3 FY18", 
    "titleUrl": "https://contoso.com/hr/link", 
    "link": "https://contoso.com/hr/link", 
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?" 

} 
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="e5600-126">Asignar el diseño a las propiedades del resultado</span><span class="sxs-lookup"><span data-stu-id="e5600-126">Map the layout to the result properties</span></span>

<span data-ttu-id="e5600-127">Debe asignar cada campo del diseño a una propiedad de resultado o a una propiedad de conector para generar el JSON del diseño de resultados.</span><span class="sxs-lookup"><span data-stu-id="e5600-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Captura de pantalla de un diseño de ejemplo en la página del diseñador de diseño de búsqueda con un campo seleccionado y el panel de propiedades abierto.](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="e5600-129">Seleccione un campo en el diseño para resaltar las variables que se deben asignar.</span><span class="sxs-lookup"><span data-stu-id="e5600-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="e5600-130">Puede usar varias variables para un solo campo y todos los campos deben asignarse a las propiedades del resultado.</span><span class="sxs-lookup"><span data-stu-id="e5600-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="e5600-131">Aspectos que tener en cuenta...</span><span class="sxs-lookup"><span data-stu-id="e5600-131">Things to consider...</span></span>

<span data-ttu-id="e5600-132">Antes de empezar, hay algunas cosas que debe hacer y algunas cosas que debe evitar para asegurarse de que los diseños se realicen correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5600-132">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="e5600-133">Correcto</span><span class="sxs-lookup"><span data-stu-id="e5600-133">Do</span></span>

- <span data-ttu-id="e5600-134">Edite una plantilla para proporcionar el vínculo del logotipo en el diseño si está usando vínculos estáticos para los logotipos y no las propiedades de los resultados.</span><span class="sxs-lookup"><span data-stu-id="e5600-134">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>   
- <span data-ttu-id="e5600-135">Validar el diseño de los resultados de los escenarios en los que no se devuelven datos para una propiedad de resultado usada en el JSON del resultado.</span><span class="sxs-lookup"><span data-stu-id="e5600-135">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="e5600-136">Use la `$when` condición para ocultar un elemento si la propiedad no contiene datos.</span><span class="sxs-lookup"><span data-stu-id="e5600-136">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="e5600-137">Asegúrese de que los tipos de datos `$when` de la condición y la propiedad result coinciden.</span><span class="sxs-lookup"><span data-stu-id="e5600-137">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="e5600-138">Por ejemplo, no compare `Number` con `Text` en la `$when` condición.</span><span class="sxs-lookup"><span data-stu-id="e5600-138">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="e5600-139">Piense en los requisitos de tema al diseñar un diseño de resultados.</span><span class="sxs-lookup"><span data-stu-id="e5600-139">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="e5600-140">Asegúrese de que el `Textblock`  elemento puede controlar el contenido dinámico.</span><span class="sxs-lookup"><span data-stu-id="e5600-140">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="e5600-141">Puede usar las propiedades `wrap` del `maxLines` elemento y para este propósito.</span><span class="sxs-lookup"><span data-stu-id="e5600-141">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span> 
- <span data-ttu-id="e5600-142">Dar formato adecuado a la fecha `{DATE()}` al usar en Markdown.</span><span class="sxs-lookup"><span data-stu-id="e5600-142">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="e5600-143">Incorrecto</span><span class="sxs-lookup"><span data-stu-id="e5600-143">Don't</span></span>

- <span data-ttu-id="e5600-144">No defina tipos de datos no válidos al enlazar valores.</span><span class="sxs-lookup"><span data-stu-id="e5600-144">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="e5600-145">Para obtener más información acerca de los tipos de datos, consulte [administrar el esquema de búsqueda](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span><span class="sxs-lookup"><span data-stu-id="e5600-145">For more information about data types, see [Manage the Search schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="e5600-146">Evite recortar el resultado en la página de resultados mediante el alto máximo de la JSON del diseño de resultados.</span><span class="sxs-lookup"><span data-stu-id="e5600-146">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="e5600-147">Si supera el alto máximo del diseño de los resultados, el resultado se recortará en la página de resultados.</span><span class="sxs-lookup"><span data-stu-id="e5600-147">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="e5600-148">No use `px` valores en las propiedades del elemento.</span><span class="sxs-lookup"><span data-stu-id="e5600-148">Don't use `px` values in element properties.</span></span>


## <a name="resources"></a><span data-ttu-id="e5600-149">Recursos</span><span class="sxs-lookup"><span data-stu-id="e5600-149">Resources</span></span>
[<span data-ttu-id="e5600-150">Página personalizar resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="e5600-150">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="e5600-151">Tarjetas adaptables</span><span class="sxs-lookup"><span data-stu-id="e5600-151">Adaptive cards</span></span>](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="e5600-152">Idioma de plantilla de tarjetas adaptables</span><span class="sxs-lookup"><span data-stu-id="e5600-152">Adaptive Cards Template language</span></span>](https://docs.microsoft.com/adaptive-cards/templating/language)

[<span data-ttu-id="e5600-153">Esquema de tarjeta adaptable</span><span class="sxs-lookup"><span data-stu-id="e5600-153">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)
