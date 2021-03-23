---
title: Conector de Gráfico de uso compartido de archivos para Microsoft Search
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
ROBOTS: NoIndex
description: Configurar el conector de Gráfico de recurso compartido de archivos para Microsoft Search
ms.openlocfilehash: 792e853e5d2b7a23835dc031ff4ba4c09d619f9c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031615"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="daccd-103">Conector de Gráfico de recurso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="daccd-103">File share Graph connector</span></span>

<span data-ttu-id="daccd-104">El conector de Gráfico de recursos compartidos de archivos permite a los usuarios de la organización buscar recursos compartidos de archivos locales de Windows.</span><span class="sxs-lookup"><span data-stu-id="daccd-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="daccd-105">Lea el [**artículo Configurar para el conector de Graph**](configure-connector.md) para comprender el proceso de configuración general de los conectores de Graph.</span><span class="sxs-lookup"><span data-stu-id="daccd-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="daccd-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="daccd-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="daccd-107">Instalar el agente de conector de Graph</span><span class="sxs-lookup"><span data-stu-id="daccd-107">Install the Graph connector agent</span></span>

<span data-ttu-id="daccd-108">Para indizar los recursos compartidos de archivos de Windows, debes instalar y registrar el agente de conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="daccd-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="daccd-109">Consulte [Instalar el agente de conector de Graph](on-prem-agent.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="daccd-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="daccd-110">Requisitos de contenido</span><span class="sxs-lookup"><span data-stu-id="daccd-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="daccd-111">Tipos de archivo</span><span class="sxs-lookup"><span data-stu-id="daccd-111">File types</span></span>

<span data-ttu-id="daccd-112">El contenido de los siguientes formatos se puede indizar y buscar: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLSB, XLSX, XLT, XLXM, XML, XPS y ZIP.</span><span class="sxs-lookup"><span data-stu-id="daccd-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="daccd-113">Solo se indiza el contenido textual de estos formatos.</span><span class="sxs-lookup"><span data-stu-id="daccd-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="daccd-114">Se omite todo el contenido multimedia.</span><span class="sxs-lookup"><span data-stu-id="daccd-114">All multimedia content is ignored.</span></span> <span data-ttu-id="daccd-115">Para cualquier archivo que no pertenezca a este formato, solo se indizan los metadatos.</span><span class="sxs-lookup"><span data-stu-id="daccd-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="daccd-116">Límites de tamaño de archivo</span><span class="sxs-lookup"><span data-stu-id="daccd-116">File size limits</span></span>

<span data-ttu-id="daccd-117">El tamaño máximo de archivo admitido es de 100 MB.</span><span class="sxs-lookup"><span data-stu-id="daccd-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="daccd-118">Los archivos que superen los 100 MB no se indizan.</span><span class="sxs-lookup"><span data-stu-id="daccd-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="daccd-119">El límite máximo de tamaño posterior al procesado es de 4 MB.</span><span class="sxs-lookup"><span data-stu-id="daccd-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="daccd-120">El procesamiento se detiene cuando el tamaño de un archivo alcanza los 4 MB.</span><span class="sxs-lookup"><span data-stu-id="daccd-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="daccd-121">Por lo tanto, es posible que algunas frases presentes en el archivo no funcionen para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="daccd-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="daccd-122">Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="daccd-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="daccd-123">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="daccd-123">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="daccd-124">Paso 2: Nombrar la conexión</span><span class="sxs-lookup"><span data-stu-id="daccd-124">Step 2: Name the connection</span></span>

<span data-ttu-id="daccd-125">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="daccd-125">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="daccd-126">Paso 3: Configurar las opciones de conexión</span><span class="sxs-lookup"><span data-stu-id="daccd-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="daccd-127">En la **página Conectarse al origen de** datos, seleccione Recurso **compartido** de archivos y proporcione el nombre, el identificador de conexión y la descripción.</span><span class="sxs-lookup"><span data-stu-id="daccd-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="daccd-128">En la página siguiente, proporcione la ruta de acceso al recurso compartido de archivos y seleccione el agente de conector de Graph instalado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="daccd-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="daccd-129">Escriba las credenciales de una [cuenta de usuario de Microsoft Windows](https://microsoft.com/windows) con acceso de lectura a todos los archivos del recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="daccd-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="daccd-130">Conservar el último tiempo de acceso</span><span class="sxs-lookup"><span data-stu-id="daccd-130">Preserve last access time</span></span>

