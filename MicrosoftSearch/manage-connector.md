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

# <a name="monitor-your-connections"></a><span data-ttu-id="7146e-103">Supervisar las conexiones</span><span class="sxs-lookup"><span data-stu-id="7146e-103">Monitor your connections</span></span>

<span data-ttu-id="7146e-104">Para obtener acceso a los conectores y administrarlos, debe designarse como administrador de búsqueda para su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="7146e-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="7146e-105">Póngase en contacto con el administrador de inquilinos para que le aprovisione el rol de administrador de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7146e-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="7146e-106">Operaciones de conexión</span><span class="sxs-lookup"><span data-stu-id="7146e-106">Connection Operations</span></span>

<span data-ttu-id="7146e-107">Vaya a la [pestaña Conectores en](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) el Centro de administración de [Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="7146e-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="7146e-108">Para cada tipo de conector, el Centro [de administración de Microsoft 365](https://admin.microsoft.com) admite las operaciones que se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="7146e-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="7146e-109">Operación</span><span class="sxs-lookup"><span data-stu-id="7146e-109">Operation</span></span> | <span data-ttu-id="7146e-110">Conector creado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="7146e-110">Microsoft-built connector</span></span> | <span data-ttu-id="7146e-111">Conector asociado o personalizado</span><span class="sxs-lookup"><span data-stu-id="7146e-111">Partner or custom-built connector</span></span>
--- | --- | ---
<span data-ttu-id="7146e-112">Agregar una conexión</span><span class="sxs-lookup"><span data-stu-id="7146e-112">Add a connection</span></span> | :heavy_check_mark: <span data-ttu-id="7146e-113">(Vea [Configurar el conector creado por Microsoft)](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="7146e-113">(See [Configure your Microsoft-built connector](configure-connector.md))</span></span> | :x: <span data-ttu-id="7146e-114">(Consulte la experiencia de usuario del administrador del conector personalizado o asociado)</span><span class="sxs-lookup"><span data-stu-id="7146e-114">(Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="7146e-115">Eliminar una conexión</span><span class="sxs-lookup"><span data-stu-id="7146e-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="7146e-118">Editar una conexión publicada</span><span class="sxs-lookup"><span data-stu-id="7146e-118">Edit a published connection</span></span> | :heavy_check_mark: <span data-ttu-id="7146e-119">Name</span><span class="sxs-lookup"><span data-stu-id="7146e-119">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="7146e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="7146e-120">Description</span></span><br></br> :heavy_check_mark: <span data-ttu-id="7146e-121">credenciales de autenticación para el origen de datos externo</span><span class="sxs-lookup"><span data-stu-id="7146e-121">Authentication credentials for your external data source</span></span><br></br> :heavy_check_mark: <span data-ttu-id="7146e-122">credenciales de puerta de enlace para el origen de datos local</span><span class="sxs-lookup"><span data-stu-id="7146e-122">Gateway credentials for your on-premises data source</span></span><br></br> :heavy_check_mark: <span data-ttu-id="7146e-123">Programación de actualización</span><span class="sxs-lookup"><span data-stu-id="7146e-123">Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="7146e-124">Name</span><span class="sxs-lookup"><span data-stu-id="7146e-124">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="7146e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="7146e-125">Description</span></span>
<span data-ttu-id="7146e-126">Editar un borrador de conexión</span><span class="sxs-lookup"><span data-stu-id="7146e-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a><span data-ttu-id="7146e-129">Supervisar el estado de conexión</span><span class="sxs-lookup"><span data-stu-id="7146e-129">Monitor your connection status</span></span>

<span data-ttu-id="7146e-130">Después de crear una conexión, el número de elementos **procesados** se muestra en la pestaña Conectores de la **página Búsqueda de Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="7146e-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="7146e-131">Una vez completado correctamente el rastreo completo inicial, se muestra el progreso de los rastreos incrementales periódicos.</span><span class="sxs-lookup"><span data-stu-id="7146e-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="7146e-132">En esta página se proporciona información sobre las operaciones diarias del conector y una introducción a los registros y al historial de errores.</span><span class="sxs-lookup"><span data-stu-id="7146e-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="7146e-133">Cuatro estados se muestran en la columna **Estado** en cada conexión:</span><span class="sxs-lookup"><span data-stu-id="7146e-133">Four states show up in the **Status** column against each connection:</span></span>

* <span data-ttu-id="7146e-134">**Sincronización.**</span><span class="sxs-lookup"><span data-stu-id="7146e-134">**Syncing**.</span></span> <span data-ttu-id="7146e-135">El conector rastrea los datos del origen para indizar los elementos existentes y realizar cualquier actualización.</span><span class="sxs-lookup"><span data-stu-id="7146e-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="7146e-136">**Habilitado:** la conexión está habilitada y no hay ningún rastreo activo ejecutándose en ella.</span><span class="sxs-lookup"><span data-stu-id="7146e-136">**Enabled**: The connection is enabled, and there's no active crawl running against it.</span></span> <span data-ttu-id="7146e-137">**La última hora de sincronización** indica cuándo se produjo el último rastreo correcto.</span><span class="sxs-lookup"><span data-stu-id="7146e-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="7146e-138">La conexión es tan reciente como la última hora de sincronización.</span><span class="sxs-lookup"><span data-stu-id="7146e-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="7146e-139">**En pausa.**</span><span class="sxs-lookup"><span data-stu-id="7146e-139">**Paused**.</span></span> <span data-ttu-id="7146e-140">Los administradores pausan los rastreos mediante la opción de pausa.</span><span class="sxs-lookup"><span data-stu-id="7146e-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="7146e-141">El siguiente rastreo solo se ejecuta cuando se reanuda manualmente.</span><span class="sxs-lookup"><span data-stu-id="7146e-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="7146e-142">Sin embargo, los datos de esta conexión siguen siendo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7146e-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="7146e-143">**Error**.</span><span class="sxs-lookup"><span data-stu-id="7146e-143">**Failed**.</span></span> <span data-ttu-id="7146e-144">La conexión tuvo un error crítico.</span><span class="sxs-lookup"><span data-stu-id="7146e-144">The connection had a critical failure.</span></span> <span data-ttu-id="7146e-145">Este error requiere la intervención manual.</span><span class="sxs-lookup"><span data-stu-id="7146e-145">This error requires manual intervention.</span></span> <span data-ttu-id="7146e-146">El administrador debe tomar las medidas adecuadas en función del mensaje de error que se muestra.</span><span class="sxs-lookup"><span data-stu-id="7146e-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="7146e-147">Los datos que se indizaron hasta que se produjo el error se pueden buscar.</span><span class="sxs-lookup"><span data-stu-id="7146e-147">Data that was indexed until the error occurred is searchable.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="7146e-148">Supervisar el uso de la cuota de índice</span><span class="sxs-lookup"><span data-stu-id="7146e-148">Monitor your index quota utilization</span></span>

<span data-ttu-id="7146e-149">La cuota de índice y el consumo disponibles se muestran en la página de aterrizaje de los conectores.</span><span class="sxs-lookup"><span data-stu-id="7146e-149">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![Barra de uso de cuota de índice](media/quota_utilization.png)

>[!NOTE]
><span data-ttu-id="7146e-151">Durante el período de vista previa, todas las organizaciones que probaron conectores de Graph se proporcionaron una cuota fija gratuita de hasta 2 millones de elementos en todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="7146e-151">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="7146e-152">Con los conectores de Graph que están generalmente disponibles, la cuota gratuita expirará el 1 de febrero de 2021 para las organizaciones que han estado usando conectores de Graph en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="7146e-152">With Graph connectors being generally available, the free quota will expire on Feb 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="7146e-153">Los conectores de Graph creados por Microsoft etiquetados como ["Versión preliminar"](connectors-preview.md) no se incluirán en la cuota total de índice cargada para su organización.</span><span class="sxs-lookup"><span data-stu-id="7146e-153">Microsoft-built Graph connectors labeled as ["Preview"](connectors-preview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="7146e-154">Sin embargo, se contará para el número máximo de 10 conexiones que puede configurar para su organización y el número máximo de 7 millones de elementos que su organización puede indizar entre conexiones; cada conexión tiene un límite de 700 000 elementos.</span><span class="sxs-lookup"><span data-stu-id="7146e-154">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="7146e-155">La barra de uso de la cuota indicará varios estados en función del consumo de cuota por parte de la organización:</span><span class="sxs-lookup"><span data-stu-id="7146e-155">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="7146e-156">Estado</span><span class="sxs-lookup"><span data-stu-id="7146e-156">State</span></span> | <span data-ttu-id="7146e-157">Consumo de cuota</span><span class="sxs-lookup"><span data-stu-id="7146e-157">Quota consumption</span></span>
--- | ---
<span data-ttu-id="7146e-158">Normal</span><span class="sxs-lookup"><span data-stu-id="7146e-158">Normal</span></span> | <span data-ttu-id="7146e-159">1-69%</span><span class="sxs-lookup"><span data-stu-id="7146e-159">1-69%</span></span>
<span data-ttu-id="7146e-160">Alto</span><span class="sxs-lookup"><span data-stu-id="7146e-160">High</span></span> | <span data-ttu-id="7146e-161">70-89%</span><span class="sxs-lookup"><span data-stu-id="7146e-161">70-89%</span></span>
<span data-ttu-id="7146e-162">Crítico</span><span class="sxs-lookup"><span data-stu-id="7146e-162">Critical</span></span> | <span data-ttu-id="7146e-163">90%-99%</span><span class="sxs-lookup"><span data-stu-id="7146e-163">90%-99%</span></span>
<span data-ttu-id="7146e-164">Full</span><span class="sxs-lookup"><span data-stu-id="7146e-164">Full</span></span> | <span data-ttu-id="7146e-165">100 %</span><span class="sxs-lookup"><span data-stu-id="7146e-165">100%</span></span>

<span data-ttu-id="7146e-166">El número de elementos indizados también se mostrará con cada conexión.</span><span class="sxs-lookup"><span data-stu-id="7146e-166">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="7146e-167">El número de elementos indizados por cada conexión contribuye a la cuota total disponible para su organización.</span><span class="sxs-lookup"><span data-stu-id="7146e-167">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="7146e-168">Cuando se supera la cuota de índice para su organización, se verán afectadas todas las conexiones activas y dichas conexiones funcionarán en estado de **límite superado.**</span><span class="sxs-lookup"><span data-stu-id="7146e-168">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="7146e-169">En este estado, las conexiones activas</span><span class="sxs-lookup"><span data-stu-id="7146e-169">In this state, your active connections</span></span>  

* <span data-ttu-id="7146e-170">No podrá agregar nuevos elementos.</span><span class="sxs-lookup"><span data-stu-id="7146e-170">Will not be able to add new items.</span></span>

* <span data-ttu-id="7146e-171">Podrá actualizar o eliminar elementos existentes.</span><span class="sxs-lookup"><span data-stu-id="7146e-171">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="7146e-172">Para solucionar este problema, puede realizar cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7146e-172">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="7146e-173">Obtenga información sobre cómo comprar la cuota de índice para su organización a precios [y requisitos de licencia.](licensing.md)</span><span class="sxs-lookup"><span data-stu-id="7146e-173">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="7146e-174">Identificar las conexiones que tienen demasiado contenido ingerido y actualizarlas para indizar menos elementos para que haya espacio para la cuota.</span><span class="sxs-lookup"><span data-stu-id="7146e-174">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="7146e-175">Para actualizar la conexión, debe eliminar y crear una nueva conexión con un nuevo filtro de ingesta que aporta menos elementos.</span><span class="sxs-lookup"><span data-stu-id="7146e-175">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="7146e-176">Eliminar permanentemente una o más conexiones</span><span class="sxs-lookup"><span data-stu-id="7146e-176">Permanently delete one or more connections</span></span>