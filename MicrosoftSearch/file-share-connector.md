---
title: Conector de recurso compartido de archivos para Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.date: 10/08/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de recursos compartidos de archivos para Microsoft Search.
ms.openlocfilehash: d5fbc1af2868ce7baa70017f617a9731340fb19a
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "37950031"
---
# <a name="file-share-connector"></a><span data-ttu-id="c49cb-103">Conector de uso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="c49cb-103">File share connector</span></span>

<span data-ttu-id="c49cb-104">Con el conector de recursos compartidos de archivos, los usuarios de la organización pueden buscar recursos compartidos de archivos locales.</span><span class="sxs-lookup"><span data-stu-id="c49cb-104">With the File share connector, users in your organization can search on-premises file shares.</span></span> <span data-ttu-id="c49cb-105">Los resultados de la búsqueda de estos recursos compartidos se combinan con los resultados de SharePoint y Microsoft OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="c49cb-105">The search results from these shares merge with the results from SharePoint and Microsoft OneDrive for Business.</span></span>

<span data-ttu-id="c49cb-106">Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de recursos compartidos de archivos.</span><span class="sxs-lookup"><span data-stu-id="c49cb-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a File share connector.</span></span> <span data-ttu-id="c49cb-107">Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="c49cb-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-a-data-gateway"></a><span data-ttu-id="c49cb-108">Instalar una puerta de enlace de datos</span><span class="sxs-lookup"><span data-stu-id="c49cb-108">Install a data gateway</span></span>
<span data-ttu-id="c49cb-109">Para obtener acceso a los datos de terceros, debe instalar y configurar una puerta de enlace de Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="c49cb-109">In order to access your third-party data, you must install and configure a Microsoft Power BI gateway.</span></span> <span data-ttu-id="c49cb-110">Consulte [instalar y la puerta de enlace local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c49cb-110">See [Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) to learn more.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="c49cb-111">Conectarse a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="c49cb-111">Connect to a data source</span></span>
<span data-ttu-id="c49cb-112">En la página **conectar a origen de datos** , cree una carpeta y proporcione una ruta de acceso al recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="c49cb-112">On the **Connect to data source** page, create a folder and provide a path to the file share.</span></span> <span data-ttu-id="c49cb-113">A continuación, seleccione la puerta de enlace instalada previamente.</span><span class="sxs-lookup"><span data-stu-id="c49cb-113">Then select your previously installed gateway.</span></span> <span data-ttu-id="c49cb-114">Escriba las credenciales de una cuenta de usuario de Windows con **acceso de lectura** a todos los archivos en el recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="c49cb-114">Enter the credentials for a Windows user account with **read access** to all the files in the share.</span></span> <span data-ttu-id="c49cb-115">A continuación, puede comprobar los archivos presentes en el recurso compartido y ver todos los metadatos recuperados.</span><span class="sxs-lookup"><span data-stu-id="c49cb-115">You can then verify the files present in the share and see all the fetched metadata.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="c49cb-116">Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="c49cb-116">Manage search permissions</span></span>
<span data-ttu-id="c49cb-117">El conector de recursos compartidos de archivos solo admite permisos de búsqueda visibles para **todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c49cb-117">The File share connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="c49cb-118">Los datos indizados aparecen en los resultados de la búsqueda y son visibles para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="c49cb-118">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="c49cb-119">Establecer la programación de actualización</span><span class="sxs-lookup"><span data-stu-id="c49cb-119">Set the refresh schedule</span></span>
<span data-ttu-id="c49cb-120">El intervalo de programación de actualización predeterminada recomendado es de 15 minutos, pero puede cambiarlo a otro intervalo que prefiera.</span><span class="sxs-lookup"><span data-stu-id="c49cb-120">The recommended default refresh schedule interval is 15 minutes, but you can change it to another interval that you prefer.</span></span>

## <a name="set-up-your-search-results-page"></a><span data-ttu-id="c49cb-121">Configurar la página de resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="c49cb-121">Set up your search results page</span></span>
<span data-ttu-id="c49cb-122">Para mostrar distintos resultados de conexión de archivos en las pestañas **todos** y **archivos** , debe configurar una página de resultados del motor de búsqueda de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="c49cb-122">To display different file connection results in the **All** and **Files** tabs, you need to set up a SharePoint search engine results page:</span></span>
- <span data-ttu-id="c49cb-123">La tabla **All** muestra los resultados combinados de las conexiones de archivos, archivos de SharePoint, archivos de OneDrive y sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c49cb-123">The **All** table shows combined results from your file connections, SharePoint files, OneDrive files, and SharePoint sites.</span></span> 
- <span data-ttu-id="c49cb-124">Los **archivos** verticales muestran todos los resultados de los archivos de las conexiones, SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c49cb-124">The **Files** vertical shows all file results from your connections, SharePoint, and OneDrive.</span></span>
<span data-ttu-id="c49cb-125">Los resultados de las conexiones de archivos se agregan a los resultados ya existentes en los verticales de **todos** los **archivos** y.</span><span class="sxs-lookup"><span data-stu-id="c49cb-125">Results from file connections are added to already existing results in both the **All** and **Files** verticals.</span></span>

<span data-ttu-id="c49cb-126">Para configurar la página de resultados de la búsqueda, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c49cb-126">To set up your search results page, take these steps:</span></span>
1. <span data-ttu-id="c49cb-127">Cree una colección de sitios de SharePoint con una página de búsqueda moderna.</span><span class="sxs-lookup"><span data-stu-id="c49cb-127">Create a SharePoint site collection with a modern search page.</span></span>

2. <span data-ttu-id="c49cb-128">Instale un [Shell de administración de SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).</span><span class="sxs-lookup"><span data-stu-id="c49cb-128">Install a [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

3. <span data-ttu-id="c49cb-129">Abra el shell de administración de SharePoint Online como administrador e importe el módulo **Microsoft. SharePoint. Client. dll** que se encuentra en `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.</span><span class="sxs-lookup"><span data-stu-id="c49cb-129">Open SharePoint Online Management Shell as an administrator and import the **Microsoft.SharePoint.Client.dll** module present at `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.</span></span>

> [!NOTE]
> <span data-ttu-id="c49cb-130">Esta ruta de acceso puede no ser la misma para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c49cb-130">This path might not be the same for all users.</span></span>

<span data-ttu-id="c49cb-131">Para importar el módulo, ejecute este comando en el shell de administración de SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="c49cb-131">To import the module, run this command in SharePoint Online Management Shell:</span></span>
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. <span data-ttu-id="c49cb-132">Ahora, ejecute este script:</span><span class="sxs-lookup"><span data-stu-id="c49cb-132">Now run this script:</span></span>
```bash
$orgName = Read-Host -prompt 'Please enter your org name'
$userName = Read-Host -prompt 'Enter user name'
$userCreds = Get-Credential -UserName $userName -Message "Type the password"
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCreds

$url = Read-Host -Prompt 'Please enter the site url'
$site = Get-SPOSite -Identity $url
Set-SPOSite $url -DenyAddAndCustomizePages 0

$pwd = Read-Host -AsSecureString 'type the password'
$context = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credential = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $pwd)
$context.Credentials = $credential
$web = $context.Web
$context.Load($web)
$web.AllProperties["AllVerticalContent"] = "Combined"
$web.Update()
$context.ExecuteQuery()
$web.AllProperties["FilesVerticalContent"] = "ConnectorsOnly"
$web.Update()
$context.ExecuteQuery()
Set-SPOSite $url -DenyAddAndCustomizePages 1

Write-Host "Success" -ForegroundColor Cyan
Read-Host -Prompt 'Press enter to exit'
```

5. <span data-ttu-id="c49cb-133">Escriba los valores necesarios en PowerShell, como el nombre de la organización, el nombre de usuario, la contraseña y la dirección URL del sitio.</span><span class="sxs-lookup"><span data-stu-id="c49cb-133">Enter the required values in PowerShell, such as organization name, username, password, and site URL.</span></span> <span data-ttu-id="c49cb-134">Por **ejemplo**, si las credenciales de administrador `admin@a830edad9050849823J19081300.onmicrosoft.com`son, el nombre de la organización es **a830edad9050849823J19081300**y la dirección URL `https:// a830edad9050849823J19081300.sharepoint.com`del sitio es.</span><span class="sxs-lookup"><span data-stu-id="c49cb-134">As an **example**, if your admin credentials are `admin@a830edad9050849823J19081300.onmicrosoft.com`, then your organization name is **a830edad9050849823J19081300**, and your site URL is `https:// a830edad9050849823J19081300.sharepoint.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="c49cb-135">La configuración **AllProperties** solo puede realizarse en un nivel de colección de sitios (Teams/commes).</span><span class="sxs-lookup"><span data-stu-id="c49cb-135">The **AllProperties** setting can only be done at a site collection level (Teams/Comms site).</span></span>

6. <span data-ttu-id="c49cb-136">Ahora puede buscar archivos indizados y ver los resultados en las pestañas **todos** y **archivos** .</span><span class="sxs-lookup"><span data-stu-id="c49cb-136">Now you can search for indexed files and see results in both the **All** and **Files** tabs.</span></span>

## <a name="search-for-file-share-content-in-the-search-results-page"></a><span data-ttu-id="c49cb-137">Buscar contenido de recurso compartido de archivos en la página de resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="c49cb-137">Search for file share content in the search results page</span></span>
<span data-ttu-id="c49cb-138">Para buscar contenido indizado, vaya a la Página principal de SharePoint de su inquilino de prueba.</span><span class="sxs-lookup"><span data-stu-id="c49cb-138">To search for indexed content, go to the SharePoint home page of your test tenant.</span></span> <span data-ttu-id="c49cb-139">Los resultados se mostrarán en las pestañas **todos** y **archivos** .</span><span class="sxs-lookup"><span data-stu-id="c49cb-139">Results will be displayed in the **All** and **Files** tabs.</span></span>

<span data-ttu-id="c49cb-140">Debido a las restricciones del explorador, no puede seleccionar un resultado de archivo para ver o abrir archivos en las búsquedas de recursos compartidos de archivos locales.</span><span class="sxs-lookup"><span data-stu-id="c49cb-140">Because of browser restrictions, you can't select a file result to view or open files from local file share searches.</span></span> <span data-ttu-id="c49cb-141">Para abrir estos archivos, copie el vínculo del resultado del archivo y péguelo en la barra de direcciones del explorador del sistema.</span><span class="sxs-lookup"><span data-stu-id="c49cb-141">To open these files, copy the file result's link and paste it into the address bar of your system's browser.</span></span> <span data-ttu-id="c49cb-142">Para Windows, use el explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="c49cb-142">For Windows, use Windows Explorer.</span></span> <span data-ttu-id="c49cb-143">A continuación, puede abrir el archivo en el sistema.</span><span class="sxs-lookup"><span data-stu-id="c49cb-143">Then you can open the file on your system.</span></span>

![Búsqueda de SharePoint con el cuadro de diálogo Copiar vínculo abierto.](media/fileshare-search.png)

## <a name="troubleshooting"></a><span data-ttu-id="c49cb-145">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="c49cb-145">Troubleshooting</span></span>
<span data-ttu-id="c49cb-146">Si algo es muy incorrecto en una conexión, su estado indica que **ha fallado**.</span><span class="sxs-lookup"><span data-stu-id="c49cb-146">If something is critically wrong with a connection, its status shows as **failed**.</span></span> <span data-ttu-id="c49cb-147">Para obtener más información acerca de los tres tipos de errores, vaya a la página de **detalles del error** y seleccione la conexión con error.</span><span class="sxs-lookup"><span data-stu-id="c49cb-147">To get more information on the three types of errors, go to the **error details** page and select the failing connection.</span></span> <span data-ttu-id="c49cb-148">Consulte [administrar el conector](manage-connector.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c49cb-148">See [Manage your connector](manage-connector.md) to learn more.</span></span>
1. <span data-ttu-id="c49cb-149">**No se puede obtener acceso a la puerta de enlace (código de error: 11)**.</span><span class="sxs-lookup"><span data-stu-id="c49cb-149">**Gateway not reachable (error code: 11)**.</span></span> <span data-ttu-id="c49cb-150">La máquina de la puerta de enlace para la conexión está inactiva.</span><span class="sxs-lookup"><span data-stu-id="c49cb-150">The gateway machine for the connection is down.</span></span> <span data-ttu-id="c49cb-151">Compruebe si el proceso de Microsoft Power BI se ejecuta en la máquina de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="c49cb-151">Verify if the Microsoft Power BI process runs on the gateway machine.</span></span>
2. <span data-ttu-id="c49cb-152">**Error de autenticación (código de error: 12)**.</span><span class="sxs-lookup"><span data-stu-id="c49cb-152">**Authentication error (error code: 12)**.</span></span> <span data-ttu-id="c49cb-153">Las credenciales usadas para crear la conexión expiraron o ya no son válidas.</span><span class="sxs-lookup"><span data-stu-id="c49cb-153">The credentials that were used for creating the connection expired or are no longer valid.</span></span> <span data-ttu-id="c49cb-154">Para resolver este error, escriba credenciales válidas.</span><span class="sxs-lookup"><span data-stu-id="c49cb-154">To resolve this error, enter valid credentials.</span></span>
3. <span data-ttu-id="c49cb-155">**Error interno (código de error: cualquier cosa que no sea 11 o 12)**.</span><span class="sxs-lookup"><span data-stu-id="c49cb-155">**Internal error (error code: anything other than 11 or 12)**.</span></span> <span data-ttu-id="c49cb-156">Hay un error en la infraestructura del conector.</span><span class="sxs-lookup"><span data-stu-id="c49cb-156">There's an error in the connector infrastructure.</span></span> <span data-ttu-id="c49cb-157">Vea el artículo de comentarios para obtener [información](connectors-feedback.md) sobre cómo informar de estos errores.</span><span class="sxs-lookup"><span data-stu-id="c49cb-157">See the [Feedback](connectors-feedback.md) article to find out how to report these errors.</span></span>

## <a name="limitations"></a><span data-ttu-id="c49cb-158">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="c49cb-158">Limitations</span></span>
<span data-ttu-id="c49cb-159">El conector de recursos compartidos de archivos tiene estas limitaciones en la versión preliminar:</span><span class="sxs-lookup"><span data-stu-id="c49cb-159">The File share connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="c49cb-160">Solo se pueden Indizar archivos con propiedades fijas, no con propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c49cb-160">You can only index files with fixed properties, not files with custom properties.</span></span>
* <span data-ttu-id="c49cb-161">Actualmente no se admiten las listas de control de acceso (ACL) del recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="c49cb-161">File share Access Control Lists (ACLs) aren't currently supported.</span></span>
* <span data-ttu-id="c49cb-162">Las identidades externas no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="c49cb-162">External identities aren't supported.</span></span> <span data-ttu-id="c49cb-163">Deben estar asignados a identidades de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c49cb-163">They must be mapped to Azure Active Directory identities.</span></span>