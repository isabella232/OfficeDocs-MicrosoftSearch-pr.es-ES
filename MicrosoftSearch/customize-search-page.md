---
title: Personalizar la Búsqueda de Microsoft web
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
description: Agregar verticales de búsqueda y personalizar resultados de búsqueda
ms.openlocfilehash: 4dd3f08f6d7e3df0aa983684eb0d4f649bc409a1
ms.sourcegitcommit: 1e766e1f549c46882f47df6679f5a3cdf48d70d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2021
ms.locfileid: "53463230"
---
# <a name="customize-the-search-results-page"></a>Personalizar la página de resultados de búsqueda

Puede crear verticales de búsqueda y tipos de resultados para personalizar los resultados de búsqueda que los usuarios ven cuando buscan en Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com)y Búsqueda de Microsoft en [Bing](https://bing.com). Las verticales facilitan a los usuarios encontrar la información que tienen permiso para ver. Por ejemplo, puede crear una vertical de búsqueda para los datos de análisis de marketing de software de terceros para los usuarios del departamento de marketing. También puede definir tipos de resultados y personalizar el diseño de estos datos.  

Puede crear verticales y tipos de resultados en estos niveles:

- **Nivel de** la organización: al agregar una vertical en el nivel de la organización, aparece en la página de resultados de búsqueda cuando los usuarios buscan desde su página de inicio de [SharePoint,](https://sharepoint.com/) en [Office](https://office.com)o en [Bing](https://bing.com).
- **Nivel de** sitio: por ejemplo, es posible que desee permitir a los empleados de servicio al cliente buscar incidentes de gravedad *1* directamente desde el sitio de SharePoint departamento.

## <a name="search-verticals-explained"></a>Se explicaron las verticales de búsqueda

En la parte superior de la Búsqueda de Microsoft resultados, hay una fila de pestañas. Estas son las verticales de búsqueda. Una vertical de búsqueda solo muestra resultados de un tipo determinado o de determinado contenido. Algunos ejemplos **son Archivos** o **Noticias.** De forma predeterminada, Búsqueda de Microsoft los verticales **All**, **People**, **Files**, **Sites** y **News**.  

Puede agregar verticales de búsqueda que sean relevantes para su organización. Aparecerán en la página de Búsqueda de Microsoft resultados de [SharePoint](https://sharepoint.com/), [Office](https://Office.com)y [Bing](https://bing.com). Por ejemplo, puede crear una vertical para contenido relacionado con el marketing y otra para ventas, en función del tipo de información que necesita cada grupo. Puede agregar verticales para mostrar los resultados solo del contenido indizado a través de conectores.  

### <a name="multiple-connections-in-a-vertical"></a>Varias conexiones en una vertical

Ahora, una vertical de búsqueda puede obtener resultados de varios orígenes de conectores. Esto proporciona una mayor flexibilidad en el diseño de la página de resultados de búsqueda. La experiencia administrativa existente de la configuración vertical permite seleccionar varias conexiones en el paso "Origen de contenido".
Si designa con precisión tantas etiquetas semánticas como sea posible, esta experiencia se mejorará. Puede agregar etiquetas semánticas tras la definición y la ingesta del esquema.

[Esta](configure-connector.md#step-5-assign-property-labels) es la información adicional sobre cómo crear y administrar etiquetas semánticas.

> [!NOTE]
> Varias conexiones en una vertical se encuentran actualmente en versión preliminar. Para obtener más información acerca de la vista previa, vea [Connectors preview features](connectors-overview.md#what-are-the-preview-features).

### <a name="things-you-should-know"></a>Cosas que debes saber

1. Una conexión solo se puede agregar como origen de contenido debajo de una vertical. No se permite volver a usar las conexiones en varias verticales.
2. Si necesita configurar una consulta para una búsqueda vertical en la que se han agregado varios orígenes de conexión, se deben usar propiedades de origen comunes para crear una consulta de este tipo.

## <a name="things-to-consider"></a>Consideraciones que se deben tener en cuenta

Antes de empezar, asegúrese de que el conector se ha indizado. Esto puede tardar hasta 48 horas, según el tamaño del archivo.

No puede crear una vertical para el contenido que reside en [SharePoint](https://sharepoint.com/).

Hay tres pasos básicos para agregar una vertical:

1. Cree la vertical. En este paso, se define el nombre, el origen de contenido y el ámbito de la vertical del contenido que se va a buscar.
2. Define cómo serán los resultados de esta vertical.  
3. Habilite la vertical (que se mostrará) de la página de lista vertical.

## <a name="step-1-create-the-search-vertical"></a>PASO 1: Crear la búsqueda vertical

Después de iniciar el asistente, se le guiará por los pasos para definir el nombre de la vertical, el origen de contenido y el ámbito del contenido que se va a buscar. La vertical se crea en un estado deshabilitado. Lo habilitará más adelante.

Puede usar un conjunto limitado de lenguaje de consulta de palabras clave [(KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) para restringir el ámbito. En esta página se enumeran las propiedades disponibles. Se recomienda usar palabras clave de texto libre y restricciones de propiedades con operadores booleanos para crear KQL.
KQL también admite el uso de variables de consulta [de perfil para](#profile-query-variables) ajustar los resultados en la vertical.

### <a name="create-a-vertical-at-the-organization-level"></a>Crear una vertical en el nivel de la organización

Para crear la vertical en Búsqueda de Microsoft en [SharePoint](https://sharepoint.com/) [principal,](https://office.com)Office , o [Bing](https://bing.com), siga estos pasos:

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**Verticales**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Seleccione **Agregar** para empezar.  

### <a name="create-a-vertical-at-the-site-level"></a>Crear una vertical en el nivel de sitio

1. En el [SharePoint](https://sharepoint.com/) donde desea la vertical, vaya a **Configuración**.
2. Seleccione **Información del sitio** y, a continuación, Ver toda la configuración del **sitio**.
3. Busque la sección **Búsqueda de Microsoft** y, a continuación, seleccione **Configurar Búsqueda de Microsoft para esta colección de sitios**.
4. En el panel de navegación, vaya **a Experiencia personalizada** y, a continuación, seleccione la pestaña **Verticales.**
5. Para agregar una vertical, seleccione **Agregar**.
  O bien, para editar una vertical, selecciónelo en la lista.

Recuerde que las verticales se crean en un estado deshabilitado. Deben estar habilitadas para que los usuarios puedan verlos.

## <a name="step-2-create-the-result-types"></a>PASO 2: Crear los tipos de resultados

Puede definir cómo se muestran los resultados en la vertical diseñando el diseño con tipos de resultados. El diseño de resultados le permite mostrar información importante directamente en los resultados de búsqueda, por lo que los usuarios no tienen que seleccionar cada resultado para ver si encontraron lo que están buscando.

### <a name="default-search-result-layout"></a>Diseño de resultados de búsqueda predeterminado

Se mostrará un diseño de resultados  de búsqueda predeterminado para el contenido de Connector si las etiquetas y la propiedad **de** contenido se han asignado correctamente a las propiedades de origen en el momento de configurar el conector. El título **de la** etiqueta es la etiqueta más importante. Se recomienda **encarecidamente que** tenga una propiedad asignada a esta etiqueta para usar el diseño de resultados de búsqueda predeterminado.

### <a name="create-your-own-result-type"></a>Crear su propio tipo de resultado

Puede decidir crear su propio diseño de resultados de búsqueda e invalidar el diseño de resultados de búsqueda predeterminado mediante la creación de un **tipo de resultado**. Un tipo de resultado de búsqueda es una regla que hace que diferentes tipos de resultados de búsqueda se muestren de manera distinta. Consta de lo siguiente:

- **Una o más condiciones para** comparar cada resultado de búsqueda, como el origen de contenido del resultado de la búsqueda.  
- Diseño **de resultados que** se usará para los resultados de búsqueda que cumplan las condiciones. El diseño resultante controla la forma en que todos los resultados que cumplen las condiciones aparecen y se comportan en una página de resultados de búsqueda.

**Si no se realiza la asignación adecuada para mostrar el diseño de resultados de búsqueda predeterminado, debe crear al menos un tipo de resultado para que los resultados se muestren en la vertical.** Puede crear varios tipos de resultados para cada vertical, lo que le permite usar diseños diferentes para diferentes tipos de resultados. Por ejemplo, puede personalizar los incidentes de gravedad *1* para que tengan colores más prominentes y una fuente más grande en comparación con incidentes de gravedad *3.*

Después de iniciar el asistente, se le guiará a través de los pasos para definir el nombre, el origen de contenido y las condiciones del tipo de resultado. Puede definir la prioridad del tipo de resultado desde la vista de lista.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Crear un tipo de resultado en el nivel de la organización

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**Tipos de resultados**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
2. Para agregar un **tipo de resultado,** seleccione **Agregar**. Para editar un tipo de resultado, seleccione el tipo de resultado en la lista correspondiente.

### <a name="create-a-results-type-at-the-site-level"></a>Crear un tipo de resultados en el nivel de sitio

1. En el [SharePoint](https://sharepoint.com/) donde desea crear el tipo de resultado, vaya **a Configuración**.
2. Seleccione **Información del sitio** y, a continuación, Ver toda la configuración del **sitio**.
3. Busque la sección Búsqueda de Microsoft y, a continuación, seleccione **Configurar Búsqueda de Microsoft para esta colección de sitios**.
4. En el panel de navegación, vaya **a Experiencia personalizada** y seleccione Pestaña Tipo **de** resultado.
5. Para agregar un tipo de resultado, seleccione **Agregar**.  O bien, para editar un tipo de resultado, seleccione el tipo de resultado en la lista.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>PASO 3: Ver la vertical después de habilitarla

Después de habilitar la vertical, llevará unas horas antes de poder verlo. Si no desea esperar después de habilitarlo, puede anexar **cacheClear=true** a [](https://office.com) la dirección URL en [SharePoint](https://sharepoint.com/) y Office para ver la vertical inmediatamente. Por [Bing](https://bing.com), anexa&**features=uncachedVerticals** a la dirección URL vertical de trabajo para ver las verticales inmediatamente.

> [!NOTE]
> Las verticales agregadas no serán visibles en [SharePoint](https://sharepoint.com/) y [Office](https://office.com) cuando se ven desde exploradores web móviles.

## <a name="profile-query-variables"></a>Variables de consulta de perfil

Las variables de consulta se usan en la sección consulta KQL de una vertical para proporcionar datos dinámicos como entrada a la consulta de una vertical. Puede usar variables de consulta de perfil para contextualizar los resultados de la búsqueda al usuario que ha iniciado sesión. Las variables de consulta de perfil capturan valores del perfil del usuario que ha [iniciado sesión.](/graph/api/resources/profile?view=graph-rest-beta)

Por ejemplo, si desea crear una vertical "Tickets" donde un usuario que ha iniciado sesión pueda buscar vales de soporte técnico asignados, puede especificar la siguiente consulta en la sección "Consulta" durante la creación vertical en la página de administración.  

**AssignedTo:{Profile.accounts.userPrincipalName}**

Esto limitará los resultados de la búsqueda para mostrar solo los elementos donde el usuario asignado es el usuario que realiza la búsqueda.

[El recurso Profile](/graph/api/resources/profile?view=graph-rest-beta) expone propiedades como colecciones. Por ejemplo, la información relacionada con las direcciones de correo electrónico se expone a través de la recopilación de correo electrónico, las posiciones de trabajo como colección de posiciones, y así sucesivamente. Todas las propiedades disponibles en el perfil de usuario, que tienen AAD como tipo de origen, se exponen como variables de consulta.

Considera un usuario que tiene 3 direcciones de correo electrónico disponibles en la colección de correo electrónico, como se muestra a continuación.

```json
"emails": [{ 

        "address": "Megan.Bowen@contoso.com",
        "id": "xyz", 
        "source": { 
            "CreatedBy": "xyz", 
            "CreatedOn": "2222", 
            "Type": "official" 
        },
        "type": "main" 
    }, { 
        "address": "meganb@hotmail.com",
        "id": "abc", 
        "source": { 
            "CreatedBy": "abc",
            "CreatedOn": "3333", 
            "Type": "non-official",
        },
        "type": "work"
    }, { 
        "address": "meganb@outlook.com",
        "id": "pqr", 
        "source": { 
            "CreatedBy": "pqr", 
            "CreatedOn": "4444", 
            "Type": "personal" 
        },
        "type": "personal" 
    } 
] 
```

- La consulta **MyProperty: {Profile.emails.address}** se resolverá en MyProperty: "Megan.Bowen@contoso.com".  

- Si desea resolver todos los valores del atributo address, debe usar la sintaxis de expansión de varios valores. La consulta **{| MyProperty:{Profile.emails.address}}** se resolverá en ((MyProperty:"Megan.Bowen@contoso.com") OR (MyProperty: "meganb@hotmail.com") OR (MyProperty:"meganb@outlook.com"))  

El operador "|" debe usarse para resolver variables de varios valores. Para obtener más ejemplos sobre la expansión de perfiles, consulte la tabla siguiente.

| #         | Sintaxis |  Valor devuelto  |
| --------- | ------ | --- |
| 1    | MyProperty:{Profile.emails.address}  |   "Megan.Bowen@contoso.com"  |
| 2 | MyProperty:{Profile.emails}   |    {Profile.emails} Esto no se resolverá porque los correos electrónicos son un objeto.|
| 3    | {? MyProperty:{Profile.emails}}  |  Esto no se resolverá porque los correos electrónicos son un objeto. El "?" operador omite las variables de consulta que no se resuelven. Esta variable se quitará cuando se pase más abajo por la pila de consultas.   |
| 4  | {&#124;MyProperty: {Profile.emails.source.Type}}    |  ((MyProperty:"official") OR (MyProperty:"non-official") OR (MyProperty:"personal"))    |

> [!NOTE]
>
> - Las variables de consulta de perfil solo se admiten para verticales personalizados que usan un [conector](connectors-overview.md) como origen de contenido.
> - Las variables de consulta de perfil se definen en la sección "Consulta" del [proceso de configuración vertical](customize-search-page.md#step-1-create-the-search-vertical).
> - Las variables de consulta de perfil se encuentran actualmente en versión preliminar. Para obtener más información acerca de la vista previa, vea [Connectors preview features](connectors-overview.md#what-are-the-preview-features).

## <a name="troubleshooting"></a>Solución de problemas

Esta es una lista de problemas comunes que puede encontrar y acciones para solucionarlos.

|Error  |Acción  |
|---------|---------|
| Veo un mensaje de error "Algo salió mal" en la vertical. | Tanto los tipos verticales como los de resultados son necesarios para completar la configuración. Asegúrese de haber creado ambos para el mismo origen de contenido. |
| No veo el diseño de los resultados, aunque he creado uno. | Tarda unos minutos porque esta configuración suele almacenarse en caché. Espere unos minutos e inténtelo de nuevo.        |
| No veo ningún orígenes de contenido en la página vertical o de tipo de resultado. | Asegúrese de que ha configurado conectores y datos indizados.   |

## <a name="next-steps"></a>Pasos siguientes

[Personalizar el diseño de resultados](customize-results-layout.md)
