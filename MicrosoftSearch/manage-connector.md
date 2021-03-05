---
title: Administrar Conectores de Microsoft Graph para Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Administrar Conectores de Microsoft Graph para Microsoft Search.
ms.openlocfilehash: 488b6e9452e381f8fc64ad06c6f063aa170ca7f5
ms.sourcegitcommit: 3ed4d21510020045d25e8c5b7e168013d96c1b7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50464044"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>Supervise las conexiones

Para obtener acceso y administrar los conectores, debe estar designado como administrador de búsqueda para su inquilino. Póngase en contacto con el administrador de inquilinos para aprovisionar el rol de administrador de búsqueda.

## <a name="connection-operations"></a>Operaciones de conexión

Vaya a la [pestaña Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) en el Centro de administración de [Microsoft 365](https://admin.microsoft.com).

Para cada tipo de conector, el Centro de [administración de Microsoft 365](https://admin.microsoft.com) admite las operaciones que se muestran en la tabla siguiente:

Operación | Conector creado por Microsoft | Conector asociado o personalizado
--- | --- | ---
Agregar una conexión | :heavy_check_mark: (Consulte [Configure your Microsoft-built connector](configure-connector.md)) | :x: (Consulte a su socio o experiencia de usuario de administrador de conectores personalizados)
Eliminar una conexión | :heavy_check_mark: | :heavy_check_mark:
Editar una conexión publicada | :heavy_check_mark: Name<br></br> :heavy_check_mark: Descripción<br></br> :heavy_check_mark: credenciales de autenticación para el origen de datos externo<br></br> :heavy_check_mark: credenciales de puerta de enlace para el origen de datos local<br></br> :heavy_check_mark: Programación de actualización<br></br> | :heavy_check_mark: Name<br></br> :heavy_check_mark: Descripción
Editar un borrador de conexión | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a>Supervisar el estado de la conexión

Después de crear una conexión, el número de elementos **procesados** se muestra en la pestaña Conectores de la **página Búsqueda de Microsoft.** Una vez completado correctamente el rastreo completo inicial, se muestra el progreso de los rastreos incrementales periódicos. Esta página proporciona información sobre las operaciones diarias del conector y una introducción a los registros y el historial de errores.

Cuatro estados se muestran en la **columna Estado** en cada conexión:

* **Sincronización**. El conector rastrea los datos del origen para indizar los elementos existentes y realizar cualquier actualización.

* **Enabled:** la conexión está habilitada y no hay ningún rastreo activo ejecutándose en ella. **La última hora de sincronización** indica cuándo se produjo el último rastreo correcto. La conexión es tan nueva como la última hora de sincronización.

* **Paused**. Los administradores pausan los rastreos a través de la opción de pausa. El siguiente rastreo solo se ejecuta cuando se reanuda manualmente. Sin embargo, los datos de esta conexión siguen siendo de búsqueda.

* **Error**. La conexión tuvo un error crítico. Este error requiere una intervención manual. El administrador debe realizar las acciones adecuadas en función del mensaje de error que se muestra. Los datos que se indizaron hasta que se produjo el error son de búsqueda.

## <a name="monitor-your-index-quota-utilization"></a>Supervisar el uso de la cuota de índice

La cuota de índice y el consumo disponibles se muestran en la página de aterrizaje de conectores.

![Barra de uso de cuota de índice](media/quota_utilization.png)

>[!NOTE]
>Durante el período de vista previa, a todas las organizaciones que probaron los conectores de Graph se les proporcionó una cuota fija gratuita de hasta 2 millones de elementos en todas las conexiones. Con los conectores de Graph disponibles en general, la cuota gratuita expirará el 1 de abril de 2021 para las organizaciones que han estado usando conectores de Graph en versión preliminar.
>Los conectores graph creados por Microsoft etiquetados como ["Versión preliminar"](connectors-preview.md) no se incluirán en la cuota total de índice cargado para su organización. Sin embargo, contará para el número máximo de 10 conexiones que puede configurar para su organización y el número máximo de 7 millones de elementos que su organización puede indizar entre conexiones; cada conexión tiene un límite de 700 000 elementos. 

La barra de uso de cuota indicará varios estados en función del consumo de cuota por parte de la organización:

Estado | Consumo de cuota
--- | ---
Normal | 1-69%
Alto | 70-89%
Crítico | 90%-99%
Full | 100 %

El número de elementos indizados también se mostrará con cada conexión. El número de elementos indizados por cada conexión contribuye a la cuota total disponible para su organización.

Cuando se supere la cuota de índice para la organización, todas las conexiones activas se verán afectadas y dichas conexiones funcionarán en estado de **límite superado.** En este estado, las conexiones activas  

* No podrá agregar nuevos elementos.

* Podrá actualizar o eliminar elementos existentes.

Para solucionar esto, puede hacer lo siguiente:

* Obtenga información sobre cómo comprar cuota de índice para su organización en [Requisitos de licencias y precios.](licensing.md)

* Identificar las conexiones que tienen demasiado contenido que se está ingiere y actualizarlas para indizar menos elementos para dar espacio a la cuota. Para actualizar la conexión, debe eliminar y crear una nueva conexión con un nuevo filtro de ingesta que traiga menos elementos.

* Eliminar de forma permanente una o más conexiones
