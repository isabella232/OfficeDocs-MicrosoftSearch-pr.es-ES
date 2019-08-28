---
title: Preguntas más frecuentes
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 10/19/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: cd3ee09d-58ab-4b8a-8822-fa11a1399672
ROBOTS: NoIndex
description: Obtenga respuestas a las preguntas más frecuentes acerca de la búsqueda empresarial y Microsoft Search
ms.openlocfilehash: 3b30980c76915405767381fb3b6397468bdd1b68
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639508"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="e384c-103">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="e384c-103">Frequently asked questions</span></span>

<span data-ttu-id="e384c-104">Aquí tiene una lista de las preguntas más frecuentes.</span><span class="sxs-lookup"><span data-stu-id="e384c-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="e384c-105">¿No encuentra aquí una respuesta a su pregunta?</span><span class="sxs-lookup"><span data-stu-id="e384c-105">Don't see your question answered here?</span></span> <span data-ttu-id="e384c-106">Formule su pregunta en el comentario de este artículo.</span><span class="sxs-lookup"><span data-stu-id="e384c-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="e384c-107">¿Se ofrece la comprensión de consultas avanzadas?</span><span class="sxs-lookup"><span data-stu-id="e384c-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="e384c-p102">Sí, Microsoft Search analiza el objetivo de la consulta de frases más grandes. Esta característica usa inteligencia artificial para aprender frases superfluas y comunes que los usuarios agregan a sus consultas y que no afectan a su intención de búsqueda. Por ejemplo, cuando un usuario busca "más información sobre cómo cambiar la contraseña" se extraen las palabras menos importantes de la consulta y se busca con las palabras relevantes como "Cambiar contraseña".</span><span class="sxs-lookup"><span data-stu-id="e384c-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for 'tell me more about how to change my password please' we extract the less important words from the query and trigger based on the relevant ones like 'change password.'</span></span>
  
<span data-ttu-id="e384c-111">Esta característica no reemplazará el conjunto de palabras clave en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="e384c-111">This feature will not override keywords set in the Admin portal.</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="e384c-112">¿Puedo buscar archivos locales?</span><span class="sxs-lookup"><span data-stu-id="e384c-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="e384c-113">Sí.</span><span class="sxs-lookup"><span data-stu-id="e384c-113">Yes.</span></span> <span data-ttu-id="e384c-114">Puede buscar archivos locales de SharePoint si tiene una implementación híbrida de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e384c-114">You can search on-premises SharePoint files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="e384c-115">¿Cómo hago que Bing sea el motor de búsqueda predeterminado para los usuarios de mi organización?</span><span class="sxs-lookup"><span data-stu-id="e384c-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="e384c-116">Estas instrucciones le guiarán para establecer de forma predeterminada el motor de búsqueda, la página principal y el explorador que ofrezcan a sus usuarios la mejor experiencia con Microsoft Search en Bing:</span><span class="sxs-lookup"><span data-stu-id="e384c-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in Bing:</span></span>

- [<span data-ttu-id="e384c-117">Establezca Edge como el navegador predeterminado</span><span class="sxs-lookup"><span data-stu-id="e384c-117">Set Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="e384c-118">Establezca Bing como el motor de búsqueda predeterminado</span><span class="sxs-lookup"><span data-stu-id="e384c-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="e384c-119">Establezca Bing.com como la página principal de la empresa</span><span class="sxs-lookup"><span data-stu-id="e384c-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="e384c-120">¿Cómo se protegen mis resultados de búsqueda?</span><span class="sxs-lookup"><span data-stu-id="e384c-120">How are my search results protected?</span></span>

<span data-ttu-id="e384c-121">Para poder acceder a los resultados de la nube de confianza, se requiere la autenticación de Azure Active Directory (ADD).</span><span class="sxs-lookup"><span data-stu-id="e384c-121">We require Azure Active Directory (AAD) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="e384c-122">Los usuarios autenticados solo verán el contenido al que tengan acceso.</span><span class="sxs-lookup"><span data-stu-id="e384c-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="e384c-123">Las consultas de búsqueda son no identificables y los registros se separan del tráfico de búsqueda público de Bing.</span><span class="sxs-lookup"><span data-stu-id="e384c-123">Search queries are de-identified and logs are separated from public Bing search traffic.</span></span> <span data-ttu-id="e384c-124">Este nivel de protección no está disponible en ningún otro lugar del sector.</span><span class="sxs-lookup"><span data-stu-id="e384c-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="e384c-125">¿Puedo buscar en organizaciones federadas?</span><span class="sxs-lookup"><span data-stu-id="e384c-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="e384c-126">No.</span><span class="sxs-lookup"><span data-stu-id="e384c-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="e384c-127">¿Dónde puedo obtener información sobre los niveles o categorías de cumplimiento de Office 365 y Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e384c-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="e384c-128">Encontrará más detalles en el [Marco de cumplimiento para las regulaciones y estándares del sector](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (descargar PDF).</span><span class="sxs-lookup"><span data-stu-id="e384c-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>