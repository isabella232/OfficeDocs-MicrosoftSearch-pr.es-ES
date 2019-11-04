---
title: Crear marcadores en masa
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
ROBOTS: NoIndex
description: Crear muchos marcadores a la vez con herramientas de importación para el portal de administración de Microsoft Search
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948928"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="b5ff2-103">Crear marcadores en masa</span><span class="sxs-lookup"><span data-stu-id="b5ff2-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5ff2-104">Este artículo se aplica al portal de administración de Búsqueda de Microsoft en Bing.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="b5ff2-105">Estamos pasando el portal al Centro de administración de Microsoft 365. Luego, se quitará el portal de Búsqueda de Microsoft en Bing.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="b5ff2-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="b5ff2-107">[Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="b5ff2-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="b5ff2-108">Descargue y use la plantilla. csv para crear, editar y guardar marcadores de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-108">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="b5ff2-109">Para editar de forma masiva los marcadores existentes, expórtelo del portal de administración, realice las modificaciones necesarias y, a continuación, impórtelas.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-109">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="b5ff2-110">En la esquina superior derecha de la sección Marcadores, haga clic en **importar**</span><span class="sxs-lookup"><span data-stu-id="b5ff2-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="b5ff2-111">Haga clic en **Descargar plantilla de marcadores (. csv)**</span><span class="sxs-lookup"><span data-stu-id="b5ff2-111">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="b5ff2-112">Guarde y abra el archivo .csv</span><span class="sxs-lookup"><span data-stu-id="b5ff2-112">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="b5ff2-113">Agregar el contenido y la configuración del marcador y guardar el archivo</span><span class="sxs-lookup"><span data-stu-id="b5ff2-113">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="b5ff2-114">El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación</span><span class="sxs-lookup"><span data-stu-id="b5ff2-114">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="b5ff2-115">En la esquina superior derecha de la sección Marcadores, haga clic en **importar**</span><span class="sxs-lookup"><span data-stu-id="b5ff2-115">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="b5ff2-116">En el panel importar marcadores, haga clic en **examinar** y navegue hasta el archivo. csv que desea importar.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-116">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="b5ff2-117">Haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="b5ff2-117">Click **Import**</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="b5ff2-118">Evitar errores de importación</span><span class="sxs-lookup"><span data-stu-id="b5ff2-118">Prevent import errors</span></span>      
<span data-ttu-id="b5ff2-119">Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="b5ff2-120">Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="b5ff2-121">Realice los cambios necesarios e intente importar de nuevo el archivo.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-121">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="b5ff2-122">Hasta que se resuelvan todos los errores, no podrá crear ni editar ningún marcador.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-122">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="b5ff2-123">Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:</span><span class="sxs-lookup"><span data-stu-id="b5ff2-123">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="b5ff2-124">Incluye la fila de encabezado que se encontraba en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="b5ff2-124">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="b5ff2-125">Incluye todas las columnas que se encontraban en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="b5ff2-125">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="b5ff2-126">El orden de las columnas es el mismo que el orden en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="b5ff2-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="b5ff2-127">Estas columnas pueden estar vacías: Id., Última modificación y Última modificación realizada por</span><span class="sxs-lookup"><span data-stu-id="b5ff2-127">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="b5ff2-128">La columna Estado no puede estar vacía, puesto que esta información es necesaria</span><span class="sxs-lookup"><span data-stu-id="b5ff2-128">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="b5ff2-129">En función del campo Estado, los marcadores se guardarán como borradores, sugeridos o programados, o se publicarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-129">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="b5ff2-130">Además, si incluye el identificador de un marcador existente, se reemplazará con la información del archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-130">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="b5ff2-131">Para los socios que administran varias organizaciones, puede exportar sus marcadores de una organización e importarlos en otro.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-131">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="b5ff2-132">Pero, debe eliminar todos los datos de la columna Id. antes de la importación.</span><span class="sxs-lookup"><span data-stu-id="b5ff2-132">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="b5ff2-133">Para obtener más información sobre los campos obligatorios y recomendados, vea [Create bookmarks](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="b5ff2-133">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
