---
title: Seguridad y privacidad de Microsoft Search en Bing
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
description: Proteger los datos de la compañía y los usuarios finales mientras se proporciona información a los usuarios autorizados con Microsoft Search en Bing
ms.openlocfilehash: 1cc00a3b14b1918903c9aa34a24f13b1761b64b6
ms.sourcegitcommit: 5946fe6aad2331c023bedda8faf826c0248651f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41711760"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Seguridad y privacidad de Microsoft Search en Bing

Con las medidas de privacidad y seguridad mejoradas, Microsoft Search en Bing ayuda a proteger los datos de los usuarios y el área de trabajo.

## <a name="secure-by-default"></a>Seguro por defecto

Las solicitudes de Microsoft Search en Bing se realizan a través de HTTPS. La conexión está cifrada de un extremo a otro para mejorar la seguridad.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticación y autorización con Azure Active Directory

La autenticación de Microsoft Search en Bing está ligada a Azure Active Directory. Cuando los usuarios de Microsoft Search van a Bing, el encabezado de Bing mostrará opciones de inicio de sesión para una cuenta de Microsoft, así como una cuenta profesional o educativa. Si Bing no puede determinar si un usuario es un participante elegible, los usuarios pueden ir a la página [explorar Microsoft Search](https://www.bing.com/business/explore) , donde se redirigirán automáticamente a la página de inicio de sesión de su organización.

Los usuarios pueden acceder a Microsoft Search solo a través de una cuenta profesional o educativa. Deben iniciar sesión con las mismas credenciales que usan para acceder a los servicios de Office 365, como Outlook o SharePoint. No puede usarse una cuenta personal de Microsoft para iniciar sesión en Microsoft Search.

## <a name="single-sign-on"></a>Inicio de sesión único

Si un usuario ya está autenticado con su cuenta profesional o educativa en otro servicio, como Outlook o SharePoint, se iniciará sesión automáticamente en la misma cuenta profesional o educativa cuando vaya a Bing en el mismo explorador. Además, cuando el usuario cierra sesión en su cuenta profesional o educativa, la sesión se cerrará automáticamente desde otros servicios de Microsoft Office en el mismo explorador.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Se comunica con la nube de Microsoft desde el explorador

Cuando un usuario inicia sesión con su cuenta profesional o educativa, Bing descarga las bibliotecas de cliente necesarias en el explorador para habilitar los resultados de búsqueda de Microsoft. A continuación, cuando busca, el código en el explorador llama a la nube de Office 365 para obtener resultados de trabajo. Para ello, Microsoft Search usa una API dedicada que funciona de acuerdo con los objetivos de control de SSAE 18 SOC2 Type 1. Esto significa que los resultados de trabajo y los datos de trabajo no fluyen a través de sistemas de Bing que están sujetos a objetivos de control de procesamiento de datos menos estrictos que los propios resultados de trabajo están sujetos a ser procesados en los servicios en línea de Office 365 Core.
  
## <a name="permissions"></a>Permisos

Los resultados de trabajo recuperados de cargas de trabajo de Office 365, como SharePoint y OneDrive para la Empresa, tienen restricciones re seguridad aplicadas en el origen. Los usuarios no pueden ver recursos como documentos de Word o presentaciones de PowerPoint que no puedan ver y acceder a través de Office 365. Solo pueden ver sus propios archivos y archivos que el autor ha compartido con ellos explícita o implícitamente (a través de la pertenencia a un grupo, por ejemplo) en SharePoint.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Microsoft Search en Bing protege las búsquedas en el lugar de trabajo

Cuando un usuario escribe una consulta de búsqueda en Microsoft Search en Bing, se producen dos solicitudes de búsqueda simultáneas:

- Una búsqueda de los recursos internos de la organización.
- Una búsqueda independiente de resultados públicos de Bing.com.

Como las búsquedas en el área de trabajo pueden ser confidenciales, Microsoft Search ha implementado un conjunto de medidas de confianza que describen cómo se controla la búsqueda independiente de resultados públicos de Bing.com.

### <a name="logging"></a>Registro

- Todos los registros de búsqueda de Bing.com que pertenecen a Microsoft Search en el tráfico de Bing no se asocian a la identidad del lugar de trabajo.
- Si se alcanza un conjunto de restricciones o umbrales de frecuencia que nos dan confianza de que la consulta no es específica de una organización concreta, la consulta se tratará como se describe en la sección búsqueda e inteligencia artificial de la [declaración de privacidad](https://privacy.microsoft.com/privacystatement). Por ejemplo, estas consultas se usarán para modelar y entrenar características públicas, como la sugerencia autosugerir o las búsquedas relacionadas.
- Las consultas que no cumplan el conjunto de restricciones o umbrales de frecuencia se almacenarán por separado del tráfico público que no sea de Búsqueda de Microsoft.

### <a name="advertising"></a>Publicidad

La publicidad que se muestra en Bing.com en relación con las búsquedas en el área de trabajo está relacionada únicamente con el contenido de las consultas de búsqueda. Los anuncios nunca se dirigen a los usuarios en función de su identidad laboral.

## <a name="gdpr"></a>RGPD

La [publicación de blog de mayo 21, 2018,](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) de Microsoft refleja nuestro compromiso de RGPD cumplimiento y de la forma en que Microsoft ayuda a los negocios y a las organizaciones con sus propias obligaciones de cumplimiento RGPD. Puede encontrar más información en las [preguntas más frecuentes del centro de confianza](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)de Microsoft.

Las consultas de Microsoft Search que se ejecutan con los recursos internos de un cliente y los resultados devueltos se consideran datos de cliente y, por lo tanto, también cumplen los compromisos de procesador descritos en el artículo 28, tal como se refleja en las [preguntas más frecuentes del centro de confianza](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs). Con respecto a las consultas de Microsoft Search que van a Bing públicos, Microsoft cumple con sus obligaciones RGPD como un controlador de datos.
