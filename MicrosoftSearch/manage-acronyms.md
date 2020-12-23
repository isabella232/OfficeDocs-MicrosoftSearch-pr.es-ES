---
title: Administración de las respuestas de acrónimo en Microsoft Search
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Respuestas de crear y actualizar acrónimos en Microsoft Search
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728010"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="d1846-103">La administración de acrónimos responde en Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="d1846-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="d1846-104">Los usuarios a menudo se encontraban con acrónimos y abreviaturas desconocidos que usa su organización o equipo.</span><span class="sxs-lookup"><span data-stu-id="d1846-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="d1846-105">Los términos específicos de organizaciones o equipos pueden ser nuevos para los usuarios que se mueven de un equipo a otro, trabajan con equipos de asociados internos o son nuevos en la organización.</span><span class="sxs-lookup"><span data-stu-id="d1846-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="d1846-106">Las organizaciones no siempre tienen una referencia única para su terminología estándar.</span><span class="sxs-lookup"><span data-stu-id="d1846-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="d1846-107">La ausencia de una sola referencia hace que sea difícil encontrar definiciones o expansiones para estos acrónimos.</span><span class="sxs-lookup"><span data-stu-id="d1846-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="d1846-108">Microsoft Search resuelve ese problema con acrónimos.</span><span class="sxs-lookup"><span data-stu-id="d1846-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="d1846-109">Qué experiencia tienen los usuarios</span><span class="sxs-lookup"><span data-stu-id="d1846-109">What users experience</span></span>

