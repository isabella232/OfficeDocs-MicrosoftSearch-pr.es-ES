---
title: Administrar respuestas acrónimos en Microsoft Search
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
description: Crear y actualizar respuestas de acrónimos en Microsoft Search
ms.openlocfilehash: 5677ff6915c9e43e2559964c40086cb360a05db7
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031372"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="8fae5-103">Administrar respuestas de acrónimos en Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="8fae5-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="8fae5-104">A menudo, los usuarios se topar con acrónimos y abreviaturas desconocidos usados por su organización o equipo.</span><span class="sxs-lookup"><span data-stu-id="8fae5-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="8fae5-105">Los términos que son específicos de organizaciones o equipos pueden ser nuevos para las personas que se mueven de un equipo a otro, trabajan con equipos asociados internos o son nuevos en la organización.</span><span class="sxs-lookup"><span data-stu-id="8fae5-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="8fae5-106">Las organizaciones no siempre tienen una sola referencia para su terminología estándar.</span><span class="sxs-lookup"><span data-stu-id="8fae5-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="8fae5-107">La falta de una sola referencia hace que sea difícil encontrar definiciones o expansiones para estos acrónimos.</span><span class="sxs-lookup"><span data-stu-id="8fae5-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="8fae5-108">Microsoft Search resuelve ese problema con acrónimos.</span><span class="sxs-lookup"><span data-stu-id="8fae5-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="8fae5-109">Qué experiencia tienen los usuarios</span><span class="sxs-lookup"><span data-stu-id="8fae5-109">What users experience</span></span>

