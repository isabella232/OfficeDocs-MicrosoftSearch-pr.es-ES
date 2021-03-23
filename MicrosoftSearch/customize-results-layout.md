---
title: Administrar los diseños de resultados de búsqueda
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Con tarjetas adaptables, crea un diseño para ver los resultados de búsqueda personalizados
ms.openlocfilehash: d29b1a45f11079f4b71f71a387cf43cbf2f48e7d
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031741"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="3abb9-103">Crear un diseño para personalizar los resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="3abb9-103">Create a layout to customize search results</span></span>

<span data-ttu-id="3abb9-104">Puede diseñar el diseño de resultados para una vertical personalizada mediante el diseñador de diseños de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3abb9-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="3abb9-105">Puedes empezar a diseñar el diseño eligiendo las plantillas que se ofrecen en el diseñador de diseños y usándolos si se ajustan a tus requisitos.</span><span class="sxs-lookup"><span data-stu-id="3abb9-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="3abb9-106">O puede elegir editar estas plantillas de varias maneras para ajustarse a sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="3abb9-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="3abb9-107">Por ejemplo, agregar o quitar imágenes, agregar o quitar texto y modificar texto.</span><span class="sxs-lookup"><span data-stu-id="3abb9-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="3abb9-108">Si ninguna de las plantillas cumple sus requisitos, puede empezar a diseñar el diseño con una plantilla en blanco.</span><span class="sxs-lookup"><span data-stu-id="3abb9-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

