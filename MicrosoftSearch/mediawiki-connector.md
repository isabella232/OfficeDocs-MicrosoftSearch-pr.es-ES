---
title: Conector de MediaWiki para Microsoft Search
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de MediaWiki para Microsoft Search
ms.openlocfilehash: b9c8d80ae5cb8e86b0f6341bfe9231b709569e7a
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47423022"
---
# <a name="mediawiki-connector"></a>Conector MediaWiki

Con el conector MediaWiki, su organización puede detectar e indizar datos de un sitio wiki creado mediante software de MediaWiki. Este conector indiza contenido específico en Microsoft Search y admite rastreos periódicos para mantener actualizado el índice.

Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de MediaWiki. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos

Escriba la dirección URL de MediaWiki y las credenciales para autenticar la conexión. Necesitará la siguiente información: **identificador de inquilino**, **identificador de recurso**, identificador de **cliente**y **secreto de cliente**.

## <a name="manage-the-search-schema"></a>Administrar el esquema de búsqueda

Una vez que se haya conectado correctamente, configure la asignación del esquema de búsqueda. Puede elegir las propiedades que se pueden **consultar**, realizar **búsquedas**y **recuperar**.

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda

El conector de MediaWiki solo admite permisos de búsqueda visibles para **todos los usuarios**. Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización

Esta programación actualiza los datos indizados, por lo que los cambios en el sitio wiki se reflejan en Microsoft Search. Todas las páginas nuevas, las páginas eliminadas, el contenido de la página o los cambios de metadatos aparecen en los resultados de la búsqueda después del intervalo de actualización especificado. El tiempo de rastreo depende del tamaño de la wiki. Actualmente el conector rastrea alrededor de 50 páginas por minuto.

## <a name="limitations"></a>Limitaciones

El conector de MediaWiki tiene estas limitaciones en la versión preliminar:

* Solo admite wikis basados en la nube.
* Solo admite Basic o OAuth 2,0 con Azure Active Directory o Azure Authentication.
* No admite la selección de espacio de nombres para la indización. Solo indiza los espacios de nombres **principal**, de **categoría**y de **archivo** .
* No es compatible con las listas de control de acceso (ACL). Por lo tanto, las páginas indizadas son visibles para todos los usuarios de la organización.
