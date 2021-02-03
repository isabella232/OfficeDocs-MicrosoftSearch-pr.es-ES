---
title: Conector de Gráfico de recurso compartido de archivos para Microsoft Search
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
ROBOTS: NoIndex
description: Configurar el conector de Gráfico de recurso compartido de archivos para Microsoft Search
ms.openlocfilehash: ae496d0a1f41dc75326b0f7ab96e54bda4ee879e
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084852"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="8752d-103">Conector de Gráfico de recurso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="8752d-103">File share Graph connector</span></span>

<span data-ttu-id="8752d-104">El conector de Gráfico de recursos compartidos de archivos permite a los usuarios de su organización buscar recursos compartidos de archivos locales de Windows.</span><span class="sxs-lookup"><span data-stu-id="8752d-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="8752d-105">Lea el [**artículo sobre el programa de instalación del conector de Graph**](configure-connector.md) para comprender el proceso de configuración general de los conectores de Graph.</span><span class="sxs-lookup"><span data-stu-id="8752d-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="8752d-106">Este artículo está dirigido a cualquier persona que configure, ejecute y monitore un conector de ServiceNow Graph.</span><span class="sxs-lookup"><span data-stu-id="8752d-106">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="8752d-107">Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="8752d-107">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="8752d-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="8752d-108">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="8752d-109">Instalar el agente de conector de Graph</span><span class="sxs-lookup"><span data-stu-id="8752d-109">Install the Graph connector agent</span></span>

<span data-ttu-id="8752d-110">Para indizar los recursos compartidos de archivos de Windows, debe instalar y registrar el agente del conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="8752d-110">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="8752d-111">Consulte [Instalar el agente del conector de Graph](on-prem-agent.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8752d-111">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="8752d-112">Requisitos de contenido</span><span class="sxs-lookup"><span data-stu-id="8752d-112">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="8752d-113">Tipos de archivo</span><span class="sxs-lookup"><span data-stu-id="8752d-113">File types</span></span>

<span data-ttu-id="8752d-114">Se puede indizar y buscar contenido de los siguientes formatos: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS y ZIP.</span><span class="sxs-lookup"><span data-stu-id="8752d-114">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="8752d-115">Solo se indiza el contenido textual de estos formatos.</span><span class="sxs-lookup"><span data-stu-id="8752d-115">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="8752d-116">Se omite todo el contenido multimedia.</span><span class="sxs-lookup"><span data-stu-id="8752d-116">All multimedia content is ignored.</span></span> <span data-ttu-id="8752d-117">Para cualquier archivo que no pertenezca a este formato, solo se indizan los metadatos.</span><span class="sxs-lookup"><span data-stu-id="8752d-117">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="8752d-118">Límites de tamaño de archivo</span><span class="sxs-lookup"><span data-stu-id="8752d-118">File size limits</span></span>

<span data-ttu-id="8752d-119">El tamaño máximo de archivo admitido es de 100 MB.</span><span class="sxs-lookup"><span data-stu-id="8752d-119">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="8752d-120">Los archivos que superan los 100 MB no se indizan.</span><span class="sxs-lookup"><span data-stu-id="8752d-120">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="8752d-121">El límite de tamaño máximo posterior al proceso es de 4 MB.</span><span class="sxs-lookup"><span data-stu-id="8752d-121">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="8752d-122">El procesamiento se detiene cuando el tamaño de un archivo alcanza los 4 MB.</span><span class="sxs-lookup"><span data-stu-id="8752d-122">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="8752d-123">Por lo tanto, es posible que algunas frases presentes en el archivo no funcionen para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8752d-123">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="8752d-124">Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8752d-124">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="8752d-125">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8752d-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="8752d-126">Paso 2: Nombrar la conexión</span><span class="sxs-lookup"><span data-stu-id="8752d-126">Step 2: Name the connection</span></span>

<span data-ttu-id="8752d-127">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8752d-127">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="8752d-128">Paso 3: Configurar las opciones de conexión</span><span class="sxs-lookup"><span data-stu-id="8752d-128">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="8752d-129">En la **página Conectar con origen de** datos, seleccione Recurso **compartido** de archivos y proporcione el nombre, el identificador de conexión y la descripción.</span><span class="sxs-lookup"><span data-stu-id="8752d-129">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="8752d-130">En la página siguiente, proporcione la ruta de acceso al recurso compartido de archivos y seleccione el agente de conector de Graph instalado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8752d-130">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="8752d-131">Escribe las credenciales de una cuenta [de usuario de Microsoft Windows](https://microsoft.com/windows) con acceso de lectura a todos los archivos del recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="8752d-131">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="8752d-132">Conservar el último tiempo de acceso</span><span class="sxs-lookup"><span data-stu-id="8752d-132">Preserve last access time</span></span>

<span data-ttu-id="8752d-133">Cuando el conector intenta rastrear un archivo, se actualiza el campo "hora de último acceso" en sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="8752d-133">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="8752d-134">Si depende de ese campo para las soluciones de archivado y copia de seguridad y no desea actualizarlo cuando el conector tiene acceso a él, puede configurar esta opción en la página Configuración **avanzada.**</span><span class="sxs-lookup"><span data-stu-id="8752d-134">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="8752d-135">Paso 4: Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="8752d-135">Step 4: Manage search permissions</span></span>

<span data-ttu-id="8752d-136">Puede restringir el permiso para buscar cualquier archivo basado en listas de control de acceso compartido o listas de control de acceso del Sistema de archivos de nueva tecnología (NTFS).</span><span class="sxs-lookup"><span data-stu-id="8752d-136">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="8752d-137">Si desea usar Compartir listas de control de acceso, seleccione la opción adecuada en la **página Configuración** avanzada.</span><span class="sxs-lookup"><span data-stu-id="8752d-137">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="8752d-138">Si desea usar listas de control de acceso NTFS, seleccione la opción adecuada en la página Administrar permisos **de** búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8752d-138">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="8752d-139">Paso 5: Asignar etiquetas de propiedad</span><span class="sxs-lookup"><span data-stu-id="8752d-139">Step 5: Assign property labels</span></span>

<span data-ttu-id="8752d-140">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8752d-140">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="8752d-141">Paso 6: Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="8752d-141">Step 6: Manage schema</span></span>

<span data-ttu-id="8752d-142">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8752d-142">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="8752d-143">Paso 7: Elegir la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="8752d-143">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="8752d-144">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8752d-144">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="8752d-145">Paso 8: Revisar la conexión</span><span class="sxs-lookup"><span data-stu-id="8752d-145">Step 8: Review connection</span></span>

<span data-ttu-id="8752d-146">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8752d-146">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
