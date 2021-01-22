---
title: Conector de Azure Data Lake para Microsoft Search
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector Azure Data Lake Storage Gen2 para Microsoft Search
ms.openlocfilehash: 8891c9a1fdf5397c397a941b5131f014db9e7a54
ms.sourcegitcommit: 597c338bf9c1c425747ac74a9a1ae57c5e8957ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49920726"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Conector de Azure Data Lake Storage Gen2

Con el conector Azure Data Lake Storage Gen2, los usuarios de su organización pueden buscar archivos almacenados en cuentas de [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) y Azure Data Lake Gen [2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

Este artículo está disponible para administradores de [Microsoft 365](https://www.microsoft.com/microsoft-365) o cualquier persona que configure, ejecute y monitore un conector de Azure Data Lake Storage Gen2. Proporciona información general sobre la configuración del conector, las capacidades, las limitaciones y las técnicas de solución de problemas. En el artículo, usamos *Azure Storage* como término genérico para Azure [Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) y Azure Data Lake [Gen 2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos

### <a name="primary-storage-connection-string"></a>Cadena de conexión de almacenamiento principal

En la **pantalla Autenticación y configuración,** proporcione la cadena de conexión de almacenamiento principal. Esa cadena es necesaria para permitir el acceso a la cuenta de almacenamiento. Para encontrar la cadena de conexión, vaya a [Azure Portal](https://ms.portal.azure.com/#home) y vaya a la sección **Claves** de su cuenta de Azure Storage relevante. Copie y pegue la cadena de conexión en el campo correspondiente de la pantalla.

Si no prefiere proporcionar **accountKey** (un parámetro en la cadena de conexión de almacenamiento principal), deberá conceder acceso a nuestro servicio de conectores de Graph para los siguientes roles. (Esta característica solo es compatible con el almacenamiento jerárquico. El almacenamiento de blobs tradicional tendrá que proporcionar AccountKey).
* Lector de datos blobs de almacenamiento
* Colaborador de datos de cola de almacenamiento
* Delegador de blobs de almacenamiento

Vaya a la **pestaña Control de** acceso de su cuenta de Azure Storage y siga las instrucciones para conceder acceso a la siguiente aplicación:

* **Id. de aplicación** de primera parte: 56c1da01-2129-48f7-9355-af6d59d42766
* **Nombre de la aplicación de primera parte:** Servicio de conector de Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Notificaciones de colas y cuenta de almacenamiento (opcional)

La compatibilidad para procesar cambios en tiempo real en el servicio de conectores de Graph podría agregarse en el futuro. En ese caso, supervisaremos las notificaciones de cambio de Azure Storage almacenadas en una cola. Deberá crear una cola en la misma cuenta que la cuenta de Azure Storage.

Después de crear una cola, vaya a la pestaña **Eventos** de la página de cola para configurar **la suscripción de eventos.** Elija todos los eventos Blob que recibirá la cola y conecte la cola a la cuenta de Azure Storage.

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

En la pantalla Administrar **permisos** de búsqueda, puede elegir ingerir las listas de control de acceso (ACL) de su cuenta de almacenamiento de [Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Cuando se establecen estos permisos de búsqueda, el contenido de la búsqueda se recorta en función de los permisos asignados al usuario de [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) que ha iniciado sesión buscando en el contenido. Como alternativa, puede hacer que todo el contenido indizado desde su cuenta de almacenamiento sea visible para todos los usuarios de la organización. En este caso, todos los miembros de la organización tendrán acceso a todos los datos de la cuenta de almacenamiento.

### <a name="azure-blob-storage"></a>Azure Blob Storage

Para una conexión a [Azure Blob Storage,](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)todo el contenido indizado desde el origen configurado es visible para todos los usuarios de la organización. Las listas de control de acceso no se admiten en el nivel de blob en Azure Blob Storage.

## <a name="search-permissions"></a>Permisos de búsqueda

El conector de Azure Data Lake Storage  Gen2 admite permisos de búsqueda visibles para todos o solo las personas con **acceso a este origen de datos.** Los datos indizados que aparecen en los resultados de la búsqueda podrían ser visibles para todos los usuarios de la organización o solo para los usuarios que tienen acceso a cada elemento.

## <a name="assign-property-labels"></a>Asignar etiquetas de propiedad

Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones. Aunque este paso no es obligatorio, tener algunas etiquetas de propiedad mejorará la relevancia de la búsqueda y garantizará resultados de búsqueda más precisos para los usuarios finales.

## <a name="manage-schema"></a>Administrar esquema

En  la pantalla Administrar esquema, tiene la opción de cambiar los atributos de esquema(consultables, que se pueden **buscar,** recuperables y que se pueden **refinar)** asociados con las propiedades, agregar alias opcionales y elegir la propiedad **Content.**

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización

En la **pantalla Configuración de** actualización, puede establecer el intervalo de rastreo incremental y el intervalo de rastreo completo. Los intervalos predeterminados para el conector de Azure Data Lake Storage Gen2 son de 15 minutos para un rastreo incremental y de una semana para un rastreo completo.

## <a name="limitations"></a>Limitaciones

No se puede volver a configurar una conexión publicada para Azure Blob Storage para el origen de Azure Data Lake Storage Gen2 y viceversa. En estos escenarios, se recomienda configurar una nueva conexión.
