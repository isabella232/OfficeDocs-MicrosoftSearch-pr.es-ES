---
title: Administrar verticales de búsqueda
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Administrar las verticales de búsqueda en la página de resultados
ms.openlocfilehash: 89887b6ce5391d2473692504efa3c0eb35407b48
ms.sourcegitcommit: 967a02ee932f8a6cee70cfd78bb0c8b1b78d07c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127814"
---
# <a name="manage-search-verticals"></a>Administrar verticales de búsqueda

Las verticales de búsqueda son pestañas de la página de resultados de búsqueda que muestran los resultados de un tipo específico o de orígenes seleccionados. Por ejemplo, la vertical Archivos muestra los resultados clasificados como archivos y facilita a los usuarios que buscan documentos. Puede personalizar verticales en Búsqueda de Microsoft para satisfacer las necesidades de su organización o departamentos individuales.

Puede administrar verticales en dos niveles:

- **Nivel de** la organización: aparece una vertical en el nivel de la organización en la página de resultados de búsqueda cuando los usuarios buscan desde su página de inicio de [SharePoint,](https://sharepoint.com/) Microsoft Office [y](https://office.com)Búsqueda de Microsoft en [Bing](https://bing.com)
- **Nivel de sitio:** aparece una vertical en el nivel del sitio en la página de resultados de búsqueda cuando los usuarios buscan en un SharePoint sitio. Por ejemplo, es posible que desee permitir a los empleados de servicio al cliente buscar incidentes de gravedad 1 directamente desde el sitio de SharePoint departamento.

## <a name="understanding-search-verticals"></a>Descripción de las verticales de búsqueda

Búsqueda de Microsoft tiene dos tipos de verticales, fuera del cuadro y verticales personalizados. Las verticales listas para usar como All, Files y People crean un fácil acceso a los resultados de búsqueda más usados.

Las opciones de configuración adicionales se ofrecen en verticales personalizadas y se pueden usar para crear la mejor experiencia para los usuarios.

Puede agregar verticales de búsqueda que sean relevantes para su organización. Por ejemplo, puede crear una vertical para contenido relacionado con el marketing y otra para ventas, en función del tipo de información que necesita cada departamento. Se pueden agregar verticales para mostrar los resultados del contenido indizado por conectores de [Graph,](connectors-overview.md)pero no se puede crear una vertical para el contenido que reside en SharePoint.

## <a name="create-search-verticals"></a>Crear verticales de búsqueda

La experiencia de administración vertical está controlada por el asistente, se le guiará a través de los pasos para definir el nombre, el origen de contenido y el ámbito de la vertical del contenido que se va a buscar. Puede usar un conjunto limitado de lenguaje de consulta de palabras clave [(KQL)](#keyword-query-language-kql) para definir el ámbito de la búsqueda vertical de un origen de contenido determinado.

A continuación se indican los pasos para crear las verticales personalizadas Búsqueda de Microsoft en [SharePoint principal,](https://sharepoint.com/) [Office](https://office.com/)o [Bing](https://bing.com/).  

### <a name="manage-organization-level-verticals"></a>Administrar verticales de nivel de organización

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a la página [**Verticales**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) de la sección **Personalización.**
1. Haga **clic en** Agregar para crear una nueva vertical.
1. Después de pasar por los pasos de configuración, puede revisar y guardar la vertical.  

### <a name="manage-site-level-verticals"></a>Administrar verticales de nivel de sitio

1. En el SharePoint donde desea administrar verticales, abra el panel de configuración haciendo clic en el engranaje.
1. Seleccione **Información del sitio** y, a continuación, seleccione Ver toda la configuración del **sitio**.  
1. Busque la sección Búsqueda de Microsoft y, a continuación, seleccione **Configurar la configuración de búsqueda**.
1. En el panel de navegación, vaya a Experiencia personalizada y, a continuación, **seleccione Verticales**.
1. Haga **clic en** Agregar para crear una nueva vertical.
1. Después de configurar la configuración, puede revisar y guardar la vertical.  

## <a name="view-the-vertical-in-search-results"></a>Ver la vertical en los resultados de búsqueda

Se [necesita un diseño de](manage-result-types.md) resultados de búsqueda para Graph del conector de búsqueda que se represente en la página vertical de búsqueda. Al asegurarse de que el diseño de resultados adecuado esté presente, puede habilitar la búsqueda vertical. Después de habilitar una vertical, hay un retraso de unas horas antes de poder verlo. Puede anexar cacheClear=true a la dirección URL en SharePoint y Office para ver la vertical inmediatamente. En Bing, anexa &features=uncachedVerticals a la dirección URL vertical de trabajo para ver la vertical inmediatamente.

> [!NOTE]
> Las verticales agregadas no son visibles [en SharePoint](https://sharepoint.com/) y [Office](https://office.com) cuando se ven desde exploradores web móviles.

## <a name="advanced-configuration-options"></a>Opciones de configuración avanzada

### <a name="multiple-connections-in-a-vertical"></a>Varias conexiones en una vertical

Una vertical de búsqueda puede obtener resultados de varios orígenes de conectores. Esta opción proporciona flexibilidad para diseñar la página de resultados de búsqueda. El proceso de configuración vertical permite a los administradores seleccionar varias conexiones en el paso "Origen de contenido".

Si designa con precisión tantas *etiquetas semánticas* como sea posible, esta experiencia se mejora. Se agregan etiquetas semánticas en el punto de definición e ingesta del esquema. [Vea más información sobre cómo crear y administrar etiquetas semánticas](configure-connector.md#step-6-assign-property-labels).
[Esta](configure-connector.md#step-6-assign-property-labels) es la información adicional sobre cómo crear y administrar etiquetas semánticas.

> [!NOTE]
> - Las varias conexiones de una característica vertical se encuentran actualmente en versión preliminar. Para obtener más información, vea [Connectors preview features](connectors-overview.md#what-are-the-preview-features).
> - Una conexión se puede agregar como origen de contenido en una sola vertical. No puede usar conexiones en varias verticales.

Para configurar una consulta para una vertical de búsqueda donde se han agregado varios orígenes de conexión, use propiedades de origen comunes para crear la consulta.

### <a name="keyword-query-language-kql"></a>Lenguaje de consulta de palabras clave (KQL)

Se puede agregar una consulta a una vertical para limitar los resultados que se muestran en la vertical de búsqueda mediante lenguaje de consulta de palabras clave [(KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) (compatibilidad limitada). En esta página se enumeran las propiedades disponibles. Se recomienda usar palabras clave de texto libre y restricciones de propiedades con operadores booleanos para crear KQL. Los operadores de clasificación dinámica como XRANK, operadores de proximidad y palabras no son compatibles.

Estas son algunas consultas de ejemplo.

|Escenario         | Query   |  
| --------- | ------ |
|Excluir resultados de sitios de archivo           |NOT (path:http//contoso.sharepoint.com/archive OR path:http//contoso.sharepoint.com/CompanyArchive)|
| Excluir resultados basados en la propiedad de tipo de archivo | NOT(FileType:htm)|  

#### <a name="profile-query-variables"></a>Variables de consulta de perfil

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
> - La característica de variables de consulta de perfil está actualmente en versión preliminar. Para obtener más información acerca de la vista previa, vea [Connectors preview features](connectors-overview.md#what-are-the-preview-features).

## <a name="troubleshooting"></a>Solución de problemas

Esta es una lista de problemas comunes que puede encontrar y acciones para solucionarlos.

|Problema  |Acción  |
|---------|---------|
| Veo un mensaje de error "Algo salió mal" en la vertical. | Tanto los tipos verticales como los de resultados son necesarios para completar la configuración. Asegúrese de que ambos están configurados para el origen de contenido. |
| No veo ningún orígenes de contenido en la página vertical. | Asegúrese de que ha configurado conectores y datos indizados.   |