<span data-ttu-id="daccd-131">Cuando el conector intenta rastrear un archivo, se actualiza el campo "Última hora de acceso" en sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="daccd-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="daccd-132">Si depende de ese campo para las soluciones de archivado y copia de seguridad y no desea actualizarlo cuando el conector tiene acceso a él, puede configurar esta opción en la página **Configuración** avanzada.</span><span class="sxs-lookup"><span data-stu-id="daccd-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="daccd-133">Paso 4: Administrar permisos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="daccd-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="daccd-134">Puede restringir el permiso para buscar cualquier archivo basado en listas de control de acceso compartido o listas de control de acceso del Sistema de archivos de nueva tecnología (NTFS), seleccionando la opción deseada en la página Administrar permisos de **búsqueda.**</span><span class="sxs-lookup"><span data-stu-id="daccd-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists, by selecting the desired option in **Manage search permissions** page.</span></span> <span data-ttu-id="daccd-135">Las cuentas de usuario y los grupos proporcionados en estas listas de control de acceso deben administrarse mediante Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="daccd-135">The user accounts and groups provided in these Access Control Lists must be managed by Active Directory (AD).</span></span> <span data-ttu-id="daccd-136">Si usa cualquier otro sistema para la administración de cuentas de usuario, puede seleccionar la opción "todos", que permite a los usuarios buscar todos los archivos sin restricciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="daccd-136">If you are using any other system for user accounts management, you can select 'everyone' option, which lets users search for all the files without any access restrictions.</span></span> <span data-ttu-id="daccd-137">Sin embargo, cuando los usuarios intentan abrir el archivo, se aplican los controles de acceso establecidos en el origen.</span><span class="sxs-lookup"><span data-stu-id="daccd-137">However, when users try to open the file, access controls set at the source apply.</span></span>

<span data-ttu-id="daccd-138">Tenga en cuenta que windows proporciona de forma predeterminada el permiso "Leer" a "Todos" en compartir ACL cuando se comparte una carpeta en la red.</span><span class="sxs-lookup"><span data-stu-id="daccd-138">Note that windows by default provides 'Read' permission to 'Everyone' in Share ACLs when a folder is shared on network.</span></span> <span data-ttu-id="daccd-139">Por extensión, si elige Compartir ACL en Administrar permisos de **búsqueda,** los usuarios podrán buscar todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="daccd-139">By extension, if you are choosing Share ACLs in **Manage search permissions**, users will be able to search for all the files.</span></span> <span data-ttu-id="daccd-140">Si desea restringir el acceso, quite el acceso "Leer" para "Todos" en recursos compartidos de archivos y proporcione acceso solo a los usuarios y grupos deseados.</span><span class="sxs-lookup"><span data-stu-id="daccd-140">If you want to restrict access, remove 'Read' access for 'Everyone' in file shares and provide access only to the desired users and groups.</span></span> <span data-ttu-id="daccd-141">A continuación, el conector lee estas restricciones de acceso y las aplica a la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="daccd-141">The connector then reads these access restrictions and applies them to search.</span></span>

<span data-ttu-id="daccd-142">Solo puede elegir Compartir ACL si la ruta de acceso al recurso compartido que proporcionó sigue el formato de ruta UNC.</span><span class="sxs-lookup"><span data-stu-id="daccd-142">You can choose Share ACLs only if the share path you provided follows UNC path format.</span></span> <span data-ttu-id="daccd-143">Puede crear una ruta de acceso en formato UNC yendo a "Uso compartido avanzado" en la opción "Uso compartido".</span><span class="sxs-lookup"><span data-stu-id="daccd-143">You can create a path in UNC format by going to 'Advanced Sharing' under 'Sharing' option.</span></span>

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="daccd-145">Paso 5: Asignar etiquetas de propiedades</span><span class="sxs-lookup"><span data-stu-id="daccd-145">Step 5: Assign property labels</span></span>

<span data-ttu-id="daccd-146">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="daccd-146">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="daccd-147">Paso 6: Administrar esquema</span><span class="sxs-lookup"><span data-stu-id="daccd-147">Step 6: Manage schema</span></span>

<span data-ttu-id="daccd-148">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="daccd-148">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="daccd-149">Paso 7: Elegir la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="daccd-149">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="daccd-150">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="daccd-150">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="daccd-151">Paso 8: Revisar la conexión</span><span class="sxs-lookup"><span data-stu-id="daccd-151">Step 8: Review connection</span></span>

<span data-ttu-id="daccd-152">Siga las instrucciones [generales de configuración](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="daccd-152">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->