---
title: Vista previa de conectores
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Obtenga información sobre la vista previa de conectores de Microsoft Graph para Microsoft Search.
ms.openlocfilehash: 81d169074a316b6ab07f47156e0f057e50c12e3e
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422896"
---
# <a name="microsoft-graph-connectors-preview"></a><span data-ttu-id="8a4a8-103">Vista previa de conectores de Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="8a4a8-103">Microsoft Graph connectors preview</span></span>

<span data-ttu-id="8a4a8-104">Los conectores de las API de Búsqueda de Microsoft (consulta e índice) y Microsoft Graph están actualmente en estado de vista previa.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-104">Microsoft Graph connectors and Microsoft Search APIs (query and index) are currently in preview status.</span></span> <span data-ttu-id="8a4a8-105">Para obtener acceso a la funcionalidad de los conectores, debe activar la opción de lanzamiento de destino en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-105">To gain access to connectors functionality, you must turn on the Targeted release option in your tenant.</span></span> <span data-ttu-id="8a4a8-106">Se trata de una vista previa temprana y no hay garantía de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-106">This is an early preview, and there's no service level guarantee.</span></span> <span data-ttu-id="8a4a8-107">Animamos a los clientes a probar la funcionalidad de los conectores y a proporcionar comentarios.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-107">We encourage customers to try connectors functionality and provide feedback.</span></span> <span data-ttu-id="8a4a8-108">No se recomienda usar conectores para fines de producción durante el período de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-108">We don’t recommend using connectors for production purposes during the preview period.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="8a4a8-109">Configurar versión de destino</span><span class="sxs-lookup"><span data-stu-id="8a4a8-109">Set up Targeted release</span></span>

<span data-ttu-id="8a4a8-110">Para probar los conectores, debe tener establecida la opción **Release dirigida** para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-110">To try connectors, you must have the **Targeted release** option set for all users in your organization.</span></span> <span data-ttu-id="8a4a8-111">Para obtener más información sobre la opción de lanzamiento de destino y cómo configurarla, consulte [configurar las opciones estándar o de versión de destino en Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="8a4a8-111">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

## <a name="choose-a-preview-environment"></a><span data-ttu-id="8a4a8-112">Elegir un entorno de vista previa</span><span class="sxs-lookup"><span data-stu-id="8a4a8-112">Choose a preview environment</span></span>

<span data-ttu-id="8a4a8-113">Para probar los conectores, las API de indización y las API de búsqueda, recomendamos estos dos métodos:</span><span class="sxs-lookup"><span data-stu-id="8a4a8-113">To try connectors, indexing APIs, and search APIs, we recommend these two methods:</span></span>

1. <span data-ttu-id="8a4a8-114">**Inquilino de prueba**.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-114">**Test tenant**.</span></span>  <span data-ttu-id="8a4a8-115">Le recomendamos que use un inquilino de prueba para probar la vista previa de conectores de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-115">We encourage you to use a test tenant to try the Microsoft Graph connectors preview.</span></span>

2. <span data-ttu-id="8a4a8-116">**Colección de sitios de prueba**.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-116">**Test site collection**.</span></span> <span data-ttu-id="8a4a8-117">Si no tiene un inquilino de prueba, puede crear una colección de sitios de prueba para probar la funcionalidad de los conectores.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-117">If you don't have a test tenant, you can create a test site collection to try out connectors functionality.</span></span> <span data-ttu-id="8a4a8-118">Para mostrar los resultados de los conectores sin afectar a las páginas de búsqueda en ninguna otra parte de la organización, personalice la experiencia de búsqueda de solo esa colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-118">To show results from connectors without impacting the search pages anywhere else in your organization, customize the search experience of only that site collection.</span></span>

## <a name="preview-limitations"></a><span data-ttu-id="8a4a8-119">Limitaciones de la vista previa</span><span class="sxs-lookup"><span data-stu-id="8a4a8-119">Preview limitations</span></span>

<span data-ttu-id="8a4a8-120">La versión preliminar tiene las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="8a4a8-120">The preview release has the following limitations:</span></span>

* <span data-ttu-id="8a4a8-121">El rendimiento de la recopilación se limita a unos cuatro elementos por segundo.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-121">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="8a4a8-122">No hay compatibilidad con las actualizaciones del esquema.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-122">There's no support for schema updates.</span></span> <span data-ttu-id="8a4a8-123">Después de crear una configuración de conexión, no hay forma de actualizar el esquema.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-123">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="8a4a8-124">Solo puede eliminar y volver a crear la conexión.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-124">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="8a4a8-125">El contenido indizado solo se muestra en la página de resultados de búsqueda bajo una vertical personalizada.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-125">Indexed content only shows up in the search results page under a custom vertical.</span></span> <span data-ttu-id="8a4a8-126">Esta restricción se aplica al contenido con tipos personalizados.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-126">This restriction applies to content with custom types.</span></span>

* <span data-ttu-id="8a4a8-127">Es posible que sea necesario eliminar y volver a crear todas las conexiones que configuró durante el período de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-127">Any connection you set up during the preview period might need to be deleted and re-created.</span></span> <span data-ttu-id="8a4a8-128">Estas conexiones ya no funcionarán si son incompatibles con los cambios realizados para mejorar el producto.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-128">Those connections won't work anymore if they're incompatible with changes made to improve the product.</span></span>

* <span data-ttu-id="8a4a8-129">Hay un límite de conexiones.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-129">There's a connections limit.</span></span> <span data-ttu-id="8a4a8-130">Cada inquilino puede crear hasta 10 conexiones.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-130">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="8a4a8-131">Tamaño del repositorio de origen.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-131">Source repository size.</span></span> <span data-ttu-id="8a4a8-132">Le recomendamos que obtenga una vista previa de los conectores con un repositorio de origen de unos 200.000 elementos, ya que se trata de nuestro límite de escala de búsqueda probada.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-132">We recommend that you preview connectors with a source repository of about 200,000 items as this is our tested search scale limit.</span></span> <span data-ttu-id="8a4a8-133">Estamos trabajando para mejorar el rendimiento de la búsqueda y esperamos admitir tamaños de repositorios más grandes en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-133">We are working on improving the performance of search, and we expect to support for larger repository sizes in the near future.</span></span>

* <span data-ttu-id="8a4a8-134">La compatibilidad de edición para la conexión no está disponible.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-134">Edit support for connection is not available.</span></span> <span data-ttu-id="8a4a8-135">Una vez creada la conexión, no podrá modificarla ni cambiarla.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-135">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="8a4a8-136">Si necesita cambiar algún detalle, debe eliminar y volver a crear la conexión.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-136">If you need to change any details, you must delete and recreate the connection.</span></span>

* <span data-ttu-id="8a4a8-137">El contenido del conector solo se puede buscar en vertical personalizados.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-137">Connector content can only be searched on custom verticals.</span></span>

* <span data-ttu-id="8a4a8-138">El contenido de los conectores de una sola conexión se puede mostrar en cada vertical personalizada y requiere la creación del tipo de resultado.</span><span class="sxs-lookup"><span data-stu-id="8a4a8-138">Connector content from only one connection can be displayed in each custom vertical and requires result type creation.</span></span>
