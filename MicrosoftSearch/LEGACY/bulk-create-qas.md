---
title: Crear preguntas y respuestas en masa
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
ROBOTS: NoIndex
description: Agregue rápidamente respuestas a las preguntas más frecuentes con herramientas de importación en el portal de administración de Búsqueda de Microsoft
ms.openlocfilehash: 660f5663ff6238f4ab59dab36d51f1311d5c7260
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311899"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="82c62-103">Crear preguntas y respuestas en masa</span><span class="sxs-lookup"><span data-stu-id="82c62-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82c62-104">Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing</span><span class="sxs-lookup"><span data-stu-id="82c62-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="82c62-105">Estamos pasando el portal al Centro de administración de Microsoft 365. Luego, se quitará el portal de Búsqueda de Microsoft en Bing.</span><span class="sxs-lookup"><span data-stu-id="82c62-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="82c62-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="82c62-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="82c62-107">[Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="82c62-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="82c62-108">Descargue y use la plantilla .csv para crear o editar preguntas y respuestas en masa.</span><span class="sxs-lookup"><span data-stu-id="82c62-108">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="82c62-109">También es una forma sencilla de guardar en masa los borradores de preguntas y respuestas que necesitan modificaciones adicionales o actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="82c62-109">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="82c62-110">Si necesita editar en masa preguntas y respuestas existentes, expórtelas desde el Portal de administración, haga los cambios necesarios y, luego, impórtelas.</span><span class="sxs-lookup"><span data-stu-id="82c62-110">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="82c62-111">En la esquina superior derecha de la sección de preguntas y respuestas, haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="82c62-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="82c62-112">Haga clic en **Descargar plantilla de preguntas y respuestas (.csv)**</span><span class="sxs-lookup"><span data-stu-id="82c62-112">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="82c62-113">Guarde y abra el archivo .csv</span><span class="sxs-lookup"><span data-stu-id="82c62-113">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="82c62-114">Agregue el contenido y la configuración de preguntas y respuestas y guarde el archivo</span><span class="sxs-lookup"><span data-stu-id="82c62-114">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="82c62-115">El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación</span><span class="sxs-lookup"><span data-stu-id="82c62-115">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="82c62-116">En la esquina superior derecha de la sección de preguntas y respuestas, haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="82c62-116">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="82c62-117">En el panel Importar preguntas y respuestas, haga clic en **Examinar** y vaya al archivo .csv que quiere importar</span><span class="sxs-lookup"><span data-stu-id="82c62-117">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="82c62-118">Haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="82c62-118">Click **Import**</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="82c62-119">Evitar errores de importación</span><span class="sxs-lookup"><span data-stu-id="82c62-119">Prevent import errors</span></span>      
<span data-ttu-id="82c62-120">Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="82c62-120">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="82c62-121">Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="82c62-121">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="82c62-122">Realice los cambios necesarios e intente importar de nuevo el archivo.</span><span class="sxs-lookup"><span data-stu-id="82c62-122">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="82c62-123">Hasta que se resuelvan todos los errores, no puede crear o editar las preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="82c62-123">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="82c62-124">Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:</span><span class="sxs-lookup"><span data-stu-id="82c62-124">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="82c62-125">Incluye la fila de encabezado que se encontraba en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="82c62-125">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="82c62-126">Incluye todas las columnas que se encontraban en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="82c62-126">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="82c62-127">El orden de las columnas es el mismo que el orden en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="82c62-127">The column order is the same as the import template</span></span>
- <span data-ttu-id="82c62-128">Estas columnas pueden estar vacías: Id., Última modificación y Última modificación realizada por</span><span class="sxs-lookup"><span data-stu-id="82c62-128">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="82c62-129">La columna Estado no puede estar vacía, puesto que esta información es necesaria</span><span class="sxs-lookup"><span data-stu-id="82c62-129">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="82c62-130">Según el campo Estado, las preguntas y respuestas se guardarán como borradores, sugeridas o programadas o se publicarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="82c62-130">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="82c62-131">Además, si incluye el Id. de preguntas y respuestas existentes, este se reemplazará con la información del archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="82c62-131">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="82c62-132">En el caso de los socios que administran varias organizaciones, puede exportar su&Q como de una organización e importarla a otra.</span><span class="sxs-lookup"><span data-stu-id="82c62-132">For partners who manage multiple organizations, you can export your Q&As from one org and import them into another.</span></span> <span data-ttu-id="82c62-133">Pero, debe eliminar todos los datos de la columna Id. antes de la importación.</span><span class="sxs-lookup"><span data-stu-id="82c62-133">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="82c62-134">Para obtener más información sobre los campos necesarios y recomendados, vea [Crear preguntas y respuestas](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="82c62-134">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

