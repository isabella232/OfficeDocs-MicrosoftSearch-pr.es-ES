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
ms.openlocfilehash: eac4180a247fe17b4e86b57a69f2b7bdb79e56bb
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367775"
---
# <a name="graph-connectors-result-cluster"></a>Clúster de resultados de conectores de Graph

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Información general sobre el clúster de resultados de conectores de Graph (versión preliminar)  

 Con los clústeres de resultados de conectores de Graph, las empresas pueden buscar contenido de orígenes de datos de terceros en su vista predeterminada (la pestaña todos) en SharePoint y Office.com.

Los clústeres de resultados ayudan a los usuarios a descubrir todo el contenido de terceros (previoulsy ligado a un único conector y al vertical) en un solo lugar. Los resultados que se muestran en un clúster de resultados se agrupan en función de cómo el administrador del inquilino los configura en una presentación vertical de búsqueda.  

## <a name="how-connector-results-are-selected-and-displayed"></a>Cómo se seleccionan y se muestran los resultados de los conectores

Los resultados de conectores proporcionados en el clúster de resultados se derivan de presentaciones verticales de búsqueda individuales con contenido de conector. Cada presentación vertical de búsqueda proporciona un conjunto de resultados relevantes que se convierten en un clúster de resultados candidatos. Los resultados relevantes se eligen en función de la propiedad "title", el fragmento de código de resultado y el componente de contenido de cada elemento.

Para garantizar la detección del contenido de las presentaciones verticales de búsqueda, le recomendamos que proporcione títulos significativos para los elementos. Esto afecta positivamente el arbitraje de los candidatos del clúster de resultados y la probabilidad de que el contenido aparezca en un clúster de resultados. Por ejemplo, evite el uso de identificadores como valores para la propiedad "título" a menos que los usuarios estén usando identificadores para buscar contenido.

La frecuencia con la que se muestra un clúster de resultados varía en factores como el número de presentaciones verticales de búsqueda que se configuran y el tipo de contenido. Al seleccionar o ignorar los resultados del clúster de resultados, se proporcionan implícitamente sugerencias que ajustarán la activación de los clústeres de resultados a lo largo del tiempo.

La experiencia de resultados de búsqueda para los elementos de conector que se muestran en el clúster de resultados es generada por el sistema y no utiliza diseños de resultados personalizados. Debe declarar la propiedad "title" y el contenido del elemento durante el registro de conexión si desea que los resultados aparezcan en el clúster de resultados.

## <a name="enable-result-clusters"></a>Habilitar clústeres de resultados
  
La experiencia del clúster de resultados está desactivada de forma predeterminada.  
Siga estos pasos para activar la experiencia en el nivel de organización:

Centro de administración de Microsoft 365

1. En el [centro de administración de Microsoft 365](https://admin.microsoft.com/), vaya a **configuración**  >  **Buscar &**  >  vertical de **Personalización** de inteligencia  >  **Verticals**.  
2. Seleccione la sección **todos los** resultados verticales e ir a la muestra de los **resultados del conector** . Activar la experiencia en el nivel de sitio.

SharePoint

1. En el sitio de SharePoint en el que desea la experiencia del clúster de resultados, vaya a **configuración**.
2. Vaya a **información del sitio** para > **ver toda la configuración del sitio**.
3. Vaya a la sección de Microsoft Search y, a continuación, seleccione **configurar Microsoft Search para esta colección de sitios**.
4. En el panel de navegación, vaya a **experiencia personalizada** y, a continuación, seleccione **vertical**.
5. Seleccione **todos** los resultados en vertical y, a continuación, habilite **Mostrar los resultados del conector**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Ver la experiencia de clúster de resultados una vez habilitada

Después de activar la experiencia del clúster de resultados, puede tardar unos minutos antes de poder verlo. Si quiere la experiencia inmediatamente, puede anexar *cacheClear = true* a la dirección URL en SharePoint y Office.
