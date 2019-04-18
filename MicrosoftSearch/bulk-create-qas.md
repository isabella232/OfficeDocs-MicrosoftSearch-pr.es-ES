---
title: Crear preguntas y respuestas de forma masiva
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
description: Agregue rápidamente respuestas a las preguntas más frecuentes con herramientas de importación en el portal de administración de Microsoft Search
ms.openlocfilehash: 28fcf57c44f809e7f9b0c1b27042f4549067a0f8
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901820"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="d01b6-103">Crear preguntas y respuestas de forma masiva</span><span class="sxs-lookup"><span data-stu-id="d01b6-103">Bulk create Q&As</span></span>

<span data-ttu-id="d01b6-104">Descargue y use la plantilla. csv para crear o editar en masa Q&As.</span><span class="sxs-lookup"><span data-stu-id="d01b6-104">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="d01b6-105">También es una forma sencilla de guardar de forma masiva borradores de Q&As que necesitan ediciones o actualizaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="d01b6-105">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="d01b6-106">Si necesita editar en masa Q&As existentes, expórtelo del portal de administración, realice las modificaciones necesarias y, a continuación, impórtelas.</span><span class="sxs-lookup"><span data-stu-id="d01b6-106">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="d01b6-107">En la esquina superior derecha de la sección Q&As, haga clic en **importar**</span><span class="sxs-lookup"><span data-stu-id="d01b6-107">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="d01b6-108">Haga clic en **Descargar plantilla de Q&A (. csv)**</span><span class="sxs-lookup"><span data-stu-id="d01b6-108">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="d01b6-109">Guardar y abrir el archivo. csv</span><span class="sxs-lookup"><span data-stu-id="d01b6-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="d01b6-110">Agregar el contenido y la configuración de Q&A y guardar el archivo</span><span class="sxs-lookup"><span data-stu-id="d01b6-110">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="d01b6-111">El archivo. csv se debe guardar como archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden provocar errores de importación</span><span class="sxs-lookup"><span data-stu-id="d01b6-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="d01b6-112">En la esquina superior derecha de la sección Q&As, haga clic en **importar**</span><span class="sxs-lookup"><span data-stu-id="d01b6-112">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="d01b6-113">En el panel de Q&As de importación, haga clic en **examinar** y navegue hasta el archivo. csv que desea importar.</span><span class="sxs-lookup"><span data-stu-id="d01b6-113">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="d01b6-114">Haga clic en **importar**</span><span class="sxs-lookup"><span data-stu-id="d01b6-114">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="d01b6-115">Impedir errores de importación</span><span class="sxs-lookup"><span data-stu-id="d01b6-115">Prevent import errors</span></span>      
<span data-ttu-id="d01b6-116">Recibirá un error si faltan datos necesarios o no son válidos.</span><span class="sxs-lookup"><span data-stu-id="d01b6-116">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="d01b6-117">Según el error, es posible que se genere un archivo de registro con más información sobre las filas y las columnas que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="d01b6-117">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="d01b6-118">Realice las modificaciones necesarias e intente importar el archivo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="d01b6-118">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="d01b6-119">Hasta que se resuelvan todos los errores, no puede crear ni editar ninguna Q&As.</span><span class="sxs-lookup"><span data-stu-id="d01b6-119">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="d01b6-120">Para ayudar a evitar errores, asegúrese de que el archivo de importación tiene el formato correcto:</span><span class="sxs-lookup"><span data-stu-id="d01b6-120">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="d01b6-121">Incluye la fila de encabezado que estaba en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="d01b6-121">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="d01b6-122">Incluye todas las columnas que estaban en la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="d01b6-122">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="d01b6-123">El orden de las columnas es el mismo que el de la plantilla de importación</span><span class="sxs-lookup"><span data-stu-id="d01b6-123">The column order is the same as the import template</span></span>
- <span data-ttu-id="d01b6-124">Estas columnas pueden estar vacías: ID, última modificación y última modificación por</span><span class="sxs-lookup"><span data-stu-id="d01b6-124">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="d01b6-125">La columna Estado no puede estar vacía, se requiere esta información</span><span class="sxs-lookup"><span data-stu-id="d01b6-125">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="d01b6-126">Según el campo de estado, Q&As se guardará como borrador, sugerido, programado o se publicará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d01b6-126">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="d01b6-127">Además, si incluye el identificador de un Q&A existente, se reemplazará con la información en el archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="d01b6-127">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="d01b6-128">Para organizaciones con varios inquilinos, puede exportar su Q&As de un inquilino e importarlo en otro.</span><span class="sxs-lookup"><span data-stu-id="d01b6-128">For organizations with mulitple tenants, you can export your Q&As from one tenant and import it into another.</span></span> <span data-ttu-id="d01b6-129">Sin embargo, debe quitar todos los datos de la columna ID antes de importar.</span><span class="sxs-lookup"><span data-stu-id="d01b6-129">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="d01b6-130">Para obtener más información acerca de los campos obligatorios y recomendados, consulte [Create Q&As](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="d01b6-130">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

