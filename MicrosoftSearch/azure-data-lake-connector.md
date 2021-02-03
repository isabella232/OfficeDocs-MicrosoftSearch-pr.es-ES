---
title: Conector de Azure Data Lake Graph para Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de Azure Data Lake Storage Gen2 Graph para Microsoft Search
ms.openlocfilehash: da508694929d3c83a456c664aa4613b09a1b14a3
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084861"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a><span data-ttu-id="73698-103">Conector de Azure Data Lake Storage Gen2 Graph</span><span class="sxs-lookup"><span data-stu-id="73698-103">Azure Data Lake Storage Gen2 Graph connector</span></span>

<span data-ttu-id="73698-104">El conector de Azure Data Lake Storage Gen2 Graph permite a los usuarios de su organización buscar archivos almacenados en cuentas de [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) y Azure Data Lake Gen [2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="73698-104">The Azure Data Lake Storage Gen2 Graph connector allows users in your organization to search for files stored in [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="73698-105">Lea el [**artículo configurar el conector de Graph**](configure-connector.md) para comprender el proceso de configuración general de los conectores de Graph.</span><span class="sxs-lookup"><span data-stu-id="73698-105">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="73698-106">Este artículo está disponible para cualquier persona que configure, ejecute y monitore un conector de Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="73698-106">This article is for anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="73698-107">Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="73698-107">It supplements the general setup process, and shows instructions that apply only for the Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="73698-108">En este artículo también se incluye información sobre [limitaciones.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="73698-108">This article also includes information about [Limitations](#limitations).</span></span>

<span data-ttu-id="73698-109">En el artículo, usamos *Azure Storage* como término genérico para Azure [Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) y Azure Data Lake [Gen 2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="73698-109">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="73698-110">Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73698-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="73698-111">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="73698-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="73698-112">Paso 2: Nombrar la conexión</span><span class="sxs-lookup"><span data-stu-id="73698-112">Step 2: Name the connection</span></span>

<span data-ttu-id="73698-113">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="73698-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="73698-114">Paso 3: Configurar las opciones de conexión</span><span class="sxs-lookup"><span data-stu-id="73698-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="73698-115">Escriba la cadena de conexión de almacenamiento principal.</span><span class="sxs-lookup"><span data-stu-id="73698-115">Enter your Primary storage connection String.</span></span> <span data-ttu-id="73698-116">Esta cadena es necesaria para permitir el acceso a la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="73698-116">This string is required to allow access to your storage account.</span></span> <span data-ttu-id="73698-117">Para encontrar la cadena de conexión, vaya a [Azure Portal](https://ms.portal.azure.com/#home) y vaya a la sección **Claves** de su cuenta de Azure Storage relevante.</span><span class="sxs-lookup"><span data-stu-id="73698-117">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span>

<span data-ttu-id="73698-118">Si prefiere no proporcionar **accountKey** (un parámetro en la cadena de conexión de almacenamiento principal), conceda acceso a nuestro servicio de conectores de Graph para los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="73698-118">If you prefer not to provide the **AccountKey** (a parameter in the primary storage connection string), grant access to our Graph Connectors Service for the following roles:</span></span>

* <span data-ttu-id="73698-119">Lector de datos blobs de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="73698-119">Storage Blob Data Reader</span></span>
* <span data-ttu-id="73698-120">Colaborador de datos de cola de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="73698-120">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="73698-121">Delegador de blobs de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="73698-121">Storage Blob Delegator</span></span>

<span data-ttu-id="73698-122">Vaya a la **pestaña Control de** acceso de su cuenta de Azure Storage y siga las instrucciones para conceder acceso a la siguiente aplicación:</span><span class="sxs-lookup"><span data-stu-id="73698-122">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="73698-123">**Id. de aplicación** de primera parte: 56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="73698-123">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="73698-124">**Nombre de la aplicación de primera parte:** Servicio de conector de Graph</span><span class="sxs-lookup"><span data-stu-id="73698-124">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="73698-125">Notificaciones de colas y cuenta de almacenamiento (opcional)</span><span class="sxs-lookup"><span data-stu-id="73698-125">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="73698-126">La compatibilidad para procesar cambios en tiempo real en el servicio de conectores de Graph podría agregarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="73698-126">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="73698-127">En ese caso, supervisaremos las notificaciones de cambio de Azure Storage almacenadas en una cola.</span><span class="sxs-lookup"><span data-stu-id="73698-127">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="73698-128">Deberá crear una cola en la misma cuenta que la cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="73698-128">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="73698-129">Después de crear una cola, vaya a la pestaña **Eventos** de la página de cola para configurar **la suscripción de eventos.**</span><span class="sxs-lookup"><span data-stu-id="73698-129">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="73698-130">Elija todos los eventos Blob que recibirá la cola y conecte la cola a la cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="73698-130">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="73698-131">Paso 4: Asignar etiquetas de propiedad</span><span class="sxs-lookup"><span data-stu-id="73698-131">Step 4: Assign property labels</span></span>

<span data-ttu-id="73698-132">Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones.</span><span class="sxs-lookup"><span data-stu-id="73698-132">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="73698-133">Aunque este paso no es obligatorio, tener algunas etiquetas de propiedad mejorará la relevancia de la búsqueda y garantizará mejores resultados de búsqueda para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="73698-133">While this step isn't mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="73698-134">Paso 5: Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="73698-134">Step 5: Manage schema</span></span>

<span data-ttu-id="73698-135">En la **pantalla Administrar** esquema, puede cambiar los atributos de esquema asociados con las propiedades, las opciones son **Consulta,** **Búsqueda,** **Recuperar** y **Refinar**.</span><span class="sxs-lookup"><span data-stu-id="73698-135">On the **Manage Schema** screen, you can change the schema attributes associated with the properties, the options are **Query**, **Search**, **Retrieve**, and **Refine**.</span></span> <span data-ttu-id="73698-136">También puede agregar alias opcionales y elegir la **propiedad Content.**</span><span class="sxs-lookup"><span data-stu-id="73698-136">You also can add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="73698-137">Paso 6: Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="73698-137">Step 6: Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="73698-138">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="73698-138">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="73698-139">Puede elegir ingerir las listas de control de acceso (ACL) de su cuenta de almacenamiento de [Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="73698-139">You can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="73698-140">Cuando se establecen estos permisos de búsqueda, el contenido de la búsqueda se recorta en función de los permisos del usuario que ha iniciado sesión en [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="73698-140">When these search permissions are set, search content is trimmed based on the permissions of the user signed in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/).</span></span> <span data-ttu-id="73698-141">Como alternativa, puede hacer que todo el contenido indizado desde su cuenta de almacenamiento sea visible para todos los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="73698-141">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="73698-142">En este caso, todos los miembros de la organización tendrán acceso a todos los datos de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="73698-142">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

<span data-ttu-id="73698-143">El conector de Azure Data Lake Storage Gen2 Graph admite permisos de búsqueda visibles para todos **los** usuarios o solo para las personas con **acceso a este origen de datos.**</span><span class="sxs-lookup"><span data-stu-id="73698-143">The Azure Data Lake Storage Gen2 Graph connector supports search permissions visible to **Everyone**, or **Only people with access to this data source**.</span></span> <span data-ttu-id="73698-144">Los datos indizados que aparecen en los resultados de la búsqueda podrían ser visibles para los usuarios de la organización que tienen acceso a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="73698-144">Indexed data that appears in the search results could be visible to users in the organization who have access to each item.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="73698-145">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="73698-145">Azure Blob Storage</span></span>

<span data-ttu-id="73698-146">Para una conexión a [Azure Blob Storage,](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)todo el contenido indizado desde el origen configurado es visible para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="73698-146">For a connection to [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="73698-147">Las listas de control de acceso no se admiten en el nivel de blob en Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="73698-147">Access control lists aren't supported at Blob level in Azure Blob Storage.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="73698-148">Paso 7: Establecer la programación de actualización</span><span class="sxs-lookup"><span data-stu-id="73698-148">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="73698-149">En la **pantalla Configuración de** actualización, puede establecer el intervalo de rastreo incremental y el intervalo de rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="73698-149">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="73698-150">Los intervalos predeterminados para el conector de Azure Data Lake Storage Gen2 son de 15 minutos para un rastreo incremental y de una semana para un rastreo completo.</span><span class="sxs-lookup"><span data-stu-id="73698-150">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="73698-151">Paso 8: Revisar la conexión</span><span class="sxs-lookup"><span data-stu-id="73698-151">Step 8: Review connection</span></span>

<span data-ttu-id="73698-152">Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="73698-152">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="73698-153">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="73698-153">Limitations</span></span>

<span data-ttu-id="73698-154">No se puede volver a configurar una conexión publicada para Azure Blob Storage para el origen de Azure Data Lake Storage Gen2 y al revés.</span><span class="sxs-lookup"><span data-stu-id="73698-154">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and the other way around.</span></span> <span data-ttu-id="73698-155">En estos escenarios, se recomienda configurar una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="73698-155">In such scenarios, it's recommended to configure a new connection.</span></span>

<span data-ttu-id="73698-156">Además, el tamaño de los archivos debe ser de 4 MB o menos para que se rastree.</span><span class="sxs-lookup"><span data-stu-id="73698-156">Also, the size of the files needs to be 4 MB or less for it to be crawled.</span></span> <span data-ttu-id="73698-157">Los tipos de archivo admitidos actualmente son:</span><span class="sxs-lookup"><span data-stu-id="73698-157">File types currently supported are:</span></span>

* <span data-ttu-id="73698-158">Word (docx, .docm, .dotx, .dotm)</span><span class="sxs-lookup"><span data-stu-id="73698-158">Word (docx, .docm, .dotx, .dotm)</span></span>
* <span data-ttu-id="73698-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span><span class="sxs-lookup"><span data-stu-id="73698-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span></span>
* <span data-ttu-id="73698-160">Excel (.xlsx, .xlsm)</span><span class="sxs-lookup"><span data-stu-id="73698-160">Excel (.xlsx, .xlsm)</span></span>
* <span data-ttu-id="73698-161">Formatos heredados de Office (.doc, .dot, etc.)</span><span class="sxs-lookup"><span data-stu-id="73698-161">Legacy Office formats (.doc, .dot, etc.)</span></span>
* <span data-ttu-id="73698-162">Texto (.txt)</span><span class="sxs-lookup"><span data-stu-id="73698-162">Text (.txt)</span></span>
* <span data-ttu-id="73698-163">HTML</span><span class="sxs-lookup"><span data-stu-id="73698-163">HTML</span></span>
* <span data-ttu-id="73698-164">PDF</span><span class="sxs-lookup"><span data-stu-id="73698-164">PDF</span></span>

<span data-ttu-id="73698-165">No se admiten archivos binarios como imágenes (.jpg, .bmp, etc.).</span><span class="sxs-lookup"><span data-stu-id="73698-165">Binary files like images (.jpg, .bmp, etc.) are not supported.</span></span> <span data-ttu-id="73698-166">Por ejemplo, si un archivo .docx contiene solo imágenes, es posible que se omita porque no devuelve ningún contenido.</span><span class="sxs-lookup"><span data-stu-id="73698-166">For example, if a .docx file contains only images, it might be skipped because it didn't return any content.</span></span>
