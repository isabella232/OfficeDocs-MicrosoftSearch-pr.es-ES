---
title: Introducción a los conectores
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Introducción a los conectores de Microsoft Graph para Microsoft Search
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367527"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Información general sobre los conectores de Microsoft Graph

[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indiza todos los datos de [Microsoft 365](https://www.microsoft.com/microsoft-365) para permitir que los usuarios puedan buscar en ellos. Con los conectores de Microsoft Graph, su organización puede indizar datos de terceros para que aparezcan en los resultados de la búsqueda de Microsoft. Esto amplía los tipos de orígenes de contenido que se pueden buscar en las aplicaciones de productividad de Microsoft 365 y el más amplio ecosistema de Microsoft. Los datos de terceros pueden hospedarse localmente o en nubes públicas o privadas.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

El resto de este artículo está pensado para ayudar a los administradores de Microsoft 365 a encontrar los recursos que están disponible para responder las siguientes preguntas:

* [¿Qué orígenes de datos se pueden conectar a Microsoft Search?](#what-data-sources-can-be-connected-to-microsoft-search)
* [¿Cómo se administran las conexiones?](#how-do-i-manage-my-connections)
* [¿Cuáles son los requisitos de licencia y los términos de uso de los conectores de Graph?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [¿Cómo se personalizan y configuran los resultados de la búsqueda?](#how-do-i-customize-and-configure-search-results)
* [¿Cómo se busca en los datos de los conectores de una aplicación personalizada?](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> Los conectores de Microsoft Graph y las API de Microsoft Search ahora están disponibles para el público en general. Las primeras implementaciones serán a los clientes configurados para la versión dirigida. Si desea usar un conector de Graph en su espacio empresarial, los usuarios y administradores deben optar por la [versión dirigida](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>¿Qué orígenes de datos se pueden conectar a Microsoft Search?

Microsoft proporciona diez conectores de Graph y nuestros socios de ecosistemas han creado más de 100 conectores de gráficos adicionales. También puede crear su propio conector para gráficos. 

### <a name="graph-connectors-by-microsoft"></a>Conectores de Graph de Microsoft

Puede conectarse a los siguientes orígenes de datos mediante conectores de Graph creados por Microsoft:

<!---Need to add a few links below when docs exist--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* SQL de Azure
* [Sitios web de la empresa](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [Compartir archivos](fileshare-connector.md)
* Oracle (versión preliminar)
* [Salesforce (versión preliminar)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

La [Galería de conectores de Graph](connectors-gallery.md) contiene una breve descripción de cada uno de estos conectores de Graph. Si está listo para conectar uno de estos orígenes de datos al espacio empresarial, asegúrese de leer la [información general del programa de instalación](configure-connector.md) y los artículos de la sección Setup Connectors by Microsoft que se aplican a su origen de datos.

### <a name="graph-connectors-by-our-partners"></a>Conectores de gráficos por nuestros partners

La [Galería de conectores de Microsoft Graph](connectors-gallery.md) incluye una breve descripción de cada uno de los conectores de gráficos creados por nuestros socios y un vínculo al sitio web de cada socio. Póngase en contacto con cada socio directamente para obtener más información.

### <a name="build-your-own-graph-connector"></a>Crear su propio conector para gráficos

Si tiene previsto crear su propio conector para gráficos, vea la información [General de la API de búsqueda de Microsoft en Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) para obtener más información.

## <a name="how-do-i-manage-my-connections"></a>¿Cómo se administran las conexiones?

Puede administrar las conexiones desde la [pestaña conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) del centro de [administración de Microsoft 365](https://admin.microsoft.com/). Para obtener más información, vea [administrar las conexiones](manage-connector.md) .

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>¿Cuáles son los requisitos de licencia y los términos de uso de los conectores de Graph?

Necesita una licencia válida de Microsoft 365 o de Office 365 y suficientes conectores de gráficos para que los usuarios de la organización puedan ver los datos de los conectores en los resultados de la búsqueda.

Para obtener más información, consulte [requisitos de licencia y precios](licensing.md) y [condiciones de uso](terms-of-use.md).

## <a name="how-do-i-customize-and-configure-search-results"></a>¿Cómo se personalizan y configuran los resultados de la búsqueda?

Hay varias formas de personalizar y configurar los resultados de la búsqueda. Consulte los siguientes artículos para obtener más información:

* [Administrar los sectores verticales y los tipos de resultados](customize-search-page.md)
* [Administre los diseños de resultados de búsqueda](customize-results-layout.md)
* [Administrar clúster de resultados](result-cluster.md)
* [Administrar filtros personalizados](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>¿Cómo se busca en los datos de los conectores de una aplicación personalizada?

Una vez indizados los datos personalizados, los desarrolladores pueden [consultar estos datos](https://docs.microsoft.com/graph/search-concept-custom-types). Puede ver los datos en cualquier aplicación. Para obtener más información, vea la [información general de la API de búsqueda de Microsoft en Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).
