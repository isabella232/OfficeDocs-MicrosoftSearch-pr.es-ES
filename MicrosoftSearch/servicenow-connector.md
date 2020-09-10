---
title: Conector de ServiceNow para Microsoft Search
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
description: Configurar el conector de ServiceNow para Microsoft Search
ms.openlocfilehash: 29e8e490f114ce8537ddb973ed16ccb34f24f82f
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422869"
---
# <a name="servicenow-connector"></a>Conector de ServiceNow

Con el conector de ServiceNow, su organización puede indizar artículos de Knowledge base que son visibles para todos los usuarios de la organización. Después de configurar el conector y el contenido del índice desde ServiceNow, los usuarios finales pueden buscar dichos artículos desde cualquier cliente de Microsoft Search.  

Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de ServiceNow. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos

Para conectarse a los datos de ServiceNow, necesita la URL de **instancia de servicenow**de su organización, las credenciales de esta cuenta y el identificador de cliente y el secreto de cliente para la autenticación OAuth.  

Normalmente, la **dirección URL** de la instancia de ServiceNow de la organización es similar a **https:// &lt; -Organization-Domain>. Service-Now.com**. Junto con esta dirección URL, necesitará una cuenta para configurar la conexión a ServiceNow, así como para permitir que Microsoft Search actualice los artículos periódicamente desde ServiceNow en función de la programación de actualización.

Para autenticar y sincronizar el contenido desde ServiceNow, elija uno de los dos métodos admitidos:

1. Autenticación básica
2. OAuth (recomendado)

> [!Note]
> Para usar OAuth para la autenticación, un administrador de ServiceNow debe aprovisionar un punto de conexión en su instancia de ServiceNow para que la aplicación de Microsoft Search pueda acceder a la instancia. Para obtener más información, consulte [crear un extremo para que los clientes accedan a la instancia](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) en la documentación de ServiceNow.

En la siguiente tabla se proporcionan instrucciones sobre cómo rellenar el formulario de creación de extremos:

**Field** | **Descripción** | **Valor recomendado**
--- | --- | ---
Nombre | Este valor único identifica la aplicación para la que requiere acceso de OAuth. | Búsqueda de Microsoft
Identificador de cliente | IDENTIFICADOR único de solo lectura y generado automáticamente para la aplicación. La instancia usa el identificador de cliente cuando solicita un token de acceso. | N/D
Secreto de cliente | Con esta cadena secreta compartida, la instancia de ServiceNow y autorizar las comunicaciones de Microsoft Search entre sí. | Siga los procedimientos recomendados de seguridad tratando esto como una contraseña.
Dirección URL de redireccionamiento | Una dirección URL de devolución de llamada obligatoria a la que redirige el servidor de autorización. | https://gcs.office.com/v1.0/admin/oauth/callback
Dirección URL del logotipo | Una dirección URL que contiene la imagen del logotipo de la aplicación. | N/D
Activo | Active la casilla para activar el registro de aplicaciones. | Establecer en activo
Duración del token de actualización | Número de segundos que un token de actualización es válido. De forma predeterminada, los tokens de actualización expiran en 100 días (8640000 segundos). | 31.536.000 (1 año)
Duración del token de acceso | Número de segundos que un token de acceso es válido. | 43.200 (12 horas)

## <a name="set-a-sync-filter"></a>Establecer un filtro de sincronización

Con un filtro de sincronización, puede especificar condiciones para la sincronización de artículos. Es similar a una cláusula **Where** en una instrucción **SELECT de SQL** . Por ejemplo, puede optar por indizar solo los artículos publicados y activos. La página de configuración de SyncNow describe cómo capturar y establecer un filtro de sincronización.

## <a name="manage-the-search-schema"></a>Administrar el esquema de búsqueda

Una vez que se haya conectado correctamente, configure la asignación del esquema de búsqueda. Puede elegir las propiedades que se pueden **consultar**, realizar **búsquedas**y **recuperar**.

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda

El conector de ServiceNow solo admite permisos de búsqueda visibles para **todos los usuarios**. Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización

El conector de ServiceNow admite programaciones de actualización para rastreos completos e incrementales. Le recomendamos que configure ambos.

Una programación de rastreo completo encuentra artículos eliminados que se han sincronizado anteriormente con el índice de Microsoft Search y los artículos que se han sacado del filtro de sincronización. La primera vez que se conecte a ServiceNow, se ejecuta un rastreo completo para sincronizar todos los artículos de Knowledge base. Para sincronizar nuevos elementos y realizar actualizaciones, debe programar rastreos incrementales.

El valor predeterminado recomendado es un día para un rastreo completo y cuatro horas para un rastreo incremental.
