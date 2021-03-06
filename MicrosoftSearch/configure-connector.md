---
title: Configurar el conector de Graph creado por Microsoft para Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Introducción a la instalación para conectores de Graph de Microsoft
ms.openlocfilehash: e97b930f627a6336cc93b3a1f33e390cae4ff0aa
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508880"
---
<!-- Previous ms.author: monaray -->

<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Introducción a la instalación para conectores de Graph de Microsoft 

En este artículo se muestra el proceso básico necesario para configurar los conectores de Graph de **Microsoft** en el Centro de administración [de Microsoft 365](https://admin.microsoft.com). El proceso básico incluye los siguientes pasos:  
<!---Add links to each section in the doc--->

1. [Agregar un conector de Graph en el Centro de administración de Microsoft 365](#step-1-add-a-graph-connector-in-the-microsoft-365-admin-center)
2. [Asigne un nombre a la conexión](#step-2-name-the-connection)
3. [Configurar las opciones de conexión](#step-3-configure-the-connection-settings)
4. [Administrar permisos de búsqueda](#step-4-manage-search-permissions)
5. [Asignar etiquetas de propiedades](#step-5-assign-property-labels)
6. [Administrar esquema](#step-6-manage-schema)
7. [Actualizar configuración](#step-7-refresh-settings)
8. [Revisar conexión](#step-8-review-connection)

En este artículo también se incluye información sobre la solución de problemas, las limitaciones y los pasos siguientes:

* [Solución de problemas](#troubleshooting)
* [Limitaciones](#limitations)
* [Pasos siguientes](#next-steps)

> [!NOTE]
> El proceso de instalación es similar para todos los conectores de Graph de Microsoft, pero no es exactamente el mismo. **Además de leer este artículo, asegúrese de leer la información específica del conector para el origen de datos.**  

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365

Siga estos pasos para configurar cualquiera de los conectores de Graph creados por Microsoft:

1. Inicie sesión en su cuenta de administrador en el Centro de administración de [Microsoft 365](https://admin.microsoft.com).

2. En el panel de navegación, seleccione **Configuración** y, a continuación, seleccione **Buscar & inteligencia**. Seleccione la [pestaña Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).

3. Seleccione **+Agregar** y, a continuación, seleccione el origen de datos que desee en el menú de opciones disponibles.

   > [!div class="mx-imgBorder"]
   > ![Los orígenes de datos disponibles incluyen: ADLS Gen2, sitios web de empresa, servidor de Microsoft SQL, Azure SQL, base de datos de Oracle SQL, ServiceNow, recurso compartido de archivos, Azure DevOps y MediaWiki.](media/add-connector.png)

> [!NOTE]
> Puede agregar un máximo de diez conexiones de Graph a cada inquilino.

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Especifique estos atributos:

* Name (obligatorio)
* Id. de conexión (obligatorio)
* Descripción (opcional)

El identificador de conexión crea propiedades implícitas para el conector. Solo debe contener caracteres alfanuméricos y tener un máximo de 32 caracteres.

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

El proceso para configurar las opciones de conexión varía en función del tipo de origen de datos. Consulte la información específica del conector para el tipo de origen de datos que desea agregar al espacio empresarial para completar este paso en el proceso de instalación.  

Para obtener más información sobre cómo conectarse a un origen de datos local, vea [Install an on-premises data gateway](https://aka.ms/configuregateway).

## <a name="step-4-manage-search-permissions"></a>Paso 4: Administrar permisos de búsqueda

Las listas de control de acceso (ACL) determinan qué usuarios de la organización pueden tener acceso a cada elemento de datos.  

Algunos conectores como [Microsoft SQL](MSSQL-connector.md) y Azure Data Lake [Storage Gen2](azure-data-lake-connector.md) admiten las ACL de [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/)

Otros conectores como [ServiceNow,](servicenow-connector.md) [Azure DevOps](azure-devops-connector.md)y [Salesforce](salesforce-connector.md) admiten la sincronización de usuarios y grupos que no son de Azure AD.  

## <a name="step-5-assign-property-labels"></a>Paso 5: Asignar etiquetas de propiedades

Puede asignar etiquetas semánticas a las propiedades de origen en la página "Asignar etiquetas de propiedades". Las etiquetas son etiquetas conocidas proporcionadas por Microsoft que proporcionan un significado semántico. Permiten a Microsoft integrar los datos del conector en experiencias de Microsoft 365, como búsqueda mejorada, tarjetas de personas, detección inteligente y mucho más.  

En la tabla siguiente se enumeran las etiquetas admitidas actualmente y sus descripciones.  

Etiqueta | Descripción
--- | ---  
**title** | El título del elemento que desea que se muestra en la búsqueda y otras experiencias
**url** | La dirección URL de destino del elemento en el sistema de origen
**createdBy** | Nombre de la persona que creó el elemento
**lastModifiedBy** | Nombre de la persona que editó el elemento recientemente
**authors** | Nombre de las personas que participaron o colaboraron en el elemento
**createdDateTime** | Cuándo se creó el elemento
**lastModifiedDateTime** | Cuándo fue el elemento editado más recientemente
**fileName** | Nombre del elemento de archivo
**fileExtension** | Tipo de elemento de archivo como .pdf o .word

Las propiedades de esta página están seleccionadas previamente en función del origen de datos, pero puede cambiar esta selección si hay una propiedad diferente que sea más adecuada para una etiqueta determinada.  

El título **de la** etiqueta es la etiqueta más importante. Se recomienda **encarecidamente que** tenga una propiedad asignada a esta etiqueta para que la conexión participe en la experiencia del [clúster de resultados.](result-cluster.md)

Asignar etiquetas incorrectamente provocará una experiencia de búsqueda deteriorada. Está bien que algunas etiquetas no tengan asignada una propiedad.  

## <a name="step-6-manage-schema"></a>Paso 6: Administrar esquema

### <a name="content-property"></a>Content (propiedad)

Se recomienda seleccionar una propiedad **content** en el menú desplegable de opciones o mantener el valor predeterminado si hay una. Esta propiedad se usa para la indización de texto completo del contenido, la generación de fragmentos de código de página de resultados de [búsqueda,](result-cluster.md) la participación del clúster de resultados, la detección de idiomas, la compatibilidad con HTML/texto, la clasificación y la relevancia y la formulación de consultas.

Si selecciona una propiedad de contenido, tendrá la opción de usar la propiedad generada por el sistema **ResultSnippet** al [crear el tipo de resultado](customize-results-layout.md). Esta propiedad sirve como marcador de posición para los fragmentos de código dinámicos que se generan a partir de la propiedad de contenido en el momento de la consulta. Si usa esta propiedad en el tipo de resultado, se generarán fragmentos de código en los resultados de búsqueda.

### <a name="creating-aliases-for-source-properties"></a>Creación de alias para propiedades de origen

Puede agregar alias a sus propiedades en la columna "Alias" de la página "Administrar esquema". Los alias son nombres descriptivos para las propiedades y también se usan en consultas y en la creación de filtros. También se usan para normalizar las propiedades de origen de varias conexiones, de modo que tienen el mismo nombre. De este modo, puede crear un único filtro para una vertical con varias conexiones. Para obtener más información, vea [Personalizar la página de resultados de búsqueda](customize-search-page.md).  

### <a name="search-schema-attributes"></a>Atributos de esquema de búsqueda

Puede establecer los atributos del esquema de búsqueda para controlar la funcionalidad de búsqueda de cada propiedad de origen. Un esquema de búsqueda ayuda a determinar qué resultados se muestran en la página de resultados de búsqueda y a qué información pueden ver y acceder los usuarios finales.

Los atributos de esquema de búsqueda **incluyen opciones para Query**, **Search,** **Retrieve** y **Refine**. En la tabla siguiente se enumeran cada uno de los atributos que admiten los conectores de Microsoft Graph y se explican sus funciones.

Atributo de esquema de búsqueda | Función | Ejemplo
--- | --- | ---
BUSCAR | Hace que se busque el contenido de texto de una propiedad. El contenido de la propiedad se incluye en el índice de texto completo. | Si la propiedad es **title**, una consulta de **Enterprise** devuelve respuestas que contienen la palabra **Enterprise** en cualquier texto o título.
QUERY | Busca por consulta una coincidencia de una propiedad determinada. A continuación, el nombre de la propiedad se puede especificar en la consulta mediante programación o de forma literal. |  Si se puede consultar la propiedad **Title,** se admite la consulta **Title: Enterprise.**
RETRIEVE | Solo se pueden usar propiedades recuperables en el tipo de resultado y mostrar en el resultado de la búsqueda. |
REFINE | La opción refinar se puede usar como en la página de resultados de Microsoft Search. | Los usuarios de la organización pueden [filtrar](custom-filters.md) por **dirección URL** en la página de resultados de búsqueda si la propiedad refine está marcada durante la configuración de la conexión

Para todos los conectores excepto el conector de recurso compartido de archivos, los tipos personalizados deben establecerse manualmente. Para activar las funcionalidades de búsqueda para cada campo, necesita un esquema de búsqueda asignado a una lista de propiedades. El asistente para la conexión selecciona automáticamente un esquema de búsqueda en función del conjunto de propiedades de origen que elija. Puede modificar este esquema seleccionando las casillas de cada propiedad y atributo de la página del esquema de búsqueda.

> [!div class="mx-imgBorder"]
> ![El esquema de un conector se puede personalizar agregando o quitando funciones Query, Search y Retrieve.](media/manageschema.png)

### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Restricciones y recomendaciones para la configuración del esquema de búsqueda

* Solo **se** puede buscar en la propiedad content. Una vez seleccionada en el desplegable, esta propiedad no se puede usar con las opciones **retrieve** o **query**.

* Se producen problemas de rendimiento significativos cuando los resultados de búsqueda se representan con la **propiedad de** contenido. Un ejemplo es el **campo Contenido** de texto de un artículo [de ServiceNow](https://www.servicenow.com) knowledge-base.

* Solo las propiedades marcadas como representaciones recuperables en los resultados de búsqueda y se pueden usar para crear tipos de resultados modernos (MRT).

* Solo se pueden marcar las propiedades de cadena que se pueden buscar.

> [!NOTE]
> Después de crear una conexión, **no puede** modificar el esquema. Para ello, debe eliminar la conexión y crear una nueva.

## <a name="step-7-refresh-settings"></a>Paso 7: Actualizar configuración

El intervalo de actualización determina la frecuencia con la que los datos se sincronizan entre el origen de datos y Microsoft Search. Cada tipo de origen de datos tiene un conjunto diferente de programaciones de actualización óptimas en función de la frecuencia con la que se modifican los datos y el tipo de modificaciones.

Hay dos tipos de intervalos de actualización, que son **Actualización** completa e **Actualización incremental,** pero las actualizaciones incrementales no están disponibles para algunos orígenes de datos.

Con una actualización completa, el motor de búsqueda procesa e indiza todos los elementos del origen de contenido, independientemente de los rastreos anteriores. Una actualización completa funciona mejor para estas situaciones:

* Detección de eliminaciones de datos.
* La actualización incremental encontró errores y falló.
* Se modificaron las ACL.
* Se modificaron las reglas de rastreo.
* El esquema de la conexión se ha actualizado (aún no se admiten actualizaciones de esquema).

Con una **actualización incremental,** el motor de búsqueda puede procesar e indizar solo los elementos que se crearon o modificaron desde el último rastreo correcto. Como resultado, no todos los datos del origen de contenido se reindexa. Las actualizaciones incrementales funcionan mejor para detectar contenido, metadatos, permisos y otras actualizaciones.

Las actualizaciones incrementales son mucho más rápidas que las actualizaciones completa porque los elementos sin cambios no se procesan. Sin embargo, si decide ejecutar actualizaciones incrementales, aún debe ejecutar actualizaciones completa periódicamente para mantener la sincronización correcta de datos entre el origen de contenido y el índice de búsqueda.

> [!div class="mx-imgBorder"]
> ![Configuración de rastreo incremental y intervalo de rastreo completo que muestra Incremental a 15 minutos y Rastreo completo a 1 semana.](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Puede revisar toda la configuración y editar la configuración según sea necesario antes de completar la conexión. **Asegúrese de leer la información específica del conector para el origen de datos si aún no lo ha hecho.** Seleccione **Finalizar la actualización** cuando esté listo para completar la conexión.

### <a name="confirm-if-the-connection-setup-worked"></a>Confirmar si la configuración de conexión funcionó

Vaya a la lista de las conexiones **publicadas** en la pestaña Conectores del [Centro de administración.](https://admin.microsoft.com) Para obtener información sobre cómo realizar actualizaciones y eliminaciones, consulte [Manage your connector](manage-connector.md).

## <a name="troubleshooting"></a>Solución de problemas
<!---Insert troubleshooting recommendations for this data source-->
Lea la información específica del conector para el origen de datos. 

> [!NOTE]
> No todos los artículos específicos del conector incluyen recomendaciones de solución de problemas en este momento.

## <a name="limitations"></a>Limitaciones
<!---Insert limitations for this data source-->
Para obtener información sobre las limitaciones que se aplican a todos los orígenes de datos, consulte el artículo Información general sobre los conectores [de Microsoft Graph.](connectors-overview.md)

Consulta la información específica del conector para el origen de datos para averiguar si se aplican otras limitaciones a ese conector de Graph en particular.

## <a name="next-steps"></a>Pasos siguientes

Después de publicar la conexión, debe personalizar la página de resultados de búsqueda. Para obtener información sobre cómo personalizar los resultados de búsqueda, [vea Personalizar la página de resultados de búsqueda](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).
