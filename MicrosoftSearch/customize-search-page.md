---
title: Personalizar la Búsqueda de Microsoft web
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Agregar verticales de búsqueda y personalizar resultados de búsqueda
ms.openlocfilehash: 1ca436a2617e32e285715e4fffd622dc7a571ca1
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973572"
---
# <a name="customize-the-search-results-page"></a>Personalizar la página de resultados de búsqueda

Puede crear verticales  de búsqueda y tipos de resultados para personalizar los *resultados* de búsqueda que los usuarios ven cuando buscan en Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com)y Búsqueda de Microsoft en [Bing](https://bing.com). Las verticales facilitan a los usuarios encontrar la información que tienen permiso para ver.

Por ejemplo, puede crear una vertical de búsqueda para los datos de análisis de marketing de software de terceros para los usuarios del departamento de marketing. También puede definir tipos de resultados y personalizar el diseño de estos datos.

## <a name="about-search-verticals"></a>Acerca de las verticales de búsqueda

Hay una fila de pestañas en la parte superior de la página Búsqueda de Microsoft resultados. Se trata de verticales de búsqueda. Una vertical de búsqueda solo muestra resultados de un tipo determinado o de un determinado conjunto de contenido. Algunos ejemplos **son Archivos** o **Noticias.** De forma predeterminada, Búsqueda de Microsoft los verticales **All**, **People**, **Files**, **Sites** y **News**.  

Puede agregar verticales de búsqueda que sean relevantes para su organización. Aparecerán en la página de Búsqueda de Microsoft resultados de SharePoint, Office y Bing. Por ejemplo, puede crear una vertical para contenido relacionado con el marketing y otra para ventas, en función del tipo de información que necesita cada departamento. Puede agregar verticales para mostrar los resultados solo del contenido indizado a través de conectores.

Puede crear verticales y tipos de resultados en dos niveles:

- **Nivel de** organización: una vertical que se crea en el nivel de la organización aparece en la página de resultados de búsqueda cuando los usuarios buscan desde su página de inicio de [SharePoint,](https://sharepoint.com/) en [Office](https://office.com)o en [Bing](https://bing.com).
- **Nivel de** sitio: por ejemplo, es posible que desee permitir a los empleados de servicio al cliente buscar incidentes de gravedad *1* directamente desde el sitio de SharePoint departamento.

### <a name="multiple-connections-in-a-vertical"></a>Varias conexiones en una vertical

Una vertical de búsqueda puede obtener resultados de varios orígenes de conectores. Esta opción proporciona flexibilidad para diseñar la página de resultados de búsqueda. El proceso de configuración vertical permite a los administradores seleccionar varias conexiones en el paso "Origen de contenido".

Si designa con precisión tantas *etiquetas semánticas* como sea posible, esta experiencia se mejora. Se agregan etiquetas semánticas en el punto de definición e ingesta del esquema. [Vea más información sobre cómo crear y administrar etiquetas semánticas](configure-connector.md#step-6-assign-property-labels).
[Esta](configure-connector.md#step-6-assign-property-labels) es la información adicional sobre cómo crear y administrar etiquetas semánticas.

> [!NOTE]
> Las varias conexiones de una característica vertical se encuentran actualmente en versión preliminar. Para obtener más información, vea [Connectors preview features](connectors-overview.md#what-are-the-preview-features).

Una conexión se puede agregar como origen de contenido en una sola vertical. No puede usar conexiones en varias verticales.

Para configurar una consulta para una vertical de búsqueda donde se han agregado varios orígenes de conexión, use propiedades de origen comunes para crear la consulta.

### <a name="before-you-create-verticals-and-result-types"></a>Antes de crear verticales y tipos de resultados

Ten en cuenta los siguientes factores:

- Asegúrese de que el conector se ha indizado. Esto puede tardar hasta 48 horas, según el tamaño del archivo.

- No puede crear una vertical para el contenido que reside en SharePoint.

Estos son los pasos para implementar una vertical:

1. Cree la vertical. En este paso, se define el nombre, el origen de contenido y el ámbito de la vertical del contenido que se va a buscar.
2. Define cómo serán los resultados de esta vertical.  
3. Habilite la vertical (que se mostrará) de la página de lista vertical.

## <a name="step-1-create-the-search-vertical"></a>Paso 1: Crear la vertical de búsqueda

Después de iniciar el asistente, se le guiará por los pasos para definir el nombre de la vertical, el origen de contenido y el ámbito del contenido que se va a buscar.

>[!Note]
>Las verticales se crean en un estado deshabilitado. Puede habilitarlos para que puedan verlos.

Puede usar un conjunto limitado de lenguaje de consulta de palabras clave [(KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) para restringir el ámbito. (Las propiedades que puede usar se describen más adelante en este artículo). Se recomienda usar palabras clave de texto libre y restricciones de propiedades con operadores booleanos. KQL también admite variables [de consulta de perfil](#profile-query-variables) para ajustar los resultados en la vertical.

### <a name="create-a-vertical-at-the-organization-level"></a>Crear una vertical en el nivel de la organización

Para crear una vertical en Búsqueda de Microsoft en SharePoint principal, Office o Bing, siga estos pasos:

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**Verticales**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Seleccione **Agregar** para empezar.  

### <a name="create-a-vertical-at-the-site-level"></a>Crear una vertical en el nivel de sitio

1. En el [SharePoint](https://sharepoint.com/) donde desea la vertical, vaya a **Configuración**.
2. Seleccione **Información del sitio** y, a continuación, seleccione Ver toda la configuración del **sitio**.
3. Busque la **Búsqueda de Microsoft** y, a continuación, seleccione **Configurar Búsqueda de Microsoft para esta colección de sitios**.
4. En el panel de navegación, vaya **a Experiencia personalizada** y, a continuación, seleccione la pestaña **Verticales.**
5. Para agregar una vertical, seleccione **Agregar**. O bien, para editar una vertical, selecciónelo en la lista.

## <a name="step-2-create-result-types"></a>Paso 2: Crear tipos de resultados

Puede usar tipos *de resultados* para definir cómo se muestran los resultados en la vertical. El diseño de resultados le permite mostrar información importante directamente en los resultados de búsqueda, por lo que los usuarios no tienen que seleccionar cada resultado para ver si encontraron lo que están buscando.

### <a name="default-search-result-layout"></a>Diseño de resultados de búsqueda predeterminado

Se mostrará un diseño de resultados  de  búsqueda predeterminado para el contenido del conector si las etiquetas y las propiedades de contenido se asignaron correctamente a las propiedades de origen cuando se configuró el conector. La *etiqueta de* título es la etiqueta más importante. Se *recomienda encarecidamente* que tenga una propiedad asignada a esta etiqueta para usar el diseño de resultados de búsqueda predeterminado.

### <a name="create-your-own-result-type"></a>Crear su propio tipo de resultado

Para crear su propio diseño de resultados de búsqueda e invalidar el diseño de resultados de búsqueda predeterminado, cree un *tipo de resultado*. Un tipo de resultado de búsqueda es una regla que hace que diferentes tipos de resultados de búsqueda se muestren de manera distinta. Estos son sus componentes:

- **Una o más condiciones para** comparar cada resultado de búsqueda, como el origen de contenido del resultado de la búsqueda.  
- Diseño **de resultados que** se usará para los resultados de búsqueda que cumplan las condiciones. El diseño resultante controla cómo aparecen y se comportan los resultados que cumplen las condiciones en una página de resultados de búsqueda.

*Si no hace una asignación adecuada para mostrar el diseño de resultados de búsqueda predeterminado, debe crear al menos un tipo de resultado para que los resultados se muestren en la vertical.* 

Puede crear varios tipos de resultados para cada vertical, lo que le permite usar diseños diferentes para diferentes tipos de resultados. Por ejemplo, puede personalizar los incidentes de gravedad *1* para que tengan colores más destacados y una fuente más grande que los incidentes de gravedad *3.*

Después de iniciar el asistente, se le guiará a través de los pasos para definir el nombre, el origen de contenido y las condiciones del tipo de resultado. Puede definir la prioridad del tipo de resultado desde la vista de lista.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Crear un tipo de resultado en el nivel de la organización

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**Tipos de resultados**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
2. Para agregar un tipo de resultado, seleccione **Agregar**. Para editar un tipo de resultado, seleccione el tipo de resultado de la lista correspondiente.

### <a name="create-a-result-type-at-the-site-level"></a>Crear un tipo de resultado en el nivel de sitio

1. En el [SharePoint](https://sharepoint.com/) donde desea el tipo de resultado, vaya a **Configuración**.
2. Seleccione **Información del sitio** y, a continuación, seleccione Ver toda la configuración del **sitio**.
3. Busque la sección **Búsqueda de Microsoft** y, a continuación, seleccione **Configurar Búsqueda de Microsoft para esta colección de sitios**.
4. En el panel de navegación, vaya **a Experiencia personalizada** y seleccione la pestaña Tipo **de** resultado.
5. Para agregar un tipo de resultado, seleccione **Agregar**.  O bien, para editar un tipo de resultado, seleccione el tipo de resultado en la lista.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>Paso 3: Ver la vertical después de habilitarla

Después de habilitar la vertical, hay un retraso de unas horas antes de poder verlo. Pero puede anexar `cacheClear=true` a la dirección URL en SharePoint y Office para ver la vertical inmediatamente. Para Bing, anexa `&features=uncachedVerticals` a la para ver la vertical `Work vertical URL` inmediatamente.

> [!NOTE]
> Las verticales agregadas no son visibles en SharePoint]( y Office cuando se https://sharepoint.com/) ven desde exploradores web móviles. [](https://office.com)

## <a name="profile-query-variables"></a>Variables de consulta de perfil

Use variables en la sección de consulta KQL de una vertical para proporcionar datos dinámicos como entrada a la consulta de una vertical. Puede usar variables de consulta de perfil para contextualizar los resultados de la búsqueda al usuario que ha iniciado sesión. Las variables de consulta de perfil capturan valores del perfil del usuario que ha [iniciado sesión.](/graph/api/resources/profile)

Por ejemplo, para crear una vertical "Tickets" para que el usuario encuentre vales de soporte técnico asignados, puede especificar la siguiente consulta en la sección "Consulta" durante la creación vertical en la página de administración:  

`AssignedTo:{Profile.accounts.userPrincipalName}`

Este idioma limitará los resultados de la búsqueda para mostrar solo los elementos para los que el usuario asignado es el usuario que ejecuta la búsqueda.

[El recurso Profile](/graph/api/resources/profile) expone propiedades como colecciones. Por ejemplo, la información relacionada con las direcciones de correo electrónico se expone a través de la recopilación de correo electrónico, las posiciones de trabajo como colección de posiciones, y así sucesivamente. Todas las propiedades disponibles en el perfil de usuario, que tienen AAD como tipo de origen, se exponen como variables de consulta.


Considere la posibilidad de un usuario que tenga tres direcciones de correo electrónico disponibles en la colección de correo electrónico, como se muestra aquí:

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

- La consulta `MyProperty: {Profile.emails.address}` se resolverá en *MyProperty: "Megan.Bowen@contoso.com".*  

- Para resolver todos los valores del atributo address, use la sintaxis de expansión de varios valores. La consulta se resolverá en `{|MyProperty:{Profile.emails.address}}` *((MyProperty:"Megan.Bowen@contoso \. com")* o *(MyProperty: "meganb@hotmail \. com")* o *(MyProperty:"meganb@outlook \. com")).*

Use el operador "|" para resolver variables de varios valores. Vea la tabla siguiente para obtener más ejemplos de expansión de perfiles.

| #         | Sintaxis |  Valor devuelto  |
| --------- | ------ | --- |
| 1    | MyProperty:{Profile.emails.address}  |   "Megan \. Bowen@contoso.com"  |
| 2 | MyProperty:{Profile.emails}   |    {Profile.emails} Esto no se resolverá porque *los correos electrónicos* son un objeto.|
| 3    | {? MyProperty:{Profile.emails}}  |  Esto no se resolverá porque *los correos electrónicos* son un objeto. El "?" operador omite las variables de consulta que no se resuelven. Esta variable se quitará cuando se pase más abajo por la pila de consultas.   |
| 4  | {&#124;MyProperty: {Profile.emails.source.Type}}    |  ((MyProperty:"official") o (MyProperty:"non-official") o (MyProperty:"personal"))    |

> [!NOTE]
>
> - Las variables de consulta de perfil solo se admiten para verticales personalizados que usan un [conector](connectors-overview.md) como origen de contenido.
> - Las variables de consulta de perfil se definen en la sección "Consulta" del proceso [de configuración vertical](customize-search-page.md#step-1-create-the-search-vertical).
> - La característica de variables de consulta de perfil está actualmente en versión preliminar. Para obtener más información acerca de la vista previa, vea [Connectors preview features](connectors-overview.md#what-are-the-preview-features).

## <a name="troubleshooting"></a>Solución de problemas

Esta es una lista de problemas comunes que puede encontrar y acciones para solucionarlos.

|Problema  |Acción  |
|---------|---------|
| Veo un mensaje de error "Algo salió mal" en la vertical. | Tanto los tipos verticales como los de resultados son necesarios para completar la configuración. Asegúrese de que creó ambos para el mismo origen de contenido. |
| No veo el diseño de los resultados, aunque he creado uno. | Puede haber un retraso de unos minutos porque esta configuración se almacena en caché. Espere unos minutos e inténtelo de nuevo.        |
| No veo ningún orígenes de contenido en la página vertical o de tipo de resultado. | Asegúrese de que ha configurado conectores y datos indizados.   |

## <a name="next-steps"></a>Pasos siguientes

[Personalizar el diseño de resultados](customize-results-layout.md)
