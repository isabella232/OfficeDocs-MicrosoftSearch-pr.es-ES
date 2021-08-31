---
title: Administrar ubicaciones
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 8ab9aa00-cd74-405f-8410-9a1c3cfacdb9
description: Con el tiempo, es posible que deba actualizar el estado y el contenido de una ubicación para que siga siendo relevante.
ms.openlocfilehash: 0c93e29c8c899a4b70a30cf97354cf00fc19667f
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701998"
---
# <a name="manage-locations"></a>Administrar ubicaciones

## <a name="location"></a>Ubicación

La ubicación permite a los usuarios buscar direcciones y localizar edificios de su organización proporcionando una ubicación exacta de oficinas, campus y edificios, junto con indicaciones para llegar a ellos. Los administradores deben agregar todas las ubicaciones importantes de su organización. A diferencia de los marcadores y las preguntas y respuestas, el índice no se actualiza inmediatamente y pueden transcurrir varias horas hasta que las ubicaciones nuevas o modificadas aparezcan en los resultados de búsqueda.

### <a name="add-or-edit-a-single-location"></a>Agregar o modificar una ubicación única

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**Ubicaciones**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)
1. Para agregar una nueva ubicación, seleccione **Agregar**.
1. Para editar una ubicación, selecciónela en la lista de ubicaciones correspondiente.
1. Al agregar o editar la información, la vista previa se actualizará automáticamente.
1. Guarde los cambios.

### <a name="bulk-add-or-edit-locations"></a>Agregar o editar ubicaciones en bloque

Los administradores pueden usar las características de Importar o Exportar para crear o editar ubicaciones en bloque.

Use la característica importar o exportar para:

1. Agregar ubicaciones en bloque: introduzca la información en el archivo de plantilla de ubicaciones y, a continuación, impórtelo.
1. Editar ubicaciones en bloque: exporte las ubicaciones a un archivo CSV; a continuación, edite la información de las ubicaciones en el archivo CSV exportado e importe el archivo CSV actualizado.
1. Ubicaciones de copia de seguridad: exporte las ubicaciones existentes a .csv archivo.

Para exportar o importar ubicaciones:

1. En la esquina superior derecha de la pestaña **Ubicaciones**, seleccione **Importar**.
Seleccione **Exportar** para descargar todas las ubicaciones existentes en un archivo CSV.
1. En el panel derecho, elija la opción Importar mediante archivo CSV.
Descargue el archivo de plantilla para obtener una lista de la información y los campos requeridos.
1. Agregue o edite la información de las ubicaciones en el archivo de plantilla y, a continuación, guárdelo en su equipo.
1. En el panel **Importar** ubicaciones, haga clic en **Examinar** y, a continuación, en el archivo CSV que desea importar.
1. Seleccione **Importar**.

Estos son algunos puntos importantes en relación con el archivo de plantilla:

- Nunca modifique los datos de los campos: *Id*, *última modificación* y *modificado por*
- Si incluye el *identificador de* una ubicación existente, se reemplazará por la información del archivo de importación.
- Si hay una ubicación existente con el mismo nombre, la ubicación se actualizará con información en el archivo de importación.
- No todos los campos del archivo de plantilla son obligatorios y los campos obligatorios varían en función del estado de la ubicación.
- Según el campo *Estado,* las ubicaciones se guardarán como borrador, sugeridas, programadas o se publicarán automáticamente.
- Para los partners que administran varias organizaciones, puede exportar las ubicaciones de una organización e importarlas a otra. Sin embargo, debe eliminar los datos de la columna *Id* antes de la importación.

> [!NOTE]
> No se pueden importar ubicaciones si hay errores en el archivo de plantilla. Para evitar errores, asegúrese de que el archivo de importación está correctamente formateado y contiene toda la información necesaria.

Para obtener más información sobre cómo evitar errores, consulte [Evitar errores de importación](manage-bookmarks.md#prevent-import-errors).
