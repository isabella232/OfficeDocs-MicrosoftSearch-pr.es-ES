---
title: Azure Data Lake Connector para Microsoft Search
ms.author: v-pamcn
author: monaray
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
ms.openlocfilehash: bedd7307ca2add52408bb9a5e3b3b21fd75df258
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "37950024"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Conector de Azure Data Lake Storage-reconexión

Con el conector de [Azure Data Lake Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) -out, los usuarios de la organización pueden buscar archivos y su contenido. Este conector obtiene acceso a los datos almacenados en contenedores de BLOB de Azure y carpetas habilitadas para jerarquía dentro de una cuenta de Azure Data Lake Storage Gen 2.

Este artículo está destinado a los administradores de Microsoft 365 o a cualquier usuario que configure, ejecute y supervise un conector de Azure Data Lake Storage. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos

### <a name="primary-storage-connection-string"></a>Cadena de conexión de almacenamiento principal 
En la pantalla **autenticación y configuración** , especifique la cadena de conexión de almacenamiento principal. Esa cadena es necesaria para permitir el acceso a su cuenta de almacenamiento. Para encontrar la cadena de conexión, vaya a [Azure portal](https://ms.portal.azure.com/#home) y vaya a la sección **claves** de la cuenta de Azure Data Lake Storage. Copie y pegue la cadena de conexión en el campo correspondiente de la pantalla.

Si no desea proporcionar el **AccountKey** (un parámetro en la cadena de conexión de almacenamiento principal), tiene que conceder acceso de lectura a nuestro servicio de conectores de Graph. En la pestaña **control de acceso** de la cuenta de Azure Data Lake Storage de Azure, siga las instrucciones de esa página para conceder acceso a la siguiente aplicación:
* **Identificador de la aplicación de primer fabricante:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Nombre de la aplicación de primer fabricante:** Servicio conector de Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Notificaciones de cuenta de almacenamiento y de cola (opcional)
La compatibilidad para procesar cambios en tiempo real en el servicio de conectores de gráficos se puede Agregar en el futuro. En ese caso, se supervisarán las notificaciones de cambios de Azure Data Lake Storage de la lista de espera almacenadas en una cola. Tendrá que crear una cola en la misma cuenta que su Azure Data Lake Storage-o en otra cuenta de almacenamiento.

Después de crear una cola, vaya a la ficha **eventos** de la página cola para configurar la suscripción de eventos. Elija todos los eventos BLOB que recibirá la cola y conéctela a la cuenta de Azure Data Lake Storage.

## <a name="manage-the-search-schema"></a>Administrar el esquema de búsqueda
En la pantalla **administrar esquema** , tiene la opción de cambiar los atributos de esquema (**consultable**, en **búsqueda**y **recuperable**) asociados con las propiedades administradas. Estos atributos de propiedad administrada son datos indizados desde su cuenta de Azure Data Lake Storage.

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda
En la pantalla **administrar permisos de búsqueda** , puede optar por recopilar las listas de control de acceso (ACL) de su cuenta de almacenamiento. Cuando se establecen estos permisos de búsqueda, el contenido de la búsqueda se recorta en función de los permisos asignados al usuario de Azure AD que haya iniciado la búsqueda en el contenido. Como alternativa, puede elegir que todo el contenido indizado de su cuenta de almacenamiento esté visible para todos los usuarios de la organización. En este caso, todos los usuarios de la organización tendrán acceso a todos los datos de la cuenta de almacenamiento.
 
## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización
En la pantalla de configuración de la **actualización** , puede establecer el intervalo de rastreo incremental y el intervalo de rastreo completo. Los intervalos predeterminados para el conector de Azure Data Lake Storage/1 son 15 minutos para un rastreo incremental y una semana para un rastreo completo.
 
## <a name="limitations"></a>Limitaciones
Actualmente, el acceso multiprotocolo de la US2 de almacenamiento de datos de Azure Data Lake está disponible únicamente en el centro de EE. UU., Oriente Central estadounidense, Canadá central, este de Asia oriental, Europa occidental, norte Europa, sudeste asiático, oeste Europa, oeste de EE. UU., Australia Oriente, Japón East, oeste de Europa y Brasil South.

Para obtener actualizaciones y más información, vea [acceso de varios protocolos en Azure Data Lake Storage (versión preliminar)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access).


