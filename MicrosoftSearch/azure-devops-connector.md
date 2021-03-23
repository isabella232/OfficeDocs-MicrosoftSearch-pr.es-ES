---
title: Conector de Azure DevOps Graph para Microsoft Search
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
description: Configurar el conector de Azure DevOps Graph para Microsoft Search
ms.openlocfilehash: 9352f619e0a48bc2dac8441107f87f725211ab13
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031318"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Conector de Azure DevOps Graph (versión preliminar)

El conector de Azure DevOps Graph permite a la organización indizar elementos de trabajo en su instancia del servicio DevOps de Azure. Después de configurar el conector y el contenido de índice de Azure DevOps, los usuarios finales pueden buscar esos elementos en Microsoft Search.

> [!NOTE]
> Lea el [**artículo Setup for your Graph connector para**](configure-connector.md) comprender las instrucciones generales de configuración de los conectores de Graph.

Este artículo está dirigido a cualquier persona que configure, ejecute y monitore un conector de Azure DevOps Graph. Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de Azure DevOps Graph.

>[!IMPORTANT]
>El conector de DevOps de Azure solo admite el servicio en la nube de Azure DevOps. Este conector no admite Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 y TFS 2013.

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

Para conectarse a la instancia de Azure DevOps, necesita el nombre de la organización de Azure [DevOps,](/azure/devops/organizations/accounts/create-organization) su identificador de aplicación y el secreto de cliente para la autenticación de OAuth.

### <a name="register-an-app"></a>Registrar una aplicación

Registra una aplicación en Azure DevOps para que la aplicación de Microsoft Search pueda tener acceso a la instancia. Para obtener más información, vea la documentación de Azure DevOps sobre cómo [registrar una aplicación.](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)

En la siguiente tabla se proporcionan instrucciones sobre cómo rellenar el formulario de registro de la aplicación:

Campos obligatorios | Descripción | Valor recomendado
--- | --- | ---
| Nombre de la compañía         | El nombre de su empresa. | Usar un valor adecuado   |
| Nombre de la aplicación     | Valor único que identifica la aplicación que está autorizando.    | Búsqueda de Microsoft     |
| Sitio web de la aplicación  | La dirección URL de la aplicación que solicitará acceso a la instancia de Azure DevOps durante la instalación del conector. (Obligatorio).  | https://<span>gcs.office.</span> com/
| Url de devolución de llamada de autorización        | Dirección URL de devolución de llamada necesaria a la que redirige el servidor de autorización. | https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback|
| Ámbitos autorizados | El ámbito de acceso de la aplicación | Seleccione los siguientes ámbitos: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)|

Al registrar la aplicación con los detalles anteriores, tendrás  el identificador de la aplicación y el secreto de cliente que se usarán para configurar el conector. 

>[!NOTE]
>Para revocar el acceso a cualquier aplicación registrada en Azure DevOps, vaya a Configuración de usuario en la parte superior derecha de la instancia de Azure DevOps. Seleccione Perfil y, a continuación, seleccione Autorizaciones en la sección Seguridad del panel lateral. Mantenga el mouse sobre una aplicación OAuth autorizada para ver el botón Revocar en la esquina de los detalles de la aplicación.

### <a name="connection-settings"></a>Configuración de conexión

Después de registrar la aplicación de Microsoft Search con Azure DevOps, puedes completar el paso de configuración de conexión. Escriba el nombre de la organización, el identificador de la aplicación y el secreto de cliente.

![Configuración de la aplicación de conexión](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>Configurar datos: seleccionar proyectos y campos

Puede elegir la conexión para indizar toda la organización o proyectos específicos.

Si elige indizar toda la organización, los elementos de todos los proyectos de la organización se indizarán. Los nuevos proyectos y elementos se indizarán durante el siguiente rastreo después de su creación.

Si elige proyectos individuales, solo se indizarán los elementos de trabajo de esos proyectos.

![Configurar datos](media/ADO_Configure_data.png)

A continuación, seleccione los campos que desea que la conexión indexe y obtenga una vista previa de los datos de estos campos antes de continuar.

![Elegir propiedades](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>Paso 4: Administrar permisos de búsqueda

El conector de DevOps de Azure admite permisos de búsqueda visibles solo para las personas con  **acceso a este origen de datos** o **todos**. Si elige Solo personas con acceso a este origen de **datos,** los datos indizados aparecerán en los resultados de búsqueda para los usuarios que tengan acceso a ellos en función de los permisos para usuarios o grupos en el nivel de ruta de acceso organización, proyecto o área en Azure DevOps. Si elige **Todos, los** datos indizados aparecerán en los resultados de la búsqueda para todos los usuarios.

## <a name="step-5-assign-property-labels"></a>Paso 5: Asignar etiquetas de propiedades

Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-6-manage-schema"></a>Paso 6: Administrar esquema

Siga las instrucciones [generales de configuración](./configure-connector.md).

## <a name="step-7-choose-refresh-settings"></a>Paso 7: Elegir la configuración de actualización

El conector de DevOps de Azure admite programaciones de actualización para rastreos completos e incrementales.
La programación recomendada es de una hora para un rastreo incremental y un día para un rastreo completo.

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->