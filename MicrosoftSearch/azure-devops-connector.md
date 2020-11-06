---
title: Conector de Azure DevOps para Microsoft Search
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de Azure DevOps para Microsoft Search
ms.openlocfilehash: a0028c3b336c2b5e3d01bb14006ee0debb4524f2
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927193"
---
# <a name="azure-devops-connector"></a>Conector de Azure DevOps

Con el conector de Azure DevOps, su organización puede indizar los elementos de trabajo en su instancia del servicio de Azure DevOps. Después de configurar el conector y el contenido de índice desde Azure DevOps, los usuarios finales pueden buscar esos elementos en Microsoft Search.

Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de Azure DevOps. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.

>[!IMPORTANT]
>El conector de Azure DevOps solo admite el servicio en la nube de Azure DevOps. El conector no admite Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 y TFS 2013.

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos

Para conectarse a la instancia de DevOps de Azure, necesita el nombre de la [organización](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) de Azure DevOps, su identificador de aplicación y el secreto de cliente para la autenticación OAuth.

### <a name="register-an-app"></a>Registrar una aplicación

Debe registrar una aplicación en Azure DevOps para que la aplicación Microsoft Search pueda tener acceso a la instancia. Para obtener más información, consulte la documentación de Azure DevOps sobre cómo [registrar una aplicación](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).

La siguiente tabla proporciona instrucciones sobre cómo rellenar el formulario de registro de la aplicación:

 **Campos obligatorios** | **Descripción**      | **Valor recomendado**
--- | --- | ---
| Nombre de la compañía         | Este es el nombre de su compañía. | Use un valor apropiado   |
| Nombre de la aplicación     | Este valor único identifica la aplicación que está autorizando.    | Búsqueda de Microsoft     |
| Sitio web de la aplicación  | Este campo obligatorio es la dirección URL de la aplicación que solicitará acceso a la instancia de Azure DevOps durante la instalación del conector.  | <https://gcs.office.com/>                |
| Dirección URL de devolución de llamada de autorización        | Una dirección URL de devolución de llamada obligatoria a la que redirige el servidor de autorización. | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| Ámbitos autorizados | Este es el ámbito de acceso para la aplicación | Seleccione los siguientes ámbitos: identidad (lectura), elementos de trabajo (lectura), grupos de variables (lectura), proyecto y equipo (lectura), gráfico (lectura)|

Al registrar la aplicación con los detalles anteriores, obtendrá el identificador de la **aplicación** y el **secreto de cliente** que se usará para configurar el conector.

>[!NOTE]
>Para revocar el acceso a cualquier aplicación registrada en Azure DevOps, vaya a configuración de usuario en la parte superior derecha de la instancia de Azure DevOps. Haga clic en perfil y, a continuación, haga clic en autorizaciones en la sección seguridad del panel lateral. Mantenga el mouse sobre una aplicación de OAuth autorizada para ver el botón revocar en la esquina de los detalles de la aplicación.

### <a name="connection-settings"></a>Configuración de conexión

Después de registrar la aplicación Microsoft Search con Azure DevOps, puede completar el paso de configuración de la conexión. Escriba el nombre de la organización, el identificador de la aplicación y el secreto de cliente.

![Configuración de la aplicación de conexión](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a>Selección de proyectos y campos

Puede elegir que la conexión se Indice en toda la organización o en proyectos específicos.

Si elige indizar toda la organización, los elementos de todos los proyectos de la organización se indizarán. Los nuevos proyectos y elementos se indizarán durante el siguiente rastreo una vez que se hayan creado. Si elige proyectos individuales, solo se indizarán los elementos de trabajo en esos proyectos.

![Configurar datos](media/ADO_Configure_data.png)

A continuación, seleccione los campos que desea que la conexión indexe y obtenga una vista previa de los datos de estos campos antes de continuar.

![Elegir propiedades](media/ADO_choose_properties.png)

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda

Actualmente, el conector de Azure DevOps solo admite permisos **de búsqueda visibles para todos los usuarios**. Los datos indizados aparecerán en los resultados de la búsqueda para todos los usuarios.

## <a name="manage-search-schema"></a>Administrar el esquema de búsqueda

Configure la asignación del esquema de búsqueda. Puede elegir qué propiedades se pueden **consultar** , **Buscar** y **recuperar**.


## <a name="set-refresh-schedule"></a>Establecer programación de actualización

El conector de DevOps de Azure admite programaciones de actualización para rastreos completos e incrementales. Un rastreo completo busca elementos de trabajo eliminados que se sincronizaron previamente con el índice de Microsoft Search. Se ejecuta un rastreo completo para sincronizar todos los elementos de trabajo. Para sincronizar los nuevos elementos de trabajo y las actualizaciones de los elementos de trabajo existentes, debe programar rastreos incrementales.

La programación recomendada es una hora para un rastreo incremental y un día para un rastreo completo.
