---
title: Clúster de resultados de conectores
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Detalles de la experiencia del clúster de resultados de conectores
ms.openlocfilehash: fb29fb9c14811698fb7c5d043853b57231c76a0b
ms.sourcegitcommit: d1bc6c41ecf47584373ce57543502bed55753d0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080841"
---
# <a name="graph-connectors-result-cluster"></a>Clúster de resultados de conectores de Gráfico

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Información general sobre el clúster de resultados de conectores de Graph (versión preliminar)  

Con los clústeres de resultados de conectores de Graph, las  empresas pueden buscar contenido de orígenes de datos de terceros en su vista predeterminada, la pestaña Todo, en SharePoint, Office.com y Búsqueda de Microsoft en Bing.

Los clústeres de resultados ayudan a los usuarios a descubrir todo el contenido de terceros en un solo lugar. Los resultados que se muestran en un clúster de resultados se agrupan en función de la configuración vertical de búsqueda.

## <a name="how-connector-results-are-selected-and-displayed"></a>Cómo se seleccionan y muestran los resultados del conector

Los resultados del conector proporcionados en el clúster de resultados se derivan de verticales de búsqueda individuales con contenido del conector. Cada vertical de búsqueda proporciona un conjunto de resultados relevantes que se convierte en un clúster de resultados candidatos. Los resultados relevantes se eligen en función de la propiedad "title" y la propiedad "content" de cada elemento. La propiedad de contenido se marca *como isContent=true* en el esquema.

Para garantizar la detección de contenido desde las verticales de búsqueda, se recomienda proporcionar títulos significativos para los elementos. Esto afecta positivamente al arbitraje de candidatos de clúster de resultados y a la probabilidad de que el contenido se muestre en un clúster de resultados. Por ejemplo, evite el uso de los IDs como valores para la propiedad "title" a menos que los usuarios usen los IDs para buscar contenido.

La frecuencia con la que se muestra un clúster de resultados varía según factores como el número de verticales de búsqueda que configure y el tipo de contenido. Al interactuar o ignorar un clúster de resultados, los usuarios proporcionarán implícitamente sugerencias que ajustarán su desencadenamiento con el tiempo.

La experiencia de resultados de búsqueda para los elementos de conector que se muestran en el clúster de [resultados](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) usa tipos de resultado definidos por usted. Si no se configura ningún tipo de resultado, se [usa un diseño generado](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) por el sistema. 

Se recomienda usar la propiedad "title" como título del resultado de la búsqueda y la propiedad "content" como descripción de la búsqueda. Esto proporcionará la mejor experiencia para los usuarios mediante la activación precisa del clúster de resultados y los resultados más relevantes en el clúster. 

## <a name="enable-result-clusters"></a>Habilitar clústeres de resultados
  
La experiencia del clúster de resultados está desactivada de forma predeterminada.  

Siga estos pasos para activar la experiencia en el nivel de organización:

1. En el [Centro de administración de Microsoft 365,](https://admin.microsoft.com)vaya a [**Verticales.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Seleccione la presentación vertical **Todos** y, a continuación, **habilite Mostrar resultados del conector.** 


Siga estos pasos para activar la experiencia en el nivel de sitio de SharePoint:

1. En el sitio de SharePoint donde desea la experiencia del clúster de resultados, vaya a **Configuración.**
2. Vaya a **Información del sitio Ver** toda la configuración del > **sitio.**
3. Vaya a la sección Búsqueda de Microsoft y, a continuación, **seleccione Configurar Microsoft Search para esta colección de sitios.**
4. En el panel de navegación, vaya **a Experiencia personalizada** y, a continuación, seleccione **Verticales.**
5. Seleccione la presentación vertical **Todos** y, a continuación, **habilite Mostrar resultados del conector.**

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Ver la experiencia del clúster de resultados después de habilitarla

Después de activar la experiencia del clúster de resultados, pueden pasar hasta 12 horas antes de poder verlo. Si desea que la experiencia sea inmediata, puede anexar *cacheClear=true* a la dirección URL en SharePoint y Office.
