---
title: Administrar filtros personalizados
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Administrar filtros personalizados
ms.openlocfilehash: 256cf9748aa3050aacf48c3562f6f84b4ba2e460
ms.sourcegitcommit: 5151bcd8fd929ef37239b7c229e2fa33b1e0e0b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235926"
---
# <a name="manage-custom-filters"></a>Administrar filtros personalizados

Puede usar filtros para personalizar la experiencia Búsqueda de Microsoft usuario. Los filtros permiten a los usuarios refinar rápidamente el conjunto de resultados de su consulta de búsqueda.

Un filtro personalizado se puede crear dentro de una vertical en función de una propiedad de conexión. Por ejemplo, puede crear un filtro **Published On** para la conexión ServiceNow dentro de una vertical.

> [!NOTE]
> Los filtros personalizados están actualmente en versión preliminar para administradores y usuarios finales en la versión dirigida. Para obtener más información acerca de la vista previa, vea [Connectors preview features](connectors-overview.md#what-are-the-preview-features).

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>Crear un filtro en una vertical de nivel organizativo

Para crear un filtro en la búsqueda de Microsoft, siga estos pasos:

1. En el Centro de administración de Microsoft 365, vaya a [Verticales](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
1. Crear o editar la vertical en la que desea crear el filtro
1. Vaya al paso "Filtros" en el asistente
1. Haga clic en "Agregar filtro" y empezar
1. Después de agregar filtros, puede revisar y guardar la vertical.

## <a name="things-to-consider"></a>Consideraciones que se deben tener en cuenta

1. Existen capacidades de filtro adicionales en el contenido de conexión.

    - También puede crear un filtro en un alias para las propiedades de origen del conector
    - Si una vertical tiene varias conexiones, puede crear un filtro común en estas conexiones. Para ello, cree el filtro en un alias común que aliase las propiedades de origen en las distintas conexiones. Por ejemplo, puede crear un filtro **Author** a través de una conexión ServiceNow y Jira mediante la creación de alias de la siguiente manera:

    | Connection | Propiedad | Alias |
    | --- | --- | --- |
    | Servicio ahora | Propietario | Autor |
    | Jira | Publisher | Autor |

1. Los filtros existen dentro del ámbito de una vertical.

    - Si se crea un filtro en una vertical que está en el nivel organizativo, el filtro solo sería visible en el nivel organizativo.
    - Si se crea un filtro en una vertical que está a nivel de sitio, el filtro solo sería visible en el nivel del sitio.

## <a name="known-limitations"></a>Limitaciones conocidas

1. Actualmente, solo puede crear filtros en las propiedades administradas & tipo de fecha.
1. No se pueden crear filtros jerárquicos.

## <a name="resources"></a>Recursos

[Administrar los sectores verticales y los tipos de resultados](customize-search-page.md)
