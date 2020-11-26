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
ms.openlocfilehash: 04ae757e95c6d3713ad03da701f99c669fb2a59c
ms.sourcegitcommit: 0ed8ec8b3c4e0f5f669005081fd8b2219f07b4f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420846"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="manage-your-connections-for-microsoft-search"></a>Administrar las conexiones de Microsoft Search

Para obtener acceso a los conectores y administrarlos, debe estar designado como administrador de búsqueda de su espacio empresarial. Póngase en contacto con el administrador de inquilinos para que le proporcione el rol de administrador de búsqueda.

## <a name="get-started"></a>Introducción

Vaya a la [pestaña conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) en el [centro de administración de Microsoft 365](https://admin.microsoft.com).

Para cada tipo de conector, el [centro de administración de Microsoft 365](https://admin.microsoft.com) admite las operaciones que se muestran en la tabla siguiente:

Operación | Conector creado por Microsoft | Asociado o conector personalizado
--- | --- | ---
Agregar una conexión | : heavy_check_mark: (vea [configurar el conector creado por Microsoft](configure-connector.md)) | : x: (consulte a su partner o a la experiencia del administrador del conector integrado personalizado)
Eliminar una conexión | :heavy_check_mark: | :heavy_check_mark:
Editar una conexión Publicada | : heavy_check_mark: nombre<br></br> : heavy_check_mark: Descripción<br></br> : heavy_check_mark: credenciales de autenticación para el origen de datos externo<br></br> : heavy_check_mark: credenciales de puerta de enlace para el origen de datos local<br></br> : heavy_check_mark: actualizar programación<br></br> | : heavy_check_mark: nombre<br></br> : heavy_check_mark: Descripción
Edición de una conexión de borrador | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a>Supervisar el estado de conexión

Después de crear una conexión, el número de elementos procesados se muestra en la ficha **conectores** de la página de **Microsoft Search** . Una vez finalizado correctamente el rastreo completo inicial, se muestra el progreso de los rastreos incrementales periódicos. Esta página proporciona información sobre las operaciones cotidianas del conector y una introducción a los registros y el historial de errores.

Se muestran cuatro Estados en la columna **Estado** para cada conexión:

* **Sincronización**. El conector está rastreando los datos del origen para indizar los elementos existentes y realizar actualizaciones.

* **Habilitada**: la conexión está habilitada y no se está ejecutando un rastreo activo en ella. **Hora de la última sincronización** indica cuándo se ha producido el último rastreo correcto. La conexión es tan nueva como la hora de la última sincronización.

* **Pausado**. Los administradores pausan los rastreos a través de la opción PAUSE. El siguiente rastreo se ejecuta solo cuando se reanuda de forma manual. Sin embargo, los datos de esta conexión continúan siendo aptos para la búsqueda.

* **Produjo un error**. La conexión tuvo un error crítico. Este error requiere intervención manual. El administrador debe realizar las acciones adecuadas según el mensaje de error que se muestra. Los datos que se indizaron hasta que se produjo el error se pueden buscar.

### <a name="view-your-last-crawl-info"></a>Ver la última información de rastreo

Después de que se complete correctamente el primer rastreo incremental inicial o completo, los últimos valores de datos de rastreo se muestran en el último encabezado de rastreo en el panel de detalles. Si no había ningún último rastreo que se haya ejecutado, no verá ninguna información en el último encabezado de rastreo. Esta información sobre el último rastreo le ayudará a comprender cómo se llevó a cabo el rastreo y a llevar a cabo los pasos necesarios siempre que sea necesario.

Los siguientes valores de último rastreo estarán disponibles para cada conexión:

Valor | Descripción
--- | ---
Completado en | Fecha y hora en que se completó el último rastreo
Tipo | Rastreo incremental o completo
Duración | ¿Cuánto tiempo tardó en completarse el último rastreo?
Operaciones correctas. | Número de elementos que se han recopilado correctamente en el último rastreo
Errores | Número de elementos con error en el último rastreo

### <a name="monitor-errors"></a>Supervisar errores

En cada **conector activo** de la ficha **conectores** , los errores de rastreo existentes se muestran en la ficha **error** . La pestaña enumera los códigos de error, el número de cada una de ellas y las opciones de descarga de registros de errores. Vea el ejemplo de la siguiente imagen. Seleccione un **código de error** para ver los detalles del error.

![Lista de conectores con un conector seleccionado y un panel de detalles que muestra 3 errores para este conector.](media/errormonitoring1.png)

Para ver los detalles específicos de un error, seleccione su código de error. Aparecerá una pantalla con los detalles del error y un vínculo. Los errores más recientes aparecen en la parte superior. Vea el ejemplo de la tabla siguiente.

![Lista de conectores con un conector seleccionado y un panel de detalles que muestra la lista de errores del conector.](media/errormonitoring2.png)

A continuación se muestra una lista de los distintos errores que pueden aparecer en cualquier conexión. Si estas soluciones no funcionan, póngase en contacto con el soporte técnico o envíenos [sus comentarios](connectors-feedback.md).

Código de error | Mensaje de error | Solución
--- | --- | ---
1000 | El origen de datos no está disponible. Compruebe la conexión a Internet o asegúrese de que el conector sigue teniendo acceso al origen de datos. | Este error se produce cuando el origen de datos no es accesible debido a un problema de red o cuando el propio origen de datos se elimina, se mueve o se cambia de nombre. Compruebe si los detalles del origen de datos proporcionados siguen siendo válidos.
1001 | No se pueden actualizar los datos porque el origen de datos está limitando el conector. | Para deslimitar el origen de datos, compruebe si se pueden aumentar los límites de escala o esperar hasta una hora menos intensa del día.
1002 | No se puede autenticar con el origen de datos. Compruebe que las credenciales asociadas a este origen de datos sean correctas. | Haga clic en **Editar** para actualizar las credenciales de autenticación.
1003 | La cuenta asociada con el conector no tiene permiso para obtener acceso al elemento. |  Asegúrese de que la cuenta correcta tiene acceso al elemento que desea indizar.
1004 | No se puede acceder a la puerta de enlace de datos local. Asegúrese de que el servicio de puerta de enlace se esté ejecutando y de que los detalles de la puerta de enlace se actualicen en la configuración de conexión. | Compruebe el equipo con la puerta de enlace, abra la aplicación de puerta de enlace de Power BI y asegúrese de que la puerta de enlace se esté ejecutando. Compruebe que la puerta de enlace usa la misma cuenta de administrador que Microsoft Search y, a continuación, asegúrese de que todos los detalles de la puerta de enlace se han actualizado en la configuración de conexión.
1005 | Las credenciales asociadas a este origen de datos han expirado. Renovar las credenciales y actualizar la conexión. | Haga clic en **Editar** para actualizar las credenciales de autenticación.
1006 | La versión de la puerta de enlace ya no está actualizada y no es compatible con este conector. Tendrá que actualizar la puerta de enlace. | Visite [instalar una puerta de enlace de datos local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) para descargar e instalar la versión más reciente de la puerta de enlace de Power BI en el equipo que contiene la puerta de enlace.
1007 | No se detectó ninguna licencia de Power BI válida. Necesita una licencia de Power BI válida para realizar este rastreo. | Necesita una licencia de Power BI válida para realizar este rastreo. Compruebe que la organización tiene una licencia válida. Si es así, inténtalo de nuevo. Si no es así, obtenga una licencia y vuelva a intentarlo.
1008 | El total de uso de la cuota de su inquilino ha alcanzado su límite. Pruebe a eliminar una conexión para liberar parte de su cuota o ajustar los filtros de ingesta para incluir menos datos. | Pruebe a eliminar una conexión para liberar parte de su cuota o ajustar los filtros de ingesta para incluir menos datos. Si estos no resuelven el problema, póngase en contacto con el soporte técnico de Microsoft.
2001 | La indización se limita debido a un gran número de actualizaciones en la cola. Dependiendo de la cola, la actualización puede tardar algún tiempo en completarse. | Espere hasta que se borre la cola.
2002 | Error de indización debido a un formato de elemento no admitido. | Consulte la documentación específica del conector para obtener más información.
2003 | Error de indización debido a contenido de elemento no admitido. | Consulte la documentación específica del conector para obtener más información.
2010 | Esta conexión ya no es válida debido a una actualización realizada por Microsoft. Elimine la conexión y cree una nueva. | Elimine la conexión y cree una nueva.
5000 | Se ha producido un error. Si el proceso sigue, póngase en contacto con el soporte técnico. |

## <a name="monitor-your-index-quota-utilization"></a>Supervisar el uso de la cuota de índice

La cuota de índice disponible y el consumo se muestran en la página de aterrizaje de los conectores.

![Barra de uso de cuota de índice](media/quota_utilization.png)

>[!NOTE]
>Durante el período de versión preliminar, cada organización que pruebe los conectores de Graph recibió una cuota fija gratuita de hasta 2 millones elementos en todas las conexiones. Con los conectores de Graph a disposición general, la cuota libre expirará el 1 de febrero de 2021 para las organizaciones que han estado usando conectores de gráficos en la versión preliminar.
>Los conectores de gráficos creados por Microsoft etiquetados como ["vista previa"](connectors-preview.md) no se incluirán en la cuota total del índice cargado para la organización. Sin embargo, se contará para el número máximo de 10 conexiones que puede configurar para su organización y el número máximo de 7 millones elementos que su organización puede indizar en todas las conexiones.

La barra de utilización de la cuota indicará varios Estados en función del consumo de cuota por parte de la organización:

Estado | Consumo de cuotas
--- | ---
Normal | 1-69%
Alto | 70-89%
Crítico | 90%-99%
Full | 100 %

El número de elementos indizados también se mostrará con cada conexión. El número de elementos indizados por cada conexión contribuye a la cuota total disponible para la organización.

Cuando se supere la cuota del índice en su organización, todas las conexiones activas se verán afectadas y las conexiones funcionarán en estado **límite superado** . En este estado, las conexiones activas  

* No podrá agregar nuevos elementos.

* Podrá actualizar o eliminar los elementos existentes.

Para solucionarlo, puede hacer lo siguiente:

* Obtenga información sobre cómo comprar una cuota de índice para su organización en [requisitos de licencia y precios](licensing.md).

* Identificar las conexiones que tienen demasiado contenido en recopilación y actualizarlas para indizar menos elementos para dejar espacio para la cuota. Para actualizar la conexión, debe eliminar y crear una nueva conexión con un nuevo filtro de recopilación que ofrezca menos elementos.

* Eliminar de forma permanente una o más conexiones

## <a name="limitations"></a>Limitaciones

* Al **publicar** un conector creado por Microsoft, la conexión puede tardar unos minutos en crearse. Durante este tiempo, la conexión mostrará su estado como pendiente.

* El [centro de administración de Microsoft 365](https://admin.microsoft.com) no permite editar el **esquema de búsqueda** después de que se publique una conexión. Para editar el esquema de búsqueda, elimine la conexión y, a continuación, cree una nueva.

* El rendimiento de la recopilación se limita a unos cuatro elementos por segundo.

* No se admiten actualizaciones de esquema. Después de crear una configuración de conexión, no hay forma de actualizar el esquema. Solo puede eliminar y volver a crear la conexión.

* Hay un límite de conexiones. Cada inquilino puede crear hasta 10 conexiones.

* La compatibilidad de edición para la conexión no está disponible. Una vez creada la conexión, no podrá modificarla ni cambiarla. Si necesita cambiar algún detalle, debe eliminar y volver a crear la conexión.
