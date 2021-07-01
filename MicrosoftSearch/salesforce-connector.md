---
title: Conector Graph salesforce para Búsqueda de Microsoft
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
description: Configurar el conector de Graph Salesforce para Búsqueda de Microsoft
ms.openlocfilehash: 4bef771538934722deaa5deac3959f21246e4529
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230938"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="547b8-103">Conector Graph Salesforce (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="547b8-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="547b8-104">El conector de Graph salesforce permite a su organización indizar objetos Contacts, Opportunities, Leads y Accounts en su instancia de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="547b8-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="547b8-105">Después de configurar el conector y el contenido de índice de Salesforce, los usuarios finales pueden buscar esos elementos desde cualquier Búsqueda de Microsoft cliente.</span><span class="sxs-lookup"><span data-stu-id="547b8-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="547b8-106">Lea el [**artículo Setup for your Graph connector para**](configure-connector.md) comprender las instrucciones generales Graph de configuración de conectores.</span><span class="sxs-lookup"><span data-stu-id="547b8-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="547b8-107">Este artículo está para cualquier persona que configure, ejecute y monitore un conector de Graph Salesforce.</span><span class="sxs-lookup"><span data-stu-id="547b8-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="547b8-108">Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de Graph Salesforce.</span><span class="sxs-lookup"><span data-stu-id="547b8-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="547b8-109">En este artículo también se incluye información sobre [limitaciones](#limitations).</span><span class="sxs-lookup"><span data-stu-id="547b8-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="547b8-110">El conector de Graph salesforce admite actualmente summer '19 o posterior.</span><span class="sxs-lookup"><span data-stu-id="547b8-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="547b8-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="547b8-111">Before you get started</span></span>

<span data-ttu-id="547b8-112">Para conectarse a la instancia de Salesforce, necesita la dirección URL de la instancia de Salesforce, el id. de cliente y el secreto de cliente para la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="547b8-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="547b8-113">Los siguientes pasos explican cómo usted o su administrador de Salesforce pueden obtener esta información de su cuenta de Salesforce:</span><span class="sxs-lookup"><span data-stu-id="547b8-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="547b8-114">Inicie sesión en la instancia de Salesforce y vaya al programa de instalación</span><span class="sxs-lookup"><span data-stu-id="547b8-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="547b8-115">Vaya a Aplicaciones -> App Manager.</span><span class="sxs-lookup"><span data-stu-id="547b8-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="547b8-116">Selecciona **Nueva aplicación conectada**.</span><span class="sxs-lookup"><span data-stu-id="547b8-116">Select **New connected app**.</span></span>