<span data-ttu-id="8fae5-110">Los usuarios de Microsoft Search pueden obtener definiciones con acrónimos en [Bing,](https://Bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)y [Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="8fae5-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="8fae5-111">En el **cuadro Buscar,** los usuarios escriben consultas como estos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="8fae5-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="8fae5-112">*Qué es* DNN</span><span class="sxs-lookup"><span data-stu-id="8fae5-112">*What is* DNN</span></span>
- <span data-ttu-id="8fae5-113">*Definir* DNN</span><span class="sxs-lookup"><span data-stu-id="8fae5-113">*Define* DNN</span></span>
- <span data-ttu-id="8fae5-114">Definición *de* DNN</span><span class="sxs-lookup"><span data-stu-id="8fae5-114">DNN *definition*</span></span>
- <span data-ttu-id="8fae5-115">*Expandir* DNN</span><span class="sxs-lookup"><span data-stu-id="8fae5-115">*Expand* DNN</span></span>
- <span data-ttu-id="8fae5-116">Expansión *de* DNN</span><span class="sxs-lookup"><span data-stu-id="8fae5-116">DNN *expansion*</span></span>
- <span data-ttu-id="8fae5-117">*Significado de* DNN</span><span class="sxs-lookup"><span data-stu-id="8fae5-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="8fae5-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="8fae5-118">DNN *means*</span></span>

<span data-ttu-id="8fae5-119">El resultado incluye todos los significados de DNN que están presentes en la organización del usuario.</span><span class="sxs-lookup"><span data-stu-id="8fae5-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="8fae5-120">Los usuarios deben escribir una consulta que incluya las palabras clave *especificadas* del acrónimo para desencadenar sus respuestas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8fae5-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="8fae5-121">Las consultas de acrónimos no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8fae5-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="8fae5-122">Configurar respuestas acrónimos</span><span class="sxs-lookup"><span data-stu-id="8fae5-122">Set up acronyms answers</span></span>

<span data-ttu-id="8fae5-123">En el [Centro de administración de Microsoft 365,](https://admin.microsoft.com)vaya a [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)y, a continuación, **seleccione Agregar acrónimos**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="8fae5-124">Microsoft Search consulta dos orígenes de datos para proporcionar acrónimos respuestas a las búsquedas de los usuarios:</span><span class="sxs-lookup"><span data-stu-id="8fae5-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="8fae5-125">**Curada por el administrador.**</span><span class="sxs-lookup"><span data-stu-id="8fae5-125">**Admin-curated**.</span></span> <span data-ttu-id="8fae5-126">Proporcionado por los administradores de TI en el [Centro de administración.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)</span><span class="sxs-lookup"><span data-stu-id="8fae5-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="8fae5-127">**System-curated**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-127">**System-curated**.</span></span> <span data-ttu-id="8fae5-128">Detectado por Microsoft Search a partir del correo electrónico y los documentos de los usuarios y los datos disponibles públicamente en la organización.</span><span class="sxs-lookup"><span data-stu-id="8fae5-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="8fae5-129">Configurar acrónimos seleccionados por el administrador</span><span class="sxs-lookup"><span data-stu-id="8fae5-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="8fae5-130">Los administradores de búsqueda pueden agregar acrónimos en la pestaña [Acrónimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) del Centro de administración  [de Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span><span class="sxs-lookup"><span data-stu-id="8fae5-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="8fae5-131">Puede agregar acrónimos desde cualquier sitio o repositorio interno al Centro de administración.</span><span class="sxs-lookup"><span data-stu-id="8fae5-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="8fae5-132">Estos acrónimos se pueden agregar al **estado Publicado** o **Borrador:**</span><span class="sxs-lookup"><span data-stu-id="8fae5-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="8fae5-133">**Estado publicado**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-133">**Published state**.</span></span> <span data-ttu-id="8fae5-134">Los acrónimos están disponibles para los usuarios de la organización a través de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="8fae5-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="8fae5-135">Los acrónimos agregados al estado publicado pueden tardar hasta tres días en estar disponibles en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="8fae5-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="8fae5-136">**Estado de borrador**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-136">**Draft state**.</span></span> <span data-ttu-id="8fae5-137">Si desea revisar un acrónimo antes de que esté disponible en Microsoft Search, puede agregar el acrónimo en estado Borrador.</span><span class="sxs-lookup"><span data-stu-id="8fae5-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="8fae5-138">Las siglas en estado Borrador no aparecerán en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8fae5-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="8fae5-139">Deberá mover el acrónimo al estado Publicado para que aparezca en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8fae5-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="8fae5-140">Puede agregar acrónimos individualmente o importarlos masivamente en un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="8fae5-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="8fae5-141">Cargue un archivo CSV con los campos que se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="8fae5-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="8fae5-142">Acrónimo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="8fae5-142">Acronym (Mandatory)</span></span> | <span data-ttu-id="8fae5-143">Expansión (obligatoria)</span><span class="sxs-lookup"><span data-stu-id="8fae5-143">Expansion (Mandatory)</span></span> | <span data-ttu-id="8fae5-144">Url</span><span class="sxs-lookup"><span data-stu-id="8fae5-144">Url</span></span> | <span data-ttu-id="8fae5-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fae5-145">Description</span></span>  | <span data-ttu-id="8fae5-146">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="8fae5-146">State (Mandatory)</span></span> | <span data-ttu-id="8fae5-147">Last Modified</span><span class="sxs-lookup"><span data-stu-id="8fae5-147">Last Modified</span></span> | <span data-ttu-id="8fae5-148">Last Modified By</span><span class="sxs-lookup"><span data-stu-id="8fae5-148">Last Modified By</span></span> | <span data-ttu-id="8fae5-149">Id</span><span class="sxs-lookup"><span data-stu-id="8fae5-149">Id</span></span> |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| <span data-ttu-id="8fae5-150">*XXX*</span><span class="sxs-lookup"><span data-stu-id="8fae5-150">*XXX*</span></span> | <span data-ttu-id="8fae5-151">*Abreviatura desletreada*</span><span class="sxs-lookup"><span data-stu-id="8fae5-151">*Spelled out abbreviation*</span></span> | <span data-ttu-id="8fae5-152">*Source*</span><span class="sxs-lookup"><span data-stu-id="8fae5-152">*Source*</span></span> |  | <span data-ttu-id="8fae5-153">*Publicado o Borrador*</span><span class="sxs-lookup"><span data-stu-id="8fae5-153">*Published or Draft*</span></span> |  |  |  |

### <a name="csv-fields"></a><span data-ttu-id="8fae5-154">Campos CSV</span><span class="sxs-lookup"><span data-stu-id="8fae5-154">CSV fields</span></span>

<span data-ttu-id="8fae5-155">**Acrónimo**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-155">**Acronym**.</span></span> <span data-ttu-id="8fae5-156">Contiene el formulario corto o acrónimo real.</span><span class="sxs-lookup"><span data-stu-id="8fae5-156">Contains the actual short form or acronym.</span></span> <span data-ttu-id="8fae5-157">Un ejemplo es *DNN*.</span><span class="sxs-lookup"><span data-stu-id="8fae5-157">An example is *DNN*.</span></span>

<span data-ttu-id="8fae5-158">**Expansión**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-158">**Expansion**.</span></span> <span data-ttu-id="8fae5-159">Contiene la expansión del acrónimo.</span><span class="sxs-lookup"><span data-stu-id="8fae5-159">Contains the expansion of the acronym.</span></span> <span data-ttu-id="8fae5-160">Un ejemplo es *Deep Neural Network*.</span><span class="sxs-lookup"><span data-stu-id="8fae5-160">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="8fae5-161">**Descripción**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-161">**Description**.</span></span> <span data-ttu-id="8fae5-162">Una breve descripción del acrónimo que proporciona a los usuarios más información sobre el acrónimo y su expansión.</span><span class="sxs-lookup"><span data-stu-id="8fae5-162">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="8fae5-163">Por ejemplo, una red neuronal profunda es una red neuronal con un cierto nivel de complejidad, una red *neuronal con más de dos capas.*</span><span class="sxs-lookup"><span data-stu-id="8fae5-163">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="8fae5-164">**Origen**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-164">**Source**.</span></span> <span data-ttu-id="8fae5-165">Dirección URL de la página o sitio web donde desea que los usuarios vayan para obtener más información sobre el acrónimo.</span><span class="sxs-lookup"><span data-stu-id="8fae5-165">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="8fae5-166">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-166">**State**.</span></span> <span data-ttu-id="8fae5-167">Este campo puede tener dos valores:</span><span class="sxs-lookup"><span data-stu-id="8fae5-167">This field can take two values:</span></span>

- <span data-ttu-id="8fae5-168">**Borrador**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-168">**Draft**.</span></span> <span data-ttu-id="8fae5-169">Agrega el acrónimo al estado Borrador.</span><span class="sxs-lookup"><span data-stu-id="8fae5-169">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="8fae5-170">**Publicado**.</span><span class="sxs-lookup"><span data-stu-id="8fae5-170">**Published**.</span></span> <span data-ttu-id="8fae5-171">Agrega el acrónimo al estado Publicado y lo hace disponible en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="8fae5-171">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="8fae5-172">Acrónimos seleccionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8fae5-172">System-curated acronyms</span></span>

<span data-ttu-id="8fae5-173">Puede ser un desafío para los administradores agregar todas las siglas usadas dentro de una organización a Respuestas.</span><span class="sxs-lookup"><span data-stu-id="8fae5-173">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="8fae5-174">Esta característica puede encontrar acrónimos que los administradores de búsqueda ni siquiera conocen.</span><span class="sxs-lookup"><span data-stu-id="8fae5-174">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="8fae5-175">Para ello, Microsoft Search también detecta y cura acrónimos de estos orígenes:</span><span class="sxs-lookup"><span data-stu-id="8fae5-175">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="8fae5-176">Mensajes de correo electrónico de los usuarios</span><span class="sxs-lookup"><span data-stu-id="8fae5-176">Users’ emails</span></span>
- <span data-ttu-id="8fae5-177">Documentos en [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)y [Microsoft OneNote](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="8fae5-177">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="8fae5-178">Documentos públicos de la organización a los que los usuarios tienen acceso en SharePoint, OneDrive o OneNote</span><span class="sxs-lookup"><span data-stu-id="8fae5-178">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="8fae5-179">Microsoft Search se asegura de que solo los usuarios con acceso y permisos a un documento puedan ver las siglas que se detectan en él.</span><span class="sxs-lookup"><span data-stu-id="8fae5-179">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="8fae5-180">Cuando se encuentra un acrónimo en el buzón de un usuario, solo ese usuario puede ver ese acrónimo.</span><span class="sxs-lookup"><span data-stu-id="8fae5-180">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="8fae5-181">No se necesita ninguna configuración para acrónimos seleccionados por el administrador.</span><span class="sxs-lookup"><span data-stu-id="8fae5-181">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8fae5-182">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="8fae5-182">Frequently asked questions</span></span>

<span data-ttu-id="8fae5-183">**P: ¿Cómo se clasifican los datos seleccionados por el administrador y los del sistema?**</span><span class="sxs-lookup"><span data-stu-id="8fae5-183">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="8fae5-184">**A:** La clasificación de los resultados puede variar de una persona a otra, ya que los resultados son personalizados para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="8fae5-184">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="8fae5-185">Ninguna de estas categorías siempre tendrá prioridad sobre la otra.</span><span class="sxs-lookup"><span data-stu-id="8fae5-185">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="8fae5-186">**P: ¿Cuánto tiempo se necesita para que los acrónimos seleccionados por el administrador sean visibles en Microsoft Search después de su publicación?**</span><span class="sxs-lookup"><span data-stu-id="8fae5-186">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="8fae5-187">**A:**  Los acrónimos agregados al estado publicado tardan hasta tres días en estar disponibles en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="8fae5-187">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="8fae5-188">**P: ¿Cómo desencadenan los usuarios las respuestas a las siglas?**</span><span class="sxs-lookup"><span data-stu-id="8fae5-188">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="8fae5-189">**A**: Para obtener respuestas de acrónimos, los usuarios deben escribir patrones de consulta específicos en un cuadro de búsqueda de [Bing,](https://bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365.](https://Office.com) </span><span class="sxs-lookup"><span data-stu-id="8fae5-189">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="8fae5-190">**P: ¿Cuánto tiempo se necesita para que aparezcan las siglas del sistema después de recibir o enviar un nuevo correo electrónico o documento?**</span><span class="sxs-lookup"><span data-stu-id="8fae5-190">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="8fae5-191">**A:** Las siglas encontradas en un nuevo correo electrónico o documento pueden tardar hasta siete días en aparecer en los resultados de microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="8fae5-191">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="8fae5-192">**P: ¿Los documentos deben tener un formato específico para que la minería los resalte?**</span><span class="sxs-lookup"><span data-stu-id="8fae5-192">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="8fae5-193">**A:** No.</span><span class="sxs-lookup"><span data-stu-id="8fae5-193">**A:** No.</span></span> <span data-ttu-id="8fae5-194">Se admiten todos los tipos de archivo excepto los archivos de imagen, carpetas y zip.</span><span class="sxs-lookup"><span data-stu-id="8fae5-194">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="8fae5-195">**P: ¿Detectará Microsoft acrónimos de documentos en todos los idiomas?**</span><span class="sxs-lookup"><span data-stu-id="8fae5-195">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="8fae5-196">**A**: Microsoft solo admite la minería de documentos en inglés.</span><span class="sxs-lookup"><span data-stu-id="8fae5-196">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="8fae5-197">La compatibilidad con otros idiomas se agregará en fases.</span><span class="sxs-lookup"><span data-stu-id="8fae5-197">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="8fae5-198">**P: ¿Qué ocurre si mi organización no quiere mostrar acrónimos seleccionados por el sistema? ¿Puedo dejar de mostrar este tipo de acrónimo en mis resultados de búsqueda?**</span><span class="sxs-lookup"><span data-stu-id="8fae5-198">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="8fae5-199">**A**: Para desactivar la presentación de acrónimos seleccionados por el sistema en los resultados de la búsqueda, cree un vale de soporte al cliente siguiendo las instrucciones del soporte técnico de contacto para [productos empresariales](/microsoft-365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="8fae5-199">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](/microsoft-365/admin/contact-support-for-business-products).</span></span>
<span data-ttu-id="8fae5-200">Después de crear un vale de soporte técnico, los acrónimos seleccionados por el sistema tardan hasta 48 horas en dejar de aparecer en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8fae5-200">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>