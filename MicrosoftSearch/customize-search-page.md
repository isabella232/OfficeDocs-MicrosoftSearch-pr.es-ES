---
title: Personalizar la página búsqueda de Microsoft
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Agregar verticales de búsqueda y personalizar los resultados de la búsqueda
ms.openlocfilehash: 4896fdb9923c93602acc48c2360039d512e4d72e
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790342"
---
# <a name="customize-the-search-results-page"></a>Personalizar la página de resultados de búsqueda

Puede crear verticales de búsqueda y tipos de resultados para personalizar los resultados de búsqueda que los usuarios ven cuando buscan en Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com)y Búsqueda de Microsoft en [Bing](https://bing.com). Las verticales facilitan a los usuarios la búsqueda de la información que tienen permiso para ver. Por ejemplo, puede crear una vertical de búsqueda para los datos de análisis de marketing de software de terceros para los usuarios del departamento de marketing. También puedes definir tipos de resultados y personalizar el diseño de estos datos.  

Puede crear verticales y tipos de resultados en estos niveles:

- **Nivel de** organización: cuando agrega una presentación vertical en el nivel de organización, aparece en la página de resultados de búsqueda cuando los usuarios buscan desde su página de inicio de [SharePoint,](https://sharepoint.com/) en [Office](https://office.com)o en [Bing.](https://bing.com)
- **Nivel de** sitio: por ejemplo, es posible que desee permitir que los empleados del servicio al cliente busquen incidentes de gravedad *1* directamente desde el sitio de SharePoint de su departamento.

## <a name="search-verticals-explained"></a>Se explicaron las verticales de búsqueda

En la parte superior de la página de resultados de Búsqueda de Microsoft, hay una fila de pestañas. Estas son las verticales de búsqueda. Una vertical de búsqueda solo muestra los resultados de un tipo determinado o de determinado contenido. Algunos ejemplos **son Archivos** o **Noticias.** De forma predeterminada, Búsqueda de Microsoft muestra las presentaciones verticales **All**, **People**, **Files**, **Sites** y **News**.  

Puede agregar verticales de búsqueda que sean relevantes para su organización. Aparecerán en la página de resultados de Búsqueda de Microsoft [en SharePoint,](https://sharepoint.com/) [Office](https://Office.com)y [Bing.](https://bing.com) Por ejemplo, puede crear una vertical para el contenido relacionado con el marketing y otra para las ventas, en función del tipo de información que necesita cada grupo. Puede agregar verticales para mostrar los resultados solo del contenido indizado a través de conectores.  

### <a name="multiple-connections-in-a-vertical"></a>Varias conexiones en una vertical

Ahora, una vertical de búsqueda puede obtener resultados de varios orígenes de conectores. Esto proporciona mayor flexibilidad a la hora de diseñar la página de resultados de búsqueda. La experiencia administrativa existente de la configuración vertical permite seleccionar varias conexiones en el paso "Origen de contenido".
Si designa con precisión tantas etiquetas semánticas como sea posible, esta experiencia se mejorará. Puede agregar etiquetas semánticas a la definición y la ingesta del esquema.

[Aquí](configure-connector.md#step-5-assign-property-labels) tiene información adicional sobre cómo crear y administrar etiquetas semánticas.

### <a name="things-you-should-know"></a>Cosas que debes saber

1. Una conexión se puede agregar como un origen de contenido solo debajo de una vertical. No se permite volver a usar conexiones en varias verticales.
2. Si necesita configurar una consulta para una vertical de búsqueda donde se han agregado varios orígenes de conexión, se deben usar propiedades de origen comunes para crear una consulta de este tipo.

## <a name="things-to-consider"></a>Consideraciones que se deben tener en cuenta

Antes de empezar, asegúrese de que el conector se ha indizado. Esto puede tardar hasta 48 horas, dependiendo del tamaño del archivo.

No puede crear una presentación vertical para el contenido que reside en [SharePoint](https://sharepoint.com/).

Hay tres pasos básicos para agregar una vertical:

1. Cree la vertical. En este paso, se define el nombre de la vertical, el origen de contenido y el ámbito del contenido que se va a buscar.
2. Define el aspecto que tendrán los resultados de esta vertical.  
3. Habilite la presentación vertical (que se mostrará) desde la página de lista vertical.

## <a name="step-1-create-the-search-vertical"></a>PASO 1: Crear la vertical de búsqueda

Después de iniciar el asistente, se le guiará a través de los pasos para definir el nombre de la vertical, el origen de contenido y el ámbito del contenido que se va a buscar. La vertical se crea en un estado deshabilitado. Lo habilitará más adelante.

Puede usar un conjunto limitado de lenguaje de [consulta de palabras clave (KQL) para](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) restringir el ámbito. En esta página se enumeran las propiedades que están disponibles. Se recomienda usar palabras clave de texto libre y restricciones de propiedad con operadores booleanos para crear el KQL.

### <a name="create-a-vertical-at-the-organization-level"></a>Crear una vertical en el nivel de organización

Para crear la presentación vertical en Búsqueda de Microsoft en la página principal de [SharePoint,](https://sharepoint.com/) [Office](https://office.com)o [Bing,](https://bing.com)siga estos pasos:

1. En el [Centro de administración de Microsoft 365,](https://admin.microsoft.com)vaya a [**Verticales.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Seleccione **Agregar** para empezar.  

### <a name="create-a-vertical-at-the-site-level"></a>Crear una vertical en el nivel de sitio

1. En el [sitio de SharePoint](https://sharepoint.com/) donde desea la presentación vertical, vaya a **Configuración.**
2. Seleccione **Información del sitio y,** a continuación, Ver toda la configuración del **sitio.**
3. Busque la sección **Búsqueda de Microsoft** y, a continuación, seleccione Configurar Microsoft Search para esta colección de **sitios.**
4. En el panel de navegación, vaya **a Experiencia personalizada** y, a continuación, seleccione la pestaña **Verticales.**
5. Para agregar una vertical, seleccione **Agregar**.
  O bien, para editar una vertical, selecciónelo en la lista.

Recuerde que las verticales se crean en un estado deshabilitado. Deben estar habilitados para que los usuarios puedan verlos.

## <a name="step-2-create-the-result-types"></a>PASO 2: Crear los tipos de resultado

Puedes definir cómo se muestran los resultados en la presentación vertical diseñando el diseño mediante tipos de resultados. El diseño de resultados le permite mostrar información importante directamente en los resultados de la búsqueda, por lo que los usuarios no tienen que seleccionar cada resultado para ver si encontraron lo que buscan.

### <a name="default-search-result-layout"></a>Diseño de resultados de búsqueda predeterminado

Se mostrará un diseño de resultados  de  búsqueda predeterminado para el contenido del conector si las etiquetas y la propiedad de contenido se han asignado correctamente a las propiedades de origen en el momento de configurar el conector. El título **de la** etiqueta es la etiqueta más importante. Se recomienda **encarecidamente que** tenga una propiedad asignada a esta etiqueta para usar el diseño de resultados de búsqueda predeterminado.

### <a name="create-your-own-result-type"></a>Crear su propio tipo de resultado

Puede decidir crear su propio diseño de resultados de búsqueda e invalidar el diseño de resultados de búsqueda predeterminado mediante la creación de un **tipo de resultado.** Un tipo de resultado de búsqueda es una regla que hace que diferentes tipos de resultados de búsqueda se muestren de manera distinta. Consta de lo siguiente:

- **Una o más condiciones con** las que comparar cada resultado de búsqueda, como el origen de contenido del resultado de la búsqueda.  
- Diseño **de resultados que** se usará para los resultados de búsqueda que cumplan las condiciones. El diseño de resultados controla la forma en que todos los resultados que cumplen las condiciones aparecen y se comportan en una página de resultados de búsqueda.

**Si no se realiza la asignación adecuada para mostrar el diseño de resultados de búsqueda predeterminado, debe crear al menos un tipo de resultado para que los resultados se muestren en la presentación vertical.** Puedes crear varios tipos de resultados para cada presentación vertical, lo que te permite usar diseños diferentes para diferentes tipos de resultados. Por ejemplo, puede personalizar los incidentes de gravedad *1* para que tengan colores más destacados y una fuente más grande en comparación con los incidentes de gravedad *3.*

Después de iniciar el asistente, se le guiará por los pasos para definir el nombre, el origen de contenido y las condiciones para el tipo de resultado. Puede definir la prioridad del tipo de resultado desde la vista de lista.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Crear un tipo de resultado en el nivel de organización

1. En el [Centro de administración de Microsoft 365,](https://admin.microsoft.com)vaya a Tipos de [**resultados.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)
2. Para agregar un **tipo de resultado,** seleccione **Agregar**. Para editar un tipo de resultado, seleccione el tipo de resultado en la lista correspondiente.

### <a name="create-a-results-type-at-the-site-level"></a>Crear un tipo de resultados en el nivel de sitio

1. En el [sitio de SharePoint](https://sharepoint.com/) donde desea crear el tipo de resultado, vaya a **Configuración.**
2. Seleccione **Información del sitio y,** a continuación, Ver toda la configuración del **sitio.**
3. Busque la sección Búsqueda de Microsoft y, a continuación, **seleccione Configurar Microsoft Search para esta colección de sitios.**
4. En el panel de navegación, vaya **a Experiencia personalizada** y seleccione la pestaña Tipo **de** resultado.
5. Para agregar un tipo de resultado, seleccione **Agregar**.  O bien, para editar un tipo de resultado, seleccione el tipo de resultado en la lista.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>PASO 3: Ver la vertical después de habilitarla

Después de habilitar la vertical, puede tardar un tiempo antes de poder verlo. Si no desea esperar después de habilitarla, puede anexar **cacheClear=true** a la dirección URL de [SharePoint](https://sharepoint.com/) y [Office](https://office.com) para ver la presentación vertical inmediatamente. Para [Bing,](https://bing.com) **anexe&features=uncachedVerticals** a la dirección URL vertical de trabajo para ver las presentaciones verticales inmediatamente.

## <a name="troubleshooting"></a>Solución de problemas

Esta es una lista de problemas comunes que pueden surgir y acciones para solucionarlos.

|Error  |Acción  |
|---------|---------|
| Veo un mensaje de error "Algo salió mal" en la vertical. | Tanto el tipo vertical como el de resultados son necesarios para completar la configuración. Asegúrese de haber creado ambos para el mismo origen de contenido. |
| No veo mi diseño de resultados, aunque he creado uno. | Esta configuración tarda unos minutos en almacenarse en caché. Espere unos minutos e inténtelo de nuevo.        |
| No veo ningún orígenes de contenido en la página vertical o de tipo de resultado. | Asegúrese de que ha configurado conectores y datos indizados.   |

## <a name="next-steps"></a>Siguientes pasos

[Personalizar el diseño de resultados](customize-results-layout.md)
