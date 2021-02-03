---
title: Conector de ServiceNow Graph para Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de ServiceNow Graph para Microsoft Search
ms.openlocfilehash: d1fdfb5f1aec5091fd526152de2bdc86932cfdb9
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084897"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

El conector de ServiceNow Graph permite a su organización indizar artículos basados en conocimientos visibles para los usuarios según los permisos de criterios de usuario de su organización. Después de configurar el conector y el contenido de índice de ServiceNow, los usuarios pueden buscar los artículos desde cualquier cliente de Microsoft Search.

> [!NOTE]
> Lea el [**artículo sobre el programa de instalación del conector de Graph**](configure-connector.md) para comprender el proceso de configuración general de los conectores de Graph.

Este artículo está dirigido a cualquier persona que configure, ejecute y monitore un conector de ServiceNow Graph. Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de ServiceNow Graph. En este artículo también se incluye información sobre [la solución de problemas](#troubleshooting) y las [limitaciones.](#limitations)
  
## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a>Paso 3: Configuración de conexión

Para conectarse a los datos de ServiceNow, use las credenciales de la dirección URL de instancia **de ServiceNow** de su organización para esta cuenta, el identificador de cliente y el secreto de cliente para la autenticación de OAuth.  

La dirección URL de instancia **de ServiceNow** de la organización suele ser similar a **https:// &lt; dominio-organización>.service-now.com**. Junto con esta dirección URL, necesita una cuenta para configurar la conexión a ServiceNow y para permitir que Microsoft Search actualice los artículos de ServiceNow en función de la programación de actualización. La cuenta debe tener al menos un <em>rol de</em> conocimiento. [Obtenga información sobre cómo asignar un rol para las cuentas de ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

>[!NOTE]
>Si desea rastrear identidades de usuario y grupo para respetar los permisos de acceso de los artículos de conocimientos en los resultados de Búsqueda de Microsoft, la cuenta debe tener acceso para leer los siguientes registros de tabla en ServiceNow:
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> Puede crear y asignar un rol para la cuenta que usa para conectarse con Microsoft Search. El acceso de lectura a las tablas se puede asignar en ese rol. Para obtener información sobre cómo establecer el acceso de lectura a los registros de tabla, vea [Protección de registros de tabla](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls).

Para autenticar y sincronizar contenido de ServiceNow, elija **uno de los tres métodos** admitidos:

1. Autenticación básica
1. ServiceNow OAuth (recomendado)
1. Azure AD OpenID Connect

### <a name="basic-authentication"></a>Autenticación básica

Escribe el nombre de usuario y la contraseña de la cuenta ServiceNow con el **rol de** conocimiento para autenticar la instancia.

### <a name="servicenow-oauth"></a>ServiceNow OAuth

Para usar ServiceNow OAuth para la autenticación, aprovisiona un punto de conexión en la instancia de ServiceNow. La aplicación de Búsqueda de Microsoft la usará para tener acceso a la instancia. Para obtener más información, consulte [Crear un punto de conexión para que los clientes obtengan](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) acceso a la instancia en la documentación de ServiceNow.

En la tabla siguiente se proporcionan instrucciones sobre cómo rellenar el formulario de creación de extremos:

Field | Descripción | Valor recomendado 
--- | --- | ---
Nombre | Valor único que identifica la aplicación para la que necesita acceso de OAuth. | Búsqueda de Microsoft
Identificador de cliente | Un identificador único generado automáticamente de solo lectura para la aplicación. La instancia usa el identificador de cliente cuando solicita un token de acceso. | N/D
Secreto de cliente | Con esta cadena secreta compartida, la instancia de ServiceNow y Microsoft Search autorizan las comunicaciones entre sí. | Siga los procedimientos recomendados de seguridad mediante el tratamiento del secreto como una contraseña.
Dirección URL de redireccionamiento | Dirección URL de devolución de llamada necesaria a la que redirige el servidor de autorización. | https://gcs.office.com/v1.0/admin/oauth/callback
Dirección URL del logotipo | Dirección URL que contiene la imagen del logotipo de la aplicación. | N/D
Activo | Active la casilla para activar el Registro de aplicaciones. | Establecer en activo
Actualizar la vida útil del token | El número de segundos que un token de actualización es válido. De forma predeterminada, los tokens de actualización expiran en 100 días (8.640.000 segundos). | 31.536.000 (1 año)
Duración del token de acceso | El número de segundos que un token de acceso es válido. | 43.200 (12 horas)

Escriba el identificador de cliente y el secreto de cliente para conectarse a la instancia. Después de conectarse, use una credencial de cuenta de ServiceNow para autenticar el permiso de rastreo. La cuenta debe tener al menos un **rol de** conocimiento.

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

Para usar Azure AD OpenID Connect para la autenticación, siga los pasos siguientes.

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>Paso 3.a: Registrar una nueva aplicación en Azure Active Directory

Para obtener información sobre cómo registrar una nueva aplicación en Azure Active Directory, vea [Registrar una aplicación.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application) Seleccione el directorio de la organización de un solo inquilino. El URI de redireccionamiento no es necesario. Después del registro, anote el id. de aplicación (cliente) y el id. de directorio (inquilino).

## <a name="step-3b-create-a-client-secret"></a>Paso 3.b: Crear un secreto de cliente

Para obtener información sobre cómo crear un secreto de cliente, vea [Crear un secreto de cliente.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) Tome nota del secreto de cliente.

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>Paso 3.c: Recuperar el identificador de objeto de entidad de servicio

Siga los pasos para recuperar el identificador de objeto de entidad de servicio

1. Ejecute PowerShell.

2. Instale Azure PowerShell con el siguiente comando.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Conéctese a Azure.

   ```powershell
   Connect-AzAccount
   ```

4. Obtener el identificador de objeto de entidad de servicio.

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   Reemplace "Application-ID" por el identificador de aplicación (cliente) (sin comillas) de la aplicación que registró en el paso 3.a. Tenga en cuenta el valor del objeto ID de los resultados de PowerShell. Es el id. de entidad de servicio.

Ahora tiene toda la información necesaria de Azure Portal. En la tabla siguiente se proporciona un resumen rápido de la información.

Propiedad | Descripción 
--- | ---
Id. de directorio (id. de inquilino) | Identificador único del inquilino de Azure Active Directory, en el paso 3.a.
Id. de aplicación (id. de cliente) | Identificador único de la aplicación registrada en el paso 3.a.
Secreto de cliente | La clave secreta de la aplicación (del paso 3.b). Tratarlo como una contraseña.
Id. de entidad de servicio | Identidad de la aplicación que se ejecuta como servicio. (del paso 3.c)

## <a name="step-3d-register-servicenow-application"></a>Paso 3.d: Registrar la aplicación ServiceNow

La instancia de ServiceNow necesita la siguiente configuración:

1. Registrar una nueva entidad OAuth OIDC. Para obtener información, [vea Crear un proveedor OAuth OIDC](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).

2. En la tabla siguiente se proporcionan instrucciones sobre cómo rellenar el formulario de registro del proveedor OIDC

   Field | Descripción | Valor recomendado
   --- | --- | ---
   Nombre | Nombre único que identifica la entidad OAuth OIDC. | Azure AD
   Identificador de cliente | El identificador de cliente de la aplicación registrada en el servidor OAuth OIDC de terceros. La instancia usa el identificador de cliente al solicitar un token de acceso. | Id. de aplicación (cliente) del paso 3.a
   Secreto de cliente | El secreto de cliente de la aplicación registrada en el servidor OAuth OIDC de terceros. | Secreto de cliente del paso 3.b

   Todos los demás valores pueden ser predeterminados.

3. En el formulario de registro del proveedor OIDC, debe agregar una nueva configuración de proveedor OIDC. Seleccione el icono de búsqueda en el campo Configuración del proveedor *OAuth OIDC* para abrir los registros de las configuraciones de OIDC. Seleccione Nuevo.

4. En la tabla siguiente se proporcionan instrucciones sobre cómo rellenar el formulario de configuración del proveedor OIDC

   Field | Valor recomendado
   --- | ---
   Proveedor OIDC |  Azure AD
   Dirección URL de metadatos de OIDC | La dirección URL debe tener el formato https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration <br/>Reemplace "tenantID" por el id. de directorio (inquilino) del paso 3.a.
   Duración de la memoria caché de configuración de OIDC |  120
   Aplicación | Global
   Notificación de usuario | sub
   Campo de usuario | Id. de usuario
   Habilitar la comprobación de notificación JTI | Deshabilitado

5. Seleccione Enviar y actualizar el formulario De entidad OAuth OIDC.

## <a name="step-3e-create-a-servicenow-account"></a>Paso 3.e: Crear una cuenta de ServiceNow

Consulte las instrucciones para crear una cuenta de ServiceNow, [crear un usuario en ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

En la tabla siguiente se proporcionan instrucciones sobre cómo rellenar el registro de la cuenta de usuario ServiceNow

Field | Valor recomendado
--- | ---
Id. de usuario | Identificador de entidad de seguridad de servicio del paso 3.c
Solo acceso al servicio web | Checked

Todos los demás valores se pueden dejar en el valor predeterminado.

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a>Paso 3.f: Habilitar el rol De conocimiento para la cuenta ServiceNow

Obtenga acceso a la cuenta de ServiceNow que creó con el id. de entidad de seguridad de ServiceNow como id. de usuario y asigne el rol de conocimiento. Puede encontrar instrucciones para asignar un rol a una cuenta de ServiceNow aquí: asignar [un rol a un usuario.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

Use el Id. de aplicación como id. de cliente del paso 3.a y el secreto de cliente del paso 3.b para autenticarse en la instancia de ServiceNow con Azure AD OpenID Connect.

## <a name="step-4-select-properties-and-filter-data"></a>Paso 4: Seleccionar propiedades y filtrar datos

En este paso, puede agregar o quitar propiedades disponibles del origen de datos ServiceNow. Microsoft 365 ya ha seleccionado algunas propiedades de forma predeterminada.

Con una cadena de consulta ServiceNow, puede especificar condiciones para sincronizar artículos. Es como una cláusula **Where** en una **instrucción SQL Select.** Por ejemplo, puede optar por indizar solo los artículos que están publicados y activos. Para obtener información sobre cómo crear su propia cadena de consulta, vea Generar una cadena [de consulta codificada mediante un filtro.](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)

Use el botón de vista previa de resultados para comprobar los valores de ejemplo de las propiedades seleccionadas y el filtro de consulta.

## <a name="step-5-manage-search-permissions"></a>Paso 5: Administrar permisos de búsqueda

El conector ServiceNow admite permisos de búsqueda visibles **para** todos o solo las personas con acceso a este origen **de datos.** Los datos indizados aparecen en los resultados de la búsqueda y son visibles para los usuarios de la organización que tienen acceso a ellos respectivamente. ServiceNow Connector admite permisos de criterios de usuario predeterminados sin scripts avanzados. Cuando el conector encuentra un criterio de usuario con un script avanzado, todos los datos que usan ese criterio de usuario no se mostrarán en los resultados de la búsqueda.

Si selecciona Solo las personas con acceso a este origen de **datos,** debe elegir si la instancia de ServiceNow tiene usuarios aprovisionados de Azure Active Directory (AAD) o usuarios que no son de AAD.

>[!NOTE]
>El conector ServiceNow está en **versión preliminar** si elige solo las personas con acceso a este origen **de datos.**

>[!NOTE]
>Si elige AAD como el tipo de origen de identidad, asegúrese de asignar la propiedad de origen UPN a la propiedad de destino de correo electrónico en ServiceNow. Para comprobar o cambiar las asignaciones, consulte Personalización de asignaciones de atributos de aprovisionamiento de usuarios para aplicaciones [SaaS en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes)

Si decidiste ingerir una ACL de la instancia de ServiceNow y seleccionaste "no AAD" para el tipo de identidad, consulta Asignar las identidades que no son de [Azure AD](map-non-aad.md) para obtener instrucciones sobre cómo asignar las identidades.

## <a name="step-6-assign-property-labels"></a>Paso 6: Asignar etiquetas de propiedad

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>Paso 7: Administrar esquema

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>Paso 8: Elegir la configuración de actualización

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
>Para las identidades, solo se aplicará el rastreo completo programado.

## <a name="step-9-review-connection"></a>Paso 9: Revisar la conexión

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>Solución de problemas

Después de publicar la conexión, personalizar la página de **resultados,** puede revisar el estado en la pestaña Conectores en el [centro de administración.](https://admin.microsoft.com) Para obtener información sobre cómo realizar actualizaciones y eliminaciones, vea [Administrar el conector.](manage-connector.md)

## <a name="limitations"></a>Limitaciones

El conector de ServiceNow Graph tiene las siguientes limitaciones en su versión más reciente:

- La indización de artículos de conocimientos disponibles para todos los miembros de una organización es una característica disponible en general.
- *Solo las personas con acceso a esta característica de origen* de datos en el paso Administrar permisos de búsqueda están en versión preliminar y solo procesa permisos de criterios [de](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) usuario. No se aplicará ningún otro tipo de permiso de acceso en los resultados de la búsqueda.
- Los criterios de usuario con scripts avanzados no se admiten en la versión preliminar actual. Los artículos de conocimientos con una restricción de acceso se indizarán con denegar el acceso de todos los usuarios y no aparecerán en los resultados de búsqueda para ningún usuario hasta que los admitamos.