<span data-ttu-id="d1846-110">Microsoft Search los usuarios pueden obtener definiciones con acrónimos en [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)y [Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="d1846-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="d1846-111">En el cuadro de **búsqueda** , los usuarios escriben consultas como estos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="d1846-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="d1846-112">*Qué es* DNN</span><span class="sxs-lookup"><span data-stu-id="d1846-112">*What is* DNN</span></span>
- <span data-ttu-id="d1846-113">*Definir* DNN</span><span class="sxs-lookup"><span data-stu-id="d1846-113">*Define* DNN</span></span>
- <span data-ttu-id="d1846-114">*Definición* de DNN</span><span class="sxs-lookup"><span data-stu-id="d1846-114">DNN *definition*</span></span>
- <span data-ttu-id="d1846-115">*Expandir* DNN</span><span class="sxs-lookup"><span data-stu-id="d1846-115">*Expand* DNN</span></span>
- <span data-ttu-id="d1846-116">*Expansión* DNN</span><span class="sxs-lookup"><span data-stu-id="d1846-116">DNN *expansion*</span></span>
- <span data-ttu-id="d1846-117">*Significado de* DNN</span><span class="sxs-lookup"><span data-stu-id="d1846-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="d1846-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="d1846-118">DNN *means*</span></span>

<span data-ttu-id="d1846-119">El resultado incluye todos los significados de DNN que están presentes en la organización del usuario.</span><span class="sxs-lookup"><span data-stu-id="d1846-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="d1846-120">Los usuarios deben escribir una consulta que incluya las *palabras clave* especificadas en el acrónimo para activar sus respuestas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d1846-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="d1846-121">Las consultas de acrónimo no distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d1846-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="d1846-122">Configurar las respuestas de los acrónimos</span><span class="sxs-lookup"><span data-stu-id="d1846-122">Set up acronyms answers</span></span>

<span data-ttu-id="d1846-123">En el [centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**acrónimos**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)y, después, seleccione **Agregar acrónimo**.</span><span class="sxs-lookup"><span data-stu-id="d1846-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="d1846-124">Microsoft Search consulta dos orígenes de datos para proporcionar a los acrónimo respuestas a las búsquedas de los usuarios:</span><span class="sxs-lookup"><span data-stu-id="d1846-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="d1846-125">**Admin-creados**.</span><span class="sxs-lookup"><span data-stu-id="d1846-125">**Admin-curated**.</span></span> <span data-ttu-id="d1846-126">LO proporcionan los administradores de TI en el [centro de administración](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="d1846-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="d1846-127">**Sistema-creados**.</span><span class="sxs-lookup"><span data-stu-id="d1846-127">**System-curated**.</span></span> <span data-ttu-id="d1846-128">Descubierto por Microsoft Search desde el correo electrónico y los documentos de los usuarios y los datos disponibles públicamente dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="d1846-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="d1846-129">Configurar acrónimos creados de administración</span><span class="sxs-lookup"><span data-stu-id="d1846-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="d1846-130">Los administradores de búsqueda pueden agregar acrónimos en la [pestaña acrónimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) del  [centro de administración de Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span><span class="sxs-lookup"><span data-stu-id="d1846-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="d1846-131">Puede Agregar acrónimos desde cualquier sitio o repositorio interno al centro de administración.</span><span class="sxs-lookup"><span data-stu-id="d1846-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="d1846-132">Estos acrónimos se pueden agregar al estado **publicado** o **borrador** :</span><span class="sxs-lookup"><span data-stu-id="d1846-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="d1846-133">**Estado publicado**.</span><span class="sxs-lookup"><span data-stu-id="d1846-133">**Published state**.</span></span> <span data-ttu-id="d1846-134">Los acrónimos están disponibles para los usuarios de la organización a través de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="d1846-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="d1846-135">Los acrónimos agregados al estado publicado pueden tardar hasta tres días en estar disponibles en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="d1846-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="d1846-136">**Estado de borrador**.</span><span class="sxs-lookup"><span data-stu-id="d1846-136">**Draft state**.</span></span> <span data-ttu-id="d1846-137">Si desea revisar un acrónimo antes de que esté disponible en Microsoft Search, puede Agregar el acrónimo en un estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="d1846-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="d1846-138">Los acrónimos en el estado de borrador no aparecerán en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d1846-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="d1846-139">Tendrá que mover el acrónimo al estado publicado para que aparezca en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d1846-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="d1846-140">Puede Agregar acrónimos de forma individual o en bloque para importarlos en un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="d1846-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="d1846-141">Cargue un archivo CSV con los campos que se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1846-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="d1846-142">Acrónimo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="d1846-142">Acronym (mandatory)</span></span> | <span data-ttu-id="d1846-143">Expansión (obligatoria)</span><span class="sxs-lookup"><span data-stu-id="d1846-143">Expansion (mandatory)</span></span> | <span data-ttu-id="d1846-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1846-144">Description</span></span>  | <span data-ttu-id="d1846-145">Origen</span><span class="sxs-lookup"><span data-stu-id="d1846-145">Source</span></span> | <span data-ttu-id="d1846-146">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="d1846-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="d1846-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="d1846-147">*XXX*</span></span> | <span data-ttu-id="d1846-148">*Abreviatura de ortografía*</span><span class="sxs-lookup"><span data-stu-id="d1846-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="d1846-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="d1846-149">*URL*</span></span> | <span data-ttu-id="d1846-150">*Publicado o borrador*</span><span class="sxs-lookup"><span data-stu-id="d1846-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="d1846-151">Campos CSV</span><span class="sxs-lookup"><span data-stu-id="d1846-151">CSV fields</span></span>

<span data-ttu-id="d1846-152">**Acrónimo**.</span><span class="sxs-lookup"><span data-stu-id="d1846-152">**Acronym**.</span></span> <span data-ttu-id="d1846-153">Contiene la forma corta o el acrónimo real.</span><span class="sxs-lookup"><span data-stu-id="d1846-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="d1846-154">Un ejemplo es *DNN*.</span><span class="sxs-lookup"><span data-stu-id="d1846-154">An example is *DNN*.</span></span>

<span data-ttu-id="d1846-155">**Expansión**.</span><span class="sxs-lookup"><span data-stu-id="d1846-155">**Expansion**.</span></span> <span data-ttu-id="d1846-156">Contiene la expansión del acrónimo.</span><span class="sxs-lookup"><span data-stu-id="d1846-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="d1846-157">Un ejemplo es una *red neuronal profunda*.</span><span class="sxs-lookup"><span data-stu-id="d1846-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="d1846-158">**Descripción**.</span><span class="sxs-lookup"><span data-stu-id="d1846-158">**Description**.</span></span> <span data-ttu-id="d1846-159">Breve descripción del acrónimo que proporciona a los usuarios más información sobre el acrónimo y su expansión.</span><span class="sxs-lookup"><span data-stu-id="d1846-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="d1846-160">Por ejemplo, *una red neuronal profunda es una red neuronal con cierto nivel de complejidad, una red neuronal con más de dos capas*.</span><span class="sxs-lookup"><span data-stu-id="d1846-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="d1846-161">**Origen**.</span><span class="sxs-lookup"><span data-stu-id="d1846-161">**Source**.</span></span> <span data-ttu-id="d1846-162">La dirección URL de la página o sitio web al que desea que vayan los usuarios para obtener más información sobre el acrónimo.</span><span class="sxs-lookup"><span data-stu-id="d1846-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="d1846-163">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="d1846-163">**State**.</span></span> <span data-ttu-id="d1846-164">Este campo puede tener dos valores:</span><span class="sxs-lookup"><span data-stu-id="d1846-164">This field can take two values:</span></span>

- <span data-ttu-id="d1846-165">**Borrador**.</span><span class="sxs-lookup"><span data-stu-id="d1846-165">**Draft**.</span></span> <span data-ttu-id="d1846-166">Agrega el acrónimo al estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="d1846-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="d1846-167">**Publicado**.</span><span class="sxs-lookup"><span data-stu-id="d1846-167">**Published**.</span></span> <span data-ttu-id="d1846-168">Agrega el acrónimo al estado publicado y lo hace disponible en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="d1846-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="d1846-169">Acrónimos del sistema creados</span><span class="sxs-lookup"><span data-stu-id="d1846-169">System-curated acronyms</span></span>

<span data-ttu-id="d1846-170">Puede que sea un reto para los administradores agregar todos los acrónimos que se usan en una organización a las respuestas.</span><span class="sxs-lookup"><span data-stu-id="d1846-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="d1846-171">Esta característica puede encontrar acrónimos que los administradores de búsqueda aún no conocen.</span><span class="sxs-lookup"><span data-stu-id="d1846-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="d1846-172">Para ello, Microsoft Search también detecta y curates acrónimos de estos orígenes:</span><span class="sxs-lookup"><span data-stu-id="d1846-172">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="d1846-173">Mensajes de correo electrónico de los usuarios</span><span class="sxs-lookup"><span data-stu-id="d1846-173">Users’ emails</span></span>
- <span data-ttu-id="d1846-174">Documentos en [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)y [Microsoft OneNote](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="d1846-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="d1846-175">Documentos públicos de la organización a los que los usuarios tienen acceso en SharePoint, OneDrive o OneNote</span><span class="sxs-lookup"><span data-stu-id="d1846-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="d1846-176">Microsoft Search se asegura de que solo los usuarios con acceso y permisos a un documento puedan ver los acrónimos que se detectan en él.</span><span class="sxs-lookup"><span data-stu-id="d1846-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="d1846-177">Cuando se encuentra un acrónimo en el buzón de un usuario, el usuario solo puede ver ese acrónimo.</span><span class="sxs-lookup"><span data-stu-id="d1846-177">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="d1846-178">No se necesita ninguna configuración para los acrónimos admin-creados.</span><span class="sxs-lookup"><span data-stu-id="d1846-178">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d1846-179">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="d1846-179">Frequently asked questions</span></span>

<span data-ttu-id="d1846-180">**P: ¿cómo se clasifican los datos de administrador-creados y del sistema creados?**</span><span class="sxs-lookup"><span data-stu-id="d1846-180">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="d1846-181">**A:** La clasificación de los resultados puede variar de una persona a otra, ya que los resultados se personalizan para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="d1846-181">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="d1846-182">Ninguna de estas categorías siempre tendrá prioridad sobre la otra.</span><span class="sxs-lookup"><span data-stu-id="d1846-182">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="d1846-183">**P: ¿Cuánto tiempo se tarda en ver los acrónimos creados de administración en Microsoft Search después de publicarlos?**</span><span class="sxs-lookup"><span data-stu-id="d1846-183">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="d1846-184">**A:**  Los acrónimos agregados al estado publicado tardan hasta tres días en estar disponibles en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="d1846-184">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="d1846-185">**P: ¿Cómo responden los usuarios que desencadenan acrónimos?**</span><span class="sxs-lookup"><span data-stu-id="d1846-185">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="d1846-186">**A: para** obtener respuestas de acrónimos, los usuarios deben escribir patrones de consulta específicos en un cuadro de **búsqueda** de [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365](https://Office.com) .</span><span class="sxs-lookup"><span data-stu-id="d1846-186">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="d1846-187">**P: ¿Cuánto tiempo tardan los acrónimos del sistema creados en aparecer después de recibir o enviar un nuevo correo electrónico o documento?**</span><span class="sxs-lookup"><span data-stu-id="d1846-187">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="d1846-188">**A:** Los acrónimos que se encuentran en un nuevo documento o correo electrónico pueden tardar hasta siete días en aparecer en los resultados de la búsqueda de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1846-188">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="d1846-189">**P: ¿es necesario que los documentos estén en un formato específico para que la extracción los recoja?**</span><span class="sxs-lookup"><span data-stu-id="d1846-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="d1846-190">**A:** No.</span><span class="sxs-lookup"><span data-stu-id="d1846-190">**A:** No.</span></span> <span data-ttu-id="d1846-191">Admitimos todos los tipos de archivo excepto Image, folders y zip.</span><span class="sxs-lookup"><span data-stu-id="d1846-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="d1846-192">**P: ¿Microsoft detectará acrónimos de los documentos en todos los idiomas?**</span><span class="sxs-lookup"><span data-stu-id="d1846-192">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="d1846-193">**A**: Microsoft solo admite la extracción de documentos en inglés.</span><span class="sxs-lookup"><span data-stu-id="d1846-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="d1846-194">La compatibilidad con otros idiomas se agregará en fases.</span><span class="sxs-lookup"><span data-stu-id="d1846-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="d1846-195">**P: ¿Qué sucede si mi organización no quiere mostrar acrónimos del sistema creados? ¿Puedo dejar de mostrar este tipo de acrónimo en mis resultados de búsqueda?**</span><span class="sxs-lookup"><span data-stu-id="d1846-195">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="d1846-196">**A: para** desactivar los acrónimos del creados del sistema en los resultados de la búsqueda, cree un vale de soporte al cliente siguiendo las instrucciones en [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span><span class="sxs-lookup"><span data-stu-id="d1846-196">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="d1846-197">Después de crear un vale de soporte técnico, tarda hasta 48 horas para que los acrónimos del creados del sistema dejen de aparecer en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d1846-197">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
