---
title: Introducción a Microsoft Graph Connectors
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
description: Información general sobre los conectores de Microsoft Graph para Microsoft Search
ms.openlocfilehash: 1b3ea74cf571b1b5a048695633f6b9f698a21bf5
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508917"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a>Información general sobre los conectores de Microsoft Graph

[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indiza todos los [datos de Microsoft 365](https://www.microsoft.com/microsoft-365) para que puedan realizar búsquedas para los usuarios. Con los conectores de Microsoft Graph, su organización puede indizar datos de terceros para que aparezcan en los resultados de Microsoft Search. Esta característica amplía los tipos de orígenes de contenido que se pueden buscar en las aplicaciones de productividad de Microsoft 365 y en el ecosistema más amplio de Microsoft. Los datos de terceros se pueden hospedar localmente o en las nubes públicas o privadas.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Este artículo está pensado para ayudar a los administradores de Microsoft 365 a localizar los recursos disponibles para responder a las siguientes preguntas:

* [¿Qué orígenes de datos se pueden conectar a Microsoft Search?](#what-data-sources-can-be-connected-to-microsoft-search)
* [¿Cómo puedo administrar mis conexiones?](#how-do-i-manage-my-connections)
* [¿Cuáles son los requisitos de licencia y los términos de uso de los conectores de Graph?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [¿Cuáles son las características de vista previa?](#what-are-the-preview-features)
* [¿Cómo puedo personalizar y configurar los resultados de búsqueda?](#how-do-i-customize-and-configure-search-results)
* [¿Cómo puedo buscar los datos del conector desde una aplicación personalizada?](#how-do-i-search-my-connector-data-from-a-custom-application)
* [¿Cómo puedo personalizar los resultados de búsqueda?](#how-do-i-customize-search-results)
* [Cuáles son las limitaciones del conector](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> Los conectores de Microsoft Graph y las API de Microsoft Search ahora están disponibles en general. Los primeros lanzamientos serán para los clientes configurados para la versión dirigida. Si desea usar un conector de Graph en el inquilino, los usuarios y administradores deben optar por [la versión dirigida](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>¿Qué orígenes de datos se pueden conectar a Microsoft Search?

Microsoft proporciona 9 conectores de Graph y nuestros socios del ecosistema han creado más de 100 conectores de Graph más. También puede crear su propio conector de Graph.

### <a name="graph-connectors-by-microsoft"></a>Conectores de Graph por Microsoft

Puede conectarse a los siguientes orígenes de datos mediante conectores de Graph creados por Microsoft:

<!---Add links below when new docs are created--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [Azure SQL y Microsoft SQL Server](MSSQL-connector.md)
* [Sitios web de la empresa](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Compartir archivos](fileshare-connector.md)
* [Oracle SQL (versión preliminar)](OracleSQL-connector.md)
* [Salesforce (versión preliminar)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

La [galería de conectores de Graph](connectors-gallery.md) contiene una breve descripción de cada uno de estos conectores de Graph. Si está listo para conectar uno de estos orígenes de datos [](configure-connector.md) al inquilino, asegúrese de leer la introducción al programa de instalación y cualquier otro artículo de la sección Setup connectors by Microsoft que se aplican al origen de datos.

### <a name="graph-connectors-by-our-partners"></a>Conectores de graph de nuestros partners

La [galería de conectores de Microsoft Graph](connectors-gallery.md) incluye una breve descripción de cada uno de los conectores de Graph creados por nuestros partners y un vínculo al sitio web de cada partner. Para obtener más información, póngase en contacto con cada partner directamente.

### <a name="build-your-own-graph-connector"></a>Crear su propio conector de Graph

Puede crear su propio conector de Graph si lo prefiere. Para obtener más información sobre la creación de conectores de Graph, vea [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).

## <a name="how-do-i-manage-my-connections"></a>¿Cómo puedo administrar mis conexiones?

Puede administrar las conexiones desde la [pestaña Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) en el Centro de administración [de Microsoft 365](https://admin.microsoft.com/). Para obtener más información acerca de la administración de conexiones, vea: [Administrar las conexiones](manage-connector.md).

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>¿Cuáles son los requisitos de licencia y los términos de uso de los conectores de Graph?

Necesita una licencia válida de Microsoft 365 u Office 365 y una cuota suficiente de Conectores de Graph para que los usuarios de su organización puedan ver los datos de los conectores en sus resultados de búsqueda.

Para obtener más información, vea [Requisitos de licencia y precios](licensing.md) y [Términos de uso.](terms-of-use.md)

## <a name="what-are-the-preview-features"></a>¿Cuáles son las características de vista previa?

Aunque los conectores de Microsoft Graph y las API de Microsoft Search ahora están disponibles en general, hay varias características que están en versión preliminar.

El conjunto de conectores y características en versión preliminar incluyen:

* [Conector de Azure DevOps](azure-devops-connector.md)
* [Conector de Salesforce](salesforce-connector.md)
* [Conector de ServiceNow](servicenow-connector.md) con permisos de búsqueda que usan ACL de origen
* [Administrar el clúster de resultados](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a>¿Cómo puedo personalizar y configurar los resultados de búsqueda?

Hay muchas maneras de personalizar y configurar los resultados de búsqueda. Vea los siguientes artículos para obtener más información:

* [Administrar los sectores verticales y los tipos de resultados](customize-search-page.md)
* [Administrar los diseños de resultados de búsqueda](customize-results-layout.md)
* [Administrar el clúster de resultados](result-cluster.md)
* [Administrar filtros personalizados](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>¿Cómo puedo buscar los datos del conector desde una aplicación personalizada?

Una vez indizados los datos personalizados, los desarrolladores [pueden consultar estos datos](https://docs.microsoft.com/graph/search-concept-custom-types). Puede ver los datos en cualquier aplicación. Para obtener más información, vea [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).

## <a name="how-do-i-customize-search-results"></a>¿Cómo puedo personalizar los resultados de búsqueda?

El siguiente paso es personalizar los resultados de búsqueda según se recomienda en este artículo [¿Cómo puedo personalizar y configurar los resultados de búsqueda?](#how-do-i-customize-and-configure-search-results). Para obtener más información sobre cómo personalizar los resultados de búsqueda, vea [Personalizar la página de resultados de búsqueda](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).

## <a name="what-are-the-connector-limitations"></a>¿Cuáles son las limitaciones del conector?

* Al publicar **un** conector creado por Microsoft, la conexión puede tardar unos minutos en crearse. Durante ese tiempo, la conexión mostrará su estado como pendiente.

* El [Centro de administración de Microsoft 365](https://admin.microsoft.com) no admite la edición del esquema de búsqueda **después** de publicar una conexión. Para editar el esquema de búsqueda, elimine la conexión y, a continuación, cree una nueva.

* El rendimiento de la ingesta se limita a unos cuatro elementos por segundo.

* No hay compatibilidad con las actualizaciones de esquema. Después de crear una configuración de conexión, no hay forma de actualizar el esquema. Solo puede eliminar y volver a crear la conexión.

* Hay un límite de conexión. Cada espacio empresarial puede crear hasta 10 conexiones.

* La compatibilidad de edición para la conexión no está disponible. Una vez creada la conexión, no puede editarla ni cambiarla. Si necesita cambiar algún detalle, debe eliminar y volver a crear la conexión.
