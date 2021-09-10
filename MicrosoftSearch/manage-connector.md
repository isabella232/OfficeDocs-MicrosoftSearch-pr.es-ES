---
title: Administrar conectores de Microsoft Graph para Búsqueda de Microsoft
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Administrar Microsoft Graph Connectors para Búsqueda de Microsoft.
ms.openlocfilehash: dd82114ff6aa651b57ce1941685840906ecf7318
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973573"
---
# <a name="monitor-your-connections"></a>Supervise las conexiones

Para obtener acceso y administrar los conectores, debe estar designado como administrador de búsqueda para su inquilino. Póngase en contacto con el administrador de inquilinos para aprovisionar el rol de administrador de búsqueda.

## <a name="connection-operations"></a>Operaciones de conexión

Vaya a la [pestaña Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) de [la Centro de administración de Microsoft 365](https://admin.microsoft.com).

Para cada tipo de conector, el [Centro de administración de Microsoft 365](https://admin.microsoft.com) admite las operaciones que se muestran en la tabla siguiente:

Operación | Conectores de Graph por Microsoft | Conectores Graph asociados o de Graph de conexión
--- | --- | ---
Agregar una conexión | :heavy_check_mark: (Vea Información [general sobre el programa de instalación](configure-connector.md)) | :x: (Consulte a su socio o experiencia de usuario de administrador de conectores personalizados)
Eliminar una conexión | :heavy_check_mark: | :heavy_check_mark:
Editar una conexión publicada | :heavy_check_mark: Nombre y descripción<br></br> :heavy_check_mark: Configuración de conexión<br></br> :heavy_check_mark: Etiquetas de propiedades<br></br> :heavy_check_mark: Esquema<br></br> :heavy_check_mark: Programación de actualización<br></br> | :heavy_check_mark: Name<br></br> :heavy_check_mark: Descripción
Editar un borrador de conexión | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a>Supervisar el estado de conexión

Después de crear una conexión, el número de elementos procesados se muestra en la pestaña **Conectores** de **Búsqueda de Microsoft** página. Una vez completado correctamente el rastreo completo inicial, se muestra el progreso de los rastreos incrementales periódicos. Esta página proporciona información sobre las operaciones diarias del conector y una introducción a los registros y el historial de errores.

Cinco estados se muestran en la **columna Estado** en cada conexión:

* **Sincronización**. El conector rastrea los datos del origen para indizar los elementos existentes y realizar cualquier actualización.

* **Listo:** la conexión está lista y no hay ningún rastreo activo ejecutándose en ella. **La última hora de sincronización** indica cuándo se produjo el último rastreo correcto. La conexión es tan nueva como la última hora de sincronización.

* **Paused**. Los administradores pausan los rastreos a través de la opción de pausa. El siguiente rastreo solo se ejecuta cuando se reanuda manualmente. Sin embargo, los datos de esta conexión siguen siendo de búsqueda.

* **Error**. La conexión tuvo un error crítico. Este error requiere una intervención manual. El administrador debe realizar las acciones adecuadas en función del mensaje de error que se muestra. Los datos que se indizaron hasta que se produjo el error son de búsqueda.

* **Error al eliminar**. Error al eliminar la conexión. Según el motivo del error, es posible que los datos aún se indexan, que aún se pueda consumir la cuota de elementos y que los rastreos aún se ejecuten para la conexión. Se recomienda intentar eliminar la conexión de nuevo en este estado.

## <a name="monitor-your-index-quota-utilization"></a>Supervisar el uso de la cuota de índice

La cuota de índice y el consumo disponibles se muestran en la página de aterrizaje de conectores.

:::image type="content" alt-text="Barra de uso de cuota de índice." source="media/quota_utilization.png" lightbox="media/quota_utilization.png":::

La barra de uso de cuota indicará varios estados en función del consumo de cuota por parte de la organización:

Estado | Niveles de uso de cuota
--- | --- 
Normal | 0-79%
Alto | 80-89%
Crítico | 90%-99%
Full | 100 %

El número de elementos indizados también se mostrará con cada conexión. El número de elementos indizados por cada conexión contribuye a la cuota total disponible para su organización.

Cuando se supere la cuota de índice para la organización, todas las conexiones activas se verán afectadas y dichas conexiones funcionarán en estado de **límite superado.** En este estado, las conexiones activas  

* No podrá agregar nuevos elementos.

* Podrá actualizar o eliminar elementos existentes.

Para solucionar esto, puede hacer lo siguiente:

* Obtenga información sobre cómo comprar cuota de índice para su organización en [Requisitos de licencias y precios.](licensing.md)

* Identificar las conexiones que tienen demasiado contenido que se está ingiere y actualizarlas para indizar menos elementos para dar espacio a la cuota. Para actualizar la conexión, debe eliminar y crear una nueva conexión con un nuevo filtro de ingesta que traiga menos elementos.

* Elimine de forma permanente una o más conexiones.
