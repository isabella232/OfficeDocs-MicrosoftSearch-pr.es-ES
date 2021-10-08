---
title: Administrar tipos de resultados
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
description: Administrar tipos de resultados en la página de resultados de búsqueda
ms.openlocfilehash: eb0c00cbc05f899a31cd961d89147ac63c97e82c
ms.sourcegitcommit: 02d4f91210d992da080fd39d5b60f8cf30d8f0b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "60238425"
---
# <a name="manage-result-types"></a>Administrar tipos de resultados

Puede definir cómo se muestran los resultados de búsqueda en la página de resultados de búsqueda diseñando [el diseño](customize-results-layout.md) con tipos de resultados. El diseño de resultados le permite mostrar información útil directamente en los resultados de búsqueda para que los usuarios puedan encontrar rápidamente la información que necesitan.

Los tipos de contenido integrados, como archivos y personas, tienen un diseño estándar que no se puede modificar. Los tipos de resultados se [usan Graph contenido de Connectors.](connectors-overview.md) Al configurar un conector con asignaciones de propiedades, Búsqueda de Microsoft un diseño de resultados de búsqueda predeterminado para los resultados de búsqueda del conector. El título *de la* etiqueta es el más importante; siempre debe tener una propiedad asignada a esta etiqueta para usar el diseño de resultados predeterminado. Sin embargo, la creación de un tipo de resultado personalizado para el contenido del conector puede hacer que esos resultados resultan más impactantes para los usuarios.

Al usar verticales y contenido del conector, debe crear un tipo de resultado o realizar las asignaciones de un diseño predeterminado. Si no lo hace, la vertical no mostrará ningún resultado de búsqueda.

## <a name="understanding-result-types"></a>Descripción de los tipos de resultados

Cree su propio [diseño de resultados de búsqueda](customize-results-layout.md) e invalide el diseño de resultados de búsqueda predeterminado mediante la creación de un tipo de resultado. Un tipo de resultado de búsqueda es una regla que hace que distintos tipos de resultados de búsqueda se muestren de forma diferente. Consta de los siguientes parámetros:

- **Una o más condiciones**   para comparar cada resultado de búsqueda con. Ejemplos de condiciones son el origen de contenido y el título.
- Diseño **de resultados que** se usará para los   resultados de búsqueda que cumplan las condiciones. El diseño resultante controla cómo aparecen los resultados que cumplen las condiciones en la página de resultados de búsqueda.

Puede usar varios tipos de resultados para el contenido que se muestra en una vertical. Esto puede ser importante al combinar varios orígenes de contenido en una sola vertical. También se puede usar para un diseño más impactante incluso cuando solo hay un tipo de contenido. Por ejemplo, en una vertical que muestra detalles de incidentes, puede personalizar los incidentes de "gravedad alta" para que tengan colores más destacados que los incidentes de "gravedad baja". Para ello, defina las condiciones de la propiedad "gravedad" en la **sección** Reglas.

## <a name="create-or-update-result-types"></a>Crear o actualizar tipos de resultados

La experiencia de administración de tipos de resultados se rige por el asistente, se le guiará a través de los pasos para definir el nombre, el origen de contenido, las reglas y el diseño. Los tipos de resultados se pueden personalizar tanto en el nivel de organización como en SharePoint nivel de sitio.

### <a name="manage-organization-level-result-types"></a>Administrar tipos de resultados a nivel de organización

1. En  [Centro de administración de Microsoft 365](https://admin.microsoft.com/), vaya a la [**página Tipos de resultados**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) de la **sección Personalización.**
2. Para crear un nuevo tipo de resultado, haga clic **en Agregar** o seleccione uno existente para editarlo.
3. Después de configurar el tipo de resultado, puede revisarlo y guardarlo.

### <a name="manage-site-level-result-types"></a>Administrar tipos de resultados de nivel de sitio

1. En el sitio de Sharepoint donde desea administrar los tipos de resultados, abra el panel de configuración haciendo clic en el engranaje.
2. Seleccione **Información del sitio** y, a continuación, seleccione Ver toda la configuración del **sitio**.  
3. Busque la sección Búsqueda de Microsoft y, a continuación, seleccione **Configurar la configuración de búsqueda**.
4. En el panel de navegación, vaya a Experiencia personalizada y seleccione el **tipo de resultado**.
5. Para agregar un tipo de resultado, haga clic **en Agregar**. O bien, para editar un tipo de resultado, seleccione el tipo de resultado en la lista.
6. Después de modificar un tipo de resultado, puede revisar y guardar el tipo de resultado.

## <a name="troubleshooting"></a>Solución de problemas

Esta es una lista de problemas comunes que puede ver y acciones para solucionarlos.

|Problema  |Acción  |
|---------|---------|
| No veo mi diseño de resultados en la página de búsqueda, aunque he creado uno. | Puede haber un retraso de unos minutos porque esta configuración se almacena en caché. Espere unos minutos e inténtelo de nuevo.        |
| No veo ningún orígenes de contenido en la página de tipo de resultado. | Asegúrese de que ha configurado conectores y datos indizados.   |
