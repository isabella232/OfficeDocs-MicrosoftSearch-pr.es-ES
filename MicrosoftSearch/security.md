---
title: Seguridad para la búsqueda de Microsoft
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: Proteger los datos de la empresa y los usuarios de ofrecer información a los usuarios autorizados con Microsoft Search
ms.openlocfilehash: 65cf1d49e32edbb8061a06f8da7ba644c2145e24
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379281"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="c32dd-103">Seguridad para la búsqueda de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c32dd-103">Security for Microsoft Search</span></span>

<span data-ttu-id="c32dd-104">Con la seguridad de nivel empresarial, Microsoft Search siempre mantiene los usuarios y los datos protegidos.</span><span class="sxs-lookup"><span data-stu-id="c32dd-104">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>
  
## <a name="secure-by-default"></a><span data-ttu-id="c32dd-105">Seguro de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="c32dd-105">Secure by default</span></span>

<span data-ttu-id="c32dd-p101">Microsoft Search garantiza siempre se realizan solicitudes a través de HTTPS. Esta medida de seguridad garantiza que la conexión está cifrada-to-end para mejorar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="c32dd-p101">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="c32dd-108">Autenticación y autorización con Active Directory de Azure</span><span class="sxs-lookup"><span data-stu-id="c32dd-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="c32dd-p102">Autenticación de Microsoft Search está vinculada a Azure Active Directory. Cuando los usuarios de Microsoft Search van a Bing, el encabezado mostrará las opciones de inicio de sesión para una cuenta de Microsoft como de Bing así como un trabajo o escuela cuenta. Si Bing no puede determinar si un usuario es un participante elegible, los usuarios pueden ir a la página de [Búsqueda de Microsoft explorar](https://www.bing.com/business/explore) , donde se le redirige automáticamente a la página de inicio de sesión de la organización.</span><span class="sxs-lookup"><span data-stu-id="c32dd-p102">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span> 
  
<span data-ttu-id="c32dd-p103">Los usuarios pueden tener acceso a Microsoft Search sólo a través de una cuenta de trabajo o escuela. Que se necesitan iniciar sesión con las mismas credenciales que se usan para tener acceso a servicios de Office 365, como SharePoint o Outlook. No se puede usar una cuenta Microsoft personal para iniciar sesión en Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="c32dd-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="c32dd-115">Los usuarios no pueden iniciar sesión a Bing con una cuenta de Microsoft y una cuenta de trabajo o escuela al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c32dd-115">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="c32dd-116">Inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="c32dd-116">Single sign-on</span></span>

<span data-ttu-id="c32dd-p104">Si un usuario se ha autenticado con su cuenta de trabajo o escuela en otro servicio, como Outlook o SharePoint, mantendrá automáticamente una sesión para Microsoft Search cuando vayan a Bing en el mismo explorador. Además, cuando el usuario inicia sesión fuera de Microsoft Search, podrá automáticamente la sesión de otros servicios en el mismo explorador.</span><span class="sxs-lookup"><span data-stu-id="c32dd-p104">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="c32dd-119">Se comunica con la nube de confianza desde el explorador</span><span class="sxs-lookup"><span data-stu-id="c32dd-119">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="c32dd-p105">Cuando un usuario inicia sesión con su trabajo o cuenta de escuela, Bing descargará las bibliotecas de cliente necesarios en el explorador para habilitar los resultados de Microsoft Search. A continuación, que busquen, el código en el explorador llama a la nube de Office 365 para obtener los resultados del trabajo. Para ello, Microsoft Search utiliza una API dedicada que es C niveles (SOC2 tipo 1) compatibles con conformidad con el [Marco de cumplimiento de los estándares del sector y las normativas](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) de Office 365 (descarga PDF). Esto significa que los resultados del trabajo y datos de trabajo nunca fluyen a través de sistemas de Bing que no sean conformes.</span><span class="sxs-lookup"><span data-stu-id="c32dd-p105">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="c32dd-124">Permisos</span><span class="sxs-lookup"><span data-stu-id="c32dd-124">Permissions</span></span>

