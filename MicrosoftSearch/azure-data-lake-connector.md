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

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Conector de Azure Data Lake Storage Gen2 Graph

El conector de Azure Data Lake Storage Gen2 Graph permite a los usuarios de su organización buscar archivos almacenados en cuentas de [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) y Azure Data Lake Gen [2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

> [!NOTE]
> Lea el [**artículo configurar el conector de Graph**](configure-connector.md) para comprender el proceso de configuración general de los conectores de Graph.

Este artículo está disponible para cualquier persona que configure, ejecute y monitore un conector de Azure Data Lake Storage Gen2. Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector de Azure Data Lake Storage Gen2. En este artículo también se incluye información sobre [limitaciones.](#limitations)

En el artículo, usamos *Azure Storage* como término genérico para Azure [Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) y Azure Data Lake [Gen 2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

Escriba la cadena de conexión de almacenamiento principal. Esta cadena es necesaria para permitir el acceso a la cuenta de almacenamiento. Para encontrar la cadena de conexión, vaya a [Azure Portal](https://ms.portal.azure.com/#home) y vaya a la sección **Claves** de su cuenta de Azure Storage relevante.

Si prefiere no proporcionar **accountKey** (un parámetro en la cadena de conexión de almacenamiento principal), conceda acceso a nuestro servicio de conectores de Graph para los siguientes roles:

* Lector de datos blobs de almacenamiento
* Colaborador de datos de cola de almacenamiento
* Delegador de blobs de almacenamiento

Vaya a la **pestaña Control de** acceso de su cuenta de Azure Storage y siga las instrucciones para conceder acceso a la siguiente aplicación:

* **Id. de aplicación** de primera parte: 56c1da01-2129-48f7-9355-af6d59d42766
* **Nombre de la aplicación de primera parte:** Servicio de conector de Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Notificaciones de colas y cuenta de almacenamiento (opcional)

La compatibilidad para procesar cambios en tiempo real en el servicio de conectores de Graph podría agregarse en el futuro. En ese caso, supervisaremos las notificaciones de cambio de Azure Storage almacenadas en una cola. Deberá crear una cola en la misma cuenta que la cuenta de Azure Storage.

Después de crear una cola, vaya a la pestaña **Eventos** de la página de cola para configurar **la suscripción de eventos.** Elija todos los eventos Blob que recibirá la cola y conecte la cola a la cuenta de Azure Storage.

## <a name="step-4-assign-property-labels"></a>Paso 4: Asignar etiquetas de propiedad

Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones. Aunque este paso no es obligatorio, tener algunas etiquetas de propiedad mejorará la relevancia de la búsqueda y garantizará mejores resultados de búsqueda para los usuarios finales.

## <a name="step-5-manage-schema"></a>Paso 5: Administrar esquema

En la **pantalla Administrar** esquema, puede cambiar los atributos de esquema asociados con las propiedades, las opciones son **Consulta,** **Búsqueda,** **Recuperar** y **Refinar**. También puede agregar alias opcionales y elegir la **propiedad Content.**

## <a name="step-6-manage-search-permissions"></a>Paso 6: Administrar permisos de búsqueda

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Puede elegir ingerir las listas de control de acceso (ACL) de su cuenta de almacenamiento de [Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Cuando se establecen estos permisos de búsqueda, el contenido de la búsqueda se recorta en función de los permisos del usuario que ha iniciado sesión en [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/) Como alternativa, puede hacer que todo el contenido indizado desde su cuenta de almacenamiento sea visible para todos los usuarios de su organización. En este caso, todos los miembros de la organización tendrán acceso a todos los datos de la cuenta de almacenamiento.

El conector de Azure Data Lake Storage Gen2 Graph admite permisos de búsqueda visibles para todos **los** usuarios o solo para las personas con **acceso a este origen de datos.** Los datos indizados que aparecen en los resultados de la búsqueda podrían ser visibles para los usuarios de la organización que tienen acceso a cada elemento.

### <a name="azure-blob-storage"></a>Azure Blob Storage

Para una conexión a [Azure Blob Storage,](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)todo el contenido indizado desde el origen configurado es visible para todos los usuarios de la organización. Las listas de control de acceso no se admiten en el nivel de blob en Azure Blob Storage.

## <a name="step-7-set-the-refresh-schedule"></a>Paso 7: Establecer la programación de actualización

En la **pantalla Configuración de** actualización, puede establecer el intervalo de rastreo incremental y el intervalo de rastreo completo. Los intervalos predeterminados para el conector de Azure Data Lake Storage Gen2 son de 15 minutos para un rastreo incremental y de una semana para un rastreo completo.

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitaciones

No se puede volver a configurar una conexión publicada para Azure Blob Storage para el origen de Azure Data Lake Storage Gen2 y al revés. En estos escenarios, se recomienda configurar una nueva conexión.

Además, el tamaño de los archivos debe ser de 4 MB o menos para que se rastree. Los tipos de archivo admitidos actualmente son:

* Word (docx, .docm, .dotx, .dotm)
* PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)
* Excel (.xlsx, .xlsm)
* Formatos heredados de Office (.doc, .dot, etc.)
* Texto (.txt)
* HTML
* PDF

No se admiten archivos binarios como imágenes (.jpg, .bmp, etc.). Por ejemplo, si un archivo .docx contiene solo imágenes, es posible que se omita porque no devuelve ningún contenido.
