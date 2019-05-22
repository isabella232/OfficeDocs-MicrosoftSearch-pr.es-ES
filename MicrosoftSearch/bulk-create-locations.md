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
description: Agregue varias ubicaciones a la vez con las herramientas de importación para el portal de administración de Búsqueda de Microsoft
ms.openlocfilehash: 1d360fda2851083def0bcbd8fcffd77cfa15240e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968295"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="c3b85-103">Crear ubicaciones en masa</span><span class="sxs-lookup"><span data-stu-id="c3b85-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3b85-104">Búsqueda de Microsoft en la configuración de Bing ya está disponible en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3b85-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c3b85-105">Empiece por [asignar administradores de búsqueda](https://docs.microsoft.com/es-ES/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="c3b85-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="c3b85-106">Descargue y use la plantilla .csv para crear, editar y guardar ubicaciones en masa.</span><span class="sxs-lookup"><span data-stu-id="c3b85-106">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="c3b85-107">En la esquina superior derecha de la sección Ubicaciones, haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="c3b85-107">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="c3b85-108">Haga clic en **Descargar plantilla de ubicaciones (.csv)**</span><span class="sxs-lookup"><span data-stu-id="c3b85-108">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="c3b85-109">Guarde y abra el archivo .csv</span><span class="sxs-lookup"><span data-stu-id="c3b85-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="c3b85-110">Agregue el contenido de la ubicación y guarde el archivo</span><span class="sxs-lookup"><span data-stu-id="c3b85-110">Add the location content and save the file</span></span>

    <span data-ttu-id="c3b85-111">El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación</span><span class="sxs-lookup"><span data-stu-id="c3b85-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="c3b85-112">En la esquina superior derecha de la sección Ubicaciones, haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="c3b85-112">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="c3b85-113">En el panel Importar ubicaciones, haga clic en **Examinar** y vaya al archivo .csv que quiere importar</span><span class="sxs-lookup"><span data-stu-id="c3b85-113">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="c3b85-114">Haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="c3b85-114">Click **Import**.</span></span>

<span data-ttu-id="c3b85-115">Los campos de las plantillas de ubicaciones de importación y exportación son los mismos.</span><span class="sxs-lookup"><span data-stu-id="c3b85-115">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="c3b85-116">Puede exportar, editar en masa e importar los cambios, o bien puede empezar con una plantilla vacía para crear nuevas ubicaciones en masa.</span><span class="sxs-lookup"><span data-stu-id="c3b85-116">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="c3b85-117">Si necesita editar en masa ubicaciones existentes, expórtelas desde el Portal de administración, haga los cambios necesarios y, después, impórtelas.</span><span class="sxs-lookup"><span data-stu-id="c3b85-117">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="c3b85-118">Evitar errores de importación</span><span class="sxs-lookup"><span data-stu-id="c3b85-118">Prevent import errors</span></span>  
<span data-ttu-id="c3b85-119">Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="c3b85-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="c3b85-120">Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="c3b85-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="c3b85-121">Realice los cambios necesarios e intente importar de nuevo el archivo.</span><span class="sxs-lookup"><span data-stu-id="c3b85-121">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3b85-122">Hasta que se resuelvan todos los errores, no podrá crear o editar las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="c3b85-122">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="c3b85-123">Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:</span><span class="sxs-lookup"><span data-stu-id="c3b85-123">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="c3b85-124">Incluye la fila de encabezado que se encontraba en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="c3b85-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="c3b85-125">Incluye todas las columnas que se encontraban en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="c3b85-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="c3b85-126">El orden de las columnas es el mismo que el orden en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="c3b85-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="c3b85-127">Estas columnas pueden estar vacías: Id., Última modificación, Última modificación realizada por y Lat/Long</span><span class="sxs-lookup"><span data-stu-id="c3b85-127">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="c3b85-128">Si el campo está vacío, intentaremos determinar lat/long en función de la dirección</span><span class="sxs-lookup"><span data-stu-id="c3b85-128">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="c3b85-129">La columna Estado no puede estar vacía, puesto que esta información es necesaria</span><span class="sxs-lookup"><span data-stu-id="c3b85-129">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="c3b85-130">En función del campo Estado, las ubicaciones se guardarán como borradores, sugeridas o programadas, o se publicarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c3b85-130">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="c3b85-131">Además, si incluye el Id. de una ubicación existente, este se reemplazará con la información del archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="c3b85-131">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="c3b85-132">Para organizaciones con múltiples espacios empresariales, se pueden exportar las ubicaciones de un espacio empresarial e importarlas en otro.</span><span class="sxs-lookup"><span data-stu-id="c3b85-132">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="c3b85-133">Pero, debe eliminar todos los datos de la columna Id. antes de la importación.</span><span class="sxs-lookup"><span data-stu-id="c3b85-133">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="c3b85-134">Para obtener más información sobre los campos necesarios y recomendados, vea [Agregar una ubicación](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="c3b85-134">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

