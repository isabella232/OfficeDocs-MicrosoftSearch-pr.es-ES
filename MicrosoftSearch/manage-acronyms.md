---
title: Administración de las respuestas de acrónimo en Microsoft Search
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Respuestas de crear y actualizar acrónimos en Microsoft Search
ms.openlocfilehash: e328ecb7604a144b51f3a1483eef1b1c3a7e0bcb
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422950"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="e88ec-103">La administración de acrónimos responde en Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="e88ec-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="e88ec-104">Los usuarios a menudo se encontraban con acrónimos y abreviaturas desconocidos que usa su organización o equipo.</span><span class="sxs-lookup"><span data-stu-id="e88ec-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="e88ec-105">Los términos específicos de organizaciones o equipos pueden ser nuevos para los usuarios que se mueven de un equipo a otro, trabajan con equipos de asociados internos o son nuevos en la organización.</span><span class="sxs-lookup"><span data-stu-id="e88ec-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="e88ec-106">Las organizaciones no siempre tienen una referencia única para su terminología estándar.</span><span class="sxs-lookup"><span data-stu-id="e88ec-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="e88ec-107">La ausencia de una sola referencia hace que sea difícil encontrar definiciones o expansiones para estos acrónimos.</span><span class="sxs-lookup"><span data-stu-id="e88ec-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="e88ec-108">Microsoft Search resuelve ese problema con acrónimos.</span><span class="sxs-lookup"><span data-stu-id="e88ec-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="e88ec-109">Qué experiencia tienen los usuarios</span><span class="sxs-lookup"><span data-stu-id="e88ec-109">What users experience</span></span>

