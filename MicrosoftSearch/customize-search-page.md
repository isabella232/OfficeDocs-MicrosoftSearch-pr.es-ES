---
title: Personalización de la página de búsqueda de Microsoft
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
description: Agregar presentaciones verticales de búsqueda y personalizar los resultados de la búsqueda
ms.openlocfilehash: 87b394847281e43683f2ed9dfd42d19aa103d3e2
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "37950056"
---
# <a name="customize-the-microsoft-search-page"></a>Personalización de la página de búsqueda de Microsoft

Mediante la creación de presentaciones verticales de búsqueda y los tipos de resultado, puede personalizar los resultados de la búsqueda que se muestran a los usuarios cuando buscan en **SharePoint**, **Office.com** y **Microsoft Search en Bing** . Las verticales permiten a los usuarios encontrar más fácilmente la información que tienen permiso para ver.  Por ejemplo, puede crear una presentación vertical de búsqueda para los datos de análisis de marketing de software de terceros para los usuarios del Departamento de marketing. También puede definir tipos de resultado y personalizar el diseño de estos datos.  

Puede crear tipos verticales y resultados en estos niveles: 

- Nivel de organización: cuando se agrega un vertical en el nivel de la organización, aparece en la página de resultados de búsqueda cuando los usuarios buscan desde su página de inicio de SharePoint, en Office.com y en Bing.com. 
- Nivel de sitio: por ejemplo, es posible que desee permitir a los empleados de servicio al cliente buscar incidentes de "gravedad 1" directamente desde el sitio de SharePoint de su departamento. 

## <a name="whats-a-search-vertical"></a>¿Qué es una presentación vertical de búsqueda?

En la parte superior de la página de resultados de Microsoft Search hay una fila de pestañas, estas son las presentaciones verticales de búsqueda. Una presentación vertical de búsqueda solo muestra los resultados de un tipo determinado o de determinado contenido, por ejemplo, solo archivos o noticias. De forma predeterminada, Microsoft Search muestra los verticales, todos los usuarios, archivos, sitios y noticias.  

Puede Agregar presentaciones verticales de búsqueda que sean relevantes para su organización. Estas aparecerán en la página de resultados de Microsoft Search en SharePoint, Office.com y Bing.  Por ejemplo, puede crear un vertical para el contenido relacionado con el marketing y otro para las ventas, en función del tipo de información que desea que tenga cada grupo. Puede Agregar vertical para mostrar los resultados sólo del contenido indizado a través de conectores.  

**Declinación de responsabilidades:** Los elementos verticales y los tipos de resultado están actualmente en versión preliminar como parte de Microsoft Connectors Preview. No puede crear un vertical para el contenido que reside en SharePoint o en el contenido indizado por el conector de FileShare. Para obtener más información acerca de la vista previa, consulte [conectores Preview](connectors-preview.md). Para participar en la vista previa, primero debe enviar el [formulario de suscripción de vista previa de conectores de Microsoft Graph](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).

## <a name="things-to-consider"></a>Aspectos que tener en cuenta...

Antes de empezar, asegúrese de que el conector se haya indizado. Puede tardar hasta 48 horas, según el tamaño del archivo.

No puede crear un vertical para el contenido que reside en SharePoint o en el contenido indizado por el conector de FileShare. Obtenga información sobre cómo indizar contenido (vincular a la documentación del conector).

En un nivel alto, hay tres pasos principales para agregar un vertical. 

1. Crear la vertical: en este paso, definirá el nombre y el origen de contenido vertical y el ámbito del contenido en el que se realizará la búsqueda. 
2. Defina el aspecto que tendrán los resultados de esta vertical.  
3. Habilite la vertical (para que se muestre) en la página de lista vertical.   

## <a name="step-1-create-the-search-vertical"></a>Paso 1: crear la presentación vertical de búsqueda

Una vez que inicie el asistente, se le guiará por los pasos necesarios para definir el nombre, el origen de contenido y el ámbito vertical del contenido en el que se realizará la búsqueda. El vertical se crea en un Estado deshabilitado. Se habilitará el vertical más adelante.

