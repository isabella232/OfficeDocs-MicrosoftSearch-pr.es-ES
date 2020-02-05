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
ms.openlocfilehash: 1acf4b5c4b3e771072ea67f4d807454723352c3f
ms.sourcegitcommit: c22e8c3dcc53857da677db98a1a2b7d5ca2c6170
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41721763"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="30642-103">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="30642-103">Frequently asked questions</span></span>

<span data-ttu-id="30642-104">Aquí tiene una lista de las preguntas más frecuentes.</span><span class="sxs-lookup"><span data-stu-id="30642-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="30642-105">¿No encuentra aquí una respuesta a su pregunta?</span><span class="sxs-lookup"><span data-stu-id="30642-105">Don't see your question answered here?</span></span> <span data-ttu-id="30642-106">Formule su pregunta en el comentario de este artículo.</span><span class="sxs-lookup"><span data-stu-id="30642-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="30642-107">¿Se ofrece la comprensión de consultas avanzadas?</span><span class="sxs-lookup"><span data-stu-id="30642-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="30642-p102">Sí, Microsoft Search analiza el intento de consulta de frases más grandes. Esta característica utiliza AI para aprender frases superfluas comunes que los usuarios agregan a sus consultas que no afectan su intento de búsqueda. Por ejemplo, cuando un usuario busca información *más información sobre cómo cambiar mi contraseña*, extraemos las palabras menos importantes de la consulta y del desencadenador en función de los aspectos relevantes como *Cambiar contraseña*.</span><span class="sxs-lookup"><span data-stu-id="30642-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for *tell me more about how to change my password please*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="30642-111">Esta característica no reemplaza las palabras clave definidas en el [centro de administración](https://admin.microsoft.com)de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="30642-111">This feature won't override keywords set in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="30642-112">¿Puedo buscar archivos locales?</span><span class="sxs-lookup"><span data-stu-id="30642-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="30642-113">Sí.</span><span class="sxs-lookup"><span data-stu-id="30642-113">Yes.</span></span> <span data-ttu-id="30642-114">Puede buscar en los archivos de [SharePoint](http://sharepoint.com/) locales si tiene una implementación híbrida de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="30642-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="30642-115">¿Cómo hago que Bing sea el motor de búsqueda predeterminado para los usuarios de mi organización?</span><span class="sxs-lookup"><span data-stu-id="30642-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="30642-116">Estas son las instrucciones para configurar el motor de búsqueda predeterminado, la Página principal predeterminada y el explorador predeterminado para proporcionar a los usuarios la mejor experiencia con Microsoft Search en [Bing](https://Bing.com):</span><span class="sxs-lookup"><span data-stu-id="30642-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="30642-117">Establecer Microsoft Edge como explorador predeterminado</span><span class="sxs-lookup"><span data-stu-id="30642-117">Set Microsoft Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="30642-118">Establezca Bing como el motor de búsqueda predeterminado</span><span class="sxs-lookup"><span data-stu-id="30642-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="30642-119">Establezca Bing.com como la página principal de la empresa</span><span class="sxs-lookup"><span data-stu-id="30642-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="30642-120">¿Cómo se protegen mis resultados de búsqueda?</span><span class="sxs-lookup"><span data-stu-id="30642-120">How are my search results protected?</span></span>

<span data-ttu-id="30642-121">Requerimos que la autenticación de [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) obtenga acceso a los resultados de la nube de confianza.</span><span class="sxs-lookup"><span data-stu-id="30642-121">We require [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="30642-122">Los usuarios autenticados solo verán el contenido al que tengan acceso.</span><span class="sxs-lookup"><span data-stu-id="30642-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="30642-123">Las consultas de búsqueda se identifican y los registros se separan del tráfico de búsqueda de [Bing](https://Bing.com) público.</span><span class="sxs-lookup"><span data-stu-id="30642-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic.</span></span> <span data-ttu-id="30642-124">Este nivel de protección no está disponible en ningún otro lugar del sector.</span><span class="sxs-lookup"><span data-stu-id="30642-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="30642-125">¿Puedo buscar en organizaciones federadas?</span><span class="sxs-lookup"><span data-stu-id="30642-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="30642-126">No.</span><span class="sxs-lookup"><span data-stu-id="30642-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="30642-127">¿Dónde puedo obtener información sobre la seguridad, el cumplimiento y la privacidad de Office 365?</span><span class="sxs-lookup"><span data-stu-id="30642-127">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="30642-128">Puede encontrar información detallada en las [páginas del centro de confianza para Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="30642-128">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="30642-129">¿Los usuarios pueden ganar puntos de Microsoft Rewards con su cuenta profesional o educativa?</span><span class="sxs-lookup"><span data-stu-id="30642-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="30642-130">Búsqueda de Microsoft necesita que los usuarios de la empresa inicien sesión con una cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="30642-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="30642-131">Sin embargo, los usuarios no podrán unirse ni iniciar sesión en el programa Microsoft Rewards con esas cuentas.</span><span class="sxs-lookup"><span data-stu-id="30642-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="30642-132">Sin embargo, hay una instancia en la que un usuario de la empresa puede ver puntos de recompensas.</span><span class="sxs-lookup"><span data-stu-id="30642-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="30642-133">Esto puede suceder cuando un usuario de Búsqueda de Microsoft tiene una cuenta de recompensas que se creó con una [cuenta de Microsoft](https://www.microsoft.com/welcome?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="30642-133">This can happen when a Microsoft Search user has a Rewards account that was created with a [Microsoft account](https://www.microsoft.com/welcome?rtc=1).</span></span> <span data-ttu-id="30642-134">(La dirección de correo electrónico asociada a una cuenta de Microsoft puede ser de Outlook.com, Hotmail.com, Gmail, Yahoo u otros proveedores). Si los usuarios inician sesión alternadamente con su cuenta profesional y una cuenta de Microsoft en la misma sesión de navegador, podrían acumular puntos en su cuenta de recompensas.</span><span class="sxs-lookup"><span data-stu-id="30642-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="30642-135">Los usuarios pueden dejar de acumular puntos mientras buscan con Búsqueda de Microsoft borrando sus cookies.</span><span class="sxs-lookup"><span data-stu-id="30642-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span>
