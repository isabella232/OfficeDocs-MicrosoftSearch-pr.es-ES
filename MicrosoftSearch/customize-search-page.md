---
title: Personalización de la página de búsqueda de Microsoft
ms.author: jypal6
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
description: Agregar presentaciones verticales de búsqueda y personalizar los resultados de la búsqueda
ms.openlocfilehash: 44b1b9ff211a65313f5c5cf532334335994c486d
ms.sourcegitcommit: 0050e113517a36e3ca26028a04ac5c236caaf524
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470285"
---
# <a name="customize-the-search-results-page"></a>Personalización de la página de resultados de búsqueda

Puede crear presentaciones verticales de búsqueda y tipos de resultado para personalizar los resultados de búsqueda que los usuarios ven cuando buscan en Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com)y Microsoft Search en [Bing](https://bing.com). Las verticales permiten a los usuarios encontrar más fácilmente la información que tienen permiso para ver. Por ejemplo, puede crear una presentación vertical de búsqueda para los datos de análisis de marketing de software de terceros para los usuarios del Departamento de marketing. También puede definir tipos de resultado y personalizar el diseño de estos datos.  

Puede crear tipos verticales y resultados en estos niveles:

- **Nivel de organización** : cuando se agrega un vertical en el nivel de la organización, aparece en la página de resultados de búsqueda cuando los usuarios buscan desde su página de inicio de [SharePoint](https://sharepoint.com/) , en [Office](https://office.com)o en [Bing](https://bing.com).
- **Nivel de sitio** : por ejemplo, es posible que desee permitir a los empleados de servicio de atención al cliente buscar incidencias de *severidad 1* directamente desde el sitio de SharePoint de su departamento.

## <a name="search-verticals-explained"></a>Explicación de las presentaciones verticales de búsqueda

En la parte superior de la página de resultados de la búsqueda de Microsoft, hay una fila de pestañas. Estas son las presentaciones verticales de búsqueda. Una presentación vertical de búsqueda solo muestra los resultados de un tipo determinado o de determinados contenidos. Algunos ejemplos son **archivos** o **noticias**. De forma predeterminada, Microsoft Search muestra los verticales **todos**, los **contactos**, **los archivos, los** **sitios**y las **noticias**.  

Puede Agregar presentaciones verticales de búsqueda que sean relevantes para su organización. Estas aparecerán en la página de resultados de Microsoft Search en [SharePoint](https://sharepoint.com/), [Office](https://Office.com)y [Bing](https://bing.com). Por ejemplo, puede crear un vertical para el contenido relacionado con el marketing y otro para las ventas, en función del tipo de información que cada grupo necesita. Puede Agregar vertical para mostrar los resultados sólo del contenido indizado a través de conectores.  

>[!NOTE]
> Los elementos verticales y los tipos de resultado están actualmente en versión preliminar como parte de la vista previa de conectores de Microsoft Graph. Para obtener más información acerca de la vista previa, consulte [conectores Preview](connectors-preview.md). Para participar en la vista previa, primero debe enviar el [formulario de suscripción de vista previa de conectores de Microsoft Graph](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).

## <a name="things-to-consider"></a>Consideraciones que se deben tener en cuenta

Antes de empezar, asegúrese de que el conector se haya indizado. Esto puede tardar hasta 48 horas, según el tamaño del archivo.

No se puede crear un vertical para contenido que reside en [SharePoint](https://sharepoint.com/) o de contenido indizado por el conector de [uso compartido de archivos](file-share-connector.md). Obtenga información sobre cómo [indizar contenido](configure-connector.md).

Hay tres pasos básicos para agregar un vertical:

1. Cree el vertical. En este paso, se define el nombre de la vertical, el origen de contenido y el ámbito del contenido que se va a buscar.
2. Defina el aspecto que tendrán los resultados de esta vertical.  
3. Habilite la vertical (para que se muestre) en la página de lista vertical.

## <a name="step-1-create-the-search-vertical"></a>Paso 1: crear la presentación vertical de búsqueda

Después de iniciar el asistente, se le guiará por los pasos necesarios para definir el nombre de la vertical, el origen de contenido y el ámbito del contenido en el que se va a buscar. El vertical se crea en un Estado deshabilitado. Lo habilitará más adelante.

Puede usar un conjunto limitado de [lenguaje de consulta de palabras clave (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) para restringir el ámbito. En esta página se enumeran las propiedades que están disponibles. Se recomienda usar palabras clave FREETEXT y restricciones de propiedad con operadores booleanos para crear KQL.

### <a name="create-a-vertical-at-the-organization-level"></a>Crear un vertical en el nivel de la organización

Para crear la vertical en Microsoft Search en [SharePoint](https://sharepoint.com/) Home, [Office](https://office.com)o [Bing](https://bing.com), siga estos pasos:

1. En el centro de [Administración](https://admin.microsoft.com)de Microsoft 365, vaya a **configuración**de las   >  **Microsoft Search**   >  **presentaciones verticales**de búsqueda de Microsoft.
1. Seleccione **Agregar** para empezar.  

### <a name="create-a-vertical-at-the-site-level"></a>Crear un vertical en el nivel de sitio

1. En el sitio de [SharePoint](https://sharepoint.com/) en el que desea que aparezca el vertical, vaya a **configuración**.
1. Seleccione **información del sitio** y, a continuación, **ver toda la configuración del sitio**.
1. Busque la sección de **Microsoft Search** y, a continuación, seleccione **configurar Microsoft Search para esta colección de sitios**.
1. En el panel de navegación, vaya a **experiencia personalizada**y, a continuación, seleccione la pestaña **vertical** .
1. Para agregar una vertical, seleccione **Agregar**.
  O bien, para editar una vertical, selecciónela en la lista.

Recuerde que los verticales se crean en un Estado deshabilitado. Deben habilitarse antes de que los usuarios puedan verlos.

## <a name="step-2-create-the-result-types"></a>Paso 2: crear los tipos de resultado

Puede definir la forma en que se muestran los resultados en vertical diseñando el diseño con los tipos de resultados. El diseño de los resultados le permite mostrar información importante directamente en los resultados de la búsqueda, de modo que los usuarios no tengan que seleccionar cada resultado para ver si encontraron lo que están buscando.

Un tipo de resultado de búsqueda es una regla que hace que diferentes tipos de resultados de búsqueda se muestren de manera distinta. Consta de lo siguiente:

- **Una o más condiciones** con las que comparar cada resultado de búsqueda, como el origen de contenido de los resultados de la búsqueda.  
- **Diseño de resultados** que se va a usar para los resultados de la búsqueda que cumplan las condiciones. El diseño de los resultados controla la forma en que todos los resultados que cumplen las condiciones aparecen y se comportan en una página de resultados de búsqueda.

**Debe crear al menos un tipo de resultado para que los resultados se muestren en la vertical.** Puede crear varios tipos de resultado para cada vertical, lo que le permite usar distintos diseños para diferentes tipos de resultados. Por ejemplo, puede personalizar los incidentes de *gravedad 1* para tener colores más prominentes y una fuente más grande en comparación con los incidentes de *gravedad 3* .

Después de iniciar el asistente, se le guiará por los pasos para definir el nombre, el origen de contenido y las condiciones para el tipo de resultado. Puede definir la prioridad del tipo de resultado de la vista de lista.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Crear un tipo de resultado en el nivel de organización

1. En el [centro de administración](https://admin.microsoft.com), vaya a **configuración**de  >  **Microsoft Search**y, a continuación, seleccione **tipo de resultado**.
1. Para agregar un **tipo de resultado**, seleccione **Agregar**. Para editar un tipo de resultado, seleccione el tipo de resultado en la lista correspondiente.

### <a name="create-a-results-type-at-the-site-level"></a>Crear un tipo de resultados en el nivel de sitio

1. En el sitio de [SharePoint](https://sharepoint.com/) en el que desea crear el tipo de resultado, vaya a **configuración**.
1. Seleccione **información del sitio** y, a continuación, **ver toda la configuración del sitio**.
1. Busque la sección de Microsoft Search y, a continuación, seleccione **configurar Microsoft Search para esta colección de sitios**.
1. En el panel de navegación, vaya a **experiencia personalizada**y seleccione la pestaña **tipo de resultado** .
2. Para agregar un tipo de resultado, seleccione **Agregar**.  O bien, para editar un tipo de resultado, seleccione el tipo de resultado en la lista.

### <a name="view-the-vertical-after-its-enabled"></a>Ver la vertical después de que esté habilitada

Después de habilitar el vertical, puede tardar un rato antes de poder verlo. Si no quiere esperar después de habilitarla, puede anexar **cacheClear = true** a la dirección URL de [SharePoint](https://sharepoint.com/) y [Office](https://office.com) para ver la vertical inmediatamente.

## <a name="troubleshooting"></a>Solución de problemas

Esta es una lista de problemas comunes que puede encontrarse y acciones para corregirlos.

|Error  |Action  |
|---------|---------|
| Aparece el mensaje de error "se ha producido un problema" en la vertical. | Tanto los tipos de resultados como los verticales son necesarios para completar la configuración. Asegúrese de que ha creado ambos para el mismo origen de contenido. |
| No veo el diseño de los resultados, aunque creé uno. | Tarda unos minutos porque esta configuración suele almacenarse en caché. Espere unos minutos y vuelva a intentarlo.        |
| No veo ningún origen de contenido en la página tipo de resultado o vertical. | Asegúrese de que ha configurado los conectores y los datos indizados.   |

## <a name="next-steps"></a>Siguientes pasos

[Paso 3: personalizar el diseño de los resultados](customize-results-layout.md)
