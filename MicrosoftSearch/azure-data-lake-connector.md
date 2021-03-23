---
title: Conector de Azure Data Lake Graph para Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de Azure Data Lake Storage Gen2 Graph para Microsoft Search
ms.openlocfilehash: 37a035b3de9dc217f885f193992d1e74a675fb35
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031327"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a><span data-ttu-id="6755c-103">Conector de Azure Data Lake Storage Gen2 Graph</span><span class="sxs-lookup"><span data-stu-id="6755c-103">Azure Data Lake Storage Gen2 Graph connector</span></span>

<span data-ttu-id="6755c-104">El conector de Azure Data Lake Storage Gen2 Graph permite a los usuarios de su organización buscar archivos almacenados en cuentas de Almacenamiento de [blobs](/azure/storage/blobs/storage-blobs-introduction) de Azure [y Azure Data Lake Gen 2 Storage.](/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="6755c-104">The Azure Data Lake Storage Gen2 Graph connector allows users in your organization to search for files stored in [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="6755c-105">Lea el [**artículo Configurar el conector de Graph**](configure-connector.md) para comprender las instrucciones generales de configuración de conectores de Graph.</span><span class="sxs-lookup"><span data-stu-id="6755c-105">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="6755c-106">Este artículo está para cualquier persona que configure, ejecute y monitore un conector de Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="6755c-106">This article is for anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="6755c-107">Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="6755c-107">It supplements the general setup process, and shows instructions that apply only for the Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="6755c-108">En este artículo también se incluye información sobre [limitaciones](#limitations).</span><span class="sxs-lookup"><span data-stu-id="6755c-108">This article also includes information about [Limitations](#limitations).</span></span>

<span data-ttu-id="6755c-109">En el artículo, usamos *Azure Storage* como término genérico para Azure [Blob Storage](/azure/storage/blobs/storage-blobs-introduction) y Azure Data Lake [Gen 2 Storage](/azure/storage/blobs/data-lake-storage-introduction).</span><span class="sxs-lookup"><span data-stu-id="6755c-109">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6755c-110">Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6755c-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="6755c-111">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="6755c-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="6755c-112">Paso 2: Nombrar la conexión</span><span class="sxs-lookup"><span data-stu-id="6755c-112">Step 2: Name the connection</span></span>

<span data-ttu-id="6755c-113">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="6755c-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="6755c-114">Paso 3: Configurar las opciones de conexión</span><span class="sxs-lookup"><span data-stu-id="6755c-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="6755c-115">Escriba la cadena de conexión de almacenamiento principal.</span><span class="sxs-lookup"><span data-stu-id="6755c-115">Enter your Primary storage connection String.</span></span> <span data-ttu-id="6755c-116">Esta cadena es necesaria para permitir el acceso a la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6755c-116">This string is required to allow access to your storage account.</span></span> <span data-ttu-id="6755c-117">Para buscar la cadena de conexión, vaya a [Azure Portal](https://ms.portal.azure.com/#home) y vaya a la sección **Claves** de su cuenta de Azure Storage correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6755c-117">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span>

<span data-ttu-id="6755c-118">Si prefiere no proporcionar **accountkey** (un parámetro en la cadena de conexión de almacenamiento principal), conceda acceso a nuestro servicio de conectores de Graph para los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="6755c-118">If you prefer not to provide the **AccountKey** (a parameter in the primary storage connection string), grant access to our Graph Connectors Service for the following roles:</span></span>

* <span data-ttu-id="6755c-119">Lector de datos de blobs de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6755c-119">Storage Blob Data Reader</span></span>
* <span data-ttu-id="6755c-120">Colaborador de datos de cola de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6755c-120">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="6755c-121">Delegator de blobs de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6755c-121">Storage Blob Delegator</span></span>

<span data-ttu-id="6755c-122">Vaya a la pestaña **Control de** acceso de su cuenta de Azure Storage y siga las instrucciones que se indican para conceder acceso a la siguiente aplicación:</span><span class="sxs-lookup"><span data-stu-id="6755c-122">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="6755c-123">**Id. de aplicación de** primera persona: 56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="6755c-123">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="6755c-124">**Nombre de la aplicación de primer usuario:** Servicio de Graph Connector</span><span class="sxs-lookup"><span data-stu-id="6755c-124">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="6755c-125">Notificaciones de colas y cuenta de almacenamiento (opcional)</span><span class="sxs-lookup"><span data-stu-id="6755c-125">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="6755c-126">La compatibilidad para procesar cambios en tiempo real en el Servicio de conectores de Graph podría agregarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="6755c-126">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="6755c-127">En ese caso, supervisaremos las notificaciones de cambios de Azure Storage almacenadas en una cola.</span><span class="sxs-lookup"><span data-stu-id="6755c-127">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="6755c-128">Deberá crear una cola en la misma cuenta que la cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="6755c-128">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="6755c-129">Después de crear una cola, vaya a la **pestaña Eventos** de la página de cola para configurar **la suscripción a eventos**.</span><span class="sxs-lookup"><span data-stu-id="6755c-129">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="6755c-130">Elija todos los eventos blob que recibirá la cola y conecte la cola a la cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="6755c-130">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="6755c-131">Paso 4: Asignar etiquetas de propiedades</span><span class="sxs-lookup"><span data-stu-id="6755c-131">Step 4: Assign property labels</span></span>

<span data-ttu-id="6755c-132">Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones.</span><span class="sxs-lookup"><span data-stu-id="6755c-132">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="6755c-133">Aunque este paso no es obligatorio, tener algunas etiquetas de propiedades mejorará la relevancia de la búsqueda y garantizará mejores resultados de búsqueda para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="6755c-133">While this step isn't mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="6755c-134">Paso 5: Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="6755c-134">Step 5: Manage schema</span></span>

<span data-ttu-id="6755c-135">En la **pantalla Administrar esquema,** puede cambiar los atributos de esquema asociados con las propiedades, las opciones son **Query**, **Search,** **Retrieve** y **Refine**.</span><span class="sxs-lookup"><span data-stu-id="6755c-135">On the **Manage Schema** screen, you can change the schema attributes associated with the properties, the options are **Query**, **Search**, **Retrieve**, and **Refine**.</span></span> <span data-ttu-id="6755c-136">También puede agregar alias opcionales y elegir la **propiedad Content.**</span><span class="sxs-lookup"><span data-stu-id="6755c-136">You also can add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="6755c-137">Paso 6: Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="6755c-137">Step 6: Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="6755c-138">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="6755c-138">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="6755c-139">Puede elegir ingerir las listas de control de acceso (ACL) de su cuenta de almacenamiento de [Azure Data Lake Gen 2.](/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="6755c-139">You can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="6755c-140">Cuando se establecen estos permisos de búsqueda, el contenido de búsqueda se recorta en función de los permisos del usuario que ha firmado en [Azure Active Directory](/azure/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="6755c-140">When these search permissions are set, search content is trimmed based on the permissions of the user signed in [Azure Active Directory](/azure/active-directory/).</span></span> <span data-ttu-id="6755c-141">Como alternativa, puede elegir hacer que todo el contenido indizado desde su cuenta de almacenamiento sea visible para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="6755c-141">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="6755c-142">En este caso, todos los usuarios de la organización tendrán acceso a todos los datos de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6755c-142">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

<span data-ttu-id="6755c-143">El conector de Azure Data Lake Storage Gen2 Graph admite permisos de búsqueda visibles para todos **o** solo personas con **acceso a este origen de datos.**</span><span class="sxs-lookup"><span data-stu-id="6755c-143">The Azure Data Lake Storage Gen2 Graph connector supports search permissions visible to **Everyone**, or **Only people with access to this data source**.</span></span> <span data-ttu-id="6755c-144">Los datos indizados que aparecen en los resultados de la búsqueda podrían ser visibles para los usuarios de la organización que tienen acceso a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="6755c-144">Indexed data that appears in the search results could be visible to users in the organization who have access to each item.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="6755c-145">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="6755c-145">Azure Blob Storage</span></span>

<span data-ttu-id="6755c-146">Para una conexión a [Azure Blob Storage,](/azure/storage/blobs/storage-blobs-introduction)todo el contenido indizado desde el origen configurado es visible para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="6755c-146">For a connection to [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="6755c-147">Las listas de control de acceso no se admiten en el nivel de blob en Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="6755c-147">Access control lists aren't supported at Blob level in Azure Blob Storage.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="6755c-148">Paso 7: Establecer la programación de actualización</span><span class="sxs-lookup"><span data-stu-id="6755c-148">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="6755c-149">En la **pantalla Actualizar configuración,** puede establecer el intervalo de rastreo incremental y el intervalo de rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="6755c-149">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="6755c-150">Los intervalos predeterminados para el conector de Azure Data Lake Storage Gen2 son 15 minutos para un rastreo incremental y una semana para un rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="6755c-150">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="6755c-151">Paso 8: Revisar la conexión</span><span class="sxs-lookup"><span data-stu-id="6755c-151">Step 8: Review connection</span></span>

<span data-ttu-id="6755c-152">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="6755c-152">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="6755c-153">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="6755c-153">Limitations</span></span>

<span data-ttu-id="6755c-154">Una conexión publicada para Azure Blob Storage no se puede volver a configurar para el origen de Azure Data Lake Storage Gen2 y al revés.</span><span class="sxs-lookup"><span data-stu-id="6755c-154">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and the other way around.</span></span> <span data-ttu-id="6755c-155">En estos escenarios, se recomienda configurar una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="6755c-155">In such scenarios, it's recommended to configure a new connection.</span></span>

<span data-ttu-id="6755c-156">Además, el tamaño de los archivos debe ser de 4 MB o menos para que se rastree.</span><span class="sxs-lookup"><span data-stu-id="6755c-156">Also, the size of the files needs to be 4 MB or less for it to be crawled.</span></span> <span data-ttu-id="6755c-157">Los tipos de archivo admitidos actualmente son:</span><span class="sxs-lookup"><span data-stu-id="6755c-157">File types currently supported are:</span></span>

* <span data-ttu-id="6755c-158">Word (docx, .docm, .dotx, .dotm)</span><span class="sxs-lookup"><span data-stu-id="6755c-158">Word (docx, .docm, .dotx, .dotm)</span></span>
* <span data-ttu-id="6755c-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span><span class="sxs-lookup"><span data-stu-id="6755c-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span></span>
* <span data-ttu-id="6755c-160">Excel (.xlsx, .xlsm)</span><span class="sxs-lookup"><span data-stu-id="6755c-160">Excel (.xlsx, .xlsm)</span></span>
* <span data-ttu-id="6755c-161">Formatos heredados de Office (.doc, .dot, etc.)</span><span class="sxs-lookup"><span data-stu-id="6755c-161">Legacy Office formats (.doc, .dot, etc.)</span></span>
* <span data-ttu-id="6755c-162">Texto (.txt)</span><span class="sxs-lookup"><span data-stu-id="6755c-162">Text (.txt)</span></span>
* <span data-ttu-id="6755c-163">HTML</span><span class="sxs-lookup"><span data-stu-id="6755c-163">HTML</span></span>
* <span data-ttu-id="6755c-164">PDF</span><span class="sxs-lookup"><span data-stu-id="6755c-164">PDF</span></span>

<span data-ttu-id="6755c-165">No se admiten archivos binarios como imágenes (.jpg, .bmp, etc.).</span><span class="sxs-lookup"><span data-stu-id="6755c-165">Binary files like images (.jpg, .bmp, etc.) are not supported.</span></span> <span data-ttu-id="6755c-166">Por ejemplo, si un archivo .docx solo contiene imágenes, puede omitirse porque no devuelve ningún contenido.</span><span class="sxs-lookup"><span data-stu-id="6755c-166">For example, if a .docx file contains only images, it might be skipped because it didn't return any content.</span></span>