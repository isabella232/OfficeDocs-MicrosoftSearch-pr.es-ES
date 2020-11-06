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
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927390"
---
# <a name="create-custom-filters"></a>Crear filtros personalizados

Puede crear filtros para personalizar la experiencia de búsqueda que los usuarios ven cuando buscan en Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com)y Microsoft Search en [Bing](https://bing.com). Filtros permite a los usuarios refinar rápidamente el conjunto de resultados de la consulta de búsqueda.

Se puede crear un filtro personalizado dentro de un vertical basado en una propiedad de conexión. Por ejemplo, puede crear un filtro **publicado en** para la conexión de ServiceNow dentro de una vertical personalizada.

## <a name="things-to-consider"></a>Consideraciones que se deben tener en cuenta

1. Para crear un filtro personalizado en el origen de contenido de conexión, se proporcionan algunas funciones adicionales:
- También puede crear un filtro en un alias para las propiedades de origen del conector
- En caso de que la vertical tenga varias conexiones, puede crear un filtro común a través de estas conexiones. Para ello, cree el filtro en un alias común que contenga los alias de las propiedades de origen en distintas conexiones. Por ejemplo, puede crear un filtro de **autor** en un ServiceNow & una conexión JIRA mediante la creación de alias de la siguiente manera:

| Connection | Propiedad | Alias |
| --- | --- | --- |
| Servicio ahora | Owner | Autor |
| Jira | Publisher | Autor |

2. Existen filtros en el ámbito de la vertical. Ello  
- Si un filtro se crea en un vertical que se encuentra en el nivel de organización, el filtro solo estaría visible en el nivel de organización.
- Si un filtro se crea en un nivel vertical que se encuentra en el nivel del sitio, el filtro solo estaría visible en el nivel de sitio.

## <a name="steps-to-create-custom-filter"></a>Pasos para crear un filtro personalizado

### <a name="create-filter-in-organizational-level-vertical"></a>Crear filtro a nivel de organización vertical:

Para crear un filtro en Microsoft Search, siga estos pasos:

1. En el centro de administración de Microsoft 365, vaya a la página [vertical](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .
2. Crear o editar el vertical en el que desea crear el filtro
3. Vaya al paso "filtros" del asistente.
4. Haga clic en "agregar filtro" y empiece después de agregar filtros, puede revisar y guardar el vertical.

## <a name="known-limitations"></a>Limitaciones conocidas

1. Actualmente, solo se pueden crear filtros en las propiedades administradas de tipo de fecha & cadena.
2. No puede crear filtros jerárquicos

## <a name="resources"></a>Recursos

[Página personalizar resultados de búsqueda](customize-search-page.md)