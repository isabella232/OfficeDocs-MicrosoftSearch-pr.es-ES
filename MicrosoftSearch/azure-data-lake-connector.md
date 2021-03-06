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
ms.openlocfilehash: 2bb9570bc3b0a5adef7ac72ea1620c4f22a8aefb
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508890"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Conector de Azure Data Lake Storage Gen2 Graph

El conector de Azure Data Lake Storage Gen2 Graph permite a los usuarios de su organización buscar archivos almacenados en cuentas de Almacenamiento de [blobs](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) de Azure [y Azure Data Lake Gen 2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

> [!NOTE]
> Lea el [**artículo Configurar el conector de Graph**](configure-connector.md) para comprender las instrucciones generales de configuración de conectores de Graph.

Este artículo está para cualquier persona que configure, ejecute y monitore un conector de Azure Data Lake Storage Gen2. Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de Azure Data Lake Storage Gen2. En este artículo también se incluye información sobre [limitaciones](#limitations).

En el artículo, usamos *Azure Storage* como término genérico para Azure [Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) y Azure Data Lake [Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

Escriba la cadena de conexión de almacenamiento principal. Esta cadena es necesaria para permitir el acceso a la cuenta de almacenamiento. Para buscar la cadena de conexión, vaya a [Azure Portal](https://ms.portal.azure.com/#home) y vaya a la sección **Claves** de su cuenta de Azure Storage correspondiente.

Si prefiere no proporcionar **accountkey** (un parámetro en la cadena de conexión de almacenamiento principal), conceda acceso a nuestro servicio de conectores de Graph para los siguientes roles:

* Lector de datos de blobs de almacenamiento
* Colaborador de datos de cola de almacenamiento
* Delegator de blobs de almacenamiento

Vaya a la pestaña **Control de** acceso de su cuenta de Azure Storage y siga las instrucciones que se indican para conceder acceso a la siguiente aplicación:

* **Id. de aplicación de** primera persona: 56c1da01-2129-48f7-9355-af6d59d42766
* **Nombre de la aplicación de primer usuario:** Servicio de Graph Connector

### <a name="storage-account-and-queue-notifications-optional"></a>Notificaciones de colas y cuenta de almacenamiento (opcional)

La compatibilidad para procesar cambios en tiempo real en el Servicio de conectores de Graph podría agregarse en el futuro. En ese caso, supervisaremos las notificaciones de cambios de Azure Storage almacenadas en una cola. Deberá crear una cola en la misma cuenta que la cuenta de Azure Storage.

Después de crear una cola, vaya a la **pestaña Eventos** de la página de cola para configurar **la suscripción a eventos**. Elija todos los eventos blob que recibirá la cola y conecte la cola a la cuenta de Azure Storage.

## <a name="step-4-assign-property-labels"></a>Paso 4: Asignar etiquetas de propiedades

Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones. Aunque este paso no es obligatorio, tener algunas etiquetas de propiedades mejorará la relevancia de la búsqueda y garantizará mejores resultados de búsqueda para los usuarios finales.

## <a name="step-5-manage-schema"></a>Paso 5: Administrar esquema

En la **pantalla Administrar esquema,** puede cambiar los atributos de esquema asociados con las propiedades, las opciones son **Query**, **Search,** **Retrieve** y **Refine**. También puede agregar alias opcionales y elegir la **propiedad Content.**

## <a name="step-6-manage-search-permissions"></a>Paso 6: Administrar permisos de búsqueda

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Puede elegir ingerir las listas de control de acceso (ACL) de su cuenta de almacenamiento de [Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Cuando se establecen estos permisos de búsqueda, el contenido de búsqueda se recorta en función de los permisos del usuario que ha firmado en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/). Como alternativa, puede elegir hacer que todo el contenido indizado desde su cuenta de almacenamiento sea visible para todos los usuarios de la organización. En este caso, todos los usuarios de la organización tendrán acceso a todos los datos de la cuenta de almacenamiento.

El conector de Azure Data Lake Storage Gen2 Graph admite permisos de búsqueda visibles para todos **o** solo personas con **acceso a este origen de datos.** Los datos indizados que aparecen en los resultados de la búsqueda podrían ser visibles para los usuarios de la organización que tienen acceso a cada elemento.

### <a name="azure-blob-storage"></a>Azure Blob Storage

Para una conexión a [Azure Blob Storage,](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)todo el contenido indizado desde el origen configurado es visible para todos los usuarios de la organización. Las listas de control de acceso no se admiten en el nivel de blob en Azure Blob Storage.

## <a name="step-7-set-the-refresh-schedule"></a>Paso 7: Establecer la programación de actualización

En la **pantalla Actualizar configuración,** puede establecer el intervalo de rastreo incremental y el intervalo de rastreo completo. Los intervalos predeterminados para el conector de Azure Data Lake Storage Gen2 son 15 minutos para un rastreo incremental y una semana para un rastreo completo.

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitaciones

Una conexión publicada para Azure Blob Storage no se puede volver a configurar para el origen de Azure Data Lake Storage Gen2 y al revés. En estos escenarios, se recomienda configurar una nueva conexión.

Además, el tamaño de los archivos debe ser de 4 MB o menos para que se rastree. Los tipos de archivo admitidos actualmente son:

* Word (docx, .docm, .dotx, .dotm)
* PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)
* Excel (.xlsx, .xlsm)
* Formatos heredados de Office (.doc, .dot, etc.)
* Texto (.txt)
* HTML
* PDF

No se admiten archivos binarios como imágenes (.jpg, .bmp, etc.). Por ejemplo, si un archivo .docx solo contiene imágenes, puede omitirse porque no devuelve ningún contenido.
