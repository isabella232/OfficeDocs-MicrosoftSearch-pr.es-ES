---
title: Conector de Graph MediaWiki para Búsqueda de Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de Graph MediaWiki para Búsqueda de Microsoft
ms.openlocfilehash: fff24ce918e3eab6a50d78977749a030ef17d0aef235e6d98e02bdf54fc63a0c
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532699"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>Conector de Graph MediaWiki

El conector de Graph MediaWiki permite a su organización detectar e indizar datos de un wiki creado mediante el software MediaWiki. Este conector indiza el contenido especificado en Búsqueda de Microsoft y admite rastreos periódicos para mantener el índice actualizado.

> [!NOTE]
> Lea el [**artículo Setup for your Graph connector para**](configure-connector.md) comprender las instrucciones generales Graph de configuración de conectores.

Este artículo está para cualquier persona que configure, ejecute y monitore un conector Graph MediaWiki. Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector Graph MediaWiki. En este artículo también se incluye información sobre [limitaciones](#limitations).

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

Escribe la **dirección URL wiki** y elige el tipo de **autenticación** en el menú desplegable de opciones. Las opciones **son None**, **Basic** y **OAuth 2.0 AAD**.

Si elige Básico **como** tipo de autenticación,  deberá proporcionar el nombre de usuario y **la contraseña** para el wiki.

Si elige **OAuth 2.0 AAD** como tipo de autenticación, deberá proporcionar el **id.** de recurso de la instalación wiki. También deberá proporcionar el  identificador de cliente y el secreto de **cliente generados** en la página de registro de la aplicación de AAD.

## <a name="step-4-manage-search-permissions"></a>Paso 4: Administrar permisos de búsqueda

El conector de MediaWiki solo admite permisos de búsqueda visibles para **Todos**. Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.

## <a name="step-5-assign-property-labels"></a>Paso 5: Asignar etiquetas de propiedades

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Paso 6: Administrar esquema

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Paso 7: Elegir la configuración de actualización

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Limitaciones

El conector de MediaWiki tiene estas limitaciones en la versión preliminar:

* Solo admite wikis basados en la nube.
* Solo admite Basic u OAuth 2.0 con Azure Active Directory autenticación de Azure.
* No admite la selección de espacios de nombres para la indización. Indiza solo los espacios de nombres Main, Category y File.
* No admite listas de control de acceso (ACL). Por lo tanto, las páginas indizadas son visibles para todos los usuarios de la organización.