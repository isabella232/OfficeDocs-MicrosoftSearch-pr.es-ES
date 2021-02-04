---
title: Conector de Salesforce Graph para Microsoft Search
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
description: Configurar el conector de Salesforce Graph para Microsoft Search
ms.openlocfilehash: 6771bc0b234bc2570a8b1fa7174b9b9244cf3958
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097452"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a>Conector de Salesforce Graph (versión preliminar)

El conector de Salesforce Graph permite a su organización indizar los objetos Contactos, Oportunidades, Clientes potenciales y Cuentas en su instancia de Salesforce. Después de configurar el conector y el contenido de índice de Salesforce, los usuarios finales pueden buscar esos elementos desde cualquier cliente de Microsoft Search.

> [!NOTE]
> Lea el [**artículo sobre el programa de instalación del conector de Graph**](configure-connector.md) para comprender el proceso de configuración general de los conectores de Graph.

Este artículo está dirigido a cualquier persona que configure, ejecute y monitore un conector de Salesforce Graph. Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de Salesforce Graph. En este artículo también se incluye información sobre [limitaciones.](#limitations)

>[!IMPORTANT]
>Actualmente, el conector de Salesforce Graph es compatible con el verano 19 o posterior.

## <a name="before-you-get-started"></a>Antes de empezar

Para conectarse a la instancia de Salesforce, necesita la dirección URL de la instancia de Salesforce, el id. de cliente y el secreto de cliente para la autenticación de OAuth. Los siguientes pasos explican cómo usted o su administrador de Salesforce pueden obtener esta información de su cuenta de Salesforce:

- Inicie sesión en la instancia de Salesforce y vaya a Configuración

- Ve a Aplicaciones -> App Manager.

- Seleccione **Nueva aplicación conectada.**

- Complete la sección api de la siguiente manera:

    - Active la casilla de verificación Habilitar **configuración de Oauth**.

    - Especifique la dirección URL de devolución de llamada como: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - Seleccione estos ámbitos de OAuth necesarios.

        - Obtener acceso y administrar los datos (api)

        - Realizar solicitudes en su nombre en cualquier momento (refresh_token, offline_access)

    - Active la casilla requerir **secreto para el flujo del servidor web.**

    - Guarda la aplicación.
    
      > [!div class="mx-imgBorder"]
      > ![Sección api en la instancia de Salesforce después de que el administrador haya especificado todas las configuraciones necesarias enumeradas anteriormente.](media/salesforce-connector/sf1.png)

- Copie la clave de consumidor y el secreto de consumidor. Esta información se usará como identificador de cliente y secreto de cliente cuando configure la configuración de conexión para el conector de Graph en el portal de administración de Microsoft 365.

  > [!div class="mx-imgBorder"]
  > ![Resultados devueltos por la sección api en la instancia de Salesforce después de que el administrador haya enviado todas las configuraciones necesarias. La clave de consumidor está en la parte superior de la columna izquierda y el secreto de consumidor está en la parte superior de la columna derecha.](media/salesforce-connector/clientsecret.png)
  
- Antes de cerrar la instancia de Salesforce, siga estos pasos para asegurarse de que los tokens de actualización no expiren:
    - Ir a Aplicaciones -> App Manager
    - Busca la aplicación que creaste y selecciona la lista desplegable a la derecha. Seleccionar **Administrar**
    - Seleccionar **directivas de edición**
    - Para la directiva de token de actualización, seleccione **Actualizar token es válido hasta que se revoque**

  > [!div class="mx-imgBorder"]
  > ![Seleccione la directiva de token de actualización denominada "El token de actualización es válido hasta que se revoque"](media/salesforce-connector/oauthpolicies.png)

Ahora puede usar el Centro [de administración de M365](https://admin.microsoft.com/) para completar el resto del proceso de configuración del conector de Graph.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

Para la dirección URL de instancia, use https://[domain].my.salesforce.com, donde el dominio sería el dominio salesforce de su organización.

Escriba el id. de cliente y el secreto de cliente que obtuvo de la instancia de Salesforce y seleccione Iniciar sesión.

La primera vez que haya intentado iniciar sesión con esta configuración, verá una ventana emergente que le pedirá que inicie sesión en Salesforce con su nombre de usuario y contraseña de administrador. La captura de pantalla siguiente muestra el elemento emergente. Escriba sus credenciales y seleccione "Iniciar sesión".

  ![Cuadro emergente de inicio de sesión que pide nombre de usuario y contraseña.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >Si no aparece la ventana emergente, es posible que se bloquee en el explorador, por lo que debe permitir las ventanas emergentes y los redireccionamientos.

Compruebe que la conexión se ha realizado correctamente buscando un banner verde que diga "Conexión correcta", como se muestra en la siguiente captura de pantalla.

  > [!div class="mx-imgBorder"]
  > ![Captura de pantalla del inicio de sesión correcto. El banner verde que dice "Conexión correcta" se encuentra en el campo de la dirección URL de la instancia de Salesforce](media/salesforce-connector/sf5.png)

## <a name="step-4-manage-search-permissions"></a>Paso 4: Administrar permisos de búsqueda

Deberá elegir qué usuarios verán los resultados de búsqueda de este origen de datos. Si permites que solo determinados usuarios de Azure Active Directory (Azure AD) o usuarios que no son de Azure AD vean los resultados de la búsqueda, asegúrate de asignar las identidades.

## <a name="step-4a-select-permissions"></a>Paso 4a: Seleccionar permisos

Puede elegir ingerir listas de control de acceso (ACL) de la instancia de Salesforce o permitir que todos los usuarios de su organización vean los resultados de la búsqueda de este origen de datos. Las ACL pueden incluir identidades de Azure Active Directory (AAD) (usuarios federados de Azure AD a Salesforce), identidades que no son de Azure AD (usuarios nativos de Salesforce que tienen identidades correspondientes en Azure AD) o ambas.

>[!NOTE]
>Si usa un proveedor de identidades de terceros como Ping ID o secureAuth, debe seleccionar "non-AAD" como el tipo de identidad.

> [!div class="mx-imgBorder"]
> ![Seleccione la pantalla de permisos que ha completado un administrador. El administrador ha seleccionado la opción "Solo las personas con acceso a este origen de datos" y también ha seleccionado "AAD" en un menú desplegable de tipos de identidad.](media/salesforce-connector/sf6.png)

Si decidió ingerir una ACL de la instancia de Salesforce y seleccionó "no AAD" para el tipo de identidad, consulte Asignar las identidades que no son de [Azure AD](map-non-aad.md) para obtener instrucciones sobre cómo asignar las identidades.

## <a name="step-4b-map-aad-identities"></a>Paso 4b: Asignar identidades de AAD

Si decidió ingerir una ACL de la instancia de Salesforce y seleccionó "AAD" para el tipo de identidad, consulte Asignar las identidades de [Azure AD](map-aad.md) para obtener instrucciones sobre cómo asignar las identidades. Para obtener información sobre cómo configurar el SSO de Azure AD para Salesforce, vea este [tutorial.](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial)

## <a name="step-5-assign-property-labels"></a>Paso 5: Asignar etiquetas de propiedad

Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones. Aunque este paso no es obligatorio, tener algunas etiquetas de propiedad mejorará la relevancia de la búsqueda y garantizará mejores resultados de búsqueda para los usuarios finales. De forma predeterminada, algunas de las etiquetas como "Title", "URL", "CreatedBy" y "LastModifiedBy" ya tienen asignadas propiedades de origen.

## <a name="step-6-manage-schema"></a>Paso 6: Administrar esquema

Puede seleccionar qué propiedades de origen deben indizarse para que se muestren en los resultados de la búsqueda. De forma predeterminada, el Asistente para la conexión selecciona un esquema de búsqueda basado en un conjunto de propiedades de origen. Puede modificarlo seleccionando las casillas de cada propiedad y atributo en la página del esquema de búsqueda. Los atributos del esquema de búsqueda incluyen Buscar, Consultar, Recuperar y Refinar.
Refinar le permite definir las propiedades que se pueden usar más adelante como refinadores o filtros personalizados en la experiencia de búsqueda.  

> [!div class="mx-imgBorder"]
> ![Seleccione el esquema para cada propiedad de origen. Las opciones son Consulta, Búsqueda, Recuperar y Refinar](media/salesforce-connector/sf9.png)

## <a name="step-7-set-the-refresh-schedule"></a>Paso 7: Establecer la programación de actualización

Actualmente, el conector de Salesforce solo admite programaciones de actualización para rastreos completos.

>[!IMPORTANT]
>Un rastreo completo busca objetos eliminados y usuarios que se sincronizaron previamente con el índice de Búsqueda de Microsoft.

La programación recomendada es de una semana para un rastreo completo.

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitaciones

- Actualmente, el conector de Graph no admite el uso compartido y el uso compartido basados en territorios basados en el territorio mediante grupos personales de Salesforce.
- Hay un error conocido en la API de Salesforce que usa el conector de Graph, donde actualmente no se respetan los valores predeterminados privados de toda la organización para clientes potenciales.  
- Si un campo tiene establecida la seguridad de nivel de campo (FLS) para un perfil, el conector de Graph no ingeri ese campo para ningún perfil de esa organización de Salesforce. Como resultado, los usuarios no podrán buscar valores para esos campos ni se mostrarán en los resultados.  
- En la pantalla Administrar esquema, estos nombres de propiedad estándar comunes se enumeran una vez, las opciones son **Consulta,** **Búsqueda,** Recuperar y Refinar, y se aplican a todos o ninguno.
    - Nombre
    - Url
    - Descripción
    - Fax
    - Phone
    - MobilePhone
    - Correo electrónico
    - Tipo
    - El título
    - AccountId
    - AccountName
    - AccountUrl
    - AccountOwner
    - AccountOwnerUrl
    - Owner
    - OwnerUrl
    - CreatedBy
    - CreatedByUrl
    - LastModifiedBy
    - LastModifiedByUrl
    - LastModifiedDate
    - ObjectName
