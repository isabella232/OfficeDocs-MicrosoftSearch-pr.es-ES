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
description: Cree varios marcadores a la vez con las herramientas de importación para el portal de administración de Búsqueda de Microsoft
ms.openlocfilehash: 1b3922215534391c65547a4ece22310261626036
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591426"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="66775-103">Crear marcadores en masa</span><span class="sxs-lookup"><span data-stu-id="66775-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66775-104">Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing</span><span class="sxs-lookup"><span data-stu-id="66775-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="66775-105">Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se quitará.</span><span class="sxs-lookup"><span data-stu-id="66775-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="66775-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="66775-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="66775-107">[Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="66775-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="66775-108">Descargue y use la plantilla .csv para crear, editar y guardar marcadores en masa.</span><span class="sxs-lookup"><span data-stu-id="66775-108">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="66775-109">Si necesita editar en masa marcadores existentes, expórtelos desde el Portal de administración, haga los cambios necesarios y, luego, impórtelos.</span><span class="sxs-lookup"><span data-stu-id="66775-109">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="66775-110">En la esquina superior derecha de la sección Marcadores, haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="66775-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="66775-111">Haga clic en **Descargar plantilla de marcadores (.csv)**</span><span class="sxs-lookup"><span data-stu-id="66775-111">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="66775-112">Guarde y abra el archivo .csv</span><span class="sxs-lookup"><span data-stu-id="66775-112">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="66775-113">Agregue el contenido y la configuración de los marcadores y guarde el archivo</span><span class="sxs-lookup"><span data-stu-id="66775-113">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="66775-114">El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación</span><span class="sxs-lookup"><span data-stu-id="66775-114">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="66775-115">En la esquina superior derecha de la sección Marcadores, haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="66775-115">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="66775-116">En el panel Importar marcadores, haga clic en **Examinar** y vaya al archivo .csv que quiere importar</span><span class="sxs-lookup"><span data-stu-id="66775-116">In the Import bookmarks pane, select **Browse** and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="66775-117">Haga clic en **Importar**</span><span class="sxs-lookup"><span data-stu-id="66775-117">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="66775-118">Evitar errores de importación</span><span class="sxs-lookup"><span data-stu-id="66775-118">Prevent import errors</span></span>      
<span data-ttu-id="66775-119">Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="66775-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="66775-120">Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="66775-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="66775-121">Realice los cambios necesarios e intente importar de nuevo el archivo.</span><span class="sxs-lookup"><span data-stu-id="66775-121">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="66775-122">Hasta que se resuelvan todos los errores, no podrá crear o editar los marcadores.</span><span class="sxs-lookup"><span data-stu-id="66775-122">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="66775-123">Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:</span><span class="sxs-lookup"><span data-stu-id="66775-123">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="66775-124">Incluye la fila de encabezado que se encontraba en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="66775-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="66775-125">Incluye todas las columnas que se encontraban en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="66775-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="66775-126">El orden de las columnas es el mismo que el orden en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="66775-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="66775-127">Estas columnas pueden estar vacías: Id., Última modificación y Última modificación realizada por</span><span class="sxs-lookup"><span data-stu-id="66775-127">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="66775-128">La columna Estado no puede estar vacía, puesto que esta información es necesaria</span><span class="sxs-lookup"><span data-stu-id="66775-128">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="66775-129">En función del campo Estado, los marcadores se guardarán como borradores, sugeridos o programados, o se publicarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="66775-129">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="66775-130">Además, si incluye el Id. de un marcador existente, este se reemplazará con la información del archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="66775-130">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="66775-131">Para organizaciones con múltiples espacios empresariales, se pueden exportar los marcadores de un espacio empresarial e importarlos en otro.</span><span class="sxs-lookup"><span data-stu-id="66775-131">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="66775-132">Pero, debe eliminar todos los datos de la columna Id. antes de la importación.</span><span class="sxs-lookup"><span data-stu-id="66775-132">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="66775-133">Para obtener más información sobre los campos necesarios y recomendados, vea [Crear marcadores](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="66775-133">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
