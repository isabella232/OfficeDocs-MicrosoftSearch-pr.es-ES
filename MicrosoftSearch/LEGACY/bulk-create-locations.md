---
title: Crear ubicaciones de forma masiva
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
ROBOTS: NoIndex
description: Agregar muchas ubicaciones a la vez con herramientas de importación para el portal de administración de Microsoft Search
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311913"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="34485-103">Crear ubicaciones de forma masiva</span><span class="sxs-lookup"><span data-stu-id="34485-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34485-104">Este artículo se aplica al portal de administración de Búsqueda de Microsoft en Bing.</span><span class="sxs-lookup"><span data-stu-id="34485-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="34485-105">Estamos pasando el portal al Centro de administración de Microsoft 365. Luego, se quitará el portal de Búsqueda de Microsoft en Bing.</span><span class="sxs-lookup"><span data-stu-id="34485-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="34485-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="34485-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="34485-107">[Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="34485-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="34485-108">Descargue y use la plantilla. csv para crear, editar y guardar ubicaciones en masa.</span><span class="sxs-lookup"><span data-stu-id="34485-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="34485-109">En la esquina superior derecha de la sección ubicaciones, haga clic en **importar** .</span><span class="sxs-lookup"><span data-stu-id="34485-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="34485-110">Haga clic en **Descargar ubicación de plantilla (. csv)**</span><span class="sxs-lookup"><span data-stu-id="34485-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="34485-111">Guarde y abra el archivo .csv</span><span class="sxs-lookup"><span data-stu-id="34485-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="34485-112">Agregar el contenido de ubicación y guardar el archivo</span><span class="sxs-lookup"><span data-stu-id="34485-112">Add the location content and save the file</span></span>

    <span data-ttu-id="34485-113">El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación</span><span class="sxs-lookup"><span data-stu-id="34485-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="34485-114">En la esquina superior derecha de la sección ubicaciones, haga clic en **importar** .</span><span class="sxs-lookup"><span data-stu-id="34485-114">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="34485-115">En el panel ubicaciones de importación, haga clic en **examinar** y navegue hasta el archivo. csv que desea importar.</span><span class="sxs-lookup"><span data-stu-id="34485-115">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="34485-116">Haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="34485-116">Click **Import**</span></span>

<span data-ttu-id="34485-117">Los campos de las plantillas de ubicaciones de importación y exportación son los mismos.</span><span class="sxs-lookup"><span data-stu-id="34485-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="34485-118">Puede exportar, editar en masa e importar las ediciones o empezar con una plantilla vacía para crear en masa nuevas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="34485-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="34485-119">Para editar en masa las ubicaciones existentes, exportas del portal de administración, realice las modificaciones necesarias y, a continuación, impórtelas.</span><span class="sxs-lookup"><span data-stu-id="34485-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="34485-120">Evitar errores de importación</span><span class="sxs-lookup"><span data-stu-id="34485-120">Prevent import errors</span></span>  
<span data-ttu-id="34485-121">Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="34485-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="34485-122">Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="34485-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="34485-123">Realice los cambios necesarios e intente importar de nuevo el archivo.</span><span class="sxs-lookup"><span data-stu-id="34485-123">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34485-124">Hasta que se resuelvan todos los errores, no podrá crear ni editar ninguna ubicación.</span><span class="sxs-lookup"><span data-stu-id="34485-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="34485-125">Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:</span><span class="sxs-lookup"><span data-stu-id="34485-125">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="34485-126">Incluye la fila de encabezado que se encontraba en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="34485-126">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="34485-127">Incluye todas las columnas que se encontraban en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="34485-127">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="34485-128">El orden de las columnas es el mismo que el orden en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="34485-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="34485-129">Estas columnas pueden estar vacías: ID, última modificación, última modificación por y lat/long</span><span class="sxs-lookup"><span data-stu-id="34485-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="34485-130">Intentaremos determinar lat/long en función de la dirección si el campo está vacío</span><span class="sxs-lookup"><span data-stu-id="34485-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="34485-131">La columna Estado no puede estar vacía, puesto que esta información es necesaria</span><span class="sxs-lookup"><span data-stu-id="34485-131">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="34485-132">Según el campo de estado, las ubicaciones se guardarán como borrador, sugerida, programada o se publicarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="34485-132">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="34485-133">Además, si incluye el identificador de una ubicación existente, se reemplazará con la información del archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="34485-133">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="34485-134">Para los asociados que administran varias organizaciones, puede exportar sus ubicaciones de una organización e importarlas a otra.</span><span class="sxs-lookup"><span data-stu-id="34485-134">For partners who manage multiple organizations, you can export your locations from one org and import them into another.</span></span> <span data-ttu-id="34485-135">Pero, debe eliminar todos los datos de la columna Id. antes de la importación.</span><span class="sxs-lookup"><span data-stu-id="34485-135">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="34485-136">Para obtener más información acerca de los campos obligatorios y recomendados, vea [Agregar una ubicación](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="34485-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

