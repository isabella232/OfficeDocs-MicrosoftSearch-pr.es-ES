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
description: Agregar muchas ubicaciones a la vez con herramientas de importación para el portal de administración de Microsoft Search
ms.openlocfilehash: eb51b93ceaa560e5142ac46d316ba745c614fe34
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068414"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="8f938-103">Crear ubicaciones de forma masiva</span><span class="sxs-lookup"><span data-stu-id="8f938-103">Bulk create locations</span></span>

<span data-ttu-id="8f938-104">Descargue y use la plantilla. csv para crear, editar y guardar ubicaciones en masa.</span><span class="sxs-lookup"><span data-stu-id="8f938-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="8f938-105">En la esquina superior derecha de la sección ubicaciones, haga clic en **importar** .</span><span class="sxs-lookup"><span data-stu-id="8f938-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="8f938-106">Haga clic en **Descargar ubicación de plantilla (. csv)**</span><span class="sxs-lookup"><span data-stu-id="8f938-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="8f938-107">Guardar y abrir el archivo. csv</span><span class="sxs-lookup"><span data-stu-id="8f938-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="8f938-108">Agregar el contenido de ubicación y guardar el archivo</span><span class="sxs-lookup"><span data-stu-id="8f938-108">Add the location content and save the file</span></span>
    
5. <span data-ttu-id="8f938-109">En la esquina superior derecha de la sección ubicaciones, haga clic en **importar** .</span><span class="sxs-lookup"><span data-stu-id="8f938-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="8f938-110">En el panel ubicaciones de importación, haga clic en **examinar** y navegue hasta el archivo. csv que desea importar.</span><span class="sxs-lookup"><span data-stu-id="8f938-110">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="8f938-111">Haga clic en **importar**</span><span class="sxs-lookup"><span data-stu-id="8f938-111">Click **Import**</span></span>

<span data-ttu-id="8f938-p101">Los campos de las plantillas de ubicaciones de importación y exportación son los mismos. Puede exportar, editar en masa e importar las ediciones o empezar con una plantilla vacía para crear en masa nuevas ubicaciones. Para editar en masa las ubicaciones existentes, exportas del portal de administración, realice las modificaciones necesarias y, a continuación, impórtelas.</span><span class="sxs-lookup"><span data-stu-id="8f938-p101">The fields in the import and export locations templates are the same. You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations. To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="8f938-115">Impedir errores de importación</span><span class="sxs-lookup"><span data-stu-id="8f938-115">Prevent import errors</span></span>  
<span data-ttu-id="8f938-p102">Recibirá un error si faltan datos necesarios o no son válidos. Según el error, es posible que se genere un archivo de registro con más información sobre las filas y las columnas que deben corregirse. Realice las modificaciones necesarias e intente importar el archivo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8f938-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f938-119">Hasta que se resuelvan todos los errores, no podrá crear ni editar ninguna ubicación.</span><span class="sxs-lookup"><span data-stu-id="8f938-119">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="8f938-120">Para ayudar a evitar errores, asegúrese de que el archivo de importación tiene el formato correcto:</span><span class="sxs-lookup"><span data-stu-id="8f938-120">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="8f938-121">Incluye la fila de encabezado que estaba en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="8f938-121">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="8f938-122">Incluye todas las columnas que estaban en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="8f938-122">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="8f938-123">El orden de las columnas es el mismo que el de la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="8f938-123">The column order is the same as the import template</span></span>
- <span data-ttu-id="8f938-124">Estas columnas pueden estar vacías: ID, última modificación, última modificación por y lat/long</span><span class="sxs-lookup"><span data-stu-id="8f938-124">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="8f938-125">Intentaremos determinar lat/long en función de la dirección si el campo está vacío</span><span class="sxs-lookup"><span data-stu-id="8f938-125">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="8f938-126">La columna Estado no puede estar vacía, se requiere esta información</span><span class="sxs-lookup"><span data-stu-id="8f938-126">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="8f938-127">Según el campo de estado, las ubicaciones se guardarán como borrador, sugerida, programada o se publicarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8f938-127">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="8f938-128">Además, si incluye el identificador de una ubicación existente, se reemplazará con la información del archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="8f938-128">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="8f938-p103">En el caso de organizaciones con varios inquilinos, puede exportar sus ubicaciones de un inquilino e importarlas a otro. Sin embargo, debe quitar todos los datos de la columna ID antes de importar.</span><span class="sxs-lookup"><span data-stu-id="8f938-p103">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="8f938-131">Para obtener más información acerca de los campos obligatorios y recomendados, vea [Agregar una ubicación](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="8f938-131">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

