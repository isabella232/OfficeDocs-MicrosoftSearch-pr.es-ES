---
title: Conector de Graph Atlassian jira para Búsqueda de Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de Graph Atlassian Jira para Búsqueda de Microsoft
ms.openlocfilehash: 0b4b1dc0ed1f9e9d3ca57f98dc3878f63e68d510
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "59376136"
---
# <a name="atlassian-jira-graph-connector-preview"></a>Conector de Graph Atlassian Jira (versión preliminar)

El conector de Graph Atlassian Jira permite a la organización indizar los problemas de Jira. Después de configurar el conector y el contenido de índice desde el sitio jira, los usuarios finales pueden buscar esos elementos en Búsqueda de Microsoft.

> [!NOTE]
> Lea el [**artículo Setup for your Graph connector para**](configure-connector.md) comprender las instrucciones generales Graph de configuración de conectores.

Este artículo está para cualquier persona que configure, ejecute y monitore un conector de Graph Atlassian Jira. Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de configuración Graph Atlassian Jira.

>[!IMPORTANT]
>El conector de Graph Atlassian Jira solo admite instancias hospedadas en la nube de Jira. Las versiones de Jira Server y Jira Data Center no son compatibles con este conector.

## <a name="before-you-get-started"></a>Antes de empezar
Debe ser el administrador del inquilino M365 de la organización, así como el administrador del sitio Jira de su organización.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector Graph en el Centro de administración de Microsoft 365
Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión
Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión
Para conectarse al sitio de Jira, use la dirección URL del sitio de Jira. Una dirección URL del sitio en la nube de Jira normalmente tiene el aspecto *de https://<organization_name>.atlassian.net/*. Puede elegir autenticación básica o OAuth 2.0 (recomendado) para autenticarse en el sitio de Jira.

