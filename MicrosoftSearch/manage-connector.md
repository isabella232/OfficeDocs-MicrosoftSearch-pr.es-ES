---
title: Administrar conectores de Microsoft Graph para Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Administrar conectores de Microsoft Graph para Microsoft Search.
ms.openlocfilehash: 5aab310a05d073221918a8aaa80ea1e06c818e51
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "37950071"
---
# <a name="manage-your-connector-for-microsoft-search"></a>Administrar el conector para Microsoft Search

Para obtener acceso a los conectores y administrarlos, debe estar designado como administrador de búsqueda de su espacio empresarial. Póngase en contacto con el administrador de inquilinos para que le proporcione el rol de administrador de búsqueda.

## <a name="get-started"></a>Introducción

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com).
2. Vaya a **configuración** > **conectores**de**Microsoft Search** > .

Para cada tipo de conector, el [centro de administración de Microsoft 365](https://admin.microsoft.com) admite las operaciones que se muestran en la tabla siguiente:

**Operación** | **Conector creado por Microsoft** | **Asociado o conector personalizado**
--- | --- | ---
Agregar una conexión | : heavy_check_mark: (vea [configurar el conector creado por Microsoft](configure-connector.md)) | : x: (consulte a su partner o a la experiencia del administrador del conector integrado personalizado)
Eliminar una conexión | :heavy_check_mark: | :heavy_check_mark:
Editar una conexión Publicada | : heavy_check_mark: nombre<br></br> : heavy_check_mark: Descripción<br></br> : heavy_check_mark: credenciales de autenticación para el origen de datos externo<br></br> : heavy_check_mark: credenciales de puerta de enlace para el origen de datos local<br></br> : heavy_check_mark: actualizar programación<br></br> | : heavy_check_mark: nombre<br></br> : heavy_check_mark: Descripción
Edición de una conexión de borrador | :heavy_check_mark: | días

## <a name="monitor-your-connection-status"></a>Supervisar el estado de conexión
Después de crear una conexión, el número de elementos procesados se muestra en la ficha **conectores** de la página de **Microsoft Search** . Una vez finalizado correctamente el rastreo completo inicial, se muestra el progreso de los rastreos incrementales periódicos. Esta página proporciona información sobre las operaciones cotidianas del conector y una introducción a los registros y el historial de errores.

Se muestran cuatro Estados en la columna **Estado** para cada conexión:
* **Sincronización**. El conector está rastreando los datos del origen para indizar los elementos existentes y realizar actualizaciones.
* **Habilitada**: la conexión está habilitada y no se está ejecutando un rastreo activo en ella. **Hora de la última sincronización** indica cuándo se ha producido el último rastreo correcto. La conexión es tan nueva como la hora de la última sincronización.
* **Pausado**. Los administradores pausan los rastreos a través de la opción PAUSE. El siguiente rastreo se ejecuta solo cuando se reanuda de forma manual. Sin embargo, los datos de esta conexión continúan siendo aptos para la búsqueda.
* **Produjo un error**. La conexión tuvo un error crítico. Este error requiere intervención manual. El administrador debe realizar las acciones adecuadas según el mensaje de error que se muestra. Los datos que se indizaron hasta que se produjo el error se pueden buscar.

### <a name="monitor-errors"></a>Supervisar errores
En cada **conector activo** de la ficha **conectores** , los errores de rastreo existentes se muestran en la ficha **error** . La pestaña enumera los códigos de error, el número de cada una de ellas y las opciones de descarga de registros de errores. Vea el ejemplo de la siguiente imagen. Seleccione un **código de error** para ver los detalles del error.

![Lista de conectores con un conector seleccionado y un panel de detalles que muestra 3 errores para este conector.](media/errormonitoring1.png)

Para ver los detalles específicos de un error, seleccione su código de error. Aparecerá una pantalla con los detalles del error y un vínculo. Los errores más recientes aparecen en la parte superior. Vea el ejemplo de la tabla siguiente.

![Lista de conectores con un conector seleccionado y un panel de detalles que muestra la lista de errores del conector. ](media/errormonitoring2.png)

## <a name="preview-limitations"></a>Limitaciones de la vista previa
* Al **publicar** un conector creado por Microsoft, la conexión puede tardar unos minutos en crearse. Durante este tiempo, la conexión muestra su estado como pendiente. Además, no se actualiza automáticamente, por lo que debe actualizarse manualmente.
* El [centro de administración de Microsoft 365](https://admin.microsoft.com) no permite ver y editar el **esquema de búsqueda** una vez que se ha publicado una conexión. Para editar el esquema de búsqueda, elimine la conexión y, a continuación, cree una nueva.
* Al administrar la **programación de actualización**de la conexión, se muestra el número de elementos que se sincronizan durante cada sesión. Sin embargo, el historial de sincronización no está disponible.
