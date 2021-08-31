---
title: ServiceNow Graph conector para Búsqueda de Microsoft
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de Graph ServiceNow para Búsqueda de Microsoft
ms.openlocfilehash: fccae6c2a007470eb9ef56130cb952158c01610c
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701916"
---
<!---Previous ms.author: kam1 --->


# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

Con Microsoft Graph Connector para ServiceNow, su organización puede indizar artículos de knowledge base que son visibles para todos los usuarios o restringidos con permisos de criterios de usuario dentro de su organización. Después de configurar el conector y el contenido de índice de ServiceNow, los usuarios finales pueden buscar esos artículos desde cualquier Búsqueda de Microsoft cliente.  

También puede consultar el [siguiente vídeo](https://www.youtube.com/watch?v=TVSkJpk1RiE) para obtener más información sobre la Graph Connector en la administración de permisos de búsqueda.

[![Administración de permisos de búsqueda en Microsoft Graph Connector para ServiceNow.](https://img.youtube.com/vi/TVSkJpk1RiE/hqdefault.jpg)](https://www.youtube.com/watch?v=TVSkJpk1RiE)

Este artículo está para Microsoft 365 administradores o cualquier persona que configure, ejecute y monitore un conector Graph ServiceNow. Complementa las instrucciones generales que se proporcionan en el artículo [Configurar el Graph conector.](configure-connector.md) Si aún no lo ha hecho, lea todo el artículo Configurar su Graph Connector para comprender el proceso de configuración general.

Cada paso del proceso de configuración se muestra a continuación junto con una nota que indica que debe seguir las [](#troubleshooting) instrucciones generales de configuración U otras instrucciones que se aplican solo al conector Graph ServiceNow, incluida la información sobre la solución de problemas y las limitaciones [.](#limitations)  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector Graph en el Centro de administración de Microsoft 365.
Siga las instrucciones generales de configuración.

## <a name="step-2-name-the-connection"></a>Paso 2: Asigne un nombre a la conexión.
Siga las instrucciones generales de configuración.


## <a name="step-3-connection-settings"></a>Paso 3: Conexión Configuración
Para conectarse a los datos de ServiceNow, necesita la dirección URL de instancia **de ServiceNow de su organización.** La dirección URL de instancia de ServiceNow de la organización suele ser similar a **https:// &lt; su-organización-dominio>.service-now.com**. 

Junto con esta dirección URL, necesitará una cuenta de servicio para configurar la conexión **a** ServiceNow, así como para permitir que Búsqueda de Microsoft actualice periódicamente los artículos de conocimientos según la programación de actualización. La cuenta de servicio necesitará acceso de lectura a los siguientes registros de tabla **de ServiceNow** para rastrear correctamente varias entidades.

**Característica** | **Tablas necesarias de acceso de lectura** | **Descripción**
--- | --- | ---
Indexar artículos de conocimientos disponibles para <em>todos</em> | kb_knowledge | Para rastrear artículos de conocimientos
Indexar y admitir permisos de criterios de usuario | kb_uc_can_read_mtom | Quién puede leer esta base de conocimientos
| | kb_uc_can_contribute_mtom | Quién puede contribuir a esta base de conocimientos
| | kb_uc_cannot_read_mtom | Quién puede leer esta base de conocimientos
| | kb_uc_cannot_contribute_mtom | Quién puede contribuir a esta base de conocimientos
| | sys_user | Tabla de usuario de lectura
| | sys_user_has_role | Leer información de roles de los usuarios
| | sys_user_grmember | Leer pertenencia a grupos de usuarios
| | user_criteria | Leer permisos de criterios de usuario
| | kb_knowledge_base | Leer información de knowledge base

Puede crear **y asignar un rol para** la cuenta de servicio que use para conectarse con Búsqueda de Microsoft. [Obtenga información sobre cómo asignar un rol para cuentas de ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html). El acceso de lectura a las tablas se puede asignar en el rol creado. Para obtener información sobre cómo establecer el acceso de lectura a los registros de tabla, vea [Securing Table Records](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls). 


>[!NOTE]
> ServiceNow Graph Connector puede indizar artículos de conocimientos y permisos de criterios de usuario sin scripts avanzados. Si un criterio de usuario contiene un script avanzado, todos los artículos de conocimiento relacionados se ocultarán de los resultados de búsqueda.

Para autenticar y sincronizar contenido de ServiceNow, elija **uno de los tres métodos** admitidos: 
 
- Autenticación básica 
- ServiceNow OAuth (recomendado)
- Azure AD OpenID Conectar

## <a name="step-31-basic-authentication"></a>Paso 3.1: Autenticación básica

Escriba el nombre de usuario y la contraseña de la cuenta de ServiceNow con **el rol de** conocimiento para autenticarse en la instancia.

## <a name="step-32-servicenow-oauth"></a>Paso 3.2: ServiceNow OAuth

Para usar ServiceNow OAuth para la autenticación, un administrador de ServiceNow debe aprovisionar un punto de conexión en la instancia de ServiceNow para que la aplicación Búsqueda de Microsoft pueda tener acceso a él. Para obtener más información, vea [Create an endpoint for clients to access the instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) en la documentación de ServiceNow.

En la tabla siguiente se proporcionan instrucciones sobre cómo rellenar el formulario de creación de extremos:

Field | Descripción | Valor recomendado 
--- | --- | ---
Nombre | Valor único que identifica la aplicación para la que necesita acceso de OAuth. | Búsqueda de Microsoft
Id. de cliente | Un identificador único de solo lectura generado automáticamente para la aplicación. La instancia usa el identificador de cliente cuando solicita un token de acceso. | N/D
Secreto de cliente | Con esta cadena secreta compartida, la instancia de ServiceNow Búsqueda de Microsoft autorizar las comunicaciones entre sí. | Siga los procedimientos recomendados de seguridad tratando el secreto como una contraseña.
Dirección URL de redireccionamiento | Dirección URL de devolución de llamada necesaria a la que redirige el servidor de autorización. | https://gcs.office.com/v1.0/admin/oauth/callback
URL del logotipo | Dirección URL que contiene la imagen del logotipo de la aplicación. | N/D
Activo | Active la casilla para activar el Registro de aplicaciones. | Establecer en activo
Actualizar duración del token | El número de segundos que un token de actualización es válido. De forma predeterminada, los tokens de actualización expiran en 100 días (8.640.000 segundos). | 31.536.000 (1 año)
Duración del token de acceso | El número de segundos que un token de acceso es válido. | 43.200 (12 horas)

Escriba el identificador de cliente y el secreto de cliente para conectarse a la instancia. Después de conectarse, use una credencial de cuenta de ServiceNow para autenticar el permiso para rastrear. La cuenta debe tener al menos un **rol de** conocimiento. Consulte la tabla al principio del paso [3:](#step-3-connection-settings) configuración de conexión para proporcionar acceso de lectura a más registros de tabla de ServiceNow y permisos de criterios de usuario de índice.

## <a name="step-33-azure-ad-openid-connect"></a>Paso 3.3: Azure AD OpenID Conectar

Para usar Azure AD OpenID Conectar para la autenticación, siga los pasos que se indican a continuación.

### <a name="step-331-register-a-new-application-in-azure-active-directory"></a>Paso 3.3.1: Registrar una nueva aplicación en Azure Active Directory

Para obtener información sobre cómo registrar una nueva aplicación en Azure Active Directory, vea [Register an application](/azure/active-directory/develop/quickstart-register-app#register-an-application). Seleccione directorio de organización de inquilino único. Uri de redireccionamiento no es necesario. Después del registro, anote el identificador de aplicación (cliente) y el identificador de directorio (inquilino).

### <a name="step-332-create-a-client-secret"></a>Paso 3.3.2: Crear un secreto de cliente

Para obtener información sobre cómo crear un secreto de cliente, vea [Creating a client secret](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret). Tome nota del secreto de cliente.

### <a name="step-333-retrieve-service-principal-object-identifier"></a>Paso 3.3.3: Recuperar el identificador de objeto de entidad de seguridad de servicio

Siga los pasos para recuperar el identificador de objeto de entidad de seguridad de servicio

1. Ejecute PowerShell.

2. Instale Azure PowerShell mediante el siguiente comando.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Conectar a Azure.

   ```powershell
   Connect-AzAccount
   ```

4. Obtener identificador de objeto de entidad de seguridad de servicio.

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   Reemplace "Id. de aplicación" por identificador de aplicación (cliente) (sin comillas) de la aplicación que registró en el paso 3.a. Tenga en cuenta el valor del objeto ID de la salida de PowerShell. Es el id. de entidad de servicio.

Ahora tiene toda la información necesaria de Azure Portal. En la tabla siguiente se proporciona un resumen rápido de la información.

Propiedad | Descripción 
--- | ---
Id. de directorio (identificador de inquilino) | Identificador único del Azure Active Directory inquilino, desde el paso 3.a.
Id. de aplicación (id. de cliente) | Identificador único de la aplicación registrada en el paso 3.a.
Secreto de cliente | La clave secreta de la aplicación (desde el paso 3.b). Tráela como una contraseña.
Id. de entidad de servicio | Identidad de la aplicación que se ejecuta como servicio. (desde el paso 3.c)

### <a name="step-334-register-servicenow-application"></a>Paso 3.3.4: Registrar la aplicación ServiceNow

La instancia de ServiceNow necesita la siguiente configuración:

1. Registrar una nueva entidad OAuth OIDC. Para obtener información, vea [Create an OAuth OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).

2. En la siguiente tabla se proporcionan instrucciones sobre cómo rellenar el formulario de registro del proveedor de OIDC

   Field | Descripción | Valor recomendado
   --- | --- | ---
   Nombre | Un nombre único que identifica la entidad OAuth OIDC. | Azure AD
   Id. de cliente | El identificador de cliente de la aplicación registrada en el servidor OAuth OIDC de terceros. La instancia usa el identificador de cliente al solicitar un token de acceso. | Id. de aplicación (cliente) del paso 3.a
   Secreto de cliente | El secreto de cliente de la aplicación registrada en el servidor OAuth OIDC de terceros. | Secreto de cliente del paso 3.b

   Todos los demás valores pueden ser predeterminados.

3. En el formulario de registro del proveedor de OIDC, debe agregar una nueva configuración de proveedor de OIDC. Seleccione el icono de búsqueda en el campo Configuración del proveedor *OAuth OIDC* para abrir los registros de las configuraciones de OIDC. Seleccione Nuevo.

4. En la tabla siguiente se proporcionan instrucciones sobre cómo rellenar el formulario de configuración del proveedor de OIDC

   Field | Valor recomendado
   --- | ---
   Proveedor de OIDC |  Azure AD
   URL de metadatos de OIDC | La dirección URL debe tener el formato https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration <br/>Reemplace "tenantID" por el id. de directorio (inquilino) del paso 3.a.
   Duración de la memoria caché de configuración de OIDC |  120
   Application | Global
   Notificación de usuario | sub
   Campo de usuario | Id. de usuario
   Habilitar la comprobación de notificación JTI | Deshabilitado

5. Seleccione Enviar y actualizar el formulario Entidad OAuth OIDC.

### <a name="step-335-create-a-servicenow-account"></a>Paso 3.3.5: Crear una cuenta de ServiceNow

Consulte las instrucciones para crear una cuenta de ServiceNow, [crear un usuario en ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

En la siguiente tabla se proporcionan instrucciones sobre cómo rellenar el registro de la cuenta de usuario de ServiceNow

Field | Valor recomendado
--- | ---
Id. de usuario | Id. de entidad de servicio del paso 3.c
Solo acceso al servicio web | Checked

Todos los demás valores se pueden dejar como predeterminados.

### <a name="step-336-enable-knowledge-role-for-the-servicenow-account"></a>Paso 3.3.6: Habilitar el rol De conocimiento para la cuenta de ServiceNow

Obtenga acceso a la cuenta de ServiceNow que creó con el id. de entidad de seguridad de ServiceNow como id. de usuario y asigne el rol de conocimiento. Puede encontrar instrucciones para asignar un rol a una cuenta de ServiceNow aquí, [asigne un rol a un usuario](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html). Consulte la tabla al principio del paso [3:](#step-3-connection-settings) configuración de conexión para proporcionar acceso de lectura a más registros de tabla de ServiceNow y permisos de criterios de usuario de índice.

Use id. de aplicación como id. de cliente (desde el paso 3.a) y secreto de cliente (desde el paso 3.b) en el Asistente para la configuración del centro de administración para autenticarse en la instancia de ServiceNow con Azure AD OpenID Conectar.

## <a name="step-4-select-properties-and-filter-data"></a>Paso 4: Seleccionar propiedades y filtrar datos

En este paso, puede agregar o quitar las propiedades disponibles del origen de datos de ServiceNow. Microsoft 365 ya ha seleccionado algunas propiedades de forma predeterminada.

Con una cadena de consulta ServiceNow, puede especificar condiciones para sincronizar artículos. Es como una cláusula **Where** en una **instrucción SQL Select.** Por ejemplo, puede elegir indizar solo los artículos publicados y activos. Para obtener información sobre cómo crear su propia cadena de consulta, vea [Generate an encoded query string using a filter](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).

Use el botón de vista previa de resultados para comprobar los valores de ejemplo de las propiedades seleccionadas y el filtro de consulta.

## <a name="step-5-manage-search-permissions"></a>Paso 5: Administrar permisos de búsqueda

El conector servicenow admite permisos de búsqueda visibles **para** todos o solo las personas con acceso a este origen **de datos.** Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización o usuarios que tienen acceso a ellos mediante el permiso de criterios de usuario respectivamente. Si un artículo de conocimientos no está habilitado con criterios de usuario, aparecerá en los resultados de búsqueda de todos los usuarios de la organización.

ServiceNow Graph Connector admite permisos de criterios de usuario predeterminados sin scripts avanzados. Cuando el conector encuentra un criterio de usuario con un script avanzado, todos los datos que usan ese criterio de usuario no aparecerán en los resultados de la búsqueda.

Si elige **Solo** personas con acceso a este origen de datos, deberá elegir si la instancia de ServiceNow tiene usuarios aprovisionados Azure Active Directory (AAD) o usuarios que no son AAD.

>[!NOTE]
>Si elige AAD como el tipo de origen de identidad, asegúrese de asignar la propiedad de origen UserPrincipalName (UPN) a la propiedad de destino de correo electrónico en ServiceNow. Para comprobar o cambiar las asignaciones, vea [Customizing user provisioning attribute-mappings for SaaS applications in Azure Active Directory](/azure/active-directory/app-provisioning/customize-application-attributes).

Si ha elegido "no AAD" para el tipo de identidad, vea Asignar las identidades que no son de [Azure AD](map-non-aad.md) para obtener instrucciones sobre cómo asignar las identidades. 


## <a name="step-6-assign-property-labels"></a>Paso 6: Asignar etiquetas de propiedades

Siga las instrucciones generales de configuración.

## <a name="step-7-manage-schema"></a>Paso 7: Administrar esquema

Siga las instrucciones generales de configuración.

## <a name="step-8-choose-refresh-settings"></a>Paso 8: Elegir la configuración de actualización

Siga las instrucciones generales de configuración.

>[!NOTE]
>En el caso de las identidades, solo se aplicará el rastreo completo programado.

## <a name="step-9-review-connection"></a>Paso 9: Revisar conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).

ServiceNow Graph connector tiene las siguientes limitaciones en su versión más reciente:

Después de publicar la conexión, debe personalizar la página de resultados de búsqueda. Para obtener información sobre cómo personalizar los resultados de búsqueda, [vea Personalizar la página de resultados de búsqueda](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).

## <a name="limitations"></a>Limitaciones
ServiceNow Graph connector tiene las siguientes limitaciones en su versión más reciente:
- La indización de artículos de conocimientos disponibles para todos los usuarios de una organización es una característica disponible en general.
- *Solo las personas con acceso a esta* característica de origen de datos en el paso Administrar permisos de búsqueda están en el canal de lanzamiento dirigido y solo procesa permisos de criterios [de](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) usuario. Cualquier otro tipo de permisos de acceso no se aplicará en los resultados de la búsqueda.
- Los criterios de usuario con scripts avanzados no se admiten en la versión actual. Los artículos de conocimientos con esta restricción de acceso se indizarán con denegar el acceso de todos, es decir, no aparecerán en los resultados de búsqueda a ningún usuario hasta que los admitamos.

## <a name="troubleshooting"></a>Solución de problemas
Después de publicar la conexión, personalizar la página de resultados, puede revisar el estado en la pestaña **Orígenes** de datos en el [Centro de administración.](https://admin.microsoft.com) Para obtener información sobre cómo realizar actualizaciones y eliminaciones, consulte [Manage your connector](manage-connector.md).
Puede encontrar los pasos para solucionar problemas que se ven a continuación.
### <a name="1-unable-to-login-due-to-single-sign-on-enabled-servicenow-instance"></a>1. No se puede iniciar sesión debido a la instancia Sign-On ServiceNow habilitada

Si su organización ha habilitado Single Sign-On (SSO) en ServiceNow, es posible que tenga problemas para iniciar sesión con la cuenta de servicio. Puede abrir el inicio de sesión <em> `login.do` </em> basado en nombre de usuario y contraseña agregando a la dirección URL de la instancia de ServiceNow. Ejemplo. `https://<your-organization-domain>.service-now.com./login.do` 

### <a name="2-unauthorized-or-forbidden-response-to-api-request"></a>2. Respuesta no autorizada o prohibida a la solicitud de API

#### <a name="21-check-table-access-permissions"></a>2.1. Comprobar permisos de acceso a tablas
Si ve una respuesta prohibida o no autorizada en el estado de conexión, compruebe si la cuenta de servicio ha requerido acceso a las tablas mencionadas en el paso [3: configuración de conexión](#step-3-connection-settings). Compruebe si todas las columnas de las tablas tienen acceso de lectura.

#### <a name="22-check-if-servicenow-instance-behind-firewall"></a>2.2. Comprobar si la instancia de ServiceNow está detrás del firewall
Graph Es posible que connector no pueda llegar a la instancia de ServiceNow si está detrás de un firewall de red. Necesitará permitir explícitamente el acceso a Graph connector. Puede encontrar el intervalo de direcciones IP públicas de Graph Connector Service en la tabla siguiente. En función de la región del espacio empresarial, agrégála a la lista blanca de la red de instancia de ServiceNow.

**Entorno** | **Región** | **Range**
--- | --- | ---
PROD | Norteamérica | 52.250.92.252/30, 52.224.250.216/30
PROD | Europa | 20.54.41.208/30, 51.105.159.88/30 
PROD | Asia Pacífico | 52.139.188.212/30, 20.43.146.44/30 

#### <a name="23-access-permissions-not-working-as-expected"></a>2.3. Los permisos de acceso no funcionan como se esperaba
Si observa discrepancias en los permisos de acceso aplicados a los resultados de búsqueda, compruebe el diagrama de flujo de acceso para conocer los criterios de usuario en la administración del acceso a [las bases de conocimiento y los artículos](https://docs.servicenow.com/bundle/rome-servicenow-platform/page/product/knowledge-management/concept/user-access-knowledge.html).

Si tiene otros problemas o desea proporcionar comentarios, escríbanos [aka.ms/TalkToGraphConnectors](https://aka.ms/TalkToGraphConnectors)
