---
title: Conector de sitios web de empresa para Microsoft Search
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
description: Configurar el conector de sitios web de empresa para Microsoft Search
ms.openlocfilehash: 4fb80ce4e3dbc77638e3b7db9c2ebd3c39d5a6d8
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422959"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a>Conector de sitios web de empresa

Con el conector para sitios web de la empresa, su organización puede indizar artículos y **contenido desde sus sitios web de orientación interna**. Después de configurar el conector y sincronizar el contenido del sitio web, los usuarios finales pueden buscar ese contenido desde cualquier cliente de Microsoft Search.

Este artículo está destinado a los administradores de [Microsoft 365](https://www.microsoft.com/microsoft-365) o a cualquiera que configure, ejecute y supervise un conector de sitios web de empresa. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.  

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos

Para conectarse a su origen de datos, necesita su dirección URL raíz y un formulario de autenticación: ninguno, autenticación básica o OAuth 2,0 con [Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/).

### <a name="authentication"></a>Autenticación

La autenticación básica requiere un nombre de usuario y una contraseña. Cree esta cuenta de bot mediante el [centro de administración de Microsoft 365](https://admin.microsoft.com).

OAuth 2,0 con [Azure ad](https://docs.microsoft.com/azure/active-directory/) requiere un identificador de recurso, un identificador de cliente y un secreto de cliente.

Para obtener más información, vea [autorizar el acceso a aplicaciones Web de Azure Active Directory mediante el flujo de concesión de código de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Regístrese con los siguientes valores:

**Name:** Búsqueda de Microsoft <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Para obtener los valores para los recursos, client_id y client_secret, vaya a **usar el código de autorización para solicitar un token de acceso** en la Página Web de dirección URL de redireccionamiento.

Para obtener más información, consulte [QuickStart: registrar una aplicación con la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

### <a name="root-url"></a>Dirección URL raíz

La dirección URL raíz es lo que inicia el rastreo y se usa para la autenticación. Puede obtener la dirección URL de la Página principal del sitio web que desea rastrear.

## <a name="select-the-source-properties"></a>Seleccionar las propiedades de origen

Las propiedades de origen se definen en función del formato de datos del sitio web de la empresa. Sin embargo, puede crear una **lista de exclusión** para excluir algunas direcciones URL de rastreo si el contenido es sensible o no merece el rastreo. Para crear una lista de exclusión, examine la dirección URL raíz. Tiene la opción de agregar las direcciones URL excluidas a la lista durante el proceso de configuración.

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda

No hay compatibilidad con las listas de control de acceso (ACL). Por lo tanto, se recomienda conectar solo los sitios web que son visibles para cualquier usuario de su organización.

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización

El conector para sitios web de empresa solo admite un rastreo completo. Esto significa que el conector Lee todo el contenido del sitio web durante cada rastreo. Para asegurarse de que el conector obtiene tiempo suficiente para leer el contenido, se recomienda establecer un intervalo de actualización de gran tamaño. Se recomienda una actualización programada entre una y dos semanas.

## <a name="troubleshooting"></a>Solución de problemas

Al leer el contenido del sitio web, el rastreo puede encontrar algunos errores de origen que están representados por los códigos de error detallados a continuación. Para obtener más información sobre los tipos de errores, vaya a la página **detalles de error** después de seleccionar la conexión. Haga clic en el **código de error** para ver errores más detallados. Consulte también [administrar el conector](https://docs.microsoft.com/microsoftsearch/manage-connector) para obtener más información.

 Código de error detallado | Mensaje de error
 --- | ---
 6001 | No se puede obtener acceso al sitio que está intentando indizar
 6005 | La página de origen que se está intentando indizar se ha bloqueado por la configuración de robots.txt.
 6008 | No se puede resolver el DNS
 6009 | Para todos los errores del lado cliente (excepto HTTP 404, 408), consulte los códigos de error HTTP 4xx para obtener más información.
 6013 | No se pudo encontrar la página de origen que se está intentando indizar. (Error HTTP 404)
 6018 | La página de origen no responde y se ha agotado el tiempo de espera de la solicitud. (Error HTTP 408)
 6021 | La página de origen que se intenta indizar no tiene contenido textual en la página.
 6023 | La página de origen que se está intentando indizar no es compatible (no es una página HTML)
 6024 | La página de origen que se está intentando indizar tiene contenido no admitido.

* Los errores 6001-6013 se producen cuando no se puede obtener acceso al origen de datos debido a un problema de red o cuando el propio origen de datos se elimina, se mueve o se cambia de nombre. Compruebe si los detalles del origen de datos proporcionados siguen siendo válidos.
* Error 6021-6024 el error se produce cuando el origen de datos contiene contenido no textual en la página o cuando la página no es HTML. Compruebe el origen de datos y agregue esta página en la lista de exclusión o ignore el error.

## <a name="limitations"></a>Limitaciones

El conector de sitios web de empresa no admite la búsqueda de datos en **páginas web dinámicas**. Algunos ejemplos de estas páginas web se activan en sistemas de administración de contenido como [Confluence](https://www.atlassian.com/software/confluence) y [Unily](https://www.unily.com/) o bases de datos que almacenan contenido de sitios Web.
