---
title: Seguridad para la búsqueda de Microsoft
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: Proteger los datos de la empresa y los usuarios de ofrecer información a los usuarios autorizados con Microsoft Search
ms.openlocfilehash: 5f59e0e2969ef829d7c14b07ecb47d645cc63013
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612525"
---
# <a name="security-for-microsoft-search"></a>Seguridad para la búsqueda de Microsoft

Con la seguridad de nivel empresarial, Microsoft Search siempre mantiene los usuarios y los datos protegidos.
  
## <a name="secure-by-default"></a>Seguro de forma predeterminada

Microsoft Search garantiza siempre se realizan solicitudes a través de HTTPS. Esta medida de seguridad garantiza que la conexión está cifrada-to-end para mejorar la seguridad.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticación y autorización con Active Directory de Azure

Autenticación de Microsoft Search está vinculada a Azure Active Directory. Cuando los usuarios de Microsoft Search van a Bing, el encabezado mostrará las opciones de inicio de sesión para una cuenta de Microsoft como de Bing así como un trabajo o escuela cuenta. Si Bing no puede determinar si un usuario es un participante elegible, los usuarios pueden ir a la página de [Búsqueda de Microsoft explorar](https://www.bing.com/business/explore) , donde se le redirige automáticamente a la página de inicio de sesión de la organización. 
  
Los usuarios pueden tener acceso a Microsoft Search sólo a través de una cuenta de trabajo o escuela. Que se necesitan iniciar sesión con las mismas credenciales que se usan para tener acceso a servicios de Office 365, como SharePoint o Outlook. No se puede usar una cuenta Microsoft personal para iniciar sesión en Microsoft Search.
  
Los usuarios no pueden iniciar sesión a Bing con una cuenta de Microsoft y una cuenta de trabajo o escuela al mismo tiempo.
  
## <a name="single-sign-on"></a>Inicio de sesión único

Si un usuario se ha autenticado con su cuenta de trabajo o escuela en otro servicio, como Outlook o SharePoint, mantendrá automáticamente una sesión para Microsoft Search cuando vayan a Bing en el mismo explorador. Además, cuando el usuario inicia sesión fuera de Microsoft Search, podrá automáticamente la sesión de otros servicios en el mismo explorador.
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>Se comunica con la nube de confianza desde el explorador

Cuando un usuario inicia sesión con su trabajo o cuenta de escuela, Bing descargará las bibliotecas de cliente necesarios en el explorador para habilitar los resultados de Microsoft Search. A continuación, que busquen, el código en el explorador llama a la nube de Office 365 para obtener los resultados del trabajo. Para ello, Microsoft Search utiliza una API dedicada que es C niveles (SOC2 tipo 1) compatibles con conformidad con el [Marco de cumplimiento de los estándares del sector y las normativas](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) de Office 365 (descarga PDF). Esto significa que los resultados del trabajo y datos de trabajo nunca fluyen a través de sistemas de Bing que no sean conformes. 
  
## <a name="permissions"></a>Permisos

Resultados de trabajo recuperados de las cargas de trabajo de Office 365, como SharePoint y OneDrive para la empresa son seguridad restricciones en el origen. Los usuarios no podrán ver los recursos, como documentos de Word o presentaciones de PowerPoint que no se pueden ver y obtener acceso a través de Office 365. Sólo puede ver sus propios archivos y archivos que se han compartido con ellos por el autor de forma explícita o implícita (a través de la pertenencia a un grupo, por ejemplo) en SharePoint.
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Protege las consultas de usuario desde la parte pública de Bing

Debido a que las búsquedas relacionadas con el trabajo pueden ser confidenciales, Microsoft Search ha implementado un conjunto de medidas de confianza para cómo estos se controlan mediante el elemento de resultados web públicos de Bing.
  
Independientemente de si una consulta de usuario contiene uno o más resultados de trabajo en la respuesta devuelta, se toman las medidas siguientes:
  
- Registro
    
  - Todos los registros de búsqueda perteneciente al tráfico de Microsoft Search se identifican desaprovisionamiento y se almacena por separado del tráfico público, que no sean Microsoft Search. Sí están conservan de 18 meses y acceso está limitado únicamente con fines de depuración.
    
  - Las consultas de estos registros no se usan para modelo o tren públicas características tales como autosuggest o relacionadas con las búsquedas para la web pública.
    
  - Acceso restringido se administra a través de diversos mecanismos seguros, incluidos los grupos de seguridad y otras capas dentro del sistema de ingeniería.
    
- Historial de búsqueda
    
  - Cuando inicia sesión con una cuenta de trabajo o escuela, buscar en el historial de un usuario no estará disponible en otros equipos o dispositivos.
    
- Publicidad
    
  - Las consultas de búsqueda de Enterprise nunca se comparte con ni se sugiere a los anunciantes.
    
  - Los registros de los anuncios de búsqueda perteneciente a Microsoft Search se almacenan por separado del tráfico público.
    
  - ADS nunca destinados a un usuario en función de su identidad de trabajo u organización.
    
## <a name="gdpr"></a>RGPD

El [21 de mayo de 2018, la entrada de blog](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) de Microsoft refleja nuestro compromiso de cumplimiento de GDPR y cómo Microsoft ayuda a las empresas y las organizaciones con sus propios obligaciones de cumplimiento de normas de GDPR. Puede encontrar detalles adicionales en las [Preguntas más frecuentes del centro de confianza](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)de Microsoft. Las consultas de Microsoft Search que funcionan con los datos de cliente de los clientes organizativos dentro de los servicios en línea también va a satisfacer los compromisos de procesador que se describen en el artículo 28 tal como se refleja en las [Preguntas más frecuentes del centro de confianza](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Con respecto a las consultas de Microsoft Search que vaya a Bing pública, Microsoft es un controlador de datos y ha implementado medidas para desaprovisionamiento identificar las consultas, tal como se describe en GDPR.


