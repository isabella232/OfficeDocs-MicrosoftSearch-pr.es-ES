---
title: Administrar Microsoft Graph Connectors para Microsoft Search
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Administrar Microsoft Graph Connectors para Microsoft Search.
ms.openlocfilehash: 685b501f3afe25d75c13a1fe6cc2c1b5db8a3511
ms.sourcegitcommit: e5d695c40b68c2f1fa082fa9de20b9aa6d5b8050
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52325172"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="af92f-103">Supervise las conexiones</span><span class="sxs-lookup"><span data-stu-id="af92f-103">Monitor your connections</span></span>

<span data-ttu-id="af92f-104">Para obtener acceso y administrar los conectores, debe estar designado como administrador de búsqueda para su inquilino.</span><span class="sxs-lookup"><span data-stu-id="af92f-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="af92f-105">Póngase en contacto con el administrador de inquilinos para aprovisionar el rol de administrador de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="af92f-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="af92f-106">Operaciones de conexión</span><span class="sxs-lookup"><span data-stu-id="af92f-106">Connection Operations</span></span>

<span data-ttu-id="af92f-107">Vaya a la [pestaña Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) en el [centro Microsoft 365 administración.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="af92f-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="af92f-108">Para cada tipo de conector, Microsoft 365 centro de administración [admite](https://admin.microsoft.com) las operaciones que se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="af92f-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="af92f-109">Operación</span><span class="sxs-lookup"><span data-stu-id="af92f-109">Operation</span></span> | <span data-ttu-id="af92f-110">Conectores de Graph por Microsoft</span><span class="sxs-lookup"><span data-stu-id="af92f-110">Graph connectors by Microsoft</span></span> | <span data-ttu-id="af92f-111">Conectores Graph asociados o de Graph de conexión</span><span class="sxs-lookup"><span data-stu-id="af92f-111">Partner or Graph connectors</span></span>
--- | --- | ---
<span data-ttu-id="af92f-112">Agregar una conexión</span><span class="sxs-lookup"><span data-stu-id="af92f-112">Add a connection</span></span> | :heavy_check_mark: <span data-ttu-id="af92f-113">(Vea Información [general sobre el programa de instalación](configure-connector.md))</span><span class="sxs-lookup"><span data-stu-id="af92f-113">(See [Setup overview](configure-connector.md))</span></span> | :x: <span data-ttu-id="af92f-114">(Consulte a su socio o experiencia de usuario de administrador de conectores personalizados)</span><span class="sxs-lookup"><span data-stu-id="af92f-114">(Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="af92f-115">Eliminar una conexión</span><span class="sxs-lookup"><span data-stu-id="af92f-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="af92f-118">Editar una conexión publicada</span><span class="sxs-lookup"><span data-stu-id="af92f-118">Edit a published connection</span></span> | :heavy_check_mark: <span data-ttu-id="af92f-119">Nombre y descripción</span><span class="sxs-lookup"><span data-stu-id="af92f-119">Name and Description</span></span><br></br> :heavy_check_mark: <span data-ttu-id="af92f-120">Configuración de conexión</span><span class="sxs-lookup"><span data-stu-id="af92f-120">Connection settings</span></span><br></br> :heavy_check_mark: <span data-ttu-id="af92f-121">Etiquetas de propiedades</span><span class="sxs-lookup"><span data-stu-id="af92f-121">Property labels</span></span><br></br> :heavy_check_mark: <span data-ttu-id="af92f-122">Esquema</span><span class="sxs-lookup"><span data-stu-id="af92f-122">Schema</span></span><br></br> :heavy_check_mark: <span data-ttu-id="af92f-123">Programación de actualización</span><span class="sxs-lookup"><span data-stu-id="af92f-123">Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="af92f-124">Name</span><span class="sxs-lookup"><span data-stu-id="af92f-124">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="af92f-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="af92f-125">Description</span></span>
<span data-ttu-id="af92f-126">Editar un borrador de conexión</span><span class="sxs-lookup"><span data-stu-id="af92f-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a><span data-ttu-id="af92f-129">Supervisar el estado de conexión</span><span class="sxs-lookup"><span data-stu-id="af92f-129">Monitor your connection state</span></span>

<span data-ttu-id="af92f-130">Después de crear una conexión, el número de elementos **procesados** se muestra en la pestaña Conectores de la **página Búsqueda de Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="af92f-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="af92f-131">Una vez completado correctamente el rastreo completo inicial, se muestra el progreso de los rastreos incrementales periódicos.</span><span class="sxs-lookup"><span data-stu-id="af92f-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="af92f-132">Esta página proporciona información sobre las operaciones diarias del conector y una introducción a los registros y el historial de errores.</span><span class="sxs-lookup"><span data-stu-id="af92f-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="af92f-133">Cinco estados se muestran en la **columna Estado** en cada conexión:</span><span class="sxs-lookup"><span data-stu-id="af92f-133">Five states show up in the **State** column against each connection:</span></span>

* <span data-ttu-id="af92f-134">**Sincronización**.</span><span class="sxs-lookup"><span data-stu-id="af92f-134">**Syncing**.</span></span> <span data-ttu-id="af92f-135">El conector rastrea los datos del origen para indizar los elementos existentes y realizar cualquier actualización.</span><span class="sxs-lookup"><span data-stu-id="af92f-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="af92f-136">**Listo:** la conexión está lista y no hay ningún rastreo activo ejecutándose en ella.</span><span class="sxs-lookup"><span data-stu-id="af92f-136">**Ready**: The connection is ready, and there's no active crawl running against it.</span></span> <span data-ttu-id="af92f-137">**La última hora de sincronización** indica cuándo se produjo el último rastreo correcto.</span><span class="sxs-lookup"><span data-stu-id="af92f-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="af92f-138">La conexión es tan nueva como la última hora de sincronización.</span><span class="sxs-lookup"><span data-stu-id="af92f-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="af92f-139">**Paused**.</span><span class="sxs-lookup"><span data-stu-id="af92f-139">**Paused**.</span></span> <span data-ttu-id="af92f-140">Los administradores pausan los rastreos a través de la opción de pausa.</span><span class="sxs-lookup"><span data-stu-id="af92f-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="af92f-141">El siguiente rastreo solo se ejecuta cuando se reanuda manualmente.</span><span class="sxs-lookup"><span data-stu-id="af92f-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="af92f-142">Sin embargo, los datos de esta conexión siguen siendo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="af92f-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="af92f-143">**Error**.</span><span class="sxs-lookup"><span data-stu-id="af92f-143">**Failed**.</span></span> <span data-ttu-id="af92f-144">La conexión tuvo un error crítico.</span><span class="sxs-lookup"><span data-stu-id="af92f-144">The connection had a critical failure.</span></span> <span data-ttu-id="af92f-145">Este error requiere una intervención manual.</span><span class="sxs-lookup"><span data-stu-id="af92f-145">This error requires manual intervention.</span></span> <span data-ttu-id="af92f-146">El administrador debe realizar las acciones adecuadas en función del mensaje de error que se muestra.</span><span class="sxs-lookup"><span data-stu-id="af92f-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="af92f-147">Los datos que se indizaron hasta que se produjo el error son de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="af92f-147">Data that was indexed until the error occurred is searchable.</span></span>

* <span data-ttu-id="af92f-148">**Error al eliminar**.</span><span class="sxs-lookup"><span data-stu-id="af92f-148">**Delete Failed**.</span></span> <span data-ttu-id="af92f-149">Error al eliminar la conexión.</span><span class="sxs-lookup"><span data-stu-id="af92f-149">The deletion of connection failed.</span></span> <span data-ttu-id="af92f-150">Según el motivo del error, es posible que los datos aún se indexan, que aún se pueda consumir la cuota de elementos y que los rastreos aún se ejecuten para la conexión.</span><span class="sxs-lookup"><span data-stu-id="af92f-150">Depending upon the failure reason, the data might still be indexed, item quota may still be consumed and crawls might still run for the connection.</span></span> <span data-ttu-id="af92f-151">Se recomienda intentar eliminar la conexión de nuevo en este estado.</span><span class="sxs-lookup"><span data-stu-id="af92f-151">It is recommended to try deleting the connection again in this state.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="af92f-152">Supervisar el uso de la cuota de índice</span><span class="sxs-lookup"><span data-stu-id="af92f-152">Monitor your index quota utilization</span></span>

<span data-ttu-id="af92f-153">La cuota de índice y el consumo disponibles se muestran en la página de aterrizaje de conectores.</span><span class="sxs-lookup"><span data-stu-id="af92f-153">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![Barra de uso de cuota de índice](media/quota_utilization.png)
 
>[!NOTE]
><span data-ttu-id="af92f-155">Durante el período de vista previa, todas las organizaciones que probaron Graph conectores se les proporcionó una cuota fija gratuita de hasta 2 millones de elementos en todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="af92f-155">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="af92f-156">Con Graph conectores de Graph disponibles, la cuota gratuita expirará el 1 de abril de 2021 para las organizaciones que han estado usando conectores Graph en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="af92f-156">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="af92f-157">Los conectores de Graph creados por Microsoft etiquetados como ["Versión preliminar"](./connectors-overview.md) no se incluirán en la cuota total de índice cargado para su organización.</span><span class="sxs-lookup"><span data-stu-id="af92f-157">Microsoft-built Graph connectors labeled as ["Preview"](./connectors-overview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="af92f-158">Sin embargo, contará para el número máximo de 10 conexiones que puede configurar para su organización y el número máximo de 7 millones de elementos que su organización puede indizar entre conexiones; cada conexión tiene un límite de 700 000 elementos.</span><span class="sxs-lookup"><span data-stu-id="af92f-158">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="af92f-159">La barra de uso de cuota indicará varios estados en función del consumo de cuota por parte de la organización:</span><span class="sxs-lookup"><span data-stu-id="af92f-159">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="af92f-160">Estado</span><span class="sxs-lookup"><span data-stu-id="af92f-160">State</span></span> | <span data-ttu-id="af92f-161">Niveles de uso de cuota</span><span class="sxs-lookup"><span data-stu-id="af92f-161">Quota utilization levels</span></span>
--- | --- 
<span data-ttu-id="af92f-162">Normal</span><span class="sxs-lookup"><span data-stu-id="af92f-162">Normal</span></span> | <span data-ttu-id="af92f-163">0-79%</span><span class="sxs-lookup"><span data-stu-id="af92f-163">0-79%</span></span>
<span data-ttu-id="af92f-164">Alto</span><span class="sxs-lookup"><span data-stu-id="af92f-164">High</span></span> | <span data-ttu-id="af92f-165">80-89%</span><span class="sxs-lookup"><span data-stu-id="af92f-165">80-89%</span></span>
<span data-ttu-id="af92f-166">Critico</span><span class="sxs-lookup"><span data-stu-id="af92f-166">Critical</span></span> | <span data-ttu-id="af92f-167">90%-99%</span><span class="sxs-lookup"><span data-stu-id="af92f-167">90%-99%</span></span>
<span data-ttu-id="af92f-168">Full</span><span class="sxs-lookup"><span data-stu-id="af92f-168">Full</span></span> | <span data-ttu-id="af92f-169">100 %</span><span class="sxs-lookup"><span data-stu-id="af92f-169">100%</span></span>

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

<span data-ttu-id="af92f-170">El número de elementos indizados también se mostrará con cada conexión.</span><span class="sxs-lookup"><span data-stu-id="af92f-170">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="af92f-171">El número de elementos indizados por cada conexión contribuye a la cuota total disponible para su organización.</span><span class="sxs-lookup"><span data-stu-id="af92f-171">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="af92f-172">Cuando se supere la cuota de índice para la organización, todas las conexiones activas se verán afectadas y dichas conexiones funcionarán en estado de **límite superado.**</span><span class="sxs-lookup"><span data-stu-id="af92f-172">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="af92f-173">En este estado, las conexiones activas</span><span class="sxs-lookup"><span data-stu-id="af92f-173">In this state, your active connections</span></span>  

* <span data-ttu-id="af92f-174">No podrá agregar nuevos elementos.</span><span class="sxs-lookup"><span data-stu-id="af92f-174">Will not be able to add new items.</span></span>

* <span data-ttu-id="af92f-175">Podrá actualizar o eliminar elementos existentes.</span><span class="sxs-lookup"><span data-stu-id="af92f-175">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="af92f-176">Para solucionar esto, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af92f-176">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="af92f-177">Obtenga información sobre cómo comprar cuota de índice para su organización en [Requisitos de licencias y precios.](licensing.md)</span><span class="sxs-lookup"><span data-stu-id="af92f-177">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="af92f-178">Identificar las conexiones que tienen demasiado contenido que se está ingiere y actualizarlas para indizar menos elementos para dar espacio a la cuota.</span><span class="sxs-lookup"><span data-stu-id="af92f-178">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="af92f-179">Para actualizar la conexión, debe eliminar y crear una nueva conexión con un nuevo filtro de ingesta que traiga menos elementos.</span><span class="sxs-lookup"><span data-stu-id="af92f-179">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="af92f-180">Eliminar de forma permanente una o más conexiones</span><span class="sxs-lookup"><span data-stu-id="af92f-180">Permanently delete one or more connections</span></span>