<span data-ttu-id="c32dd-p106">Resultados de trabajo recuperados de las cargas de trabajo de Office 365, como SharePoint y OneDrive para la empresa son seguridad restricciones en el origen. Los usuarios no podrán ver los recursos, como documentos de Word o presentaciones de PowerPoint que no se pueden ver y obtener acceso a través de Office 365. Sólo puede ver sus propios archivos y archivos que se han compartido con ellos por el autor de forma explícita o implícita (a través de la pertenencia a un grupo, por ejemplo) en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c32dd-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="c32dd-128">Protege las consultas de usuario desde la parte pública de Bing</span><span class="sxs-lookup"><span data-stu-id="c32dd-128">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="c32dd-129">Debido a que las búsquedas relacionadas con el trabajo pueden ser confidenciales, Microsoft Search ha implementado un conjunto de medidas de confianza para cómo estos se controlan mediante el elemento de resultados web públicos de Bing.</span><span class="sxs-lookup"><span data-stu-id="c32dd-129">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="c32dd-130">Independientemente de si una consulta de usuario contiene uno o más resultados de trabajo en la respuesta devuelta, se toman las medidas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c32dd-130">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="c32dd-131">Registro</span><span class="sxs-lookup"><span data-stu-id="c32dd-131">Logging</span></span>
    
  - <span data-ttu-id="c32dd-p107">Todos los registros de búsqueda perteneciente al tráfico de Microsoft Search se identifican desaprovisionamiento y se almacena por separado del tráfico público, que no sean Microsoft Search. Sí están conservan de 18 meses y acceso está limitado únicamente con fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="c32dd-p107">All search logs pertaining to Microsoft Search traffic are de-identified and stored separately from public, non-Microsoft Search traffic. They're retained for 18 months, and access is restricted for debugging purposes only.</span></span>
    
  - <span data-ttu-id="c32dd-134">Las consultas de estos registros no se usan para modelo o tren públicas características tales como autosuggest o relacionadas con las búsquedas para la web pública.</span><span class="sxs-lookup"><span data-stu-id="c32dd-134">The queries in these logs are not used to model or train public features such as autosuggest or related searches for the public web.</span></span>
    
  - <span data-ttu-id="c32dd-135">Acceso restringido se administra a través de diversos mecanismos seguros, incluidos los grupos de seguridad y otras capas dentro del sistema de ingeniería.</span><span class="sxs-lookup"><span data-stu-id="c32dd-135">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
    
- <span data-ttu-id="c32dd-136">Historial de búsqueda</span><span class="sxs-lookup"><span data-stu-id="c32dd-136">Search history</span></span>
    
  - <span data-ttu-id="c32dd-137">Cuando inicia sesión con una cuenta de trabajo o escuela, buscar en el historial de un usuario no estará disponible en otros equipos o dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c32dd-137">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
    
- <span data-ttu-id="c32dd-138">Publicidad</span><span class="sxs-lookup"><span data-stu-id="c32dd-138">Advertising</span></span>
    
  - <span data-ttu-id="c32dd-139">Las consultas de búsqueda de Enterprise nunca se comparte con ni se sugiere a los anunciantes.</span><span class="sxs-lookup"><span data-stu-id="c32dd-139">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
    
  - <span data-ttu-id="c32dd-140">Los registros de los anuncios de búsqueda perteneciente a Microsoft Search se almacenan por separado del tráfico público.</span><span class="sxs-lookup"><span data-stu-id="c32dd-140">Search Ads logs pertaining to Microsoft Search are stored separately from public traffic.</span></span>
    
  - <span data-ttu-id="c32dd-141">ADS nunca destinados a un usuario en función de su identidad de trabajo u organización.</span><span class="sxs-lookup"><span data-stu-id="c32dd-141">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="c32dd-142">RGPD</span><span class="sxs-lookup"><span data-stu-id="c32dd-142">GDPR</span></span>

<span data-ttu-id="c32dd-p108">El [21 de mayo de 2018, la entrada de blog](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) de Microsoft refleja nuestro compromiso de cumplimiento de GDPR y cómo Microsoft ayuda a las empresas y las organizaciones con sus propios obligaciones de cumplimiento de normas de GDPR. Puede encontrar detalles adicionales en las [Preguntas más frecuentes del centro de confianza](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)de Microsoft. Las consultas de Microsoft Search que funcionan con los datos de cliente de los clientes organizativos dentro de los servicios en línea también va a satisfacer los compromisos de procesador que se describen en el artículo 28 tal como se refleja en las [Preguntas más frecuentes del centro de confianza](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Con respecto a las consultas de Microsoft Search que vaya a Bing pública, Microsoft es un controlador de datos y ha implementado medidas para desaprovisionamiento identificar las consultas, tal como se describe en GDPR.</span><span class="sxs-lookup"><span data-stu-id="c32dd-p108">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>


