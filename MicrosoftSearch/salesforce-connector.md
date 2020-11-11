---
title: Conector de Salesforce para Microsoft Search
ms.author: rusamai
author: rsamai
manager: jameslao
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Configurar el conector de Salesforce para Microsoft Search
ms.openlocfilehash: 8de7784cae7d430bc385889bd836360c69492591
ms.sourcegitcommit: 77ec27736f3c8434b2ac47e10897ac2606ee8a03
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "48992956"
---
# <a name="salesforce-connector"></a><span data-ttu-id="900b6-103">Conector de Salesforce</span><span class="sxs-lookup"><span data-stu-id="900b6-103">Salesforce connector</span></span>

<span data-ttu-id="900b6-104">Con el conector gráfico de Salesforce, su organización puede indizar los objetos Contacts, oportunidades, clientes potenciales y cuentas en su instancia de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="900b6-104">With the Salesforce Graph connector, your organization can index Contacts, Opportunities, Leads and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="900b6-105">Después de configurar el conector y el contenido del índice desde Salesforce, los usuarios finales pueden buscar dichos elementos desde cualquier cliente de Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="900b6-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client</span></span>

<span data-ttu-id="900b6-106">Este artículo está destinado a los administradores de [Microsoft 365](https://www.microsoft.com/microsoft-365) o a cualquiera que configure, ejecute y supervise un conector de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="900b6-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors a Salesforce connector.</span></span> <span data-ttu-id="900b6-107">Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="900b6-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="900b6-108">El conector gráfico de Salesforce actualmente es compatible con las versiones de verano "20, primavera" 20, invierno "20 y verano de" 19 ".</span><span class="sxs-lookup"><span data-stu-id="900b6-108">The Salesforce Graph connector currently supports Summer ’20, Spring’20, Winter’20, and Summer ’19 versions.</span></span>

## <a name="connection-settings"></a><span data-ttu-id="900b6-109">Configuración de conexión</span><span class="sxs-lookup"><span data-stu-id="900b6-109">Connection settings</span></span>

<span data-ttu-id="900b6-110">Para conectarse a su instancia de Salesforce, necesita la dirección URL de la instancia de Salesforce, el identificador de cliente y el secreto de cliente para la autenticación OAuth.</span><span class="sxs-lookup"><span data-stu-id="900b6-110">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="900b6-111">Los siguientes pasos explican cómo usted o su administrador de Salesforce pueden obtener esta información de su cuenta de Salesforce:</span><span class="sxs-lookup"><span data-stu-id="900b6-111">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="900b6-112">Inicie sesión en su instancia de Salesforce y vaya a configuración</span><span class="sxs-lookup"><span data-stu-id="900b6-112">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="900b6-113">Vaya a apps-> App Manager.</span><span class="sxs-lookup"><span data-stu-id="900b6-113">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="900b6-114">Seleccione **nueva aplicación conectada**.</span><span class="sxs-lookup"><span data-stu-id="900b6-114">Select **New connected app**.</span></span>

- <span data-ttu-id="900b6-115">Complete la sección API de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="900b6-115">Complete the API section as follows:</span></span>

    - <span data-ttu-id="900b6-116">Marque la casilla de verificación **Habilitar configuración de OAuth**.</span><span class="sxs-lookup"><span data-stu-id="900b6-116">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="900b6-117">Especifique la dirección URL de devolución de llamada como: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="900b6-117">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="900b6-118">Seleccione estos ámbitos de OAuth necesarios.</span><span class="sxs-lookup"><span data-stu-id="900b6-118">Select these required OAuth scopes.</span></span> 

        - <span data-ttu-id="900b6-119">Obtener acceso y administrar los datos (API)</span><span class="sxs-lookup"><span data-stu-id="900b6-119">Access and manage your data (api)</span></span> 

        - <span data-ttu-id="900b6-120">Realizar solicitudes en su nombre en cualquier momento (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="900b6-120">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span> 

    - <span data-ttu-id="900b6-121">Marque la casilla **requerir secreto para el flujo del servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="900b6-121">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="900b6-122">Guarde la aplicación.</span><span class="sxs-lookup"><span data-stu-id="900b6-122">Save the app.</span></span>
    
      ![Sección API de la instancia de Salesforce después de que el administrador haya especificado todas las configuraciones necesarias enumeradas anteriormente.](media/salesforce-connector/sf1.png)

- <span data-ttu-id="900b6-124">Copie la clave de consumidor y el secreto de consumidor.</span><span class="sxs-lookup"><span data-stu-id="900b6-124">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="900b6-125">Se usarán como el identificador de cliente y el secreto de cliente al configurar las opciones de conexión para el conector de Graph en el portal de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="900b6-125">These will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  ![Resultados devueltos por la sección API en la instancia de Salesforce después de que el administrador haya enviado todas las configuraciones necesarias.](media/salesforce-connector/clientsecret.png)
- <span data-ttu-id="900b6-128">Antes de cerrar la instancia de Salesforce, siga estos pasos para asegurarse de que los tokens de actualización no expiren:</span><span class="sxs-lookup"><span data-stu-id="900b6-128">Before closing your Salesforce instance, perform the following steps to ensure that refresh tokens do not expire:</span></span> 
    - <span data-ttu-id="900b6-129">Vaya a apps-> App Manager</span><span class="sxs-lookup"><span data-stu-id="900b6-129">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="900b6-130">Busque la aplicación que acaba de crear y seleccione la lista desplegable de la derecha.</span><span class="sxs-lookup"><span data-stu-id="900b6-130">Find the app you just created and select the drop down on the right.</span></span> <span data-ttu-id="900b6-131">Seleccione **administrar**</span><span class="sxs-lookup"><span data-stu-id="900b6-131">Select **Manage**</span></span>
    - <span data-ttu-id="900b6-132">Seleccionar **editar directivas**</span><span class="sxs-lookup"><span data-stu-id="900b6-132">Select **edit policies**</span></span>
    - <span data-ttu-id="900b6-133">Para la Directiva de token de actualización, seleccione el **token de actualización es válido hasta que se revoca**</span><span class="sxs-lookup"><span data-stu-id="900b6-133">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  ![Seleccione la Directiva de token de actualización denominada "el token de actualización es válida hasta que se revoca"](media/salesforce-connector/oauthpolicies.png)

<span data-ttu-id="900b6-135">Ahora puede usar el [centro de administración de M365](https://admin.microsoft.com/) para completar el resto del proceso de instalación del conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="900b6-135">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>  

<span data-ttu-id="900b6-136">Configure las opciones de conexión para su conector para gráficos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="900b6-136">Configure the Connection settings for your Graph connector as follows:</span></span>

- <span data-ttu-id="900b6-137">Para la dirección URL de instancia, use https://[dominio]. My. salesforce. com donde dominio sería el dominio de Salesforce de su organización.</span><span class="sxs-lookup"><span data-stu-id="900b6-137">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span> 
- <span data-ttu-id="900b6-138">Escriba el identificador de cliente y el secreto de cliente que obtuvo de la instancia de Salesforce y seleccione iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="900b6-138">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>
- <span data-ttu-id="900b6-139">Si esta es la primera vez que intenta iniciar sesión con esta configuración, recibirá una ventana emergente que le pedirá que inicie sesión en Salesforce con el nombre de usuario y la contraseña de administrador.</span><span class="sxs-lookup"><span data-stu-id="900b6-139">If this is the first time you have attempted to Sign in with these settings, you will get a pop up asking you to login to Salesforce with your admin username and password.</span></span> <span data-ttu-id="900b6-140">La captura de pantalla siguiente muestra el elemento emergente.</span><span class="sxs-lookup"><span data-stu-id="900b6-140">The screenshot below shows the popup.</span></span> <span data-ttu-id="900b6-141">Escriba sus credenciales y seleccione iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="900b6-141">Enter your credentials and select Log in.</span></span>

  ![Mensaje emergente de inicio de sesión que solicita el nombre de usuario y la contraseña.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="900b6-143">Si no aparece la ventana emergente, es posible que se bloquee en el explorador, por lo que debe permitir los elementos emergentes y las redirecciones.</span><span class="sxs-lookup"><span data-stu-id="900b6-143">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

  >[!NOTE]
  ><span data-ttu-id="900b6-144">Si su organización usa el inicio de sesión único (SSO), puede seleccionar **usar dominio personalizado** en la esquina inferior derecha de la interfaz de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="900b6-144">If your organization uses single sign-on (SSO), you can select **Use Custom Domain** in the bottom, right-hand corner of the login interface.</span></span> <span data-ttu-id="900b6-145">Escriba el dominio y, después, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="900b6-145">Enter the domain and then select **Continue**.</span></span> <span data-ttu-id="900b6-146">Irá a la página de inicio de sesión específico de la organización, donde tendrá una opción para iniciar sesión con SSO.</span><span class="sxs-lookup"><span data-stu-id="900b6-146">It will go to your organization specific login page where you will have an option to login with SSO.</span></span>

- <span data-ttu-id="900b6-147">Compruebe que la conexión se ha realizado correctamente buscando un banner verde que diga "conexión correcta", tal y como se muestra en la captura de pantalla siguiente.</span><span class="sxs-lookup"><span data-stu-id="900b6-147">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  ![Captura de pantalla de inicio de sesión correcto.](media/salesforce-connector/sf5.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="900b6-150">Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="900b6-150">Manage search permissions</span></span>
<span data-ttu-id="900b6-151">Tendrá que elegir qué usuarios verán los resultados de la búsqueda de este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="900b6-151">You will need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="900b6-152">Si solo permite que determinados usuarios de Azure Active Directory (AAD) o no AAD vean los resultados de la búsqueda, tendrá que asignar las identidades.</span><span class="sxs-lookup"><span data-stu-id="900b6-152">If you allow only certain Azure Active Directory (AAD) or Non-AAD users to see the search results, you will then need to map the identities.</span></span>

### <a name="select-permissions"></a><span data-ttu-id="900b6-153">Seleccionar permisos</span><span class="sxs-lookup"><span data-stu-id="900b6-153">Select Permissions</span></span>
<span data-ttu-id="900b6-154">Puede optar por recopilar listas de control de acceso (ACL) de su instancia de Salesforce o permitir que todos los usuarios de la organización vean los resultados de la búsqueda de este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="900b6-154">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or you can allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="900b6-155">Las ACL pueden incluir identidades de Azure Active Directory (AAD), identidades que no son de AAD o ambas.</span><span class="sxs-lookup"><span data-stu-id="900b6-155">ACLs can include Azure Active Directory (AAD) identities, Non-AAD identities, or both.</span></span>

![Seleccione la pantalla de permisos que ha completado un administrador. El administrador ha seleccionado la opción "solo personas con acceso a este origen de datos" y también ha seleccionado "AAD" en un menú desplegable de tipos de identidad.](media/salesforce-connector/sf6.png)

### <a name="map-non-aad-identities"></a><span data-ttu-id="900b6-157">Asignar identidades que no son AAD</span><span class="sxs-lookup"><span data-stu-id="900b6-157">Map non-AAD identities</span></span> 
<span data-ttu-id="900b6-158">Si opta por ingesta de una ACL de su instancia de Salesforce y ha seleccionado "no-AAD" para el tipo de identidad, consulte [asignar las identidades que no son de Azure ad ](map-non-aad.md) para obtener instrucciones sobre cómo asignar las identidades.</span><span class="sxs-lookup"><span data-stu-id="900b6-158">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type see [Map your non-Azure AD Identities ](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="map-aad-identities"></a><span data-ttu-id="900b6-159">Asignar identidades de AAD</span><span class="sxs-lookup"><span data-stu-id="900b6-159">Map AAD identities</span></span>
<span data-ttu-id="900b6-160">Si optó por la incorporación de una ACL desde su instancia de Salesforce y seleccionó "AAD" para el tipo de identidad, consulte [asignar las identidades de Azure ad](map-aad.md) para obtener instrucciones sobre cómo asignar las identidades.</span><span class="sxs-lookup"><span data-stu-id="900b6-160">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="900b6-161">Asignar etiquetas de propiedad</span><span class="sxs-lookup"><span data-stu-id="900b6-161">Assign property labels</span></span> 
<span data-ttu-id="900b6-162">Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones.</span><span class="sxs-lookup"><span data-stu-id="900b6-162">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="900b6-163">Aunque este paso no es obligatorio, tener algunas etiquetas de propiedades mejorará la relevancia de la búsqueda y garantizará resultados de búsqueda más precisos para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="900b6-163">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span> <span data-ttu-id="900b6-164">De forma predeterminada, algunas de las etiquetas como "title", "URL" y "LastModifiedBy" ya tienen asignadas propiedades de origen.</span><span class="sxs-lookup"><span data-stu-id="900b6-164">By default, some of the Labels like ”Title”, “url”, and  “LastModifiedBy” have already been assigned source properties.</span></span>

![Pantalla de asignación de etiquetas de propiedades que muestra las propiedades de origen predeterminadas.](media/salesforce-connector/sf8.png)

## <a name="manage-schema"></a><span data-ttu-id="900b6-166">Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="900b6-166">Manage Schema</span></span>
<span data-ttu-id="900b6-167">Puede seleccionar qué propiedades de origen deben indizarse para que se puedan mostrar en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="900b6-167">You can select what source properties should be indexed so that they can show up in search results.</span></span> <span data-ttu-id="900b6-168">El Asistente para la conexión selecciona de forma predeterminada un esquema de búsqueda en función de un conjunto de propiedades de origen.</span><span class="sxs-lookup"><span data-stu-id="900b6-168">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="900b6-169">Puede modificarla activando las casillas para cada propiedad y atributo en la página esquema de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="900b6-169">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="900b6-170">Los atributos de esquema de búsqueda incluyen búsqueda, consulta, recuperar y refinar.</span><span class="sxs-lookup"><span data-stu-id="900b6-170">Search schema attributes include Search, Query, Retrieve and Refine.</span></span> <span data-ttu-id="900b6-171">Refinar permite definir las propiedades que se pueden usar más adelante como refinadores personalizados o filtros en la experiencia de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="900b6-171">Refine allows you to define the properties which can be later used as custom refiners or filters in the search experience.</span></span>  

![Seleccione el esquema para cada propiedad de origen.](media/salesforce-connector/sf9.png)

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="900b6-174">Establecer la programación de actualización</span><span class="sxs-lookup"><span data-stu-id="900b6-174">Set the refresh schedule</span></span>

<span data-ttu-id="900b6-175">El conector de Salesforce solo admite programaciones de actualización para rastreos completos actualmente.</span><span class="sxs-lookup"><span data-stu-id="900b6-175">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="900b6-176">Un rastreo completo busca objetos eliminados y usuarios que se han sincronizado anteriormente en el índice de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="900b6-176">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="900b6-177">La programación recomendada es una semana para un rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="900b6-177">The recommended schedule is one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="900b6-178">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="900b6-178">Limitations</span></span>

- <span data-ttu-id="900b6-179">En este momento, el conector de Graph no admite el uso compartido y uso compartido basado en territorio de Apex con grupos personales de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="900b6-179">The Graph connector does not currently support Apex based , territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="900b6-180">Hay un error conocido en la API de Salesforce que usa el conector de Graph en el que actualmente no se respetan los valores predeterminados de la organización privada para los clientes potenciales.</span><span class="sxs-lookup"><span data-stu-id="900b6-180">There is a known bug in the Salesforce API that the Graph connector uses where the private org wide defaults for leads is not honored currently.</span></span>  
- <span data-ttu-id="900b6-181">Si un campo tiene un nivel de seguridad de nivel de campo (FLS) establecido para un perfil, el conector de Graph no inscribirá ese campo para los perfiles de esa organización de Salesforce. Por lo tanto, los usuarios no podrán buscar en los valores de esos campos, ni se mostrarán en los resultados.</span><span class="sxs-lookup"><span data-stu-id="900b6-181">If a field has field level security (FLS) set for a profile, the Graph connector will not ingest that field for any profiles in that Salesforce org. Users will thus not be able to search on values for those fields, nor will it  show up in the results.</span></span>  
- <span data-ttu-id="900b6-182">Cualquier configuración de FLS se respetará durante las sincronizaciones completas del conector.</span><span class="sxs-lookup"><span data-stu-id="900b6-182">Any FLS set up will be honored during the Full syncs of the connector.</span></span>
- <span data-ttu-id="900b6-183">En la pantalla Administrar esquema, estos nombres de propiedades estándar comunes se muestran una vez y se realiza la selección para que se puedan consultar, realizar búsquedas y recuperarse en todos o en ninguno.</span><span class="sxs-lookup"><span data-stu-id="900b6-183">In the Manage Schema screen these common standard property names are listed once and the selection done to make them queryable, searchable and retrievable apply to all or none.</span></span>
    - <span data-ttu-id="900b6-184">Nombre</span><span class="sxs-lookup"><span data-stu-id="900b6-184">Name</span></span>
    - <span data-ttu-id="900b6-185">Url</span><span class="sxs-lookup"><span data-stu-id="900b6-185">Url</span></span> 
    - <span data-ttu-id="900b6-186">Descripción</span><span class="sxs-lookup"><span data-stu-id="900b6-186">Description</span></span>
    - <span data-ttu-id="900b6-187">Fax</span><span class="sxs-lookup"><span data-stu-id="900b6-187">Fax</span></span>
    - <span data-ttu-id="900b6-188">Phone</span><span class="sxs-lookup"><span data-stu-id="900b6-188">Phone</span></span>
    - <span data-ttu-id="900b6-189">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="900b6-189">MobilePhone</span></span>
    - <span data-ttu-id="900b6-190">Correo electrónico</span><span class="sxs-lookup"><span data-stu-id="900b6-190">Email</span></span>
    - <span data-ttu-id="900b6-191">Tipo</span><span class="sxs-lookup"><span data-stu-id="900b6-191">Type</span></span>
    - <span data-ttu-id="900b6-192">El título</span><span class="sxs-lookup"><span data-stu-id="900b6-192">Title</span></span>
    - <span data-ttu-id="900b6-193">AccountId</span><span class="sxs-lookup"><span data-stu-id="900b6-193">AccountId</span></span>
    - <span data-ttu-id="900b6-194">AccountName</span><span class="sxs-lookup"><span data-stu-id="900b6-194">AccountName</span></span>
    - <span data-ttu-id="900b6-195">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="900b6-195">AccountUrl</span></span>
    - <span data-ttu-id="900b6-196">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="900b6-196">AccountOwner</span></span>
    - <span data-ttu-id="900b6-197">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="900b6-197">AccountOwnerUrl</span></span>
    - <span data-ttu-id="900b6-198">Owner</span><span class="sxs-lookup"><span data-stu-id="900b6-198">Owner</span></span>
    - <span data-ttu-id="900b6-199">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="900b6-199">OwnerUrl</span></span>
    - <span data-ttu-id="900b6-200">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="900b6-200">CreatedBy</span></span> 
    - <span data-ttu-id="900b6-201">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="900b6-201">CreatedByUrl</span></span> 
    - <span data-ttu-id="900b6-202">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="900b6-202">LastModifiedBy</span></span> 
    - <span data-ttu-id="900b6-203">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="900b6-203">LastModifiedByUrl</span></span> 
    - <span data-ttu-id="900b6-204">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="900b6-204">LastModifiedDate</span></span>
    - <span data-ttu-id="900b6-205">ObjectName</span><span class="sxs-lookup"><span data-stu-id="900b6-205">ObjectName</span></span> 
