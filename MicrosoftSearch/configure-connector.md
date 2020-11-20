---
title: Configurar el conector creado por Microsoft para Microsoft Search
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector creado por Microsoft para Microsoft Search
ms.openlocfilehash: 86ddf0387e3d00a005f25207a322c8470799b76b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367612"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Introducción al programa de instalación de los conectores de Graph en Microsoft 

En este artículo se resume el proceso básico necesario para usar el [centro de administración de microsoft 365](https://admin.microsoft.com) para configurar cualquiera de los conectores de Graph por parte de Microsoft. El proceso básico incluye los pasos siguientes:  
<!---Add links to each section in the doc--->

1. Agregue un conector de Graph en el centro de administración de Microsoft 365.
2. Asigne un nombre a la conexión.
3. Configure las opciones de conexión.
4. Administrar permisos de búsqueda.
5. Asignar etiquetas de propiedades.
6. Administrar esquema.
7. Elija Actualizar configuración.
8. Revise la conexión.

Es importante tener en cuenta que el proceso de instalación es muy similar para todos los conectores de Graph de Microsoft, pero no es exactamente el mismo. **Además de leer este artículo, asegúrese de leer el conector específico para su origen de datos.**  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: agregar un conector de Graph en el centro de administración de Microsoft 365

Complete los pasos siguientes para configurar cualquiera de los conectores creados por Microsoft.

1. Inicie sesión en su cuenta de administrador en el [centro de administración de Microsoft 365](https://admin.microsoft.com)
2. En el panel de navegación, seleccione **configuración** y, a continuación, seleccione **búsqueda & inteligencia**. Seleccione la [pestaña conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).
3.  Seleccione **+ Agregar** y, a continuación, seleccione el origen de datos que desee en el menú de opciones disponibles.

![Los orígenes de datos disponibles son: ADLS, sitios web de la empresa, Microsoft SQL Server, Azure SQL, base de datos SQL de Oracle, ServiceNow, recurso compartido de archivos, Azure DevOps y MediaWiki.](media/add-connector.png)

>[! Nota:] puede Agregar un máximo de diez conexiones de Graph a cada inquilino.

## <a name="step-2-name-the-connection"></a>Paso 2: asignar un nombre a la conexión
Tendrá que especificar estos atributos: 

* Nombre  
* IDENTIFICADOR de conexión 
* Descripción (opcional) 

El identificador de conexión crea propiedades implícitas para el conector. Debe contener solo caracteres alfanuméricos y tener un máximo de 32 caracteres. 

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: configurar las opciones de conexión

El proceso para configurar las opciones de conexión varía en función del tipo de origen de datos. Vea la información específica del conector para el tipo de origen de datos que desee agregar al inquilino para completar este paso en el proceso de instalación.  

Para obtener más información acerca de cómo conectarse a un origen de datos local, vea [instalar una puerta de enlace de datos local](https://aka.ms/configuregateway).

## <a name="step-4-manage-search-permissions"></a>Paso 4: administrar los permisos de búsqueda

Las listas de control de acceso (ACL) determinan qué usuarios de la organización pueden tener acceso a cada elemento de datos.  

Algunos conectores como [Microsoft SQL](MSSQL-connector.md) y [Azure Data Lake Storage](azure-data-lake-connector.md) alterno admiten de [forma nativa Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/) ACLs.

Otros conectores como [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md)y [Salesforce](salesforce-connector.md) admiten la sincronización de usuarios y grupos que no son de Azure ad.  

## <a name="step-5-assign-property-labels"></a>Paso 5: asignar etiquetas de propiedad
Puede asignar etiquetas semánticas a las propiedades de origen en la página "asignar etiquetas de propiedad". Las etiquetas son etiquetas conocidas que proporciona Microsoft y que proporcionan el significado semántico. Permiten a Microsoft integrar los datos de los conectores en experiencias de Microsoft 365 como búsquedas mejoradas, tarjetas de contactos, detección inteligente y mucho más.  

En la siguiente tabla se enumeran las etiquetas admitidas actualmente y sus descripciones.  

Etiqueta | Description
--- | ---  
**title** | El título del elemento que quiere mostrar en la búsqueda y en otras experiencias 
**url** | La dirección URL de destino del elemento en el sistema de origen 
**createdBy** | Nombre de la persona que creó el elemento 
**lastModifiedBy** | Nombre de la persona que editó recientemente el elemento 
**sus** | Nombre de las personas que participaron o colaboraron en el elemento 
**createdDateTime** | Cuándo se creó el elemento 
**lastModifiedDateTime** | ¿Cuándo se modificó el elemento más recientemente? 
**fileName** | Nombre del elemento de archivo 
**fileExtension** | Tipo de elemento de archivo como. pdf o. Word 

Las propiedades de esta página están preseleccionadas según el origen de datos, pero puede cambiar esta selección si hay una propiedad distinta que sea más adecuada para una etiqueta en particular.  

El **título** de la etiqueta es la etiqueta más importante. Se **recomienda encarecidamente** tener una propiedad asignada a esta etiqueta para que la conexión participe en la experiencia de [clúster de resultados](result-cluster.md).

La asignación incorrecta de etiquetas hará que se produzca una experiencia de búsqueda deteriorada. No es correcto que algunas etiquetas tengan asignada una propiedad.  

## <a name="step-6-manage-schema"></a>Paso 6: administrar esquema

### <a name="content-property"></a>Propiedad Content

Se recomienda encarecidamente seleccionar una propiedad de contenido * * "en el menú desplegable de opciones, o bien mantener el valor predeterminado si hay alguno presente. Esta propiedad se usa para la indización de texto completo del contenido, la generación de fragmentos de código de página de resultados de búsqueda, la participación en [clústeres de resultados](result-cluster.md) , la detección de idiomas, la compatibilidad con texto y HTML, la clasificación y relevancia, y la formulación de consultas.

Si selecciona una propiedad de contenido, tendrá la opción de usar la propiedad generada por el sistema **ResultSnippet** al [crear el tipo de resultado](customize-results-layout.md). Esta propiedad actúa como un marcador de posición para los fragmentos de código dinámico que se generan a partir de la propiedad de contenido en el momento de la consulta. Si usa esta propiedad en el tipo de resultado, los fragmentos de código se generarán en los resultados de la búsqueda.

### <a name="creating-aliases-for-source-properties"></a>Crear alias para propiedades de origen

Puede Agregar alias a sus propiedades en la columna "alias" en la página "administrar esquema". Los alias son nombres descriptivos de las propiedades. Se usan en consultas y en la creación de filtros. También se usan para normalizar las propiedades de origen de varias conexiones, de modo que tengan el mismo nombre. De este modo, puede crear un filtro único para un valor vertical con varias conexiones. Para obtener más información, vea [personalizar la página de resultados de búsqueda](customize-search-page.md) .  

### <a name="search-schema-attributes"></a>Atributos de esquema de búsqueda

Puede establecer los atributos del esquema de búsqueda para controlar la funcionalidad de búsqueda de cada propiedad de origen. Un esquema de búsqueda ayuda a determinar los resultados que se muestran en la página de resultados de búsqueda y la información que los usuarios finales pueden ver y a los que se accede.

Los atributos de esquema de búsqueda incluyen **búsquedas**, **consultas**, **recuperables** y **refinables**. En la siguiente tabla se enumeran todos los atributos compatibles con los conectores de Microsoft Graph y se explican sus funciones.

Atributo de esquema de búsqueda | Función | Ejemplo
--- | --- | ---
QUE permiten búsquedas | Hace que el contenido de texto de una propiedad permita la búsqueda. El contenido de la propiedad se incluye en el índice de texto completo. | Si la propiedad es **title**, una consulta de **Enterprise** devuelve respuestas que contienen la palabra **Enterprise** en cualquier texto o título.
CONSULTABLE | Busca una coincidencia para una propiedad determinada en la consulta. A continuación, se puede especificar el nombre de la propiedad en la consulta, ya sea mediante programación o literalmente. |  Si la propiedad **title** es consultable, el título de la consulta **: Enterprise** es compatible. 
RECUPERABLE | Solo se pueden usar propiedades recuperables en el tipo de resultado y se muestran en los resultados de la búsqueda. |
PARA restricción | Las propiedades refinables se pueden usar como en la página de resultados de la búsqueda de Microsoft. | Los usuarios de la organización pueden [filtrar](custom-filters.md) por **lastModifiedDateTime** en la página de resultados de búsqueda si la propiedad se marca como refinable durante la configuración de la conexión.

Para todos los conectores excepto el conector de recursos compartidos de archivos, los tipos personalizados deben establecerse manualmente. Para activar las capacidades de búsqueda para cada campo, necesita un esquema de búsqueda asignado a una lista de propiedades. El Asistente para la conexión selecciona automáticamente un esquema de búsqueda en función del conjunto de propiedades de origen que elija. Puede modificar este esquema activando las casillas de verificación de cada propiedad y atributo en la página esquema de búsqueda.

![El esquema de un conector se puede personalizar agregando o quitando funciones de consulta, búsqueda y recuperación.](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Restricciones y recomendaciones para la configuración del esquema de búsqueda

* La propiedad **Content** sólo se pueden buscar. Una vez seleccionada en la lista desplegable, esta propiedad no se puede marcar como **recuperable** o **consultable**.

* Se producen problemas de rendimiento significativos cuando los resultados de la búsqueda se representan con la propiedad **Content** . Un ejemplo es el campo de contenido de **texto** de un artículo de base de conocimiento de [ServiceNow](https://www.servicenow.com) .

* Solo las propiedades marcadas como representables recuperables en los resultados de búsqueda y se pueden usar para crear tipos de resultado modernos (MRTs).

* Solo las propiedades de cadena se pueden marcar como buscables.

> [!NOTE]
> Después de crear una conexión, **no** puede modificar el esquema. Para ello, debe eliminar la conexión y crear una nueva.

## <a name="step-7-refresh-settings"></a>Paso 7: Actualizar configuración

El intervalo de actualización determina la frecuencia con la que los datos se sincronizan entre el origen de datos y Microsoft Search. Cada tipo de origen de datos tiene un conjunto diferente de programaciones de actualización óptimas en función de la frecuencia con la que se modifican los datos y el tipo de modificaciones.

Hay dos tipos de intervalos de actualización, que son la **actualización completa** y la **actualización incremental**, pero las actualizaciones incrementales no están disponibles para algunos orígenes de datos.

Con una actualización completa, el motor de búsqueda procesa e indiza todos los elementos del origen de contenido, independientemente de los rastreos anteriores. Una actualización completa funciona mejor en estas situaciones:

* Detección de eliminaciones de datos.
* La actualización incremental no pudo actualizar el contenido debido a errores.
* Las ACL se modificaron.
* Se modificaron las reglas de rastreo.
* Cuándo se actualizó el esquema para la conexión (las actualizaciones de esquema aún no son compatibles)

Con una **actualización incremental**, el motor de búsqueda puede procesar e indizar sólo los elementos que se crearon o modificaron desde el último rastreo correcto. Por lo tanto, no todos los datos en el origen de contenido se vuelven a indizar. La actualización incremental funciona mejor para detectar contenido, metadatos, permisos y otras actualizaciones.

Las actualizaciones incrementales son mucho más rápidas que las actualizaciones completas porque no se procesan los elementos que no han cambiado. Sin embargo, si elige ejecutar actualizaciones incrementales, aún tendrá que ejecutar actualizaciones completas de forma periódica para mantener una sincronización de datos precisa entre el origen de contenido y el índice de búsqueda.

![El rastreo incremental y la configuración de intervalo de rastreo completo muestran una incremental a los 15 minutos y un rastreo completo a una semana.](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>Paso 8: revisar la conexión

Puede revisar toda la configuración y editar la configuración según sea necesario antes de completar la conexión. **Si aún no lo ha hecho, asegúrese de leer la información específica del conector para su origen de datos.** Seleccione **Finalizar actualización** cuando esté listo para completar la conexión.

## <a name="how-do-i-know-the-connection-setup-worked"></a>¿Cómo sé si funcionó la configuración de la conexión?

Vaya a la lista de las conexiones publicadas en la ficha **conectores** del [centro de administración](https://admin.microsoft.com). Para obtener información sobre cómo realizar actualizaciones y eliminaciones, consulte [administrar el conector](manage-connector.md).
