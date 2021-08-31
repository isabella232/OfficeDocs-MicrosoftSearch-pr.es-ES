---
title: Azure DevOps Graph conector para Búsqueda de Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector Azure DevOps Graph para Búsqueda de Microsoft
ms.openlocfilehash: 9c3c5d994f8470cdd70dc07445ede2c74f688383
ms.sourcegitcommit: be5dcc7005447d6139e39d86211c7ec4cd5dd907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2021
ms.locfileid: "58639574"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Azure DevOps Graph (versión preliminar)

El Azure DevOps Graph permite a la organización indizar elementos de trabajo en su instancia del servicio Azure DevOps trabajo. Después de configurar el conector y el contenido de índice Azure DevOps, los usuarios finales pueden buscar esos elementos en Búsqueda de Microsoft.

> [!NOTE]
> Lea el [**artículo Setup for your Graph connector para**](configure-connector.md) comprender las instrucciones generales Graph de configuración de conectores.

Este artículo está para cualquier persona que configure, ejecute y monitore un Azure DevOps Graph conector. Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al Azure DevOps Graph conector.

>[!IMPORTANT]
>El Azure DevOps solo admite el Azure DevOps en la nube. Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 y TFS 2013 no son compatibles con este conector.

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

Para conectarse a la instancia Azure DevOps, necesita [](/azure/devops/organizations/accounts/create-organization) el nombre Azure DevOps organización, su identificador de aplicación y el secreto de cliente para la autenticación de OAuth.

### <a name="register-an-app"></a>Registrar una aplicación

Registra una aplicación en Azure DevOps para que Búsqueda de Microsoft la aplicación pueda tener acceso a la instancia. Para obtener más información, consulta Azure DevOps documentación sobre cómo [registrar una aplicación](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).

En la siguiente tabla se proporcionan instrucciones sobre cómo rellenar el formulario de registro de la aplicación:

Campos obligatorios | Descripción | Valor recomendado
--- | --- | ---
| Nombre de la compañía         | El nombre de su empresa. | Usar un valor adecuado   |
| Nombre de la aplicación     | Valor único que identifica la aplicación que está autorizando.    | Búsqueda de Microsoft     |
| Sitio web de la aplicación  | La dirección URL de la aplicación que solicitará acceso a la instancia Azure DevOps durante la instalación del conector. (Obligatorio).  | https://<span>gcs.office.</span> com/
| Url de devolución de llamada de autorización        | Dirección URL de devolución de llamada necesaria a la que redirige el servidor de autorización. | https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback|
| Ámbitos autorizados | El ámbito de acceso de la aplicación | Seleccione los siguientes ámbitos: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read), Analytics (read)|

>[!IMPORTANT]
>Los ámbitos autorizados que selecciones para la aplicación deben coincidir exactamente con los ámbitos indicados anteriormente. Si omite uno de los ámbitos autorizados de la lista o agrega otro ámbito, se producirá un error en la autorización.

Al registrar la aplicación con los detalles anteriores, tendrás  el identificador de la aplicación y el secreto de cliente que se usarán para configurar el conector. 

>[!NOTE]
>Para revocar el acceso a cualquier aplicación registrada en Azure DevOps, ve a Configuración de usuario en la parte superior derecha de la Azure DevOps instancia. Seleccione Perfil y, a continuación, seleccione Autorizaciones en la sección Seguridad del panel lateral. Mantenga el mouse sobre una aplicación OAuth autorizada para ver el botón Revocar en la esquina de los detalles de la aplicación.

### <a name="connection-settings"></a>Configuración de conexión

Después de registrar la aplicación Búsqueda de Microsoft con Azure DevOps, puedes completar el paso de configuración de conexión. Escriba el nombre de la organización, el identificador de la aplicación y el secreto de cliente.

![Aplicación de conexión Configuración.](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>Configurar datos: seleccionar proyectos y campos

Puede elegir la conexión para indizar toda la organización o proyectos específicos.

Si elige indizar toda la organización, los elementos de todos los proyectos de la organización se indizarán. Los nuevos proyectos y elementos se indizarán durante el siguiente rastreo después de su creación.

Si elige proyectos individuales, solo se indizarán los elementos de trabajo de esos proyectos.

![Configurar datos.](media/ADO_Configure_data.png)

A continuación, seleccione los campos que desea que la conexión indexe y obtenga una vista previa de los datos de estos campos antes de continuar.

![Elija propiedades.](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>Paso 4: Administrar permisos de búsqueda

El Azure DevOps admite permisos de búsqueda visibles para solo personas con  **acceso a este origen de datos** o **todos**. Si elige Solo personas con acceso a este origen de **datos,** los datos indizados aparecerán en los resultados de búsqueda para los usuarios que tengan acceso a ellos en función de los permisos para usuarios o grupos en el nivel de ruta de acceso de la organización, Project o Área en Azure DevOps. Si elige **Todos, los** datos indizados aparecerán en los resultados de la búsqueda para todos los usuarios.

## <a name="step-5-assign-property-labels"></a>Paso 5: Asignar etiquetas de propiedades

Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-6-manage-schema"></a>Paso 6: Administrar esquema

Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-7-choose-refresh-settings"></a>Paso 7: Elegir la configuración de actualización

El Azure DevOps admite programaciones de actualización para rastreos completos e incrementales.
La programación recomendada es de una hora para un rastreo incremental y un día para un rastreo completo.

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).

>[!TIP]
>**Tipo de resultado predeterminado**
>* El Azure DevOps registra automáticamente un tipo [de resultado](./customize-search-page.md#step-2-create-result-types) una vez que se publica el conector. El tipo de resultado usa un diseño de resultados generado [dinámicamente](./customize-results-layout.md) en función de los campos seleccionados en el paso 3. 
>* Para administrar el tipo de resultado, vaya a [**Tipos de resultados**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) en el [Centro de administración de Microsoft 365](https://admin.microsoft.com). El tipo de resultado predeterminado se denominará `ConnectionId` "Predeterminado". Por ejemplo, si el identificador de conexión es , el diseño `AzureDevOps` de resultados se denominará: "AzureDevOpsDefault"
>* Además, puede elegir crear su propio tipo de resultado si es necesario.

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="troubleshooting"></a>Solución de problemas
A continuación se muestra un error común observado al configurar el conector y su posible motivo.

| Paso de configuración | Mensaje de error | Posibles motivos |
| ------------ | ------------ | ------------ |
|  | `The account associated with the connector doesn't have permission to access the item.` | La aplicación registrada no tiene ninguno de los ámbitos OAuth necesarios. (Nota: el 31/8/2021 se introdujo un nuevo requisito de ámbito de OAuth "Analytics:read")  |

<!---## Limitations-->
<!---Insert limitations for this data source-->