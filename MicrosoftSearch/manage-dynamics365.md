---
title: Búsqueda de federación de Dynamics 365 (versión preliminar)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Administrar cómo aparece el contenido de Dynamics 365 en los resultados de búsqueda
ms.openlocfilehash: 5f642bcb026358e57258e5e736fc263616fc4b05
ms.sourcegitcommit: f07a2e578b6c9ed5a1a3b22266cca371782870a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "53067936"
---
# <a name="dynamics-365-federation-search-preview"></a><span data-ttu-id="3ffd9-103">Búsqueda de federación de Dynamics 365 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="3ffd9-103">Dynamics 365 federation search (preview)</span></span>

## <a name="microsoft-search-federation-and-connectors"></a><span data-ttu-id="3ffd9-104">Búsqueda de Microsoft Federación y conectores</span><span class="sxs-lookup"><span data-stu-id="3ffd9-104">Microsoft Search Federation and connectors</span></span>

<span data-ttu-id="3ffd9-105">Para ayudar a Búsqueda de Microsoft más útil, estamos presentando Búsqueda de Microsoft Federación.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-105">To help make Microsoft Search more useful, we're introducing Microsoft Search Federation.</span></span> <span data-ttu-id="3ffd9-106">Con la búsqueda federada, las organizaciones pueden hacer que los datos de estos escenarios puedan ser accesibles en Búsqueda de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="3ffd9-106">With federated search, organizations can make data in these scenarios accessible in Microsoft Search:</span></span>

* <span data-ttu-id="3ffd9-107">Datos en sistemas que están sujetos a estrictos requisitos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3ffd9-107">Data in systems that are subject to strict compliance requirements</span></span>
* <span data-ttu-id="3ffd9-108">Datos que no pueden salir de los límites del sistema</span><span class="sxs-lookup"><span data-stu-id="3ffd9-108">Data that can't leave system boundaries</span></span>
* <span data-ttu-id="3ffd9-109">Datos confidenciales almacenados localmente que su organización no quiere indizar en la nube</span><span class="sxs-lookup"><span data-stu-id="3ffd9-109">Sensitive data stored on-prem that your organization doesn’t want indexed on the cloud</span></span>

<span data-ttu-id="3ffd9-110">Los datos a los que se accede a través de una conexión de búsqueda federada no se indizan en Búsqueda de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-110">Data accessed through a federated search connection isn't indexed in Microsoft Search.</span></span> <span data-ttu-id="3ffd9-111">Además, con conectores integrados de Microsoft, es fácil configurar conexiones de búsqueda federadas.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-111">Also, using built-in connectors from Microsoft, it's easy to set up federated search connections.</span></span> <span data-ttu-id="3ffd9-112">Nuestro conector de Dynamics 365 está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-112">Our Dynamics 365 connector is currently in preview.</span></span> <span data-ttu-id="3ffd9-113">Si está interesado en unirse a la vista previa, háganoslo saber en [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).</span><span class="sxs-lookup"><span data-stu-id="3ffd9-113">If you're interested in joining the preview, let us know at [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).</span></span>

## <a name="dynamics-365-federation-connector"></a><span data-ttu-id="3ffd9-114">Conector de federación de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3ffd9-114">Dynamics 365 federation connector</span></span>

<span data-ttu-id="3ffd9-115">Microsoft Dynamics 365 es una línea de aplicaciones empresariales inteligentes diseñadas para la planeación de recursos empresariales y la administración de relaciones con el cliente.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-115">Microsoft Dynamics 365 is a line of intelligent business applications designed for enterprise resource planning and customer relationship management.</span></span> <span data-ttu-id="3ffd9-116">Con la federación de Dynamics 365, Búsqueda de Microsoft proporciona una experiencia de búsqueda sin problemas, lo que permite a los usuarios encontrar fácilmente los datos empresariales y de clientes más relevantes almacenados en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-116">With Dynamics 365 federation, Microsoft Search provides a seamless search experience, enabling users to easily find the most relevant customer and business data stored in Dynamics 365.</span></span> <span data-ttu-id="3ffd9-117">El conector de federación de Dynamics 365 proporciona algunas ventajas clave:</span><span class="sxs-lookup"><span data-stu-id="3ffd9-117">The Dynamics 365 federation connector provides some key benefits:</span></span>

