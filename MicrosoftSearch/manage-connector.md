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
ms.openlocfilehash: cf1231f8003d166977398ef4bdcc1ad12104dd05
ms.sourcegitcommit: d22fe2a34d7efe2dd5bbb456f0d00eb5f6c7608c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880613"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="manage-your-connections-for-microsoft-search"></a>Administrar las conexiones para Microsoft Search

Para obtener acceso a los conectores y administrarlos, debe designarse como administrador de búsqueda para su espacio empresarial. Póngase en contacto con el administrador de inquilinos para que le aprovisione el rol de administrador de búsqueda.

## <a name="get-started"></a>Introducción

Vaya a la [pestaña Conectores en](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) el Centro de administración de [Microsoft 365.](https://admin.microsoft.com)

Para cada tipo de conector, el Centro [de administración de Microsoft 365](https://admin.microsoft.com) admite las operaciones que se muestran en la tabla siguiente:

Operación | Conector creado por Microsoft | Conector asociado o personalizado
--- | --- | ---
Agregar una conexión | :heavy_check_mark: (Vea [Configurar el conector creado por Microsoft)](configure-connector.md) | :x: (Consulte la experiencia de usuario del administrador del conector personalizado o asociado)
Eliminar una conexión | :heavy_check_mark: | :heavy_check_mark:
Editar una conexión publicada | :heavy_check_mark: Name<br></br> :heavy_check_mark: Descripción<br></br> :heavy_check_mark: credenciales de autenticación para el origen de datos externo<br></br> :heavy_check_mark: credenciales de puerta de enlace para el origen de datos local<br></br> :heavy_check_mark: Programación de actualización<br></br> | :heavy_check_mark: Name<br></br> :heavy_check_mark: Descripción
Editar un borrador de conexión | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a>Supervisar el estado de conexión

Después de crear una conexión, el número de elementos **procesados** se muestra en la pestaña Conectores de la página **Búsqueda de Microsoft.** Una vez completado correctamente el rastreo completo inicial, se muestra el progreso de los rastreos incrementales periódicos. En esta página se proporciona información sobre las operaciones diarias del conector y una introducción a los registros y al historial de errores.

Cuatro estados se muestran en la columna **Estado** en cada conexión:

* **Sincronización.** El conector rastrea los datos del origen para indizar los elementos existentes y realizar cualquier actualización.

* **Habilitado:** la conexión está habilitada y no hay ningún rastreo activo ejecutándose en ella. **La última hora de sincronización** indica cuándo se produjo el último rastreo correcto. La conexión es tan reciente como la última hora de sincronización.

* **En pausa.** Los administradores pausan los rastreos mediante la opción de pausa. El siguiente rastreo solo se ejecuta cuando se reanuda manualmente. Sin embargo, los datos de esta conexión siguen siendo de búsqueda.

* **Error**. La conexión tuvo un error crítico. Este error requiere la intervención manual. El administrador debe tomar las medidas adecuadas en función del mensaje de error que se muestra. Los datos que se indizaron hasta que se produjo el error se pueden buscar.

### <a name="view-your-last-crawl-info"></a>Ver la información del último rastreo

Una vez completado correctamente el primer rastreo incremental o completo inicial, los últimos valores de datos de rastreo se muestran en el encabezado del último rastreo en el panel de detalles. Si no se ejecutó el último rastreo, no verá información en el encabezado del último rastreo. Esta información sobre el último rastreo le ayudará a obtener información sobre cómo se realizó el rastreo y a realizar los pasos necesarios siempre que sea necesario.

Los siguientes valores de último rastreo estarán disponibles para cada conexión:

Valor | Description
--- | ---
Completado en | Fecha y hora en que se completó el último rastreo
Tipo | Rastreo incremental o completo
Duración | cuánto tiempo tardaron en completarse los últimos rastreos
Operaciones correctas. | Número de elementos que se han ingerido correctamente en el último rastreo
Errores | Número de elementos que se han producido errores en el último rastreo

### <a name="monitor-errors"></a>Supervisar errores

Para cada **conector activo de** la ficha Conectores, los errores de rastreo **existentes** se muestran en la **pestaña Error.** La pestaña enumera los códigos de error, el recuento de cada una y las opciones de descarga del registro de errores. Vea el ejemplo en la imagen siguiente. Seleccione un **código de error** para ver los detalles del error.

![Lista de conectores con un conector seleccionado y panel de detalles que muestra 3 errores para este conector.](media/errormonitoring1.png)

Para ver los detalles específicos de un error, seleccione su código de error. Aparece una pantalla con detalles de error y un vínculo. Los errores más recientes aparecen en la parte superior. Vea el ejemplo en la tabla siguiente.

![Lista de conectores con un conector seleccionado y el panel de detalles que muestra la lista de errores del conector.](media/errormonitoring2.png)

A continuación se muestra la lista de diferentes errores que pueden aparecer en cualquier conexión.

Código de error | Mensaje de error | Solución
--- | --- | ---
1000 | El origen de datos no está disponible. Compruebe la conexión a Internet o asegúrese de que el conector sigue teniendo acceso al origen de datos. | Este error se produce cuando no se puede tener acceso al origen de datos debido a un problema de red o cuando se elimina, mueve o cambia el nombre del origen de datos. Compruebe si los detalles del origen de datos proporcionados siguen siendo válidos.
1001 | No se pueden actualizar los datos porque el origen de datos limita el conector. | Para desarroque el origen de datos, compruebe si sus límites de escala pueden aumentarse o esperar hasta una hora del día menos intensa para el tráfico.
1002 | No se puede autenticar con el origen de datos. Compruebe que las credenciales asociadas a este origen de datos son correctas. | Haga **clic en Editar** para actualizar las credenciales de autenticación.
1003 | La cuenta asociada al conector no tiene permiso para obtener acceso al elemento. |  Asegúrese de que la cuenta adecuada tiene acceso al elemento que desea indizar.
1004 | No se puede acceder a la puerta de enlace de datos local. Asegúrese de que el servicio de puerta de enlace se está ejecutando y de que los detalles de la puerta de enlace se actualizan en la configuración de conexión. | Compruebe el equipo con la puerta de enlace, abra la aplicación de puerta de enlace de Power BI y asegúrese de que la puerta de enlace se está ejecutando. Compruebe que la puerta de enlace usa la misma cuenta de administrador que Microsoft Search y, a continuación, asegúrese de que todos los detalles de la puerta de enlace se actualizan en la configuración de conexión.
1005 | Las credenciales asociadas a este origen de datos han expirado. Renueve las credenciales y actualice la conexión. | Haga **clic en Editar** para actualizar las credenciales de autenticación.
1006 | La versión de la puerta de enlace no está actualizada y ya no admite este conector. Deberá actualizar la puerta de enlace. | Visite [Instalar una puerta de](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) enlace de datos local para descargar e instalar la versión más reciente de la puerta de enlace de Power BI en el equipo que contiene la puerta de enlace.
1007 | No se detectó ninguna licencia válida de Power BI. Necesita una licencia válida de Power BI para realizar este rastreo. | Necesita una licencia válida de Power BI para realizar este rastreo. Compruebe que su organización tiene una licencia válida. Si es así, inténtelo de nuevo. Si no es así, obtenga una licencia y vuelva a intentarlo.
1008 | El uso total de la cuota del espacio empresarial ha alcanzado su límite. Intenta eliminar una conexión para liberar parte de la cuota o ajustar los filtros de ingesta para traer menos datos. | Intenta eliminar una conexión para liberar parte de la cuota o ajustar los filtros de ingesta para traer menos datos. Si estos no resuelven el problema, póngase en contacto con el soporte técnico de Microsoft.
2001 | La indización se limita debido a un gran número de actualizaciones en la cola. Según la cola, las actualizaciones pueden tardar algún tiempo en completarse. | Espere hasta que se borra la cola.
2002 | Error en la indización debido al formato de elemento no admitido. | Vea la documentación específica del conector para obtener más información.
2003 | Error en la indización debido al contenido de elementos no admitidos. | Vea la documentación específica del conector para obtener más información.
2010 | Esta conexión ya no es válida debido a una actualización realizada por Microsoft. Elimine la conexión y cree una nueva. | Elimine la conexión y cree una nueva.
5000 | Algo salió mal. Si esto continúa, póngase en contacto con el soporte técnico. |

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

## <a name="limitations"></a>Limitaciones

* Al publicar **un** conector creado por Microsoft, la conexión puede tardar unos minutos en crearse. Durante ese tiempo, la conexión mostrará su estado como pendiente.

* El Centro de administración de [Microsoft 365](https://admin.microsoft.com) no admite la edición del esquema de búsqueda **después** de publicar una conexión. Para editar el esquema de búsqueda, elimine la conexión y, a continuación, cree una nueva.

* El rendimiento de ingesta se limita a unos cuatro elementos por segundo.

* No se admiten actualizaciones de esquema. Después de crear una configuración de conexión, no hay ninguna forma de actualizar el esquema. Solo puede eliminar y volver a crear la conexión.

* Hay un límite de conexiones. Cada inquilino puede crear hasta 10 conexiones.

* La compatibilidad de edición para la conexión no está disponible. Una vez creada la conexión, no podrá editarla ni cambiarla. Si necesita cambiar algún detalle, debe eliminar y volver a crear la conexión.
