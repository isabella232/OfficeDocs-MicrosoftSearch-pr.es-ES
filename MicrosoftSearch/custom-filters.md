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
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790338"
---
# <a name="manage-custom-filters"></a>Administrar filtros personalizados

Puede usar filtros para personalizar la experiencia de Búsqueda de Microsoft. Los filtros permiten a los usuarios refinar rápidamente el conjunto de resultados de su consulta de búsqueda.

Se puede crear un filtro personalizado dentro de una vertical en función de una propiedad de conexión. Por ejemplo, puede crear un filtro **Publicado en** para la conexión ServiceNow dentro de una vertical.

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>Crear un filtro en una vertical de nivel organizativo

Para crear un filtro en la búsqueda de Microsoft, siga estos pasos:

1. En el Centro de administración de Microsoft 365, vaya [a Verticales.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
1. Crear o editar la vertical en la que desea crear el filtro
1. Vaya al paso "Filtros" en el asistente
1. Haz clic en "Agregar filtro" y empieza a trabajar
1. Después de agregar filtros, puede revisar y guardar la vertical.

## <a name="things-to-consider"></a>Consideraciones que se deben tener en cuenta

1. Existen capacidades de filtro adicionales en el contenido de la conexión.

    - También puede crear un filtro en un alias para las propiedades de origen del conector
    - Si una vertical tiene varias conexiones, puede crear un filtro común en estas conexiones. Esto se puede hacer creando el filtro en un alias común que aliase las propiedades de origen en las distintas conexiones. Por ejemplo, puede crear un filtro **De** autor a través de una conexión ServiceNow y Jira mediante la creación de alias de la siguiente manera:

    | Connection | Propiedad | Alias |
    | --- | --- | --- |
    | Servicio ahora | Owner | Autor |
    | Jira | Publisher | Autor |

1. Los filtros existen en el ámbito de una vertical.

    - Si se crea un filtro en una vertical que se encuentra en el nivel organizativo, el filtro solo será visible en el nivel de la organización.
    - Si se crea un filtro en una vertical que se encuentra en el nivel de sitio, el filtro solo será visible en el nivel de sitio.

## <a name="known-limitations"></a>Limitaciones conocidas

1. Actualmente, solo puede crear filtros en cadenas & propiedades administradas de tipo de fecha.
1. No puede crear filtros jerárquicos.

## <a name="resources"></a>Recursos

[Administrar los sectores verticales y los tipos de resultados](customize-search-page.md)