* <span data-ttu-id="3ffd9-118">**Fácil de administrar:** Proceso simplificado para configurar y mantener la conexión de búsqueda a una instancia de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-118">**Easy to administer:** Streamlined process to configure and maintain the search connection to a Dynamics 365 instance.</span></span>
* <span data-ttu-id="3ffd9-119">**Fácil de usar:** Los usuarios pueden encontrar fácilmente y rápidamente información clave almacenada en Dynamics 365, incluidas cuentas, contactos, oportunidades abiertas y mucho más.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-119">**Easy to use:** Users can easily and quickly find key information stored in Dynamics 365, including accounts, contacts, open opportunities, and more.</span></span>
* <span data-ttu-id="3ffd9-120">**Contenido más enriquecido:** Para que los resultados de búsqueda de Dynamics 365 sea más útil, incluyen información clave como clientes potenciales, contactos y detalles de cuenta.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-120">**Richer content:** To make Dynamics 365 search results more useful, they include key information like leads, contacts, and account details.</span></span>
* <span data-ttu-id="3ffd9-121">**Protección de datos integrada:** Los resultados de Dynamics 365 solo aparecerán para los usuarios que tengan acceso a la instancia conectada.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-121">**Built-in data protection:** Dynamics 365 results will only appear for users that have access to the connected instance.</span></span>
* <span data-ttu-id="3ffd9-122">**Experiencia de búsqueda unificada:** Para mantener una experiencia coherente, los resultados de Dynamics 365 son coherentes en todos los puntos de entrada de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-122">**Unified search experience:** To maintain a cohesive experience, Dynamics 365 results are consistent across all search entry points.</span></span> <span data-ttu-id="3ffd9-123">Donde quiera que busque, tendrá los mismos resultados con la misma apariencia.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-123">Wherever you search, you'll get the same results with the same look and feel.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="3ffd9-124">Qué experiencia tienen los usuarios</span><span class="sxs-lookup"><span data-stu-id="3ffd9-124">What users experience</span></span>

<span data-ttu-id="3ffd9-125">Las respuestas de Dynamics 365 aparecen en los resultados de búsqueda en todos los lienzos de Búsqueda de Microsoft, incluidos SharePoint Online, Bing y Office.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-125">Dynamics 365 answers appear in search results across all Microsoft Search canvases, including SharePoint Online, Bing, and Office.</span></span>

:::image type="content" alt-text="Captura de pantalla de las respuestas de Dynamics 365 en SharePoint, Bing y Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

<span data-ttu-id="3ffd9-127">Desde la respuesta, es fácil ver más resultados de búsqueda de Dynamics 365 mediante el vínculo **Más resultados de Dynamics 365.**</span><span class="sxs-lookup"><span data-stu-id="3ffd9-127">From the answer, it's easy to see more Dynamics 365 search results by using the **More Dynamics 365 results** link.</span></span> <span data-ttu-id="3ffd9-128">Lleva a los usuarios a una página de resultados de Dynamics 365 dedicada con más resultados relevantes para su consulta.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-128">It takes users to a dedicated Dynamics 365 results page with more results relevant to their query.</span></span>

:::image type="content" alt-text="Captura de pantalla de Dynamics 365 vertical y resultados en SharePoint, Bing y Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

<span data-ttu-id="3ffd9-130">Al hacer clic o pulsar en cualquier resultado se abre Dynamics 365 y se muestra la información detallada.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-130">Clicking or tapping any result opens Dynamics 365 and shows the detailed information.</span></span>

