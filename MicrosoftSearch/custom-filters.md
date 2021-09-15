---
title: Administrar filtros
ms.author: v-revathib
author: revathi-b
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Administrar filtros para su uso en el SERP
ms.openlocfilehash: c614d4b60c746f2e18fdb3352281891ea5134373
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "59376201"
---
# <a name="manage-filters"></a>Administrar filtros

Los filtros permiten a los usuarios refinar los resultados de sus consultas y mostrar los resultados refinados. Puede personalizar los filtros disponibles para los usuarios en la Búsqueda de Microsoft usuario.

Hay dos tipos de filtros disponibles en la página de búsqueda.

- Filtros sin usar
- Filtros personalizados

> [!NOTE]
> Los filtros personalizados están actualmente en versión preliminar para administradores y usuarios finales en la versión dirigida. Para obtener más información acerca de la vista previa, vea [Connectors preview features](connectors-overview.md#what-are-the-preview-features).

## <a name="out-of-the-box-filters"></a>Filtros sin usar

Los filtros sin usar están disponibles de forma predeterminada en verticales de búsqueda como All, Files, Images y News. En las verticales "All" y "File", puede ver el filtro "Tipo de archivo" en la propiedad FileType y el filtro "Last modified" en la propiedad LastModifiedTime. Estos filtros están disponibles en SharePoint home, Office.com, SharePoint Sites y Work vertical in Bing.

## <a name="custom-filters"></a>Filtros personalizados

Los filtros se pueden agregar a las verticales de búsqueda personalizadas en el nivel de organización y de sitio. Las propiedades administradas refinables se usan para configurar filtros en el Asistente para administración vertical.  A continuación, se puede crear un filtro personalizado dentro de una vertical en función de una propiedad de conexión. Por ejemplo, puede crear un filtro Published On para una conexión ServiceNow dentro de una vertical.

Los filtros configurados para verticales en el ámbito de la organización estarán disponibles en el ámbito de la organización. Los filtros también se pueden configurar en el ámbito del sitio.  

## <a name="create-organization-level-filters"></a>Crear filtros de nivel de organización

1. En  [Centro de administración de Microsoft 365](https://admin.microsoft.com/), vaya a  [**Verticales**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Seleccione la vertical preferida donde desea crear un filtro y haga clic en **Editar**.  
3. Vaya al paso Filtros del asistente de la vertical.
4. Haga **clic en Agregar un filtro** para configurar filtros en propiedades administradas refinables.
5. Después de agregar filtros, puede revisar y guardar la vertical.

## <a name="create-sharepoint-site-level-filters"></a>Crear SharePoint de nivel de sitio

1. En [SharePoint centro de administración,](https://sharepoint.com/)vaya a Configuración.
2. Busque la sección Búsqueda de Microsoft y, a continuación, seleccione **Configurar Búsqueda de Microsoft para esta colección de sitios**.
3. En el panel de navegación, vaya a Experiencia personalizada y, a continuación,  **seleccione Verticales**.
4. Seleccione la vertical preferida para crear el filtro y haga clic en **Editar**.
5. Vaya al paso Filtros del asistente de la vertical.
6. Haga **clic en Agregar un filtro** para configurar filtros en propiedades administradas refinables.
7. Después de agregar filtros, puede revisar y guardar la vertical.

## <a name="filter-across-multiple-properties"></a>Filtrar entre varias propiedades

Las verticales se pueden crear con uno o varios orígenes de contenido. Cuando una vertical se configura con varios orígenes de contenido, la lista de propiedades del refinador muestra a qué origen de contenido pertenece cada propiedad refinable. Las propiedades administradas comunes se combinarán en función del nombre (o alias) y el tipo de datos. Los filtros también se pueden configurar en estas propiedades comunes. Para ello, cree el filtro en un alias común que aliase las propiedades de origen en las distintas conexiones. Por ejemplo, puede crear un filtro **author** en las conexiones ServiceNow y Jira mediante la creación de alias de la siguiente manera:

 | Connection | Propiedad | Alias |
 | --- | --- | --- |
 | Servicio ahora | Owner | Autor |
 | Jira | Publisher | Autor |

## <a name="important-details"></a>Detalles importantes

- Los filtros solo se pueden agregar a verticales personalizados. No se pueden agregar nuevos filtros a verticales desasoyéndolo como All, Files, People, Sites, News.
- Los filtros se pueden configurar en las propiedades Text y DateTime.
- Está limitado a un total de 50 filtros.
- No se puede ajustar el orden de los filtros desajustados.
- Los filtros no se admiten para OneDrive contenido. Los valores de filtro correspondientes a los resultados de OneDrive no aparecerán en los filtros.
- Los valores de filtro personalizados mostrarán opciones de SharePoint contenido y no del contenido de One Drive.Por ejemplo, si crea un filtro personalizado para 'Autor' y el contenido de SharePoint contiene resultados solo de un autor, 'Amy', y el contenido de OneDrive solo contiene resultados de un autor llamado 'Juan', el filtro personalizado autor mostrará 'Amy' como única opción.
- Un valor de filtro que se muestra SharePoint se aplicará al OneDrive cuando se usa.
