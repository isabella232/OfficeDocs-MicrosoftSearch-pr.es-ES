---
title: Conector de Graph nube de confluencia para Búsqueda de Microsoft
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de Confluence Cloud Graph para Búsqueda de Microsoft
ms.openlocfilehash: baf6139257c8bf8e40bc997e2a408efb4fc2549f
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973532"
---
<!---Previous ms.author: kam1 --->

# <a name="confluence-cloud-graph-connector-preview"></a>Conector de confluencia Graph nube (versión preliminar)

Confluence Cloud Graph connector permite a la organización indizar el contenido de Confluencia. Después de configurar los datos de conector e índice desde el sitio de Confluencia, los usuarios finales pueden buscar ese contenido en Búsqueda de Microsoft.

>[!NOTE]
>Confluence Cloud Graph Connector está en versión preliminar. Si desea obtener acceso anticipado para probarlo, regístrese con [<b> este formulario </b>](https://forms.office.com/r/duLxv8Nf8U).  

Este artículo está para Microsoft 365 administradores o cualquier persona que configure, ejecute y monitore un conector de confluencia Graph nube. Complementa las instrucciones generales que se proporcionan en el artículo [Configurar el Graph conector.](configure-connector.md) Si aún no lo ha hecho, lea todo el artículo Configurar su Graph Connector para comprender el proceso de configuración general.

Cada paso del proceso de configuración se muestra a continuación junto con una nota que indica que debe seguir las instrucciones [](#troubleshooting) generales de configuración U otras instrucciones que se aplican solo al conector de Confluence Cloud Graph, incluida la información sobre solución de problemas y limitaciones [.](#limitations)


## <a name="before-you-get-started"></a>Antes de empezar
Debe ser el administrador del inquilino M365 de la organización, así como el administrador del sitio de confluencia de su organización.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector Graph en el Centro de administración de Microsoft 365
Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión
Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión
Para conectarse al sitio de Confluencia, use la dirección URL del sitio. Normalmente, una dirección URL de sitio en la nube de Confluencia tiene el aspecto *de https://<organization_name>.atlassian.net/*. Puede elegir autenticación básica o OAuth 2.0 (recomendado) para autenticarse en el sitio de Confluencia.

### <a name="basic-auth"></a>Autenticación básica
Escribe el nombre de usuario de tu cuenta (normalmente id. de correo electrónico) y el token de API para autenticar con autenticación básica. Para obtener más información sobre cómo generar un token de API, consulte la documentación de Atlassian sobre cómo administrar tokens de API para su cuenta [atlassiana.](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

### <a name="oauth-20"></a>OAuth 2.0
Registra una aplicación en Confluence Cloud para que Búsqueda de Microsoft la aplicación pueda tener acceso a la instancia. Para obtener más información, vea la documentación de soporte técnico de Atlassian sobre cómo [habilitar OAuth 2.0](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-).

Los siguientes pasos proporcionan instrucciones sobre cómo registrar la aplicación:

1. Inicia sesión en la [consola de desarrolladores de Atlassian](https://developer.atlassian.com/console/myapps/) con tu cuenta de administrador de Confluencia atlassiana.
2. Haga clic en `Create` y seleccione `OAuth 2.0 integration`
3. Proporcione un nombre adecuado para la aplicación y cree la nueva aplicación.
4. Navegue desde `Permissions` el panel de navegación a la izquierda. Haga clic `Add` en `Confluence API` . Una vez agregado, haga clic en `Configure` y agregue los siguientes ámbitos - , , , , `Read Confluence space summary` , y `Read Confluence content properties` `Read Confluence detailed content` `Read Confluence content summary` `Read content permission in Confluence` `Read user` `Read user groups` `Search Confluence content and space summaries` .
5. Navegue desde `Authorization` el panel de navegación a la izquierda. Agregue la dirección URL de `https://gcs.office.com/v1.0/admin/oauth/callback` devolución de llamada y guarde los cambios.
6. Navegue desde `Settings` el panel de navegación a la izquierda. Se obtiene el `Client ID` y `Secret` de esta página.

Al registrar la aplicación con los detalles anteriores, tendrás el **id. de** cliente y el **secreto**. Complete el paso de configuración de conexión con estos.

## <a name="step-4-select-properties-and-filter-data"></a>Paso 4: Seleccionar propiedades y filtrar datos

En este paso, puede agregar o quitar las propiedades disponibles del origen de datos de Confluence. Microsoft 365 ya ha seleccionado algunas propiedades de forma predeterminada.

Con una cadena de lenguaje de consulta de confluencia (CQL), puede especificar condiciones para sincronizar páginas. Es como una cláusula **Where** en una **instrucción SQL Select.** Por ejemplo, puede elegir indizar solo las páginas modificadas en los últimos dos años. Para obtener información sobre cómo crear su propia cadena de consulta, vea [Búsqueda avanzada con CQL](https://developer.atlassian.com/server/confluence/advanced-searching-using-cql/). De forma predeterminada, el conector indizará todos los blogs y páginas.

Use el botón de vista previa de resultados para comprobar los valores de ejemplo de las propiedades seleccionadas y la cadena CQL.

## <a name="step-5-manage-search-permissions"></a>Paso 5: Administrar permisos de búsqueda

Confluence Cloud Graph connector supports search permissions visible to  **Everyone** or **Only people with access to this data source**. Si elige **Todos, los** datos indizados aparecerán en los resultados de la búsqueda para todos los usuarios. Si elige Solo **personas con acceso** a este origen de datos, los datos indizados aparecerán en los resultados de búsqueda para los usuarios que tengan acceso a ellos.

En Confluence Cloud, los permisos de seguridad para usuarios y grupos se definen mediante permisos de espacio y restricciones de página. Confluence Cloud Graph Connector aplica permisos de espacio si no hay restricciones de página. Las restricciones de nivel de página, si están presentes, tendrán prioridad sobre los permisos de espacio.

Si elige **Solo** personas con acceso a este origen de datos, deberá elegir si el sitio de Confluencia tiene usuarios aprovisionados Azure Active Directory (AAD) o usuarios que no son AAD.

Para identificar qué opción es adecuada para su organización:

1. Elija la **opción AAD** si el identificador  de correo electrónico de los usuarios de Confluence es el mismo que el UserPrincipalName (UPN) de los usuarios de AAD.
2. Elija la **opción No AAD** si el identificador  de correo electrónico de los usuarios de Confluence es diferente del UserPrincipalName (UPN) de los usuarios de AAD. 

>[!NOTE]
> * Si elige AAD como el tipo de origen de identidad, el conector asigna los id. de correo electrónico de los usuarios obtenidos de Confluencia directamente a la propiedad UPN de AAD.
> * Si eligió "Non-AAD" para el tipo de identidad, consulte [Map your non-Azure AD Identities](map-non-aad.md) para obtener instrucciones sobre cómo asignar las identidades. Puede usar esta opción para proporcionar la expresión regular de asignación de Id. de correo electrónico a UPN.

## <a name="step-6-assign-property-labels"></a>Paso 6: Asignar etiquetas de propiedades

Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-7-manage-schema"></a>Paso 7: Administrar esquema

Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-8-choose-refresh-settings"></a>Paso 8: Elegir la configuración de actualización

Siga las instrucciones [generales de configuración](./configure-connector.md).

>[!NOTE]
>Para las actualizaciones de permisos de acceso, solo se aplicará el rastreo completo programado.

## <a name="step-9-review-connection"></a>Paso 9: Revisar conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).

Después de publicar la conexión, debe personalizar la página de resultados de búsqueda. Para obtener información sobre cómo personalizar los resultados de búsqueda, [vea Personalizar la página de resultados de búsqueda](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).

## <a name="troubleshooting"></a>Solución de problemas
Debajo hay una lista de errores comunes observados al configurar el conector y sus posibles razones.

| Paso de configuración | Mensaje de error | Posibles motivos |
| ------------ | ------------ | ------------ |
| Configuración de conexión | La solicitud es incorrecta o tiene un formato no válido. | Dirección URL de sitio de Confluencia incorrecta |
| Configuración de conexión | No se puede llegar al servicio en la nube confluencia para el sitio de Confluencia. | Dirección URL de sitio de Confluencia incorrecta |
| Configuración de conexión | El cliente no tiene permiso para realizar la acción. | Token de API no válido proporcionado para autenticación básica |
| Seleccionar propiedades | Sin mensaje de error ni resultados de vista previa | Compruebe si la consulta CQL es válida |

## <a name="limitations"></a>Limitaciones
Confluence Cloud Graph connector tiene las siguientes limitaciones conocidas en su versión más reciente:

- Confluence Cloud Connector no indiza los archivos adjuntos y los comentarios.
- Las implementaciones del servidor de indización y del centro de datos se liberarán como un conector independiente.