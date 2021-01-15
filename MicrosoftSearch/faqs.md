---
title: Preguntas más frecuentes
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Obtenga respuestas a las preguntas más frecuentes acerca de la búsqueda empresarial y Microsoft Search
ms.openlocfilehash: abaa1a232b08ba586dd6cd777f7e54c323159dee
ms.sourcegitcommit: aa7774d2bdff2bd9e1b7f51fcda90fa6b0c3a5ca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867382"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="accc8-103">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="accc8-103">Frequently asked questions</span></span>

<span data-ttu-id="accc8-104">Aquí tiene una lista de las preguntas más frecuentes.</span><span class="sxs-lookup"><span data-stu-id="accc8-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="accc8-105">¿No encuentra aquí una respuesta a su pregunta?</span><span class="sxs-lookup"><span data-stu-id="accc8-105">Don't see your question answered here?</span></span> <span data-ttu-id="accc8-106">Formule su pregunta en el comentario de este artículo.</span><span class="sxs-lookup"><span data-stu-id="accc8-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="accc8-107">¿Se ofrece la comprensión de consultas avanzadas?</span><span class="sxs-lookup"><span data-stu-id="accc8-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="accc8-p102">Sí, Microsoft Search analiza la intención de consulta de frases más grandes. Esta característica usa AI para aprender frases superfluas comunes que los usuarios agregan a sus consultas que no afectan a su intención de búsqueda. Por ejemplo, cuando un usuario busca información sobre cómo cambiar mi *contraseña,* extraemos las palabras menos importantes de la consulta y el desencadenador en función de las relevantes, como cambiar *contraseña.*</span><span class="sxs-lookup"><span data-stu-id="accc8-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="accc8-111">Esta característica no invalidará las palabras clave establecidas en el Centro [de administración de Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="accc8-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="accc8-112">¿Puedo buscar archivos locales?</span><span class="sxs-lookup"><span data-stu-id="accc8-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="accc8-113">Sí.</span><span class="sxs-lookup"><span data-stu-id="accc8-113">Yes.</span></span> <span data-ttu-id="accc8-114">Puede buscar archivos de [SharePoint](http://sharepoint.com/) locales si tiene una implementación híbrida de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="accc8-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="accc8-115">¿Cómo hago que Bing sea el motor de búsqueda predeterminado para los usuarios de mi organización?</span><span class="sxs-lookup"><span data-stu-id="accc8-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="accc8-116">Estas son las instrucciones para configurar el motor de búsqueda predeterminado, la página principal predeterminada y el explorador predeterminado para ofrecer a los usuarios la mejor experiencia con Búsqueda de Microsoft en [Bing:](https://Bing.com)</span><span class="sxs-lookup"><span data-stu-id="accc8-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="accc8-117">Establecer Microsoft Edge como explorador predeterminado</span><span class="sxs-lookup"><span data-stu-id="accc8-117">Set Microsoft Edge as your default browser</span></span>](/deployedge/edge-default-browser)
- [<span data-ttu-id="accc8-118">Establezca Bing como el motor de búsqueda predeterminado</span><span class="sxs-lookup"><span data-stu-id="accc8-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="accc8-119">Establezca Bing.com como la página principal de la empresa</span><span class="sxs-lookup"><span data-stu-id="accc8-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="accc8-120">¿Cómo se protegen mis resultados de búsqueda?</span><span class="sxs-lookup"><span data-stu-id="accc8-120">How are my search results protected?</span></span>

<span data-ttu-id="accc8-121">Se requiere [la autenticación de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) para obtener acceso a los resultados de la nube de confianza.</span><span class="sxs-lookup"><span data-stu-id="accc8-121">We require [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="accc8-122">Los usuarios autenticados solo verán el contenido al que tengan acceso.</span><span class="sxs-lookup"><span data-stu-id="accc8-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="accc8-123">Las consultas de búsqueda se desentieran y los registros se separan del tráfico de búsqueda público de [Bing](https://Bing.com) cuando se usa Microsoft Search en Bing.</span><span class="sxs-lookup"><span data-stu-id="accc8-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic when you use Microsoft Search in Bing.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="accc8-124">¿Puedo buscar en organizaciones federadas?</span><span class="sxs-lookup"><span data-stu-id="accc8-124">Can I search across federated organizations?</span></span>

<span data-ttu-id="accc8-125">No.</span><span class="sxs-lookup"><span data-stu-id="accc8-125">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="accc8-126">¿Dónde puedo obtener información sobre la seguridad, el cumplimiento y la privacidad de Office 365?</span><span class="sxs-lookup"><span data-stu-id="accc8-126">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="accc8-127">Puede encontrar detalles en las páginas [del Centro de confianza para Office 365.](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="accc8-127">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="accc8-128">¿Los usuarios pueden ganar puntos de Microsoft Rewards con su cuenta profesional o educativa?</span><span class="sxs-lookup"><span data-stu-id="accc8-128">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="accc8-129">Búsqueda de Microsoft necesita que los usuarios de la empresa inicien sesión con una cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="accc8-129">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="accc8-130">Sin embargo, los usuarios no podrán unirse ni iniciar sesión en el programa Microsoft Rewards con esas cuentas.</span><span class="sxs-lookup"><span data-stu-id="accc8-130">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="accc8-131">Sin embargo, hay una instancia en la que un usuario de la empresa puede ver puntos de recompensas.</span><span class="sxs-lookup"><span data-stu-id="accc8-131">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="accc8-132">Esto puede suceder cuando un usuario de Búsqueda de Microsoft tiene una cuenta de recompensas que se creó con una [cuenta de Microsoft](https://www.microsoft.com/welcome?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="accc8-132">This can happen when a Microsoft Search user has a Rewards account that was created with a [Microsoft account](https://www.microsoft.com/welcome?rtc=1).</span></span> <span data-ttu-id="accc8-133">(La dirección de correo electrónico asociada a una cuenta de Microsoft puede ser de Outlook.com, Hotmail.com, Gmail, Yahoo u otros proveedores). Si los usuarios inician sesión alternadamente con su cuenta profesional y una cuenta de Microsoft en la misma sesión de navegador, podrían acumular puntos en su cuenta de recompensas.</span><span class="sxs-lookup"><span data-stu-id="accc8-133">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="accc8-134">Los usuarios pueden dejar de acumular puntos mientras buscan con Búsqueda de Microsoft borrando sus cookies.</span><span class="sxs-lookup"><span data-stu-id="accc8-134">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="accc8-135">¿Pueden los usuarios invitados aprovechar Microsoft Search en mi organización?</span><span class="sxs-lookup"><span data-stu-id="accc8-135">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="accc8-136">Microsoft 365 permite la colaboración enriqueccional con personas externas a su organización a través [del acceso de invitados.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span><span class="sxs-lookup"><span data-stu-id="accc8-136">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="accc8-137">Estos usuarios podrán realizar operaciones de búsqueda en documentos, sitios, grupos, listas y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="accc8-137">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="accc8-138">Sin embargo, los usuarios invitados no tendrán la experiencia completa y personalizada de Microsoft Search y es posible que deba aprovechar el cuadro de búsqueda en la página en lugar del cuadro unificado de Búsqueda de Microsoft en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="accc8-138">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>
