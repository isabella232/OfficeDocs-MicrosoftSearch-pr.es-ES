---
title: Conector de uso compartido de archivos
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurar el conector de recurso compartido de archivos para Microsoft Search
ms.openlocfilehash: a95cfe90ca35a385bb9ce3a4c565c18c5a42ec80
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408937"
---
# <a name="file-share-connector"></a><span data-ttu-id="71fd7-103">Conector de uso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="71fd7-103">File share connector</span></span>

<span data-ttu-id="71fd7-104">Con el conector de archivo del gráfico de archivos compartidos, los usuarios de la organización pueden buscar recursos compartidos de archivos de Windows locales.</span><span class="sxs-lookup"><span data-stu-id="71fd7-104">With the File share Graph connector, users in your organization can search on-premise Windows file shares.</span></span>

<span data-ttu-id="71fd7-105">Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de recursos compartidos de archivos.</span><span class="sxs-lookup"><span data-stu-id="71fd7-105">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a file share connector.</span></span> <span data-ttu-id="71fd7-106">Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="71fd7-106">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-graph-connector-agent"></a><span data-ttu-id="71fd7-107">Instalar el agente de conector de Graph</span><span class="sxs-lookup"><span data-stu-id="71fd7-107">Install Graph connector agent</span></span>

<span data-ttu-id="71fd7-108">Para indizar los recursos compartidos de archivos de Windows, debe instalar y registrar el software del [agente de conector de Graph](on-prem-agent.md) .</span><span class="sxs-lookup"><span data-stu-id="71fd7-108">In order to index your Windows file shares, you must install and register [Graph connector agent](on-prem-agent.md) software.</span></span>

## <a name="content-requirements"></a><span data-ttu-id="71fd7-109">Requisitos de contenido</span><span class="sxs-lookup"><span data-stu-id="71fd7-109">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="71fd7-110">Tipos de archivo</span><span class="sxs-lookup"><span data-stu-id="71fd7-110">File types</span></span>

<span data-ttu-id="71fd7-111">Se puede indizar y buscar el contenido de los siguientes formatos: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, DAB, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS y ZIP.</span><span class="sxs-lookup"><span data-stu-id="71fd7-111">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="71fd7-112">Solo se indiza el contenido textual de estos formatos.</span><span class="sxs-lookup"><span data-stu-id="71fd7-112">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="71fd7-113">Se omite todo el contenido multimedia.</span><span class="sxs-lookup"><span data-stu-id="71fd7-113">All multimedia content is ignored.</span></span> <span data-ttu-id="71fd7-114">En el caso de los archivos que no pertenecen a este formato, los metadatos se indizan por sí solos.</span><span class="sxs-lookup"><span data-stu-id="71fd7-114">For any file that does not belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="71fd7-115">Límites de tamaño de archivo</span><span class="sxs-lookup"><span data-stu-id="71fd7-115">File size limits</span></span>

<span data-ttu-id="71fd7-116">El tamaño máximo de archivo admitido es 100 MB.</span><span class="sxs-lookup"><span data-stu-id="71fd7-116">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="71fd7-117">Los archivos que superan los 100 MB no se indizan.</span><span class="sxs-lookup"><span data-stu-id="71fd7-117">Files that exceed 100 MB are not indexed.</span></span> <span data-ttu-id="71fd7-118">El límite de tamaño posterior al proceso es de 4 MB.</span><span class="sxs-lookup"><span data-stu-id="71fd7-118">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="71fd7-119">El procesamiento se detiene cuando el tamaño de un archivo alcanza 4 MB.</span><span class="sxs-lookup"><span data-stu-id="71fd7-119">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="71fd7-120">Por lo tanto, es posible que algunas frases presentes en el archivo no funcionen para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="71fd7-120">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="71fd7-121">Conectarse a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="71fd7-121">Connect to a data source</span></span>

<span data-ttu-id="71fd7-122">En la página **conectar con origen de datos** , seleccione **recurso compartido de archivos** y proporcione el nombre, el identificador de conexión y la descripción.</span><span class="sxs-lookup"><span data-stu-id="71fd7-122">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="71fd7-123">En la página siguiente, especifique la ruta de acceso al recurso compartido de archivos y seleccione el agente de conectores de Graph instalado previamente.</span><span class="sxs-lookup"><span data-stu-id="71fd7-123">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="71fd7-124">Escriba las credenciales de una cuenta de usuario de [Microsoft Windows](https://microsoft.com/windows) con acceso de lectura a todos los archivos en el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="71fd7-124">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

## <a name="preserve-last-access-time"></a><span data-ttu-id="71fd7-125">Conservar la hora del último acceso</span><span class="sxs-lookup"><span data-stu-id="71fd7-125">Preserve last access time</span></span>

<span data-ttu-id="71fd7-126">Cuando el conector intenta rastrear un archivo, se actualiza el campo "hora del último acceso" en sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="71fd7-126">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="71fd7-127">Si depende de ese campo para cualquier solución de archivado y copia de seguridad y no desea actualizarlo cuando el conector tenga acceso a él, puede configurar esta opción en la página **Configuración avanzada** .</span><span class="sxs-lookup"><span data-stu-id="71fd7-127">If you depend on that field for any archiving and backup solutions and do not want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="71fd7-128">Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="71fd7-128">Manage search permissions</span></span>

<span data-ttu-id="71fd7-129">Puede restringir el permiso para buscar cualquier archivo basado en compartir listas de control de acceso o en listas de control de acceso del sistema de archivos de tecnología (NTFS).</span><span class="sxs-lookup"><span data-stu-id="71fd7-129">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="71fd7-130">Si desea usar compartir listas de control de acceso, seleccione la opción adecuada en la página **Configuración avanzada** .</span><span class="sxs-lookup"><span data-stu-id="71fd7-130">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="71fd7-131">Si desea usar las listas de control de acceso de NTFS, seleccione la opción correspondiente en la página **administrar permisos de búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="71fd7-131">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="71fd7-132">Asignar etiquetas de propiedad</span><span class="sxs-lookup"><span data-stu-id="71fd7-132">Assign property labels</span></span>

<span data-ttu-id="71fd7-133">Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones.</span><span class="sxs-lookup"><span data-stu-id="71fd7-133">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="71fd7-134">Aunque este paso no es obligatorio, tener algunas etiquetas de propiedades mejorará la relevancia de la búsqueda y garantizará resultados de búsqueda más precisos para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="71fd7-134">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="71fd7-135">Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="71fd7-135">Manage schema</span></span>

<span data-ttu-id="71fd7-136">En la pantalla **administrar esquema** , tiene la opción de cambiar los atributos de esquema (**consultable**, **búsquedas**, **recuperables** y **refinables**) asociados con las propiedades, agregar alias opcionales y elegir la propiedad de **contenido** .</span><span class="sxs-lookup"><span data-stu-id="71fd7-136">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="71fd7-137">Establecer la programación de actualización</span><span class="sxs-lookup"><span data-stu-id="71fd7-137">Set the refresh schedule</span></span>

<span data-ttu-id="71fd7-138">El intervalo de programación de actualización predeterminada recomendado es de 15 minutos, pero puede cambiarlo según sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="71fd7-138">The recommended default refresh schedule interval is 15 minutes, but you can change it based on your preferences.</span></span>
