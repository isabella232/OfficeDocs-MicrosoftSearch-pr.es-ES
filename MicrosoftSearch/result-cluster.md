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
description: Detalles del resultado de los conectores experiencia de clúster
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773031"
---
# <a name="graph-connectors-result-cluster"></a>Clúster de resultados de conectores de Graph

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Información general sobre el clúster de resultados de conectores de Graph (versión preliminar)  

Con los clústeres de resultados de conectores de Graph, las empresas pueden buscar contenido de orígenes de datos de terceros en su vista predeterminada, en la pestaña **todos** , en SharePoint, Office.com y Microsoft Search en Bing.

Los clústeres de resultados ayudan a los usuarios a descubrir todo el contenido de terceros en un solo lugar. Los resultados que se muestran en un clúster de resultados se agrupan en función de la configuración vertical de búsqueda.

## <a name="how-connector-results-are-selected-and-displayed"></a>Cómo se seleccionan y se muestran los resultados de los conectores

Los resultados de conectores proporcionados en el clúster de resultados se derivan de presentaciones verticales de búsqueda individuales con contenido de conector. Cada presentación vertical de búsqueda proporciona un conjunto de resultados relevantes que se convierten en un clúster de resultados candidatos. Los resultados relevantes se eligen en función de la propiedad "título" y de la propiedad "Content" de cada elemento. La propiedad de contenido se marca como *isContent = true* en el esquema.

Para garantizar la detección del contenido de las presentaciones verticales de búsqueda, le recomendamos que proporcione títulos significativos para los elementos. Esto afecta positivamente el arbitraje de los candidatos del clúster de resultados y la probabilidad de que el contenido aparezca en un clúster de resultados. Por ejemplo, evite el uso de identificadores como valores para la propiedad "título" a menos que los usuarios estén usando identificadores para buscar contenido.

La frecuencia con la que se muestra un clúster de resultados varía en factores como el número de presentaciones verticales de búsqueda que se configuran y el tipo de contenido. Mediante la interacción o la omisión de un clúster de resultados, los usuarios proporcionarán implícitamente sugerencias que ajustarán su activación a lo largo del tiempo.

La experiencia de resultados de búsqueda para los elementos de conector que se muestran en el clúster de resultados usa [tipos de resultado](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) definidos por el usuario. Si no se ha configurado ningún tipo de resultado, se usa un [diseño generado](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) por el sistema. 

Se recomienda usar la propiedad "title" como título del resultado de la búsqueda y la propiedad "Content" como la descripción de la búsqueda. Esto proporcionará la mejor experiencia para los usuarios mediante la activación precisa del clúster de resultados y los resultados más relevantes en el clúster. 

## <a name="enable-result-clusters"></a>Habilitar clústeres de resultados
  
La experiencia del clúster de resultados está desactivada de forma predeterminada.  

Siga estos pasos para activar la experiencia en el nivel de organización:

1. En el [centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**verticales**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Seleccione **todos** los resultados en vertical y, a continuación, habilite **Mostrar los resultados del conector**. 


Siga estos pasos para activar la experiencia en el nivel de sitio de SharePoint:

1. En el sitio de SharePoint en el que desea la experiencia del clúster de resultados, vaya a **configuración**.
2. Vaya a **información del sitio** para > **ver toda la configuración del sitio**.
3. Vaya a la sección de Microsoft Search y, a continuación, seleccione **configurar Microsoft Search para esta colección de sitios**.
4. En el panel de navegación, vaya a **experiencia personalizada** y, a continuación, seleccione **vertical**.
5. Seleccione **todos** los resultados en vertical y, a continuación, habilite **Mostrar los resultados del conector**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Ver la experiencia de clúster de resultados una vez habilitada

Después de activar la experiencia del clúster de resultados, puede tardar unos minutos antes de poder verlo. Si quiere la experiencia inmediatamente, puede anexar *cacheClear = true* a la dirección URL en SharePoint y Office.
