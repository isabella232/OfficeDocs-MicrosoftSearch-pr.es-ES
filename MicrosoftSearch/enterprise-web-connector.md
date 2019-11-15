---
title: Conector de sitios web de empresa para Microsoft Search
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de sitios web de empresa para Microsoft Search
ms.openlocfilehash: c2495487b24b11512a182434f72a90044a439d5d
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626277"
---
# <a name="enterprise-websites-connector"></a>Conector de sitios web de empresa

Con el conector para sitios web de la empresa, su organización puede indizar artículos y **contenido desde sus sitios web de orientación interna**. Después de configurar el conector y sincronizar el contenido del sitio web, los usuarios finales pueden buscar ese contenido desde cualquier cliente de Microsoft Search.

Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de sitios web de empresa. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.  

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos 
Para conectarse a su origen de datos, necesita su dirección URL raíz y una forma de autenticación (autenticación básica o OAuth 2,0 con Azure AD).

### <a name="root-url"></a>Dirección URL raíz
La dirección URL raíz es lo que inicia el rastreo y se usa para la autenticación. Puede obtener la dirección URL de la Página principal del sitio web que desea rastrear.

### <a name="authentication"></a>Autenticación 
La autenticación básica requiere un nombre de usuario y una contraseña. Cree esta cuenta de bot mediante el [centro de administración de Microsoft 365](https://admin.microsoft.com).

OAuth 2,0 con Azure AD requiere un identificador de espacio empresarial, un identificador de recurso, un identificador de cliente y un secreto de cliente.
Para obtener más información, vea [autorizar el acceso a aplicaciones Web de Azure Active Directory mediante el flujo de concesión de código de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Regístrese con los siguientes valores:
* **Name:** Búsqueda de Microsoft
* **Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Para obtener los valores de inquilino, recurso, client_id y client_secret con nombre, vaya a **usar el código de autorización para solicitar un token de acceso** en la Página Web de dirección URL de redireccionamiento.

Para obtener más información, consulte [QuickStart: registrar una aplicación con la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

### <a name="reverse-proxy-url"></a>Dirección URL de proxy inverso 
El conector de sitios web de empresa está basado en la nube, por lo que no tiene acceso al contenido local. Para proporcionar ese acceso, instale un proxy inverso. Un proxy inverso proporciona un acceso seguro y confiable a los sitios web locales. Se recomienda el proxy de aplicación de Azure (AAP).

El requisito de proxy inverso para la dirección URL raíz y la autenticación es el mismo que para el contenido basado en la nube, excepto que la dirección URL raíz y la autenticación las proporciona el servidor proxy inverso.

Consulte [consideraciones de seguridad para obtener acceso a aplicaciones de forma remota con el proxy de aplicación de Azure ad](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security).

## <a name="select-the-source-properties"></a>Seleccionar las propiedades de origen 
Las propiedades de origen se definen en función del formato de datos del sitio web de la empresa. Sin embargo, puede crear una **lista de exclusión** para excluir algunas direcciones URL del rastreo, ya que el contenido puede ser sensible o no merece el rastreo. Para crear una lista de exclusión, examine la dirección URL raíz. Tiene la opción de agregar las direcciones URL excluidas a la lista durante el proceso de configuración.

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda 
No se admiten las listas de control de acceso (ACL). Por lo tanto, se recomienda conectar solo los sitios web que son visibles para cualquier usuario de su organización.

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización
El conector para sitios web de empresa solo admite un rastreo completo. Esto significa que el conector Lee todo el contenido del sitio web durante cada rastreo. Para asegurarse de que el conector obtiene tiempo suficiente para leer el contenido, se recomienda establecer un intervalo de actualización de gran tamaño. Se recomienda una actualización programada entre tres días y dos semanas.

## <a name="limitations"></a>Limitaciones 
El conector de sitios web de empresa no admite la búsqueda de datos en páginas web dinámicas. Algunos ejemplos de estas páginas web se activan en sistemas de administración de contenido como Confluence y Unily o bases de datos que almacenan contenido de sitios Web.