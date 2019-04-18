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
description: Crear muchos marcadores a la vez con herramientas de importación para el portal de administración de Microsoft Search
ms.openlocfilehash: 7c134784f0ca0d4cc84d5bce3a98f7e75aa6f441
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901796"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="ef941-103">Crear marcadores en masa</span><span class="sxs-lookup"><span data-stu-id="ef941-103">Bulk create bookmarks</span></span>

<span data-ttu-id="ef941-104">Descargue y use la plantilla. csv para crear, editar y guardar marcadores de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="ef941-104">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="ef941-105">Para editar de forma masiva los marcadores existentes, expórtelo del portal de administración, realice las modificaciones necesarias y, a continuación, impórtelas.</span><span class="sxs-lookup"><span data-stu-id="ef941-105">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="ef941-106">En la esquina superior derecha de la sección Marcadores, haga clic en **importar**</span><span class="sxs-lookup"><span data-stu-id="ef941-106">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="ef941-107">Haga clic en **Descargar plantilla de marcadores (. csv)**</span><span class="sxs-lookup"><span data-stu-id="ef941-107">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="ef941-108">Guardar y abrir el archivo. csv</span><span class="sxs-lookup"><span data-stu-id="ef941-108">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="ef941-109">Agregar el contenido y la configuración del marcador y guardar el archivo</span><span class="sxs-lookup"><span data-stu-id="ef941-109">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="ef941-110">El archivo. csv se debe guardar como archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden provocar errores de importación</span><span class="sxs-lookup"><span data-stu-id="ef941-110">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="ef941-111">En la esquina superior derecha de la sección Marcadores, haga clic en **importar**</span><span class="sxs-lookup"><span data-stu-id="ef941-111">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="ef941-112">En el panel importar marcadores, haga clic en **examinar** y navegue hasta el archivo. csv que desea importar.</span><span class="sxs-lookup"><span data-stu-id="ef941-112">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="ef941-113">Haga clic en **importar**</span><span class="sxs-lookup"><span data-stu-id="ef941-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="ef941-114">Impedir errores de importación</span><span class="sxs-lookup"><span data-stu-id="ef941-114">Prevent import errors</span></span>      
<span data-ttu-id="ef941-115">Recibirá un error si faltan datos necesarios o no son válidos.</span><span class="sxs-lookup"><span data-stu-id="ef941-115">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="ef941-116">Según el error, es posible que se genere un archivo de registro con más información sobre las filas y las columnas que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="ef941-116">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="ef941-117">Realice las modificaciones necesarias e intente importar el archivo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="ef941-117">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="ef941-118">Hasta que se resuelvan todos los errores, no podrá crear ni editar ningún marcador.</span><span class="sxs-lookup"><span data-stu-id="ef941-118">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="ef941-119">Para ayudar a evitar errores, asegúrese de que el archivo de importación tiene el formato correcto:</span><span class="sxs-lookup"><span data-stu-id="ef941-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="ef941-120">Incluye la fila de encabezado que estaba en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="ef941-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="ef941-121">Incluye todas las columnas que estaban en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="ef941-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="ef941-122">El orden de las columnas es el mismo que el de la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="ef941-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="ef941-123">Estas columnas pueden estar vacías: ID, última modificación y última modificación por</span><span class="sxs-lookup"><span data-stu-id="ef941-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="ef941-124">La columna Estado no puede estar vacía, se requiere esta información</span><span class="sxs-lookup"><span data-stu-id="ef941-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="ef941-125">Según el campo de estado, los marcadores se guardarán como borrador, sugerido, programado, o se publicarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ef941-125">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="ef941-126">Además, si incluye el identificador de un marcador existente, se reemplazará con la información del archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="ef941-126">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="ef941-127">En el caso de organizaciones con varios inquilinos, puede exportar sus marcadores de un inquilino e importarlos en otro.</span><span class="sxs-lookup"><span data-stu-id="ef941-127">For organizations with mulitple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="ef941-128">Sin embargo, debe quitar todos los datos de la columna ID antes de importar.</span><span class="sxs-lookup"><span data-stu-id="ef941-128">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="ef941-129">Para obtener más información sobre los campos obligatorios y recomendados, vea [Create bookmarks](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="ef941-129">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
