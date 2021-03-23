---
title: Administrar respuestas de Power BI
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Administrar cómo aparecen los informes y los datos de Power BI en los resultados de búsqueda
ms.openlocfilehash: 3d67f79cce2392f949541690879ffb9202d79060
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031444"
---
# <a name="manage-power-bi-answers"></a>Administrar respuestas de Power BI

Para facilitar que los usuarios encuentren los datos y los análisis que necesitan para tomar decisiones fundamentadas, Microsoft Search ha agregado compatibilidad con los paneles e informes de Power BI. Estas son algunas de las ventajas de la búsqueda de Power BI:

* **Fácil de usar:** Esta experiencia de búsqueda lista para usar ayuda a los usuarios a encontrar fácilmente y rápidamente paneles e informes de Power BI en toda la organización.
* **Contenido más enriquecido:** Para que los resultados de búsqueda de Power BI sea más útil, incluyen información clave como el tipo de contenido (panel o informe) y el equipo o la persona que la posee.
* **Protección de datos integrada:** Los resultados de Power BI solo aparecerán para los usuarios que tienen acceso al panel o informe.
* **Experiencia de búsqueda unificada:** Para mantener una experiencia coherente, los resultados de Power BI son coherentes en todos los puntos de entrada de búsqueda. Donde quiera que busque, tendrá los mismos resultados con la misma apariencia.

## <a name="what-users-experience"></a>Qué experiencia tienen los usuarios

Los usuarios de Microsoft Search pueden encontrar resultados de Power BI buscando en el cuadro de búsqueda de Windows, SharePoint, Office 365 y Bing. Los usuarios pueden buscar informes y paneles con consultas como estas:

* Power BI acerca de `<topic>`
* Power BI para `<topic>`
* `<topic>` Panel de Power BI o panel de Power BI `<topic>`
* `<topic>` Informe de Power BI o informe de Power BI `<topic>`
* `<topic>` Métricas de Power BI o métricas de Power BI `<topic>`
* `<topic>` Cuadro de mandos de Power BI o cuadro de mandos de Power BI `<topic>`

Reemplace en los ejemplos anteriores por la información que está buscando, como `<topic>` ventas, uso, capacidad, 2021, Q1 y más, para ver los resultados relevantes de Power BI.

:::image type="content" source="media/powerbi-answers/powerbi-serp.png" alt-text="Captura de pantalla de un SERP con respuestas de Power BI y vertical" border="true":::

## <a name="turn-power-bi-search-on-or-off"></a>Activar o desactivar la búsqueda de Power BI

Los resultados de Power BI están habilitados para la organización de forma predeterminada. El administrador de Power BI puede deshabilitarlos en cualquier momento. En el portal de administración de Power BI, vaya a Configuración de inquilino y deshabilite la configuración Usar **búsqueda global para Power BI.** Para obtener más información, vea [Administering Power BI in the admin portal](/power-bi/admin/service-admin-portal#use-global-search-for-power-bi-preview).

:::image type="content" source="media/powerbi-answers/powerbi-admin.png" alt-text="Captura de pantalla de la configuración para activar o desactivar las respuestas de Power BI" border="true":::

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**P: ¿La búsqueda de Power BI está habilitada de forma predeterminada?**

**A:** Sí. La búsqueda de Power BI está habilitada de forma predeterminada para Microsoft Search. No hay ninguna configuración por primera vez requerida por el administrador de inquilinos para esta característica.

**P: ¿Se puede habilitar o deshabilitar la búsqueda de Power BI para grupos o usuarios específicos?**

**A:** Actualmente, solo se puede habilitar o deshabilitar para toda la organización.

**P: Si la búsqueda de Power BI está deshabilitada, ¿está oculta la página de resultados de búsqueda de Power BI?**

**A:** No. La página de resultados de búsqueda de Power BI aparecerá con un mensaje que informa a los usuarios de que no está disponible actualmente para su organización.

**P: ¿Puedo ver la página de resultados de búsqueda de Power BI si no tengo una licencia de Power BI?**

**A:** No. Si un usuario de búsqueda no tiene una licencia de Power BI, la página de resultados de búsqueda de Power BI no aparecerá en los resultados de Microsoft Search.

**P: ¿Voy a ver los resultados de búsqueda de Power BI a los que no puedo acceder?**

**A:** No. Microsoft Search solo devolverá los resultados de Power BI a los que tenga acceso.

**P: ¿Puedo personalizar los resultados de búsqueda de Power BI (por ejemplo, el tipo de informe o el propietario del informe)?**

**A:** Actualmente no se admite la personalización de los campos incluidos en los resultados de búsqueda de Power BI.