- <span data-ttu-id="547b8-117">Complete la sección API de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="547b8-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="547b8-118">Active la casilla de verificación **Habilitar Oauth Configuración**.</span><span class="sxs-lookup"><span data-stu-id="547b8-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="547b8-119">Especifique la dirección URL de devolución de llamada como: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="547b8-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="547b8-120">Seleccione estos ámbitos OAuth necesarios.</span><span class="sxs-lookup"><span data-stu-id="547b8-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="547b8-121">Obtener acceso y administrar los datos (api)</span><span class="sxs-lookup"><span data-stu-id="547b8-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="547b8-122">Realizar solicitudes en su nombre en cualquier momento (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="547b8-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="547b8-123">Active la casilla Requerir **secreto para el flujo del servidor web.**</span><span class="sxs-lookup"><span data-stu-id="547b8-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="547b8-124">Guarda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="547b8-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="547b8-125">![Sección API en la instancia de Salesforce después de que el administrador haya especificado todas las configuraciones necesarias enumeradas anteriormente.](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="547b8-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="547b8-126">Copie la clave de consumidor y el secreto de consumidor.</span><span class="sxs-lookup"><span data-stu-id="547b8-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="547b8-127">Esta información se usará como el identificador de cliente y el secreto de cliente cuando configure la conexión Configuración para el conector de Graph en el portal de administración de Microsoft 365 cliente.</span><span class="sxs-lookup"><span data-stu-id="547b8-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="547b8-128">![Resultados devueltos por la sección API en la instancia de Salesforce después de que el administrador haya enviado todas las configuraciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="547b8-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="547b8-129">Clave de consumidor está en la parte superior de la columna izquierda y Secreto de consumidor está en la parte superior de la columna derecha.](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="547b8-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="547b8-130">Antes de cerrar la instancia de Salesforce, siga estos pasos para asegurarse de que los tokens de actualización no expiren:</span><span class="sxs-lookup"><span data-stu-id="547b8-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="547b8-131">Ir a Aplicaciones -> App Manager</span><span class="sxs-lookup"><span data-stu-id="547b8-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="547b8-132">Busca la aplicación que creaste y selecciona la lista desplegable a la derecha.</span><span class="sxs-lookup"><span data-stu-id="547b8-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="547b8-133">Seleccione **Administrar**</span><span class="sxs-lookup"><span data-stu-id="547b8-133">Select **Manage**</span></span>
    - <span data-ttu-id="547b8-134">Seleccionar **directivas de edición**</span><span class="sxs-lookup"><span data-stu-id="547b8-134">Select **edit policies**</span></span>
    - <span data-ttu-id="547b8-135">Para la directiva de token de actualización, seleccione **Actualizar token es válido hasta que se revoque**</span><span class="sxs-lookup"><span data-stu-id="547b8-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="547b8-136">![Seleccione la directiva de token de actualización denominada "El token de actualización es válido hasta que se revoque"](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="547b8-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="547b8-137">Ahora puede usar el [Centro de Administración de Microsoft 365 para](https://admin.microsoft.com/) completar el resto del proceso de configuración del Graph conector.</span><span class="sxs-lookup"><span data-stu-id="547b8-137">You can now use the [Microsoft 365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="547b8-138">Paso 1: Agregar un conector Graph en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="547b8-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="547b8-139">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="547b8-139">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="547b8-140">Paso 2: Nombrar la conexión</span><span class="sxs-lookup"><span data-stu-id="547b8-140">Step 2: Name the connection</span></span>

<span data-ttu-id="547b8-141">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="547b8-141">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="547b8-142">Paso 3: Configurar las opciones de conexión</span><span class="sxs-lookup"><span data-stu-id="547b8-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="547b8-143">Para la dirección URL de instancia, use https://[domain].my.salesforce.com donde domain sería el dominio de Salesforce para su organización.</span><span class="sxs-lookup"><span data-stu-id="547b8-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="547b8-144">Escriba el id. de cliente y el secreto de cliente que obtuvo de la instancia de Salesforce y seleccione Iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="547b8-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="547b8-145">La primera vez que haya intentado iniciar sesión con esta configuración, aparecerá una ventana emergente que le pedirá que inicie sesión en Salesforce con su nombre de usuario y contraseña de administrador.</span><span class="sxs-lookup"><span data-stu-id="547b8-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="547b8-146">La captura de pantalla siguiente muestra el elemento emergente.</span><span class="sxs-lookup"><span data-stu-id="547b8-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="547b8-147">Escriba sus credenciales y seleccione "Iniciar sesión".</span><span class="sxs-lookup"><span data-stu-id="547b8-147">Enter your credentials and select "Log In".</span></span>

  ![Login pop up asking for Username and password.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="547b8-149">Si la ventana emergente no aparece, puede que se bloquee en el explorador, por lo que debe permitir las ventanas emergentes y los redireccionamientos.</span><span class="sxs-lookup"><span data-stu-id="547b8-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="547b8-150">Compruebe que la conexión se ha realizado correctamente buscando un banner verde que diga "Conexión correcta" como se muestra en la captura de pantalla siguiente.</span><span class="sxs-lookup"><span data-stu-id="547b8-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="547b8-151">![Captura de pantalla del inicio de sesión correcto.</span><span class="sxs-lookup"><span data-stu-id="547b8-151">![Screenshot of successful login.</span></span> <span data-ttu-id="547b8-152">El banner verde que indica "Conexión correcta" se encuentra en el campo de la dirección URL de la instancia de Salesforce](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="547b8-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="547b8-153">Paso 4: Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="547b8-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="547b8-154">Deberá elegir qué usuarios verán los resultados de búsqueda de este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="547b8-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="547b8-155">Si solo permite que determinados Azure Active Directory (Azure AD) o usuarios que no son de Azure AD vean los resultados de la búsqueda, asegúrese de asignar las identidades.</span><span class="sxs-lookup"><span data-stu-id="547b8-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

### <a name="step-4a-select-permissions"></a><span data-ttu-id="547b8-156">Paso 4.a: Seleccionar permisos</span><span class="sxs-lookup"><span data-stu-id="547b8-156">Step 4.a: Select permissions</span></span>

<span data-ttu-id="547b8-157">Puede elegir ingerir listas de control de acceso (ACL) desde la instancia de Salesforce o permitir que todos los usuarios de su organización vean los resultados de búsqueda de este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="547b8-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="547b8-158">Las ACL pueden incluir identidades Azure Active Directory (AAD) (usuarios federados de Azure AD a Salesforce), identidades que no son de Azure AD (usuarios nativos de Salesforce que tienen identidades correspondientes en Azure AD) o ambas.</span><span class="sxs-lookup"><span data-stu-id="547b8-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="547b8-159">Si usa un proveedor de identidades de terceros como Ping ID o secureAuth, debe seleccionar "non-AAD" como tipo de identidad.</span><span class="sxs-lookup"><span data-stu-id="547b8-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="547b8-160">![Seleccione la pantalla de permisos completada por un administrador. El administrador ha seleccionado la opción "Solo personas con acceso a este origen de datos" y también ha seleccionado "AAD" en un menú desplegable de tipos de identidad.](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="547b8-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="547b8-161">Si optó por ingerir una ACL de la instancia de Salesforce y seleccionó "non-AAD" para el tipo de identidad, consulte [Map your non-Azure AD Identities](map-non-aad.md) para obtener instrucciones sobre cómo asignar las identidades.</span><span class="sxs-lookup"><span data-stu-id="547b8-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="step-4b-map-aad-identities"></a><span data-ttu-id="547b8-162">Paso 4.b: Asignar identidades de AAD</span><span class="sxs-lookup"><span data-stu-id="547b8-162">Step 4.b: Map AAD identities</span></span>

<span data-ttu-id="547b8-163">Si optó por ingerir una ACL de la instancia de Salesforce y seleccionó "AAD" para el tipo de identidad, consulte [Map your Azure AD Identities](map-aad.md) para obtener instrucciones sobre cómo asignar las identidades.</span><span class="sxs-lookup"><span data-stu-id="547b8-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="547b8-164">Para obtener información sobre cómo configurar SSO de Azure AD para Salesforce, consulte este [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).</span><span class="sxs-lookup"><span data-stu-id="547b8-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

### <a name="apply-user-mapping-to-sync-your-salesforce-identities-to-azure-ad-identities"></a><span data-ttu-id="547b8-165">Aplicar asignación de usuario para sincronizar las identidades de Salesforce con identidades de Azure AD</span><span class="sxs-lookup"><span data-stu-id="547b8-165">Apply user mapping to sync your Salesforce identities to Azure AD identities</span></span>

<span data-ttu-id="547b8-166">En este vídeo puede ver el proceso para autenticarse en la instancia de Salesforce, sincronizar las identidades que no son de Azure Active Directory con las identidades de Azure Active Directory y aplicar los recortes de seguridad adecuados a los elementos de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="547b8-166">In this video you can see the process to authenticate to your Salesforce instance, sync your non-Azure Active Directory identities to your Azure Active Directory identities, and apply the proper security trimmings to your Salesforce items.</span></span>

> [!VIDEO https://www.youtube-nocookie.com/embed/SZYiFxZMKcM]

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="547b8-167">Paso 5: Asignar etiquetas de propiedades</span><span class="sxs-lookup"><span data-stu-id="547b8-167">Step 5: Assign property labels</span></span>

<span data-ttu-id="547b8-168">Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones.</span><span class="sxs-lookup"><span data-stu-id="547b8-168">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="547b8-169">Aunque este paso no es obligatorio, tener algunas etiquetas de propiedades mejorará la relevancia de la búsqueda y garantizará mejores resultados de búsqueda para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="547b8-169">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="547b8-170">De forma predeterminada, algunas de las etiquetas como "Title", "URL", "CreatedBy" y "LastModifiedBy" ya tienen asignadas propiedades de origen.</span><span class="sxs-lookup"><span data-stu-id="547b8-170">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="547b8-171">Paso 6: Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="547b8-171">Step 6: Manage schema</span></span>

<span data-ttu-id="547b8-172">Puede seleccionar qué propiedades de origen deben indizarse para que se muestren en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="547b8-172">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="547b8-173">El asistente para la conexión selecciona de forma predeterminada un esquema de búsqueda basado en un conjunto de propiedades de origen.</span><span class="sxs-lookup"><span data-stu-id="547b8-173">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="547b8-174">Puede modificarlo seleccionando las casillas de cada propiedad y atributo de la página del esquema de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="547b8-174">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="547b8-175">Los atributos de esquema de búsqueda incluyen Search, Query, Retrieve y Refine.</span><span class="sxs-lookup"><span data-stu-id="547b8-175">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="547b8-176">Refinar permite definir las propiedades que se pueden usar más adelante como refinadores o filtros personalizados en la experiencia de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="547b8-176">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="547b8-177">![Seleccione el esquema para cada propiedad de origen.</span><span class="sxs-lookup"><span data-stu-id="547b8-177">![Select the schema for each source property.</span></span> <span data-ttu-id="547b8-178">Las opciones son Consulta, Búsqueda, Recuperar y Refinar](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="547b8-178">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="547b8-179">Paso 7: Establecer la programación de actualización</span><span class="sxs-lookup"><span data-stu-id="547b8-179">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="547b8-180">El conector de Salesforce solo admite programaciones de actualización para rastreos completos actualmente.</span><span class="sxs-lookup"><span data-stu-id="547b8-180">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="547b8-181">Un rastreo completo busca objetos eliminados y usuarios que se sincronizaron previamente con el índice Búsqueda de Microsoft usuario.</span><span class="sxs-lookup"><span data-stu-id="547b8-181">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="547b8-182">La programación recomendada es de una semana para un rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="547b8-182">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="547b8-183">Paso 8: Revisar la conexión</span><span class="sxs-lookup"><span data-stu-id="547b8-183">Step 8: Review connection</span></span>

<span data-ttu-id="547b8-184">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="547b8-184">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="547b8-185">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="547b8-185">Limitations</span></span>

- <span data-ttu-id="547b8-186">El Graph no admite actualmente el uso compartido y el uso compartido basado en el territorio basado en Apex mediante grupos personales de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="547b8-186">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="547b8-187">Hay un error conocido en la API de Salesforce que usa el conector de Graph, donde los valores predeterminados de toda la organización privada para clientes potenciales no se respetan actualmente.</span><span class="sxs-lookup"><span data-stu-id="547b8-187">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="547b8-188">Si un campo tiene establecida la seguridad de nivel de campo (FLS) para un perfil, el conector de Graph no ingeriá ese campo para los perfiles de esa organización de Salesforce. Como resultado, los usuarios no podrán buscar en los valores de esos campos ni aparecerán en los resultados.</span><span class="sxs-lookup"><span data-stu-id="547b8-188">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="547b8-189">En la pantalla Administrar esquema, estos nombres de propiedades estándar comunes se enumeran una vez, las opciones son **Query**, **Search,** **Retrieve** y **Refine** y se aplican a todos o ninguno.</span><span class="sxs-lookup"><span data-stu-id="547b8-189">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="547b8-190">Nombre</span><span class="sxs-lookup"><span data-stu-id="547b8-190">Name</span></span>
    - <span data-ttu-id="547b8-191">Url</span><span class="sxs-lookup"><span data-stu-id="547b8-191">Url</span></span>
    - <span data-ttu-id="547b8-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="547b8-192">Description</span></span>
    - <span data-ttu-id="547b8-193">Fax</span><span class="sxs-lookup"><span data-stu-id="547b8-193">Fax</span></span>
    - <span data-ttu-id="547b8-194">Phone</span><span class="sxs-lookup"><span data-stu-id="547b8-194">Phone</span></span>
    - <span data-ttu-id="547b8-195">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="547b8-195">MobilePhone</span></span>
    - <span data-ttu-id="547b8-196">Correo electrónico</span><span class="sxs-lookup"><span data-stu-id="547b8-196">Email</span></span>
    - <span data-ttu-id="547b8-197">Tipo</span><span class="sxs-lookup"><span data-stu-id="547b8-197">Type</span></span>
    - <span data-ttu-id="547b8-198">Título</span><span class="sxs-lookup"><span data-stu-id="547b8-198">Title</span></span>
    - <span data-ttu-id="547b8-199">AccountId</span><span class="sxs-lookup"><span data-stu-id="547b8-199">AccountId</span></span>
    - <span data-ttu-id="547b8-200">AccountName</span><span class="sxs-lookup"><span data-stu-id="547b8-200">AccountName</span></span>
    - <span data-ttu-id="547b8-201">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="547b8-201">AccountUrl</span></span>
    - <span data-ttu-id="547b8-202">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="547b8-202">AccountOwner</span></span>
    - <span data-ttu-id="547b8-203">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="547b8-203">AccountOwnerUrl</span></span>
    - <span data-ttu-id="547b8-204">Propietario</span><span class="sxs-lookup"><span data-stu-id="547b8-204">Owner</span></span>
    - <span data-ttu-id="547b8-205">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="547b8-205">OwnerUrl</span></span>
    - <span data-ttu-id="547b8-206">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="547b8-206">CreatedBy</span></span>
    - <span data-ttu-id="547b8-207">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="547b8-207">CreatedByUrl</span></span>
    - <span data-ttu-id="547b8-208">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="547b8-208">LastModifiedBy</span></span>
    - <span data-ttu-id="547b8-209">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="547b8-209">LastModifiedByUrl</span></span>
    - <span data-ttu-id="547b8-210">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="547b8-210">LastModifiedDate</span></span>
    - <span data-ttu-id="547b8-211">ObjectName</span><span class="sxs-lookup"><span data-stu-id="547b8-211">ObjectName</span></span>
