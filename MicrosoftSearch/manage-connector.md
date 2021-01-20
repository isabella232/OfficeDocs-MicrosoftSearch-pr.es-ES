---
title: Administrar conectores de Microsoft Graph para Microsoft Search
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
description: Administrar conectores de Microsoft Graph para Microsoft Search.
ms.openlocfilehash: 5258f26a5c97be4ee9f90c7a8b2b9bb8fec447bc
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905934"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>Supervisar las conexiones

Para obtener acceso a los conectores y administrarlos, debe designarse como administrador de búsqueda para su espacio empresarial. Póngase en contacto con el administrador de inquilinos para que le aprovisione el rol de administrador de búsqueda.

## <a name="connection-operations"></a>Operaciones de conexión

Vaya a la [pestaña Conectores en](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) el Centro de administración de [Microsoft 365.](https://admin.microsoft.com)

Para cada tipo de conector, el Centro [de administración de Microsoft 365](https://admin.microsoft.com) admite las operaciones que se muestran en la tabla siguiente:

Operación | Conector creado por Microsoft | Conector asociado o personalizado
--- | --- | ---
Agregar una conexión | :heavy_check_mark: (Vea [Configurar el conector creado por Microsoft)](configure-connector.md) | :x: (Consulte la experiencia de usuario del administrador del conector personalizado o asociado)
Eliminar una conexión | :heavy_check_mark: | :heavy_check_mark:
Editar una conexión publicada | :heavy_check_mark: Name<br></br> :heavy_check_mark: Descripción<br></br> :heavy_check_mark: credenciales de autenticación para el origen de datos externo<br></br> :heavy_check_mark: credenciales de puerta de enlace para el origen de datos local<br></br> :heavy_check_mark: Programación de actualización<br></br> | :heavy_check_mark: Name<br></br> :heavy_check_mark: Descripción
Editar un borrador de conexión | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a>Supervisar el estado de conexión

Después de crear una conexión, el número de elementos **procesados** se muestra en la pestaña Conectores de la **página Búsqueda de Microsoft.** Una vez completado correctamente el rastreo completo inicial, se muestra el progreso de los rastreos incrementales periódicos. En esta página se proporciona información sobre las operaciones diarias del conector y una introducción a los registros y al historial de errores.

Cuatro estados se muestran en la columna **Estado** en cada conexión:

* **Sincronización.** El conector rastrea los datos del origen para indizar los elementos existentes y realizar cualquier actualización.

* **Habilitado:** la conexión está habilitada y no hay ningún rastreo activo ejecutándose en ella. **La última hora de sincronización** indica cuándo se produjo el último rastreo correcto. La conexión es tan reciente como la última hora de sincronización.

* **En pausa.** Los administradores pausan los rastreos mediante la opción de pausa. El siguiente rastreo solo se ejecuta cuando se reanuda manualmente. Sin embargo, los datos de esta conexión siguen siendo de búsqueda.

* **Error**. La conexión tuvo un error crítico. Este error requiere la intervención manual. El administrador debe tomar las medidas adecuadas en función del mensaje de error que se muestra. Los datos que se indizaron hasta que se produjo el error se pueden buscar.

## <a name="monitor-your-index-quota-utilization"></a>Supervisar el uso de la cuota de índice

La cuota de índice y el consumo disponibles se muestran en la página de aterrizaje de los conectores.

![Barra de uso de cuota de índice](media/quota_utilization.png)

>[!NOTE]
>Durante el período de vista previa, todas las organizaciones que probaron conectores de Graph se proporcionaron una cuota fija gratuita de hasta 2 millones de elementos en todas las conexiones. Con los conectores de Graph que están generalmente disponibles, la cuota gratuita expirará el 1 de febrero de 2021 para las organizaciones que han estado usando conectores de Graph en versión preliminar.
>Los conectores de Graph creados por Microsoft etiquetados como ["Versión preliminar"](connectors-preview.md) no se incluirán en la cuota total de índice cargada para su organización. Sin embargo, se contará para el número máximo de 10 conexiones que puede configurar para su organización y el número máximo de 7 millones de elementos que su organización puede indizar entre conexiones; cada conexión tiene un límite de 700 000 elementos. 

La barra de uso de la cuota indicará varios estados en función del consumo de cuota por parte de la organización:

Estado | Consumo de cuota
--- | ---
Normal | 1-69%
Alto | 70-89%
Crítico | 90%-99%
Full | 100 %

El número de elementos indizados también se mostrará con cada conexión. El número de elementos indizados por cada conexión contribuye a la cuota total disponible para su organización.

Cuando se supera la cuota de índice para su organización, se verán afectadas todas las conexiones activas y dichas conexiones funcionarán en estado de **límite superado.** En este estado, las conexiones activas  

* No podrá agregar nuevos elementos.

* Podrá actualizar o eliminar elementos existentes.

Para solucionar este problema, puede realizar cualquiera de las siguientes acciones:

* Obtenga información sobre cómo comprar la cuota de índice para su organización a precios [y requisitos de licencia.](licensing.md)

* Identificar las conexiones que tienen demasiado contenido ingerido y actualizarlas para indizar menos elementos para que haya espacio para la cuota. Para actualizar la conexión, debe eliminar y crear una nueva conexión con un nuevo filtro de ingesta que aporta menos elementos.

* Eliminar permanentemente una o más conexiones