Puede usar un conjunto limitado del lenguaje de [consulta de palabras clave (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) para restringir el ámbito, y en la página se muestran las propiedades que tiene a su disposición. Se recomienda usar palabras clave de texto libres y restricciones de propiedad con operadores booleanos para crear KQL 

### <a name="create-a-vertical-at-the-organization-level"></a>Crear un vertical en el nivel de la organización

Para crear la vertical en Microsoft Search en la Página principal, Bing o Office.com de SharePoint, siga estos pasos:

1. En el centro de administración de Microsoft 365, vaya a **configuración** >de las**presentaciones verticales**de **Microsoft Search** > .
1. Seleccione **Agregar** para empezar.  

### <a name="create-a-vertical-at-the-site-level"></a>Crear un vertical en el nivel de sitio

1. En el sitio de SharePoint en el que desea crear la vertical, vaya a **configuración**.
1. Seleccione **información del sitio**y, a continuación, **ver toda la configuración del sitio**.
1. Busque la sección de **Microsoft Search** y, a continuación, seleccione **configurar Microsoft Search para esta colección de sitios**.
1. En el panel de navegación, vaya a **experiencia personalizada**y, a continuación, seleccione la pestaña **vertical** .
1. Para agregar una vertical, seleccione **Agregar**. <br>
O BIEN <br>Para editar una vertical, selecciónela en la lista.

Recuerde que los verticales se crean en un Estado deshabilitado. Todavía tendrá que habilitarlos para que los usuarios puedan ver los verticales.

## <a name="step-2-create-the-result-types"></a>Paso 2: crear los tipos de resultado

Puede definir la forma en que se muestran los resultados en vertical diseñando el diseño con los tipos de resultados. El diseño de los resultados le permite mostrar información importante directamente en los resultados de la búsqueda, de modo que los usuarios no tengan que hacer clic en cada resultado para ver si han encontrado lo que están buscando.

Un tipo de resultado de búsqueda es una regla que hace que diferentes tipos de resultados de búsqueda se muestren de manera distinta. Consta de lo siguiente:

- *Una o más condiciones* con las que comparar cada resultado de búsqueda, como el origen de contenido de los resultados de la búsqueda.  
- *Diseño de resultados* que se va a usar para los resultados de la búsqueda que cumplan las condiciones. El diseño de los resultados controla la forma en que todos los resultados que cumplen las condiciones aparecen y se comportan en una página de resultados de búsqueda.

**Debe crear al menos un tipo de resultado para que los resultados se muestren en la vertical.** Puede crear varios tipos de resultado para cada vertical, lo que le permite usar distintos diseños para diferentes tipos de resultados. Por ejemplo, puede personalizar los incidentes de "gravedad 1" para tener colores más prominentes y una fuente más grande en comparación con los incidentes de "gravedad 3". 

 Una vez que inicie el asistente, se le guiará por los pasos para definir el nombre, el origen de contenido y las condiciones para el tipo de resultado. Puede definir la prioridad del tipo de resultado de la vista de lista. 
  
### <a name="create-a-result-type-at-the-organization-level"></a>Crear un tipo de resultado en el nivel de organización

1. En el centro de administración de Microsoft 365, vaya a **configuración** > de**Microsoft Search**y, a continuación, seleccione **tipo de resultado**.
1. Para agregar un **tipo de resultado**, seleccione **Agregar**. Para editar un tipo de resultado, seleccione el tipo de resultado en la lista correspondiente.
 
### <a name="create-a-results-type-at-the-site-level"></a>Crear un tipo de resultados en el nivel de sitio

1. En el sitio de SharePoint en el que desea crear el tipo de resultado, vaya a **configuración**.
1. Seleccione **información del sitio**y, a continuación, **ver toda la configuración del sitio**. 
1. Busque la sección de Microsoft Search y, a continuación, seleccione **configurar Microsoft Search para esta colección de sitios**.
1. En el panel de navegación, vaya a **experiencia personalizada**y, a continuación, seleccione la pestaña tipo de resultado.
1. Para agregar un tipo de resultado, seleccione **Agregar**. <br> O BIEN <br>Para editar un tipo de resultado, seleccione el tipo de resultado en la lista.

### <a name="view-the-vertical-after-enabling"></a>Ver la vertical después de la habilitación

Después de habilitar el vertical, puede tardar un rato antes de poder verlo.
Si desea esperar después de habilitarla, puede anexar *cacheClear = true* a la dirección URL de SharePoint y Office.com para ver la vertical inmediatamente.

## <a name="troubleshooting"></a>Solución de problemas

A continuación, se muestra una lista de problemas comunes que pueden surgir y las acciones para corregirlos.


|Error  |Action  |
|---------|---------|
|Aparece el error "se ha producido un problema" en la vertical|   Los tipos de resultados y los verticales son necesarios para completar la configuración. Asegúrese de que ha creado ambos para el mismo origen de contenido.      |
|¿Por qué no veo mi diseño de resultados, aunque he creado uno? | Los tipos de resultado tardan unos minutos en usarse, ya que esta configuración suele almacenarse en caché. Espere unos minutos y vuelva a intentarlo.        |
|No veo ningún origen de contenido en la página tipo de resultado o vertical     |      Asegurarse de que ha configurado los conectores y los datos indizados   |



## <a name="next-steps"></a>Pasos siguientes
[Paso 3: personalizar el diseño de los resultados](customize-results-layout.md)
