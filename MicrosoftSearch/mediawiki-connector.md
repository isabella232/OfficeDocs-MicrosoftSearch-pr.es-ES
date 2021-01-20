---
title: Conector MediaWiki para Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector MediaWiki para Microsoft Search
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905960"
---
# <a name="mediawiki-connector"></a>Conector MediaWiki

Con el conector MediaWiki, su organización puede detectar e indizar datos de un sitio wiki creado mediante el software MediaWiki. Este conector indiza el contenido especificado en Microsoft Search y admite rastreos periódicos para mantener el índice actualizado.

Este artículo está dirigido a administradores de Microsoft 365 o a cualquier persona que configure, ejecute y monitore un conector de MediaWiki Graph. Complementa las instrucciones generales proporcionadas en el artículo [Configurar el conector de Graph.](configure-connector.md) Si aún no lo ha hecho, lea todo el artículo Configurar el conector de Graph para comprender el proceso de configuración general.

Cada paso del proceso de configuración se muestra a continuación junto con una nota que indica que debe seguir las instrucciones generales de configuración u otras instrucciones que se aplican solo a conectores de MediaWiki Graph. En este artículo también se incluye información [sobre las limitaciones](#limitations) de los conectores de MediaWiki Graph. 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365.
Siga las instrucciones generales de configuración.

## <a name="step-2-name-the-connection"></a>Paso 2: Asigne un nombre a la conexión.
Siga las instrucciones generales de configuración.
 
## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión.
Escriba su **dirección URL wiki** y elija el tipo de **autenticación** en el menú desplegable de opciones. Las opciones son **None**, **Basic** y **OAuth 2.0 AAD**.

Si elige **Básico como** tipo de autenticación,  deberá proporcionar el nombre de usuario y la contraseña **para** el sitio wiki.

Si elige **OAuth 2.0 AAD** como tipo de autenticación, deberá proporcionar el id. de recurso **de** la instalación wiki. También deberá proporcionar el  identificador de cliente y el secreto de **cliente** generados en la página de registro de la aplicación de AAD. 

## <a name="step-4-manage-search-permissions"></a>Paso 4: Administrar permisos de búsqueda
El conector MediaWiki solo admite permisos de búsqueda visibles para **Todos.** Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.

## <a name="step-5-assign-property-labels"></a>Paso 5: Asignar etiquetas de propiedad
Siga las instrucciones generales de configuración.

## <a name="step-6-manage-schema"></a>Paso 6: Administrar esquema
Siga las instrucciones generales de configuración.

## <a name="step-7-choose-refresh-settings"></a>Paso 7: Elegir la configuración de actualización
Siga las instrucciones generales de configuración.

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión
Siga las instrucciones generales de configuración.

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Limitaciones
El conector MediaWiki tiene estas limitaciones en la versión preliminar:

* Solo admite wikis basadas en la nube.
* Solo admite Basic u OAuth 2.0 con Azure Active Directory o la autenticación de Azure.
* No admite la selección de espacios de nombres para la indización. Indiza solo los espacios de nombres Main, Category y File.
* No admite listas de control de acceso (ACL). Por lo tanto, las páginas indizadas son visibles para todos los usuarios de la organización.