:::image type="content" alt-text="Captura de pantalla de la página de detalles en Dynamics 365" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

<span data-ttu-id="3ffd9-132">Independientemente de dónde los usuarios inicien su búsqueda, su experiencia será coherente y les permitirá encontrar rápidamente los resultados más relevantes de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-132">No matter where your users start their search their experience will be consistent and enable them to quickly find the most relevant Dynamics 365 results.</span></span> <span data-ttu-id="3ffd9-133">Consulte nuestro vídeo de Microsoft Build 2021 para ver una demostración.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-133">Check out our Microsoft Build 2021 video for a demonstration.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4P83t]

## <a name="supported-query-patterns"></a><span data-ttu-id="3ffd9-134">Patrones de consulta admitidos</span><span class="sxs-lookup"><span data-stu-id="3ffd9-134">Supported query patterns</span></span>

<span data-ttu-id="3ffd9-135">Tanto las consultas de idioma natural como de nombre de producto se admiten al Búsqueda de Microsoft para buscar resultados de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-135">Both natural language and product name queries are supported when using Microsoft Search to find Dynamics 365 results.</span></span> <span data-ttu-id="3ffd9-136">Además, las consultas de Dynamics 365 no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-136">Also, Dynamics 365 queries aren't case sensitive.</span></span> <span data-ttu-id="3ffd9-137">Use patrones de lenguaje natural para buscar contactos, cuentas y oportunidades (por nombre de cliente o ubicación) y otras consultas usadas con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-137">Use natural language patterns to find contact, account, and opportunities--by customer name or location--and other frequently used queries.</span></span> <span data-ttu-id="3ffd9-138">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="3ffd9-138">Here are a few examples:</span></span>

* <span data-ttu-id="3ffd9-139">Quién es el contacto de Contoso</span><span class="sxs-lookup"><span data-stu-id="3ffd9-139">Who is the contact for Contoso</span></span>
* <span data-ttu-id="3ffd9-140">Oportunidades abiertas para Contoso</span><span class="sxs-lookup"><span data-stu-id="3ffd9-140">Open opportunities for Contoso</span></span>
* <span data-ttu-id="3ffd9-141">Qué son las oportunidades abiertas en Seattle</span><span class="sxs-lookup"><span data-stu-id="3ffd9-141">What are open opportunities in Seattle</span></span>
* <span data-ttu-id="3ffd9-142">Cuáles son las cuentas de Seattle</span><span class="sxs-lookup"><span data-stu-id="3ffd9-142">What are the accounts in Seattle</span></span>
* <span data-ttu-id="3ffd9-143">Cuáles son los contactos en Seattle</span><span class="sxs-lookup"><span data-stu-id="3ffd9-143">What are the contacts in Seattle</span></span>
* <span data-ttu-id="3ffd9-144">¿Cuáles son mis clientes potenciales cerrar este mes?</span><span class="sxs-lookup"><span data-stu-id="3ffd9-144">What are my leads closing this month</span></span>
* <span data-ttu-id="3ffd9-145">Llamada telefónica de prioridad alta</span><span class="sxs-lookup"><span data-stu-id="3ffd9-145">High priority phone call</span></span>
* <span data-ttu-id="3ffd9-146">Mensajes de correo electrónico que faltan de contactos</span><span class="sxs-lookup"><span data-stu-id="3ffd9-146">Contact missing emails</span></span>

<span data-ttu-id="3ffd9-147">Los patrones de nombres de producto admiten un rango de aplicaciones de Dynamics 365 y desencadenarán resultados de Dynamics 365 independientemente de dónde aparezcan en una consulta:</span><span class="sxs-lookup"><span data-stu-id="3ffd9-147">Product name patterns support a range of Dynamics 365 applications and will trigger Dynamics 365 results regardless of where they appear in a query:</span></span>

