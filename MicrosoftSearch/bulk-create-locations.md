---
title: Crear ubicaciones en masa
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
description: Agregue varias ubicaciones a la vez con las herramientas de importación para el portal de administración de Búsqueda de Microsoft
ms.openlocfilehash: 186f6973de1ff87b62b5f07a47eb41acdd842010
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591399"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="39ae3-103">Crear ubicaciones en masa</span><span class="sxs-lookup"><span data-stu-id="39ae3-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39ae3-104">Este artículo se aplica al portal de administración de Búsqueda de Microsoft in Bing.</span><span class="sxs-lookup"><span data-stu-id="39ae3-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="39ae3-105">Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se quitará.</span><span class="sxs-lookup"><span data-stu-id="39ae3-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="39ae3-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="39ae3-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="39ae3-107">[Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="39ae3-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="39ae3-108">Descargue y use la plantilla .csv para crear, editar y guardar ubicaciones en masa.</span><span class="sxs-lookup"><span data-stu-id="39ae3-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="39ae3-109">En la esquina superior derecha de la sección Ubicaciones, haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="39ae3-109">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="39ae3-110">Haga clic en **Descargar plantilla de ubicaciones (.csv)**</span><span class="sxs-lookup"><span data-stu-id="39ae3-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="39ae3-111">Guarde y abra el archivo .csv</span><span class="sxs-lookup"><span data-stu-id="39ae3-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="39ae3-112">Agregue el contenido de la ubicación y guarde el archivo</span><span class="sxs-lookup"><span data-stu-id="39ae3-112">Add the location content and save the file</span></span>

    <span data-ttu-id="39ae3-113">El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación</span><span class="sxs-lookup"><span data-stu-id="39ae3-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="39ae3-114">En la esquina superior derecha de la sección Ubicaciones, haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="39ae3-114">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="39ae3-115">En el panel Importar ubicaciones, haga clic en **Examinar** y vaya al archivo .csv que quiere importar</span><span class="sxs-lookup"><span data-stu-id="39ae3-115">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="39ae3-116">Haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="39ae3-116">Click **Import**.</span></span>

<span data-ttu-id="39ae3-117">Los campos de las plantillas de ubicaciones de importación y exportación son los mismos.</span><span class="sxs-lookup"><span data-stu-id="39ae3-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="39ae3-118">Puede exportar, editar en masa e importar los cambios, o bien puede empezar con una plantilla vacía para crear nuevas ubicaciones en masa.</span><span class="sxs-lookup"><span data-stu-id="39ae3-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="39ae3-119">Si necesita editar en masa ubicaciones existentes, expórtelas desde el Portal de administración, haga los cambios necesarios y, después, impórtelas.</span><span class="sxs-lookup"><span data-stu-id="39ae3-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="39ae3-120">Evitar errores de importación</span><span class="sxs-lookup"><span data-stu-id="39ae3-120">Prevent import errors</span></span>  
<span data-ttu-id="39ae3-121">Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="39ae3-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="39ae3-122">Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="39ae3-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="39ae3-123">Realice los cambios necesarios e intente importar de nuevo el archivo.</span><span class="sxs-lookup"><span data-stu-id="39ae3-123">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39ae3-124">Hasta que se resuelvan todos los errores, no podrá crear o editar las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="39ae3-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="39ae3-125">Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:</span><span class="sxs-lookup"><span data-stu-id="39ae3-125">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="39ae3-126">Incluye la fila de encabezado que se encontraba en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="39ae3-126">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="39ae3-127">Incluye todas las columnas que se encontraban en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="39ae3-127">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="39ae3-128">El orden de las columnas es el mismo que el orden en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="39ae3-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="39ae3-129">Estas columnas pueden estar vacías: Id., Última modificación, Última modificación realizada por y Lat/Long</span><span class="sxs-lookup"><span data-stu-id="39ae3-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="39ae3-130">Si el campo está vacío, intentaremos determinar lat/long en función de la dirección</span><span class="sxs-lookup"><span data-stu-id="39ae3-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="39ae3-131">La columna Estado no puede estar vacía, puesto que esta información es necesaria</span><span class="sxs-lookup"><span data-stu-id="39ae3-131">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="39ae3-132">En función del campo Estado, las ubicaciones se guardarán como borradores, sugeridas o programadas, o se publicarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="39ae3-132">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="39ae3-133">Además, si incluye el Id. de una ubicación existente, este se reemplazará con la información del archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="39ae3-133">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="39ae3-134">Para organizaciones con múltiples espacios empresariales, se pueden exportar las ubicaciones de un espacio empresarial e importarlas en otro.</span><span class="sxs-lookup"><span data-stu-id="39ae3-134">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="39ae3-135">Pero, debe eliminar todos los datos de la columna Id. antes de la importación.</span><span class="sxs-lookup"><span data-stu-id="39ae3-135">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="39ae3-136">Para obtener más información sobre los campos necesarios y recomendados, vea [Agregar una ubicación](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="39ae3-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

