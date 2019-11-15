---
title: Configurar Búsqueda de Microsoft
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar Búsqueda de Microsoft por primera vez.
ms.openlocfilehash: 94ee7ece8a56d599778b151d5b836240d8832762
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626913"
---
# <a name="set-up-microsoft-search"></a><span data-ttu-id="4e424-103">Configurar Búsqueda de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4e424-103">Set up Microsoft Search</span></span>

<span data-ttu-id="4e424-104">Búsqueda de Microsoft ofrece una interfaz intuitiva para ayudar a los usuarios a encontrar información como archivos y documentos, sitios internos y herramientas empresariales, personas y grupos, ubicaciones y direcciones, conversaciones y respuestas mediante un acceso seguro a todas las fuentes de datos, incluidos correos electrónicos, archivos, archivos de SharePoint, contenidos de OneDrive y otros recursos compartidos, así como de internet en la organización del usuario.</span><span class="sxs-lookup"><span data-stu-id="4e424-104">Microsoft Search provides a user-friendly interface to help users find information, like files and documents, internal sites and business tools, people and groups, locations and directions, conversations and answers by securely accessing all data sources, including emails, files, SharePoint files, OneDrive content, and other shared resources as well as the internet in the user’s organization.</span></span>

<span data-ttu-id="4e424-105">Para obtener más información sobre las características de la Búsqueda de Microsoft, vea [Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="4e424-105">To learn more about Microsoft Search features, see [Microsoft Search Overview](overview-microsoft-search.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="4e424-106">Introducción</span><span class="sxs-lookup"><span data-stu-id="4e424-106">Get Started</span></span>

<span data-ttu-id="4e424-107">La Búsqueda de Microsoft está activada de forma predeterminada para todas las aplicaciones de Microsoft compatibles, como parte de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e424-107">Microsoft Search is turned on by default for all Microsoft apps that supports it, as a part of Microsoft 365.</span></span> <span data-ttu-id="4e424-108">No se requiere ninguna configuración, pero puede mejorar la experiencia general de Microsoft Search a través de algunas tareas administrativas básicas.</span><span class="sxs-lookup"><span data-stu-id="4e424-108">There is no setup required,but you can improve the overall Microsoft Search experience through some basic administrative tasks.</span></span>

<span data-ttu-id="4e424-109">Puede administrar la Búsqueda de Microsoft desde el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e424-109">You manage Microsoft Search from Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="4e424-110">En el Centro de administración de Microsoft 365, vaya a **Configuración** > **Búsqueda de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4e424-110">In Microsoft 365 admin center, go to **Settings** > **Microsoft Search**.</span></span>

<span data-ttu-id="4e424-111">**Nota:** si no ve la Búsqueda de Microsoft en **Configuración**, active el interruptor para**Probar la versión preliminar** en la esquina superior derecha de cualquier página del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="4e424-111">**Note:** If you are NOT seeing Microsoft Search under **Settings**, turn on the **Try the preview** switch in the right top corner of any admin center page.</span></span>

<span data-ttu-id="4e424-112">Como administrador debe considerar algunos aspectos que pueden hacer que la experiencia de Búsqueda de Microsoft en su organización sea eficiente e intuitiva.</span><span class="sxs-lookup"><span data-stu-id="4e424-112">As an admin you should consider a few things that can make the Microsoft Search experience efficient and user friendly in your organization.</span></span>

## <a name="step-1-assign-search-admin-and-search-editor"></a><span data-ttu-id="4e424-113">Paso 1: asignar un editor de búsqueda y un editor de búsqueda</span><span class="sxs-lookup"><span data-stu-id="4e424-113">Step 1: Assign Search admin and Search editor</span></span>

<span data-ttu-id="4e424-114">En la Búsqueda de Microsoft, puede administrar la configuración de búsqueda de su organización y el contenido con la asignación de los siguientes roles a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="4e424-114">In Microsoft Search, you can manage your organization’s search settings and content by assigning these roles to users:</span></span>

1. <span data-ttu-id="4e424-115">**Administrador de búsqueda:** este rol puede crear y administrar el contenido de los resultados de búsqueda y definir la configuración de consulta para mejorar los resultados de búsqueda en la organización.</span><span class="sxs-lookup"><span data-stu-id="4e424-115">**Search admin:** This role can create and manage search result content and define query settings for improved search results within the organization.</span></span> <span data-ttu-id="4e424-116">El administrador de búsqueda administra la configuración de la Búsqueda de Microsoft y puede realizar todas las tareas de administración de contenido que pueda llevar a cabo un editor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e424-116">Search admin manages the Microsoft Search configuration and can perform all of the content-management tasks a Search editor can.</span></span>
2. <span data-ttu-id="4e424-117">**Editor de búsqueda:** crea, administra y elimina el contenido de la Búsqueda de Microsoft en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e424-117">**Search editor:** Creates, manages, and deletes content for Microsoft Search in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4e424-118">Este rol puede crear y administrar contenido editorial, como las preguntas más frecuentes, respuestas, lugares y ubicaciones importantes, sitios y aplicaciones frecuentemente buscados y usados, entre otras cosas.</span><span class="sxs-lookup"><span data-stu-id="4e424-118">This role can create and manage editorial content, such as frequently asked questions and answers, important places and locations, frequently searched and used sites and apps.</span></span>

<span data-ttu-id="4e424-119">Actualmente, el administrador global debe asignar los roles de administrador de búsqueda y editor de búsqueda. Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="4e424-119">Currently, the Search admin and Search editor roles must be assigned by a global admin. For more information, see [Assign admin roles](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>

<span data-ttu-id="4e424-120">Los administradores de búsqueda influyen directamente en la experiencia de búsqueda para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="4e424-120">Search administrators directly influence the search experience for end users.</span></span> <span data-ttu-id="4e424-121">Esto incluye la elección de los tipos de resultados que quiere que se muestren a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4e424-121">This includes choosing the types of results you want to surface to your users.</span></span> <span data-ttu-id="4e424-122">Puede resultar difícil para una sola persona elegir y crear contenido relevante para los muchos y diferentes temas que los usuarios buscan en una organización.</span><span class="sxs-lookup"><span data-stu-id="4e424-122">It may be difficult for one person to choose and create authoritative content on many different topics that users search for in an organization.</span></span> <span data-ttu-id="4e424-123">Le recomendamos que aproveche la experiencia y los conocimientos de los expertos en la materia (SME) y de otros usuarios agregándolos como editores de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e424-123">We recommend that you leverage the expertise and knowledge of subject matter experts (SME) and other users by adding them as Search editors.</span></span>

## <a name="step-2-create-answers"></a><span data-ttu-id="4e424-124">Paso 2: crear respuestas</span><span class="sxs-lookup"><span data-stu-id="4e424-124">Step 2: Create answers</span></span>

<span data-ttu-id="4e424-125">La Búsqueda de Microsoft proporciona a los administradores herramientas que pueden usar para crear una óptima experiencia de búsqueda para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4e424-125">Microsoft Search provides administrators with tools that they can use to build a robust search experience for their users.</span></span> <span data-ttu-id="4e424-126">En Microsoft Search, los administradores tienen tres contenidos de búsqueda diferentes que pueden crear para una mejor experiencia de búsqueda y para mejorar la "búsqueda" del contenido:</span><span class="sxs-lookup"><span data-stu-id="4e424-126">In Microsoft Search, administrators have three different search contents that they can create for a better search experience and to improve the "findability" of content:</span></span>

<span data-ttu-id="4e424-127">Los marcadores son el tipo de respuesta que se usa con más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="4e424-127">Bookmarks are the most commonly used answer type.</span></span> <span data-ttu-id="4e424-128">Promueven los mejores resultados posibles para las consultas de los usuarios a la parte superior de los resultados de búsqueda y facilitan que los usuarios encuentren lo que buscan.</span><span class="sxs-lookup"><span data-stu-id="4e424-128">They promote the best possible results for your users’ queries to the top of the search results and make it easy for your users to find what they are looking for.</span></span>
<span data-ttu-id="4e424-129">Contenido informativo que está disponible para todos los usuarios; por ejemplo, información sobre la compañía, ayuda para Windows y aplicaciones de Office, etc. Contenido que los miembros de la organización suelen buscar en su trabajo cotidiano.</span><span class="sxs-lookup"><span data-stu-id="4e424-129">Informational content that is available for everyone; for example, information about the company, help for Windows and Office apps, etc. Content that people in the organization generally search for in their day-to-day work.</span></span> <span data-ttu-id="4e424-130">Las búsquedas comunes relacionadas con el trabajo incluyen prestaciones, informes de horas y gastos, envíos de pedidos de compra y cómo obtener ayuda del departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="4e424-130">Common work-related searches include employee benefits, time and expense reporting, submitting purchase orders, and getting help from IT services.</span></span>

<span data-ttu-id="4e424-131">Para crear y administrar respuestas, consulte [planear el contenido](plan-your-content.md).</span><span class="sxs-lookup"><span data-stu-id="4e424-131">For creating and managing answers, see [Plan your content](plan-your-content.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e424-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4e424-132">Next steps</span></span>

<span data-ttu-id="4e424-133">Si desea obtener más información sobre cómo usarán Microsoft Search los usuarios, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="4e424-133">If you'd like to learn more about how your users will use Microsoft Search, see the following articles:</span></span>

- [<span data-ttu-id="4e424-134">Encuentre lo que necesita con Búsqueda de Microsoft en Office</span><span class="sxs-lookup"><span data-stu-id="4e424-134">Find what you need with Microsoft Search in Office</span></span>](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446)
- [<span data-ttu-id="4e424-135">Centro de aprendizaje de Office 365</span><span class="sxs-lookup"><span data-stu-id="4e424-135">Office 365 Training Center</span></span>](https://support.office.com/office-training-center)
- [<span data-ttu-id="4e424-136">Búsqueda de Microsoft Center</span><span class="sxs-lookup"><span data-stu-id="4e424-136">Microsoft Search Center</span></span>](https://support.office.com/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc)
