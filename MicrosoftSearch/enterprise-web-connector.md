---
title: Conector de sitios web de empresa para Microsoft Search
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
description: Configurar el conector de sitios web de empresa para Microsoft Search
ms.openlocfilehash: 443e903e0fa371d2a056fd4bf06310eb2627b11c
ms.sourcegitcommit: 031e7c595496d9faed9038725b04f3c8b5f9ccbd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604781"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a>Conector de sitios web de empresa

Con el conector para sitios web de la empresa, su organización puede indizar artículos y **contenido desde sus sitios web de orientación interna**. Después de configurar el conector y sincronizar el contenido del sitio web, los usuarios finales pueden buscar ese contenido desde cualquier cliente de Microsoft Search.

Este artículo está destinado a los administradores de [Microsoft 365](https://www.microsoft.com/microsoft-365) o a cualquiera que configure, ejecute y supervise un conector de sitios web de empresa. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.  

## <a name="connection-settings"></a>Configuración de conexión

Para conectarse a su origen de datos, debe rellenar la dirección URL raíz del sitio web, seleccionar un origen de rastreo y el tipo de autenticación que desea usar: ninguno, autenticación básica o OAuth 2,0 con [Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/). Una vez completada esta información, haga clic en probar conexión para comprobar la configuración.

### <a name="url"></a>URL

Use el campo dirección URL para especificar la raíz del sitio web que quiere rastrear. El conector de sitios web de empresa usará esta dirección URL como punto de partida y seguirá todos los vínculos de esta dirección URL para el rastreo.

### <a name="crawl-mode-cloud-or-on-premises-preview"></a>Modo de rastreo: en la nube o local (versión preliminar)

El modo de rastreo determina el tipo de sitios web que desea indizar, ya sea en la nube o en el entorno local. Para los sitios web de la nube, seleccione **nube** como modo de rastreo.

Además, el conector ahora admite el rastreo de sitios web locales. Este modo está en versión preliminar. Para obtener acceso a los datos locales, primero debe instalar y configurar el agente de conector de Graph. Para obtener más información, consulte [Graph Connector Agent](https://docs.microsoft.com/microsoftsearch/on-prem-agent).

Para los sitios web locales, seleccione **agente** como modo de rastreo y, en el campo **agente local** , elija el agente de conector de Graph que ha instalado y configurado anteriormente.  

![Captura de pantalla del panel Configuración de conexión para Enterprise web Connector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a>Autenticación

La autenticación básica requiere un nombre de usuario y una contraseña. Cree esta cuenta de bot mediante el [centro de administración de Microsoft 365](https://admin.microsoft.com).

OAuth 2,0 con [Azure ad](https://docs.microsoft.com/azure/active-directory/) requiere un identificador de recurso, un identificador de cliente y un secreto de cliente. OAuth 2,0 solo funciona con el modo de nube.

Para obtener más información, vea [autorizar el acceso a aplicaciones Web de Azure Active Directory mediante el flujo de concesión de código de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Regístrese con los siguientes valores:

**Name:** Búsqueda de Microsoft <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Para obtener los valores para los recursos, client_id y client_secret, vaya a **usar el código de autorización para solicitar un token de acceso** en la Página Web de dirección URL de redireccionamiento.

Para obtener más información, consulte [QuickStart: registrar una aplicación con la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="support-for-robotstxt"></a>Compatibilidad con robots.txt

El conector comprueba si hay un archivo de robots.txt para el sitio raíz y, si lo hay, lo seguirá y respetará las indicaciones encontradas dentro de ese archivo. Si no desea que el conector rastree determinadas páginas o directorios en el sitio, puede llamar a esas páginas o directorios en las declaraciones "Disallow" del archivo de robots.txt.

## <a name="add-urls-to-exclude"></a>Agregar direcciones URL para excluir

Si lo desea, puede crear una **lista de exclusión** para excluir algunas direcciones URL del rastreo si el contenido es sensible o no merece el rastreo. Para crear una lista de exclusión, examine la dirección URL raíz. Tiene la opción de agregar las direcciones URL excluidas a la lista durante el proceso de configuración.

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda

El conector para sitios web de empresa solo admite permisos de búsqueda visibles para **todos los usuarios**. Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.

## <a name="assign-property-labels"></a>Asignar etiquetas de propiedad

Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones. Aunque este paso no es obligatorio, tener algunas etiquetas de propiedades mejorará la relevancia de la búsqueda y garantizará resultados de búsqueda más precisos para los usuarios finales.

## <a name="manage-schema"></a>Administrar esquema

En la pantalla **administrar esquema** , tiene la opción de cambiar los atributos de esquema (**consultable**, **búsquedas**, **recuperables** y **refinables**) asociados con las propiedades, agregar alias opcionales y elegir la propiedad de **contenido** .

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización

El conector para sitios web de empresa solo admite una actualización completa. Esto significa que el conector volverá a rastrear todo el contenido del sitio web durante cada actualización. Para asegurarse de que el conector obtiene tiempo suficiente para rastrear el contenido, se recomienda establecer un intervalo de actualización de gran tamaño. Se recomienda una actualización programada entre una y dos semanas.

## <a name="troubleshooting"></a>Solución de problemas

Al leer el contenido del sitio web, el rastreo puede encontrarse con algunos errores de origen, que se representan mediante los códigos de error detallados a continuación. Para obtener más información sobre los tipos de errores, vaya a la página **detalles de error** después de seleccionar la conexión. Haga clic en el **código de error** para ver errores más detallados. Consulte también [administrar el conector](https://docs.microsoft.com/microsoftsearch/manage-connector) para obtener más información.

 Código de error detallado | Mensaje de error
 --- | ---
 6001 | No se puede obtener acceso al sitio que está intentando indizar
 6005 | La página de origen que se está intentando indizar se ha bloqueado por la configuración de robots.txt.
 6008 | No se puede resolver el DNS
 6009 | Para todos los errores del lado cliente (excepto HTTP 404, 408), consulte códigos de error HTTP 4xx para obtener más información.
 6013 | No se pudo encontrar la página de origen que se está intentando indizar. (Error HTTP 404)
 6018 | La página de origen no responde y se ha agotado el tiempo de espera de la solicitud. (Error HTTP 408)
 6021 | La página de origen que se intenta indizar no tiene contenido textual en la página.
 6023 | La página de origen que se está intentando indizar no es compatible (no es una página HTML)
 6024 | La página de origen que se está intentando indizar tiene contenido no admitido.

* Los errores 6001-6013 se producen cuando no se puede obtener acceso al origen de datos debido a un problema de red o cuando el propio origen de datos se elimina, se mueve o se cambia de nombre. Compruebe si los detalles del origen de datos proporcionados siguen siendo válidos.
* Los errores 6021-6024 se producen cuando el origen de datos contiene contenido no textual en la página o cuando la página no es HTML. Compruebe el origen de datos y agregue esta página en la lista de exclusión o ignore el error.

## <a name="limitations"></a>Limitaciones

El conector de sitios web de empresa no admite la búsqueda de datos en **páginas web dinámicas**. Algunos ejemplos de estas páginas web se activan en sistemas de administración de contenido como [Confluence](https://www.atlassian.com/software/confluence) y [Unily](https://www.unily.com/) o bases de datos que almacenan contenido de sitios Web.

## <a name="next-steps"></a>Pasos siguientes

Después de publicar la conexión, debe personalizar la página de resultados de búsqueda. Para obtener información sobre cómo personalizar los resultados de la búsqueda, vea [personalizar la página de resultados de búsqueda](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).
