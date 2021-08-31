---
title: Seguridad y privacidad para Búsqueda de Microsoft en Bing
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Proteja los datos y los usuarios finales de su empresa mientras proporciona información a los usuarios autorizados con Búsqueda de Microsoft en Bing
ms.openlocfilehash: bf3629b2508c705d19e3b7b772c6f3672063a6f1
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701862"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Seguridad y privacidad para Búsqueda de Microsoft en Bing

Con medidas de privacidad y seguridad mejoradas, Búsqueda de Microsoft en Bing ayuda a proteger los datos de los usuarios y del lugar de trabajo.

## <a name="secure-by-default"></a>Seguridad predeterminada

Búsqueda de Microsoft en Bing las solicitudes se realizan a través de HTTPS. La conexión está cifrada de un extremo a otro para mejorar la seguridad.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticación y autorización con Azure Active Directory

La autenticación Búsqueda de Microsoft en Bing está vinculada a Azure Active Directory. Cuando Búsqueda de Microsoft usuarios vayan a Bing, el encabezado Bing mostrará las opciones de inicio de sesión de una cuenta microsoft, así como una cuenta laboral o educativa. Si Bing puede determinar si un usuario es un participante elegible, los usuarios pueden ir a la página Explorar [Búsqueda de Microsoft,](https://www.bing.com/business/explore) donde se redirigirán automáticamente a la página de inicio de sesión de la organización.

Los usuarios pueden acceder a Microsoft Search solo a través de una cuenta profesional o educativa. Deben iniciar sesión con las mismas credenciales que usan para acceder a los servicios de Office 365, como Outlook o SharePoint. No puede usarse una cuenta personal de Microsoft para iniciar sesión en Microsoft Search.

## <a name="single-sign-on"></a>Inicio de sesión único

Si un usuario ya está autenticado con su cuenta profesional o educativa en otro servicio, como Outlook o SharePoint, se iniciará sesión automáticamente en la misma cuenta profesional o educativa cuando vaya a Bing en el mismo explorador. Además, cuando el usuario cierra sesión en su cuenta laboral o educativa, se cierra la sesión automáticamente de otros servicios de Microsoft Office en el mismo explorador.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Se comunica con la nube de Microsoft desde el explorador

Cuando un usuario inicia sesión con su cuenta laboral o educativa, Bing descargará las bibliotecas de cliente necesarias en el explorador para habilitar Búsqueda de Microsoft resultados. Después, cuando buscan, el código del explorador llama a la Office 365 nube para obtener resultados de trabajo. Para ello, Búsqueda de Microsoft una API dedicada que se opera de acuerdo con los objetivos de control de SSAE 18 SOC2 Tipo 1. Esto significa que los resultados del trabajo y los datos de trabajo no fluyen Bing través de sistemas que están sujetos Bing objetivos de control de procesamiento de datos menos estrictos que los propios resultados de trabajo están sujetos a cuando se procesan en Office 365 Core Online Services.
  
## <a name="permissions"></a>Permisos

Los resultados de trabajo recuperados de cargas de trabajo de Office 365, como SharePoint y OneDrive para la Empresa, tienen restricciones re seguridad aplicadas en el origen. Los usuarios no pueden ver recursos como documentos de Word o presentaciones de PowerPoint que no puedan ver y acceder a través de Office 365. Solo pueden ver sus propios archivos y archivos que el autor ha compartido con ellos explícita o implícitamente (a través de la pertenencia a un grupo, por ejemplo) en SharePoint.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Búsqueda de Microsoft en Bing protege las búsquedas en el lugar de trabajo

Cuando un usuario escribe una consulta de búsqueda en Búsqueda de Microsoft en Bing, se producen dos solicitudes de búsqueda simultáneas:

- Una búsqueda de los recursos internos de la organización.
- Una búsqueda independiente de resultados públicos de Bing.com.

Dado que las búsquedas en el lugar de trabajo pueden ser confidenciales, Búsqueda de Microsoft ha implementado un conjunto de medidas de confianza que describen cómo se controla la búsqueda independiente de resultados públicos de Bing.com.

### <a name="logging"></a>Registro

- Todos los registros Bing.com de búsqueda que pertenecen a Búsqueda de Microsoft en Bing de tráfico se desasocian de la identidad del lugar de trabajo.
- Si se cumple un conjunto de restricciones o umbrales de frecuencia que nos dan confianza de que la consulta no es específica de una organización determinada, la consulta se tratará como se describe en la sección Búsqueda e inteligencia artificial de la declaración de privacidad [.](https://privacy.microsoft.com/privacystatement) Por ejemplo, estas consultas se usarán para modelar y entrenar características públicas, como autosuggest o búsquedas relacionadas.
- Las consultas que no cumplan el conjunto de restricciones o umbrales de frecuencia se almacenarán por separado del tráfico público que no sea de Búsqueda de Microsoft.

### <a name="advertising"></a>Publicidad

La publicidad mostrada en Bing.com en relación con las búsquedas en el lugar de trabajo está relacionada únicamente con el contenido de las consultas de búsqueda. Los anuncios nunca se dirigen a los usuarios en función de su identidad laboral.

## <a name="gdpr"></a>RGPD

La entrada de blog del 21 de mayo de [2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) de Microsoft refleja nuestro compromiso con el cumplimiento del RGPD y cómo Microsoft ayuda a las empresas y organizaciones con sus propias obligaciones de cumplimiento del RGPD. Encontrará más detalles en las preguntas más frecuentes del Centro [de confianza de](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)Microsoft .

Búsqueda de Microsoft las consultas ejecutadas en los recursos internos de un cliente y los resultados devueltos se consideran datos del cliente y, como tales, también cumplen los compromisos del procesador descritos en el artículo 28, tal como se refleja en las preguntas más frecuentes del Centro de confianza [.](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs) Con respecto a las consultas de Búsqueda de Microsoft que se van a Bing público, Microsoft cumple con sus obligaciones del RGPD como responsable del tratamiento de datos.
