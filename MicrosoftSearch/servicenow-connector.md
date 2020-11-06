---
title: Conector de ServiceNow para Microsoft Search
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de ServiceNow para Microsoft Search
ms.openlocfilehash: b60583e61687b13c7fd631cd1c4a9f6d663724e8
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927202"
---
# <a name="servicenow-connector"></a>Conector de ServiceNow

Con el conector de ServiceNow, su organización puede indizar artículos de Knowledge base que son visibles para todos los usuarios de la organización. Después de configurar el conector y el contenido del índice desde ServiceNow, los usuarios finales pueden buscar dichos artículos desde cualquier cliente de Microsoft Search.  

Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de ServiceNow. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.

Obtenga información acerca de cómo tener acceso a los conectores creados por Microsoft desde [la instalación del conector creado por Microsoft para Microsoft Search](https://docs.microsoft.com/microsoftsearch/configure-connector). La configuración específica de ServiceNow Connector se explica en el artículo siguiente.

## <a name="connection-settings"></a>Configuración de conexión
Para conectarse a los datos de ServiceNow, necesita la URL de **instancia de servicenow** de su organización, las credenciales de esta cuenta y el identificador de cliente y el secreto de cliente para la autenticación OAuth.  

Normalmente, la **dirección URL** de la instancia de ServiceNow de la organización es similar a **https:// &lt; -Organization-Domain>. Service-Now.com**. Junto con esta dirección URL, necesitará una cuenta para configurar la conexión a ServiceNow, así como para permitir que Microsoft Search actualice los artículos periódicamente desde ServiceNow en función de la programación de actualización. La cuenta debe tener el rol <em>conocimiento</em> . [Obtenga información sobre cómo asignar roles para cuentas de ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

Para autenticar y sincronizar el contenido desde ServiceNow, elija **uno de los tres** métodos admitidos:
1. Autenticación básica 
2. ServiceNow OAuth (recomendado)
3. OpenID Connect de Azure AD

#### <a name="basic-authentication"></a>Autenticación básica
Escriba el nombre de usuario y la contraseña de la cuenta de ServiceNow con el rol de <em>conocimiento</em> para autenticarse en la instancia.
#### <a name="servicenow-oauth"></a>OAuth de ServiceNow

Para usar ServiceNow OAuth para la autenticación, un administrador de ServiceNow debe aprovisionar un extremo en su instancia de ServiceNow, de modo que la aplicación de Microsoft Search pueda acceder a la instancia. Para obtener más información, consulte [crear un extremo para que los clientes accedan a la instancia](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) en la documentación de ServiceNow.

En la siguiente tabla se proporcionan instrucciones sobre cómo rellenar el formulario de creación de extremos:

**Field** | **Descripción** | **Valor recomendado**
--- | --- | ---
Nombre | Este valor único identifica la aplicación para la que requiere acceso de OAuth. | Búsqueda de Microsoft
Identificador de cliente | IDENTIFICADOR único de solo lectura y generado automáticamente para la aplicación. La instancia usa el identificador de cliente cuando solicita un token de acceso. | N/D
Secreto de cliente | Con esta cadena secreta compartida, la instancia de ServiceNow y las autorizaciones de Microsoft Search permiten comunicarse entre sí. | Siga los procedimientos recomendados de seguridad tratando esto como una contraseña.
Dirección URL de redireccionamiento | Una dirección URL de devolución de llamada obligatoria a la que redirige el servidor de autorización. | https://gcs.office.com/v1.0/admin/oauth/callback
Dirección URL del logotipo | Una dirección URL que contiene la imagen del logotipo de la aplicación. | N/D
Activo | Active la casilla para activar el registro de aplicaciones. | Establecer en activo
Duración del token de actualización | Número de segundos que un token de actualización es válido. De forma predeterminada, los tokens de actualización expiran en 100 días (8640000 segundos). | 31.536.000 (1 año)
Duración del token de acceso | Número de segundos que un token de acceso es válido. | 43.200 (12 horas)

Escriba el identificador de cliente y el secreto de cliente para conectarse a su instancia. Después de conectar, use una credencial de cuenta de ServiceNow para autenticar el permiso para el rastreo. La cuenta debe tener el rol <em>conocimiento</em> . 

#### <a name="azure-ad-openid-connect"></a>OpenID Connect de Azure AD

Para usar el OpenID Connect de Azure AD para la autenticación, siga los pasos que se indican a continuación.

###### <a name="step-1-register-a-new-application-in-azure-active-directory"></a>Paso 1: registrar una nueva aplicación en Azure Active Directory

Para obtener información sobre cómo registrar una nueva aplicación en Azure Active Directory, vea [registrar una aplicación](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application). Seleccione el directorio de organización de un solo inquilino. No se necesita el URI de redireccionamiento. Después del registro, anote el identificador de la aplicación (cliente) y el identificador del directorio (inquilino).

###### <a name="step-2-create-a-client-secret"></a>Paso 2: crear un secreto de cliente

Para obtener información sobre cómo crear un secreto de cliente, vea [crear un secreto de cliente](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret). Tome nota del secreto de cliente.

###### <a name="step-3-retrieve-service-principal-object-identifier"></a>Paso 3: recuperar el identificador del objeto de entidad de servicio

Siga los pasos para recuperar el identificador de objeto de entidad de servicio

1. Ejecutar PowerShell
2. Instalar Azure PowerShell con el siguiente comando
```<language>
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
```
3. Conectarse a Azure
```<language>
    Connect-AzAccount
```
4. Obtener el identificador del objeto de entidad de servicio
```<language>
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
```
Reemplace "Application-ID" por el identificador de la aplicación (cliente) (sin comillas) de la aplicación que registró en el paso 1. Anote el valor del objeto ID de la salida de PowerShell. Es el identificador de entidad de servicio.

Ahora tiene toda la información necesaria de Azure portal. En la tabla siguiente se proporciona un resumen rápido de la información.

**Propiedad** | **Descripción**
--- | ---
IDENTIFICADOR de directorio (ID de inquilino) | Se trata de un identificador único que hace referencia al inquilino de Azure Active Directory (desde el paso 1).
IDENTIFICADOR de la aplicación (identificador de cliente) | Se trata de un identificador único que hace referencia a la aplicación registrada en el paso 1.
Secreto de cliente | Esta es la clave secreta de la aplicación (del paso 2). Trate como una contraseña.
IDENTIFICADOR de entidad de servicio | Una identidad para la aplicación que se ejecuta como un servicio. (del paso 3)

###### <a name="step-4-register-servicenow-application"></a>Paso 4: registrar una aplicación de ServiceNow

La siguiente configuración debe realizarse en la instancia de ServiceNow.

1. Registre una nueva entidad OIDC de OAuth. Para obtener más información, vea [crear un proveedor de OIDC de OAuth](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).
2. En la siguiente tabla se proporcionan instrucciones sobre cómo rellenar el formulario de registro del proveedor de OIDC

**Field** | **Descripción** | **Valor recomendado**
--- | --- | ---
Nombre | Un nombre único que identifica la entidad OIDC de OAuth. | Azure AD
Identificador de cliente | IDENTIFICADOR de cliente de la aplicación registrada en el servidor OIDC de OAuth de terceros. La instancia usa el identificador de cliente al solicitar un token de acceso. | IDENTIFICADOR de la aplicación (cliente) del paso 1
Secreto de cliente | El secreto de cliente de la aplicación registrada en el servidor OIDC de OAuth de terceros. | Secreto de cliente del paso 2

Todos los demás valores pueden ser predeterminados.

3. En el formulario de registro del proveedor OIDC, debe agregar una nueva configuración de proveedor de OIDC. Haga clic en el icono de búsqueda en el campo *configuración del proveedor OIDC de OAuth* para abrir los registros de las configuraciones de OIDC. Haga clic en Nuevo.
4. En la tabla siguiente se proporciona información sobre cómo rellenar el formulario de configuración del proveedor de OIDC

**Field** | **Valor recomendado**
--- | ---
Proveedor OIDC |  Azure AD
Dirección URL de metadatos de OIDC | Debe tener el formato HTTPS \: //login.microsoftonline.com/"tenandId"/.Well-Known/OpenID-Configuration <br/>Reemplace "tenantID" por el identificador de directorio (inquilino) del paso 1 (sin comillas).
Intervalo de vida de la memoria caché de configuración de OIDC |  120
Application | Global
Notificación de usuario | sub
Campo de usuario | Id. de usuario
Habilitar la comprobación de notificaciones de JTI | Deshabilitado

5. Haga clic en enviar y actualizar el formulario de entidad OIDC de OAuth.

###### <a name="step-5-create-a-servicenow-account"></a>Paso 5: crear una cuenta de ServiceNow

Consulte las instrucciones para crear una cuenta de ServiceNow, [crear un usuario en ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

En la siguiente tabla se proporcionan instrucciones sobre cómo rellenar el registro de la cuenta de usuario de ServiceNow.

**Field** | **Valor recomendado**
--- | ---
Id. de usuario | IDENTIFICADOR de entidad de servicio del paso 3
Acceso al servicio Web solamente | Checked

El resto de valores pueden dejarse en valores predeterminados.

###### <a name="step-6-enable-knowledge-role-for-the-servicenow-account"></a>Paso 6: habilitar rol de conocimiento para la cuenta de ServiceNow

Acceda a la cuenta de ServiceNow que ha creado con el identificador principal de ServiceNow como identificador de usuario y asigne la función de conocimiento. Aquí encontrará instrucciones para asignar un rol a una cuenta de ServiceNow, así como [para asignar una función a un usuario](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

Use el identificador de aplicación como identificador de cliente (del paso 1) y secreto de cliente (del paso 2) en el Asistente para la configuración del centro de administración para autenticarse en su instancia de ServiceNow mediante el OpenID Connect de Azure AD.

## <a name="filter-data"></a>Filtrar datos 
Con una cadena de consulta de ServiceNow, puede especificar condiciones para la sincronización de artículos. Es similar a una cláusula **Where** en una instrucción **SELECT de SQL** . Por ejemplo, puede optar por indizar solo los artículos publicados y activos. Para obtener información sobre cómo crear su propia cadena de consulta, consulte [generar una cadena de consulta codificada mediante un filtro](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda
El conector de ServiceNow solo admite permisos de búsqueda visibles para **todos los usuarios**. Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.

## <a name="manage-the-search-schema"></a>Administrar el esquema de búsqueda
Una vez que se haya conectado correctamente, configure la asignación del esquema de búsqueda. Puede elegir las propiedades que se pueden **consultar** , realizar **búsquedas** y **recuperar**. Para obtener más información acerca de la administración del esquema de búsqueda, consulte [Manage The Search Schema](https://docs.microsoft.com/microsoftsearch/configure-connector#manage-the-search-schema).

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización
El conector de ServiceNow admite programaciones de actualización para rastreos completos e incrementales. Le recomendamos que configure ambos.

Una programación de rastreo completo encuentra artículos eliminados que se han sincronizado anteriormente con el índice de Microsoft Search y los artículos que se han sacado del filtro de sincronización. La primera vez que se conecte a ServiceNow, se ejecuta un rastreo completo para sincronizar todos los artículos de Knowledge base. Para sincronizar nuevos elementos y realizar actualizaciones, debe programar rastreos incrementales.

El valor predeterminado recomendado es un día para un rastreo completo y cuatro horas para un rastreo incremental.

## <a name="review-and-publish"></a>Revisión y publicación
Después de configurar el conector, puede revisar y publicar la conexión.

## <a name="next-steps"></a>Pasos siguientes
Después de publicar la conexión, debe personalizar la página de resultados de búsqueda. Para obtener información sobre cómo personalizar los resultados de la búsqueda, vea [personalizar la página de resultados de búsqueda](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).