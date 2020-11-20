---
title: Azure Data Lake Connector para Microsoft Search
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
description: Configurar el conector de Azure Data Lake Storage-limpieza para Microsoft Search
ms.openlocfilehash: 860c923c62495c7df20152fb530797e390949305
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367590"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Conector de Azure Data Lake Storage-reconexión

Con el conector de Azure Data Lake Storage-post, los usuarios de la organización pueden buscar archivos almacenados en [Azure BLOB Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) y cuentas de [almacenamiento de Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) .

Este artículo está destinado a los administradores de [Microsoft 365](https://www.microsoft.com/microsoft-365) o a cualquier usuario que configure, ejecute y supervise un conector de Azure Data Lake Storage. Proporciona información general sobre la configuración de conectores, las capacidades, las limitaciones y las técnicas de solución de problemas. En el artículo, usamos *Azure Storage* como un término genérico para el almacenamiento de [blobs de Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) y el [almacenamiento de Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos

### <a name="primary-storage-connection-string"></a>Cadena de conexión de almacenamiento principal

En la pantalla **autenticación y configuración** , especifique la cadena de conexión de almacenamiento principal. Esa cadena es necesaria para permitir el acceso a su cuenta de almacenamiento. Para encontrar la cadena de conexión, vaya a [Azure portal](https://ms.portal.azure.com/#home) y vaya a la sección **claves** de la cuenta de almacenamiento de Azure correspondiente. Copie y pegue la cadena de conexión en el campo correspondiente de la pantalla.

Si no prefiere proporcionar el **AccountKey** (un parámetro en la cadena de conexión de almacenamiento principal), tendrá que conceder acceso a nuestro servicio de conectores de Graph para los roles siguientes.

* Lector de datos BLOB de almacenamiento
* Colaborador de datos de cola de almacenamiento
* Delegado de BLOB de almacenamiento (solo para almacenamiento jerárquico)

Navegue a la pestaña **control de acceso** de la cuenta de Azure Storage y siga las instrucciones para conceder acceso a la siguiente aplicación:

* **Identificador de la aplicación de primer fabricante:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Nombre de la aplicación de primer fabricante:** Servicio conector de Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Notificaciones de cuenta de almacenamiento y de cola (opcional)

La compatibilidad para procesar cambios en tiempo real en el servicio de conectores de gráficos se puede Agregar en el futuro. En ese caso, se supervisarán las notificaciones de cambios de almacenamiento de Azure almacenadas en una cola. Deberá crear una cola en la misma cuenta que la cuenta de almacenamiento de Azure.

Después de crear una cola, vaya a la ficha **eventos** de la página cola para configurar la **suscripción de eventos**. Elija todos los eventos BLOB que recibirá la cola y conecte la cola a la cuenta de almacenamiento de Azure.

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

En la pantalla **administrar permisos de búsqueda** , puede optar por recopilar las listas de control de acceso (ACL) de su cuenta de [almacenamiento de Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) . Cuando se establecen estos permisos de búsqueda, el contenido de la búsqueda se recorta en función de los permisos asignados al usuario de [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) que ha iniciado la búsqueda en el contenido. Como alternativa, puede elegir que todo el contenido indizado de su cuenta de almacenamiento esté visible para todos los usuarios de la organización. En este caso, todos los usuarios de la organización tendrán acceso a todos los datos de la cuenta de almacenamiento.

### <a name="azure-blob-storage"></a>Azure Blob Storage

Para una conexión a [Azure BLOB Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), todo el contenido indizado desde el origen configurado es visible para todos los usuarios de la organización. Las listas de control de acceso no se admiten en el nivel de BLOB en Azure BLOB Storage.

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda

El conector de Azure Data Lake Storage-o solo admite permisos de búsqueda visibles para **todos** los usuarios o **solo personas con acceso a este origen de datos**. Los datos indizados que aparecen en los resultados de la búsqueda pueden ser visibles para todos los usuarios de la organización o solo para los usuarios que tienen acceso a cada elemento.

## <a name="assign-property-labels"></a>Asignar etiquetas de propiedad

Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones. Aunque este paso no es obligatorio, tener algunas etiquetas de propiedades mejorará la relevancia de la búsqueda y garantizará resultados de búsqueda más precisos para los usuarios finales.

## <a name="manage-schema"></a>Administrar esquema

En la pantalla **administrar esquema** , tiene la opción de cambiar los atributos de esquema (**consultable**, **búsquedas**, **recuperables** y **refinables**) asociados con las propiedades, agregar alias opcionales y elegir la propiedad de **contenido** .

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización

En la pantalla de configuración de la **actualización** , puede establecer el intervalo de rastreo incremental y el intervalo de rastreo completo. Los intervalos predeterminados para el conector de Azure Data Lake Storage/1 son 15 minutos para un rastreo incremental y una semana para un rastreo completo.

## <a name="limitations"></a>Limitaciones

No se puede volver a configurar una conexión publicada para el almacenamiento de blobs de Azure para el origen de Azure Data Lake Storage-lectura y viceversa. En estos casos, se recomienda configurar una nueva conexión.