<span data-ttu-id="e88ec-110">Microsoft Search los usuarios pueden obtener definiciones con acrónimos en [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)y [Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="e88ec-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="e88ec-111">En el cuadro de **búsqueda** , los usuarios escriben consultas como estos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="e88ec-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="e88ec-112">*Qué es* DNN</span><span class="sxs-lookup"><span data-stu-id="e88ec-112">*What is* DNN</span></span>
- <span data-ttu-id="e88ec-113">*Definir* DNN</span><span class="sxs-lookup"><span data-stu-id="e88ec-113">*Define* DNN</span></span>
- <span data-ttu-id="e88ec-114">*Definición* de DNN</span><span class="sxs-lookup"><span data-stu-id="e88ec-114">DNN *definition*</span></span>
- <span data-ttu-id="e88ec-115">*Expandir* DNN</span><span class="sxs-lookup"><span data-stu-id="e88ec-115">*Expand* DNN</span></span>
- <span data-ttu-id="e88ec-116">*Expansión* DNN</span><span class="sxs-lookup"><span data-stu-id="e88ec-116">DNN *expansion*</span></span>
- <span data-ttu-id="e88ec-117">*Significado de* DNN</span><span class="sxs-lookup"><span data-stu-id="e88ec-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="e88ec-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="e88ec-118">DNN *means*</span></span>

<span data-ttu-id="e88ec-119">El resultado incluye todos los significados de DNN que están presentes en la organización del usuario.</span><span class="sxs-lookup"><span data-stu-id="e88ec-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="e88ec-120">Los usuarios deben escribir una consulta que incluya las *palabras clave* especificadas en el acrónimo para activar sus respuestas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e88ec-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="e88ec-121">Las consultas de acrónimo no distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e88ec-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="e88ec-122">Configurar las respuestas de los acrónimos</span><span class="sxs-lookup"><span data-stu-id="e88ec-122">Set up Acronyms answers</span></span>

<span data-ttu-id="e88ec-123">En el [centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**acrónimos**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)y, después, seleccione **Agregar acrónimo**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="e88ec-124">Microsoft Search consulta dos orígenes de datos para proporcionar a los acrónimo respuestas a las búsquedas de los usuarios:</span><span class="sxs-lookup"><span data-stu-id="e88ec-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="e88ec-125">**Acrónimos editoriales**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-125">**Editorial acronyms**.</span></span> <span data-ttu-id="e88ec-126">LO proporcionan los administradores de TI en el [centro de administración](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="e88ec-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="e88ec-127">**Acrónimos extraídos**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-127">**Mined acronyms**.</span></span> <span data-ttu-id="e88ec-128">Extraída por Microsoft Search desde el correo electrónico y los documentos personales del usuario y los datos disponibles públicamente dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="e88ec-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="e88ec-129">Configurar acrónimos editoriales</span><span class="sxs-lookup"><span data-stu-id="e88ec-129">Set up editorial acronyms</span></span>

<span data-ttu-id="e88ec-130">Los administradores de búsqueda pueden configurar acrónimos editoriales en la [pestaña acrónimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) del  [centro de administración de Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span><span class="sxs-lookup"><span data-stu-id="e88ec-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="e88ec-131">Puede Agregar acrónimos desde cualquier sitio o repositorio interno al centro de administración.</span><span class="sxs-lookup"><span data-stu-id="e88ec-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="e88ec-132">Los acrónimos editoriales se pueden agregar al estado **publicado** o **borrador** :</span><span class="sxs-lookup"><span data-stu-id="e88ec-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="e88ec-133">**Estado publicado**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-133">**Published state**.</span></span> <span data-ttu-id="e88ec-134">Los acrónimos están disponibles para los empleados de la organización a través de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="e88ec-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="e88ec-135">Los acrónimos agregados al estado publicado pueden tardar hasta tres días en estar disponibles en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="e88ec-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="e88ec-136">**Estado de borrador**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-136">**Draft state**.</span></span> <span data-ttu-id="e88ec-137">Si los administradores quieren revisar las respuestas de acrónimos antes de que estén disponibles en Microsoft Search, pueden agregar los acrónimos al estado borrador.</span><span class="sxs-lookup"><span data-stu-id="e88ec-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="e88ec-138">Los acrónimos agregados al estado de borrador no están disponibles en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="e88ec-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="e88ec-139">Los administradores deben agregar los acrónimos a estado publicado para que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="e88ec-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="e88ec-140">Los administradores pueden agregar acrónimos de forma individual o en bloque para importarlos en un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="e88ec-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="e88ec-141">Cargue un archivo CSV con los campos que se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="e88ec-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="e88ec-142">Acrónimo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e88ec-142">Acronym (mandatory)</span></span> | <span data-ttu-id="e88ec-143">Expansión (obligatoria)</span><span class="sxs-lookup"><span data-stu-id="e88ec-143">Expansion (mandatory)</span></span> | <span data-ttu-id="e88ec-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="e88ec-144">Description</span></span>  | <span data-ttu-id="e88ec-145">Origen</span><span class="sxs-lookup"><span data-stu-id="e88ec-145">Source</span></span> | <span data-ttu-id="e88ec-146">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e88ec-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="e88ec-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="e88ec-147">*XXX*</span></span> | <span data-ttu-id="e88ec-148">*Abreviatura de ortografía*</span><span class="sxs-lookup"><span data-stu-id="e88ec-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="e88ec-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="e88ec-149">*URL*</span></span> | <span data-ttu-id="e88ec-150">*Publicado o borrador*</span><span class="sxs-lookup"><span data-stu-id="e88ec-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="e88ec-151">Campos CSV</span><span class="sxs-lookup"><span data-stu-id="e88ec-151">CSV fields</span></span>

<span data-ttu-id="e88ec-152">**Acrónimo**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-152">**Acronym**.</span></span> <span data-ttu-id="e88ec-153">Contiene la forma corta o el acrónimo real.</span><span class="sxs-lookup"><span data-stu-id="e88ec-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="e88ec-154">Un ejemplo es *DNN*.</span><span class="sxs-lookup"><span data-stu-id="e88ec-154">An example is *DNN*.</span></span>

<span data-ttu-id="e88ec-155">**Expansión**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-155">**Expansion**.</span></span> <span data-ttu-id="e88ec-156">Contiene la expansión del acrónimo.</span><span class="sxs-lookup"><span data-stu-id="e88ec-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="e88ec-157">Un ejemplo es una *red neuronal profunda*.</span><span class="sxs-lookup"><span data-stu-id="e88ec-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="e88ec-158">**Descripción**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-158">**Description**.</span></span> <span data-ttu-id="e88ec-159">Breve descripción del acrónimo que proporciona a los usuarios más información sobre el acrónimo y su expansión.</span><span class="sxs-lookup"><span data-stu-id="e88ec-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="e88ec-160">Por ejemplo, *una red neuronal profunda es una red neuronal con cierto nivel de complejidad, una red neuronal con más de dos capas*.</span><span class="sxs-lookup"><span data-stu-id="e88ec-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="e88ec-161">**Origen**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-161">**Source**.</span></span> <span data-ttu-id="e88ec-162">La dirección URL de la página o sitio web al que desea que vayan los usuarios para obtener más información sobre el acrónimo.</span><span class="sxs-lookup"><span data-stu-id="e88ec-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="e88ec-163">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-163">**State**.</span></span> <span data-ttu-id="e88ec-164">Este campo puede tener dos valores:</span><span class="sxs-lookup"><span data-stu-id="e88ec-164">This field can take two values:</span></span>

- <span data-ttu-id="e88ec-165">**Borrador**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-165">**Draft**.</span></span> <span data-ttu-id="e88ec-166">Agrega el acrónimo al estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="e88ec-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="e88ec-167">**Publicado**.</span><span class="sxs-lookup"><span data-stu-id="e88ec-167">**Published**.</span></span> <span data-ttu-id="e88ec-168">Agrega el acrónimo al estado publicado y lo hace disponible en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="e88ec-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="e88ec-169">Acrónimos extraídos</span><span class="sxs-lookup"><span data-stu-id="e88ec-169">Mined acronyms</span></span>

<span data-ttu-id="e88ec-170">Puede que sea un reto para los administradores agregar todos los acrónimos que se usan en una organización a las respuestas.</span><span class="sxs-lookup"><span data-stu-id="e88ec-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="e88ec-171">Esta característica puede encontrar acrónimos que los administradores de búsqueda aún no conocen.</span><span class="sxs-lookup"><span data-stu-id="e88ec-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="e88ec-172">Para ello, Microsoft Search también retiene acrónimos de estos recursos:</span><span class="sxs-lookup"><span data-stu-id="e88ec-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="e88ec-173">Mensajes de correo electrónico de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e88ec-173">Users’ emails.</span></span>
- <span data-ttu-id="e88ec-174">Documentos en [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)y [Microsoft OneNote](https://www.onenote.com/).</span><span class="sxs-lookup"><span data-stu-id="e88ec-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/).</span></span>
- <span data-ttu-id="e88ec-175">Documentos públicos de la organización a los que los usuarios tienen acceso en SharePoint, OneDrive o OneNote.</span><span class="sxs-lookup"><span data-stu-id="e88ec-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="e88ec-176">Microsoft Search se asegura de que solo los usuarios con acceso y permisos a un documento puedan ver los acrónimos que se han extraído.</span><span class="sxs-lookup"><span data-stu-id="e88ec-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="e88ec-177">Cuando se ha extraído un acrónimo desde el buzón de un usuario, el usuario sólo puede ver ese acrónimo.</span><span class="sxs-lookup"><span data-stu-id="e88ec-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="e88ec-178">No es necesario realizar ninguna configuración para los acrónimos que se han extraído.</span><span class="sxs-lookup"><span data-stu-id="e88ec-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e88ec-179">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="e88ec-179">Frequently asked questions</span></span>

<span data-ttu-id="e88ec-180">**P: ¿cómo se clasifican los datos editoriales y extraídos?**</span><span class="sxs-lookup"><span data-stu-id="e88ec-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="e88ec-181">**A:** La característica clasifica actualmente los acrónimos editoriales superiores a los acrónimos extraídos.</span><span class="sxs-lookup"><span data-stu-id="e88ec-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="e88ec-182">**P: ¿Cuánto tiempo tardan los acrónimos de editorial en estar visibles en Microsoft Search después de publicarlos?**</span><span class="sxs-lookup"><span data-stu-id="e88ec-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="e88ec-183">**A:**  Los acrónimos agregados al estado publicado tardan hasta tres días en estar disponibles en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="e88ec-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="e88ec-184">**P: ¿Cómo responden los usuarios que desencadenan acrónimos?**</span><span class="sxs-lookup"><span data-stu-id="e88ec-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="e88ec-185">**A: para**obtener respuestas de acrónimos, los usuarios deben escribir patrones de consulta específicos en un cuadro de **búsqueda** de [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365](https://Office.com) .</span><span class="sxs-lookup"><span data-stu-id="e88ec-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="e88ec-186">**P: ¿Cuánto tiempo tardan los acrónimos extraídos en aparecer después de recibir o enviar un nuevo correo electrónico o documento?**</span><span class="sxs-lookup"><span data-stu-id="e88ec-186">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="e88ec-187">**A:** Los acrónimos extraídos de un nuevo documento o de correo electrónico pueden tardar hasta siete días en aparecer en los resultados de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="e88ec-187">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="e88ec-188">**P: ¿es necesario que los documentos estén en un formato específico para que la extracción los recoja?**</span><span class="sxs-lookup"><span data-stu-id="e88ec-188">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="e88ec-189">**A:** No.</span><span class="sxs-lookup"><span data-stu-id="e88ec-189">**A:** No.</span></span> <span data-ttu-id="e88ec-190">Admitimos todos los tipos de archivo excepto Image, folders y zip.</span><span class="sxs-lookup"><span data-stu-id="e88ec-190">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="e88ec-191">**P: ¿Microsoft Mine acrónimo de los documentos en todos los idiomas?**</span><span class="sxs-lookup"><span data-stu-id="e88ec-191">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="e88ec-192">**A**: Microsoft solo admite la extracción de documentos en inglés.</span><span class="sxs-lookup"><span data-stu-id="e88ec-192">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="e88ec-193">La compatibilidad con otros idiomas se agregará en fases.</span><span class="sxs-lookup"><span data-stu-id="e88ec-193">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="e88ec-194">**P: ¿Qué sucede si mi organización no quiere mostrar acrónimos que se han extraído? ¿Puedo dejar de mostrar acrónimos que se han extraído en los resultados de búsqueda?**</span><span class="sxs-lookup"><span data-stu-id="e88ec-194">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="e88ec-195">**A: para**desactivar la presentación de acrónimos extraídos en los resultados de la búsqueda, cree un vale de soporte al cliente siguiendo las instrucciones en [contacto soporte técnico for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span><span class="sxs-lookup"><span data-stu-id="e88ec-195">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="e88ec-196">Después de crear un vale de soporte técnico, tarda hasta 48 horas en acrónimos extraídos para dejar de aparecer en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e88ec-196">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>