* <span data-ttu-id="3ffd9-148">D365</span><span class="sxs-lookup"><span data-stu-id="3ffd9-148">D365</span></span>
* <span data-ttu-id="3ffd9-149">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3ffd9-149">Dynamics 365</span></span>
* <span data-ttu-id="3ffd9-150">Dynamics365</span><span class="sxs-lookup"><span data-stu-id="3ffd9-150">Dynamics365</span></span>
* <span data-ttu-id="3ffd9-151">Microsoft Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="3ffd9-151">Dynamics CRM</span></span>
* <span data-ttu-id="3ffd9-152">Dynamics Sales</span><span class="sxs-lookup"><span data-stu-id="3ffd9-152">Dynamics Sales</span></span>
* <span data-ttu-id="3ffd9-153">Servicio al cliente de Dynamics</span><span class="sxs-lookup"><span data-stu-id="3ffd9-153">Dynamics Customer Service</span></span>
* <span data-ttu-id="3ffd9-154">Dynamics Service</span><span class="sxs-lookup"><span data-stu-id="3ffd9-154">Dynamics Service</span></span>
* <span data-ttu-id="3ffd9-155">Dynamics Field Service</span><span class="sxs-lookup"><span data-stu-id="3ffd9-155">Dynamics Field Service</span></span>

## <a name="configure-the-dynamics-365-connector"></a><span data-ttu-id="3ffd9-156">Configurar el conector de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3ffd9-156">Configure the Dynamics 365 connector</span></span>

<span data-ttu-id="3ffd9-157">Con esta configuración sencilla, puede habilitar la experiencia de búsqueda de federación de Dynamics 365 para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-157">With this simple configuration, you can enable the Dynamics 365 federation search experience for people in your organization.</span></span>

1. <span data-ttu-id="3ffd9-158">En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [Orígenes de datos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).</span><span class="sxs-lookup"><span data-stu-id="3ffd9-158">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [Data sources](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).</span></span>

2. <span data-ttu-id="3ffd9-159">En la sección Aplicaciones y servicios de Microsoft,  en Microsoft Dynamics 365, seleccione Administrar para abrir el panel de Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-159">In the Microsoft apps and services section, under Microsoft Dynamics 365, select **Manage** to open the Microsoft Dynamics 365 panel.</span></span>

3. <span data-ttu-id="3ffd9-160">Habilite el conector para su organización.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-160">Enable the connector for your organization.</span></span>

4. <span data-ttu-id="3ffd9-161">En la **lista Extremos,** seleccione el entorno de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-161">In the **Endpoints** list, select your Dynamics 365 environment.</span></span>

5. <span data-ttu-id="3ffd9-162">En el **identificador de conexión,** escriba un identificador único para esta conexión.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-162">In the **Connection ID**, enter a unique ID for this connection.</span></span>

6. <span data-ttu-id="3ffd9-163">Revise y active la casilla de consentimiento.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-163">Review and select the consent check box.</span></span>

7. <span data-ttu-id="3ffd9-164">Seleccione **Guardar para** finalizar la configuración de conexión.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-164">Select **Save** to finish the connection setup.</span></span>

:::image type="content" alt-text="Captura de pantalla del panel de configuración de Dynamics 365 en el Centro de administración de Microsoft 365" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

<span data-ttu-id="3ffd9-166">Una vez completada la instalación, las respuestas y verticales de Dynamics 365 solo aparecerán para los usuarios con una licencia válida de Dynamics 365 y acceso al entorno de Dynamics 365 conectado.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-166">When the setup is complete, Dynamics 365 answers and vertical will only appear for users with a valid Dynamics 365 license and access to the connected Dynamics 365 environment.</span></span> <span data-ttu-id="3ffd9-167">En cualquier momento, puede volver a esta configuración y cambiar el entorno del extremo de conexión o desactivar la conexión.</span><span class="sxs-lookup"><span data-stu-id="3ffd9-167">At any time, you can return to these settings and change the connection endpoint environment or deactivate the connection.</span></span>