<span data-ttu-id="3abb9-109">Después de que el diseño esté listo, use el lenguaje de plantilla [de](/adaptive-cards/templating/language) tarjetas adaptables para crear un JSON de diseño de resultados que se usa para definir un tipo de resultado.</span><span class="sxs-lookup"><span data-stu-id="3abb9-109">After the layout is ready, use the [Adaptive Cards Template language](/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="3abb9-110">Las propiedades de resultado se asignan al diseño mediante el paso Asignación en el diseñador de diseños.</span><span class="sxs-lookup"><span data-stu-id="3abb9-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="3abb9-111">Crear un diseño por su cuenta</span><span class="sxs-lookup"><span data-stu-id="3abb9-111">Create a layout on your own</span></span>

<span data-ttu-id="3abb9-112">Crear un diseño por su cuenta requiere conocimientos de [tarjetas adaptables](/adaptive-cards/authoring-cards/getting-started) y su [esquema.](https://adaptivecards.io/explorer/)</span><span class="sxs-lookup"><span data-stu-id="3abb9-112">Creating a layout on your own requires knowledge of [adaptive cards](/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="3abb9-113">El diseño de resultados de búsqueda usa un subconjunto de los elementos ofrecidos por tarjetas adaptables y puede usar el diseñador de diseños para obtener información sobre el conjunto de elementos admitido.</span><span class="sxs-lookup"><span data-stu-id="3abb9-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="3abb9-114">Al crear su propio diseño, cree el diseño de tarjeta adaptable con datos del conector y, a continuación, finalizar el diseño.</span><span class="sxs-lookup"><span data-stu-id="3abb9-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="3abb9-115">Hay dos pasos principales para crear su propio diseño:</span><span class="sxs-lookup"><span data-stu-id="3abb9-115">There are two main steps in creating your own layout:</span></span>

- <span data-ttu-id="3abb9-116">Diseñe el diseño.</span><span class="sxs-lookup"><span data-stu-id="3abb9-116">Design the layout.</span></span>
- <span data-ttu-id="3abb9-117">Separe los datos de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3abb9-117">Separate the data from the template.</span></span>

### <a name="design-the-layout"></a><span data-ttu-id="3abb9-118">Edite el diseño.</span><span class="sxs-lookup"><span data-stu-id="3abb9-118">Design the layout</span></span>

<span data-ttu-id="3abb9-119">En este ejemplo, se muestra un diseño con un encabezado, un vínculo y un texto descriptivo.</span><span class="sxs-lookup"><span data-stu-id="3abb9-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![Ejemplo de un diseño con un encabezado, un vínculo y una descripción.](media/Verts-ExampleLayout.png)

<span data-ttu-id="3abb9-121">Y este es el archivo JSON asociado del diseño:</span><span class="sxs-lookup"><span data-stu-id="3abb9-121">And here's the layout's associated JSON file:</span></span>

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

### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="3abb9-122">Separar los datos del diseño</span><span class="sxs-lookup"><span data-stu-id="3abb9-122">Separate the data from the layout</span></span>

<span data-ttu-id="3abb9-123">Puede separar los datos del diseño y enlazar los datos.</span><span class="sxs-lookup"><span data-stu-id="3abb9-123">You can separate the data from the layout and bind the data.</span></span>

<span data-ttu-id="3abb9-124">Este es layout JSON después de enlazar los datos:</span><span class="sxs-lookup"><span data-stu-id="3abb9-124">Here's Layout JSON after binding the data:</span></span>

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

<span data-ttu-id="3abb9-125">Datos de ejemplo: especifique datos de ejemplo en el **Editor** de datos de ejemplo para ver la tarjeta enlazada a datos cuando se encuentra en **modo de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="3abb9-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="3abb9-126">Asignar el diseño a las propiedades de resultados</span><span class="sxs-lookup"><span data-stu-id="3abb9-126">Map the layout to the result properties</span></span>

<span data-ttu-id="3abb9-127">Debe asignar cada campo del diseño a una propiedad result o a una propiedad connector para generar el JSON de diseño de resultados.</span><span class="sxs-lookup"><span data-stu-id="3abb9-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Captura de pantalla de un diseño de ejemplo en la página Diseñador de diseños de búsqueda con un campo seleccionado y el panel de propiedades abierto.](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="3abb9-129">Seleccione un campo en el diseño para resaltar las variables que deben asignarse.</span><span class="sxs-lookup"><span data-stu-id="3abb9-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="3abb9-130">Puede usar varias variables para un solo campo y todos los campos deben asignarse a las propiedades de resultado.</span><span class="sxs-lookup"><span data-stu-id="3abb9-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

### <a name="show-snippet-on-search-result"></a><span data-ttu-id="3abb9-131">Mostrar fragmento de código en el resultado de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="3abb9-131">Show snippet on search result</span></span>  

<span data-ttu-id="3abb9-132">Los fragmentos de código dinámicos generados en la propiedad **de** contenido del resultado del conector se pueden mostrar en el resultado de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3abb9-132">Dynamic snippets generated on the **content** property of the connector result can be shown on the search result.</span></span> <span data-ttu-id="3abb9-133">**ResultSnippet es** la propiedad del sistema que actúa como una propiedad de marcador de posición para los fragmentos de código generados para cada resultado de Connector.</span><span class="sxs-lookup"><span data-stu-id="3abb9-133">**ResultSnippet** is the system property that acts as a placeholder property for the snippets generated for each Connector result.</span></span> <span data-ttu-id="3abb9-134">Para mostrar los fragmentos de código en el diseño de resultados, la propiedad del sistema **ResultSnippet** debe asignarse a un campo adecuado, por ejemplo Description, en el diseño de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3abb9-134">To show the snippets on the result layout, the **ResultSnippet** system property must be mapped to an appropriate field, for example Description, in the search result layout.</span></span> <span data-ttu-id="3abb9-135">Los fragmentos de código generados en cada resultado también resaltan las coincidencias del fragmento de código con el término de consulta especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3abb9-135">Snippets generated on each result also highlight the matches in the Snippet with the query term entered by the user.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="3abb9-136">Consideraciones que se deben tener en cuenta</span><span class="sxs-lookup"><span data-stu-id="3abb9-136">Things to consider</span></span>

<span data-ttu-id="3abb9-137">Antes de empezar, hay algunas cosas que debe hacer y algunas cosas que debe evitar para asegurarse de que los diseños se realicen correctamente.</span><span class="sxs-lookup"><span data-stu-id="3abb9-137">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="3abb9-138">Correcto</span><span class="sxs-lookup"><span data-stu-id="3abb9-138">Do</span></span>

- <span data-ttu-id="3abb9-139">Edite una plantilla para proporcionar el vínculo de logotipo en el diseño si usa vínculos estáticos para logotipos y no propiedades de resultados.</span><span class="sxs-lookup"><span data-stu-id="3abb9-139">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>
- <span data-ttu-id="3abb9-140">Valide el diseño de resultados para escenarios en los que no se devuelven datos para una propiedad de resultado usada en el JSON de resultados.</span><span class="sxs-lookup"><span data-stu-id="3abb9-140">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="3abb9-141">Use la `$when` condición para ocultar un elemento si la propiedad no contiene datos.</span><span class="sxs-lookup"><span data-stu-id="3abb9-141">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="3abb9-142">Asegúrese de que los tipos de datos de la `$when` condición y la propiedad result coinciden.</span><span class="sxs-lookup"><span data-stu-id="3abb9-142">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="3abb9-143">Por ejemplo, no se compare `Number` con `Text` la `$when` condición.</span><span class="sxs-lookup"><span data-stu-id="3abb9-143">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="3abb9-144">Piense en los requisitos del tema al diseñar un diseño de resultados.</span><span class="sxs-lookup"><span data-stu-id="3abb9-144">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="3abb9-145">Asegúrese de que el `Textblock`   elemento puede controlar el contenido dinámico.</span><span class="sxs-lookup"><span data-stu-id="3abb9-145">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="3abb9-146">Puede usar las propiedades `wrap` del elemento and para este `maxLines` propósito.</span><span class="sxs-lookup"><span data-stu-id="3abb9-146">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span>
- <span data-ttu-id="3abb9-147">Formatee correctamente la fecha al usar `{DATE()}` en Markdown.</span><span class="sxs-lookup"><span data-stu-id="3abb9-147">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="3abb9-148">Incorrecto</span><span class="sxs-lookup"><span data-stu-id="3abb9-148">Don't</span></span>

- <span data-ttu-id="3abb9-149">No defina tipos de datos no válidos al enlazar valores.</span><span class="sxs-lookup"><span data-stu-id="3abb9-149">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="3abb9-150">Para obtener más información acerca de los tipos de datos, [vea Manage the Search schema](/sharepoint/search/manage-the-search-schema).</span><span class="sxs-lookup"><span data-stu-id="3abb9-150">For more information about data types, see [Manage the Search schema](/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="3abb9-151">Evite recortar el resultado en la página de resultados siguiendo el alto máximo del JSON de diseño de resultados.</span><span class="sxs-lookup"><span data-stu-id="3abb9-151">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="3abb9-152">Si supera el alto máximo del diseño de resultados, el resultado se recortará en la página de resultados.</span><span class="sxs-lookup"><span data-stu-id="3abb9-152">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="3abb9-153">No use valores `px` en propiedades de elemento.</span><span class="sxs-lookup"><span data-stu-id="3abb9-153">Don't use `px` values in element properties.</span></span>
- <span data-ttu-id="3abb9-154">No use markdown con la **propiedad ResultSnippet** en el diseño de resultados para resaltar la coincidencia de consulta en el resultado de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3abb9-154">Don't use markdown with the **ResultSnippet** property in the result layout to highlight query match in the search result.</span></span>

## <a name="resources"></a><span data-ttu-id="3abb9-155">Recursos</span><span class="sxs-lookup"><span data-stu-id="3abb9-155">Resources</span></span>

[<span data-ttu-id="3abb9-156">Personalizar página de resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="3abb9-156">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="3abb9-157">Tarjetas adaptables</span><span class="sxs-lookup"><span data-stu-id="3abb9-157">Adaptive cards</span></span>](/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="3abb9-158">Idioma de plantilla de tarjetas adaptables</span><span class="sxs-lookup"><span data-stu-id="3abb9-158">Adaptive Cards Template language</span></span>](/adaptive-cards/templating/language)

[<span data-ttu-id="3abb9-159">Esquema de tarjeta adaptable</span><span class="sxs-lookup"><span data-stu-id="3abb9-159">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)