### <a name="basic-auth"></a>Autenticación básica
Escribe el nombre de usuario de tu cuenta (normalmente id. de correo electrónico) y el token de API para autenticar con autenticación básica. Para obtener más información sobre cómo generar un token de API, consulte la documentación de Atlassian sobre cómo administrar tokens de API para su cuenta [atlassiana.](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

### <a name="oauth-20"></a>OAuth 2.0
Registra una aplicación en Atlassian Jira para que Búsqueda de Microsoft aplicación pueda tener acceso a la instancia. Para obtener más información, vea la documentación de soporte técnico de Atlassian sobre cómo [habilitar OAuth 2.0](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-).

Los siguientes pasos proporcionan instrucciones sobre cómo registrar la aplicación:

1. Inicia sesión en la consola de desarrollador de [Atlassian](https://developer.atlassian.com/console/myapps/) con tu cuenta de administrador de Atlassian Jira.
2. Haga clic en `Create` y seleccione `OAuth 2.0 integration`
3. Proporcione un nombre adecuado para la aplicación y cree la nueva aplicación.
4. Navegue desde `Permissions` el panel de navegación a la izquierda. Haga clic `Add` en `Jira platform REST API` . Una vez agregado, haga clic en `Configure` y agregue los siguientes ámbitos : y `View Jira issue data` `Manage Jira global settings` `View user profiles` .
5. Navegue desde `Authorization` el panel de navegación a la izquierda. Agregue la dirección URL de `https://gcs.office.com/v1.0/admin/oauth/callback` devolución de llamada y guarde los cambios.
6. Navegue desde `Settings` el panel de navegación a la izquierda. Se obtiene el `Client ID` y `Secret` de esta página.

Al registrar la aplicación con los detalles anteriores, tendrás el **id. de** cliente y el **secreto**. Complete el paso de configuración de conexión con estos.

### <a name="step-3a-configure-data-select-projects"></a>Paso 3a: Configurar datos: Seleccionar proyectos

Puede elegir la conexión para indizar solo todo el sitio jira o proyectos específicos.

* Si elige indizar todo el sitio jira, se indizarán los problemas de Jira en todos los proyectos del sitio. Los nuevos proyectos y problemas se indizarán durante el siguiente rastreo después de crearse.
* Si elige proyectos individuales, solo se indizarán los problemas de Jira en esos proyectos.

Es posible que elija filtrar los problemas de Jira que se indizarán de 2 maneras.
* Especifique el **período de tiempo modificado del problema**. Esto solo indizará los problemas de Jira que se crean o modifican en el período de tiempo seleccionado de forma **gradual** en función del rastreo actual.
* Especifique el **archivo JQL**. Esto solo indizará los problemas de Jira que se devuelven después de filtrar en función del lenguaje de consulta Jira (JQL) proporcionado. Para obtener más información sobre el uso de JQL, consulte Documentación de soporte técnico de Atlassian sobre cómo usar la [búsqueda avanzada con jira Query Language](https://support.atlassian.com/jira-service-management-cloud/docs/use-advanced-search-with-jira-query-language-jql/)

> [!TIP]
> Puede usar el filtro JQL para indizar solo tipos de problemas de Jira específicos mediante "*issueType in (Bug,Improvement)*"

### <a name="step-3b-configure-data-select-properties"></a>Paso 3b: Configurar datos: Seleccionar propiedades

Seleccione los campos que desea que la conexión indexe y obtenga una vista previa de los datos de estos campos antes de continuar. Algunos campos ya están seleccionados de forma predeterminada y no se pueden quitar.

El conector de Graph Atlassian Jira puede indizar tanto los campos de problema predeterminados como los campos de problemas creados personalizados.

> [!NOTE]
> Si un campo creado personalizado seleccionado no está presente en algunos tipos de problema jira, el campo se ingerirá como *NULL* (en blanco).

## <a name="step-4-manage-search-permissions"></a>Paso 4: Administrar permisos de búsqueda

El conector de Graph Atlassian jira admite  **** permisos de búsqueda visibles para todos o solo las personas con **acceso a este origen de datos**. Si elige **Todos, los** datos indizados aparecerán en los resultados de la búsqueda para todos los usuarios. Si elige Solo **personas con acceso** a este origen de datos, los datos indizados aparecerán en los resultados de búsqueda para los usuarios que tengan acceso a ellos. En Atlassian Jira, los permisos de seguridad se definen mediante esquemas de permisos de proyecto que contienen grupos de nivel de sitio y roles de proyecto. La seguridad de nivel de problema también se puede definir mediante esquemas de permisos de nivel de problema.

Si elige **Solo** personas con acceso a este origen de datos, deberá elegir si el sitio jira tiene usuarios aprovisionados Azure Active Directory (AAD) o usuarios que no son AAD.

Para identificar qué opción es adecuada para su organización:

1. Elija la **opción AAD** si el identificador  de correo electrónico de los usuarios de Jira es el mismo que el UserPrincipalName (UPN) de los usuarios de AAD.
2. Elija la **opción No AAD** si el identificador  de correo electrónico de los usuarios de Jira es diferente del UserPrincipalName (UPN) de los usuarios de AAD. 

>[!NOTE]
> * Si elige AAD como el tipo de origen de identidad, el conector asigna los id. de correo electrónico de los usuarios obtenidos de Jira directamente a la propiedad UPN de AAD.
> * Si eligió "Non-AAD" para el tipo de identidad, consulte [Map your non-Azure AD Identities](map-non-aad.md) para obtener instrucciones sobre cómo asignar las identidades. Puede usar esta opción para proporcionar la expresión regular de asignación de Id. de correo electrónico a UPN.

## <a name="step-5-assign-property-labels"></a>Paso 5: Asignar etiquetas de propiedades

Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-6-manage-schema"></a>Paso 6: Administrar esquema

Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-7-choose-refresh-settings"></a>Paso 7: Elegir la configuración de actualización

El conector de Graph Atlassian Jira admite programaciones de actualización para rastreos completos e incrementales.
La programación recomendada es de una hora para un rastreo incremental y un día para un rastreo completo.

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="troubleshooting"></a>Solución de problemas
Debajo hay una lista de errores comunes observados al configurar el conector y sus posibles razones.

| Paso de configuración | Mensaje de error | Posibles motivos |
| ------------ | ------------ | ------------ |
| Configuración de conexión | La solicitud es incorrecta o tiene un formato no válido. | Dirección URL de sitio de Jira incorrecta |
| Configuración de conexión | No se puede llegar al servicio en la nube de Jira para el sitio de Jira. | Dirección URL de sitio de Jira incorrecta |
| Configuración de conexión | El cliente no tiene permiso para realizar la acción. | Token de API no válido proporcionado para autenticación básica |


## <a name="limitations"></a>Limitaciones
Las siguientes son las limitaciones conocidas del conector de Graph Atlassian:
* No se admiten las versiones de Jira Server y Data Center.