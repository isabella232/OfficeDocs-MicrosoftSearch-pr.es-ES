---
title: Seguridad de Microsoft Search
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
description: Proteja los datos empresariales y a los usuarios mientras proporciona información a los usuarios autorizados con Microsoft Search
ms.openlocfilehash: b7b62173dc61d271a4953adbf20a6cf48b122694
ms.sourcegitcommit: 4eeb78066fd13e906daed3add003398bd9d0f6ca
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2019
ms.locfileid: "35917573"
---
# <a name="security-for-microsoft-search"></a>Seguridad de Microsoft Search

Con la seguridad de nivel empresarial, Microsoft Search siempre mantiene los usuarios y los datos protegidos.


## <a name="secure-by-default"></a>Seguro por defecto

Microsoft Search siempre garantiza que las solicitudes se realizan a través de HTTPS. Esta protección garantiza que la conexión está cifrada de un extremo a otro para mejorar la seguridad.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticación y autorización con Azure Active Directory

La autenticación de Microsoft Search está ligada a Azure Active Directory. Cuando los usuarios de Microsoft Search acceden a Bing, el encabezado de Bing mostrará las opciones de inicio de sesión para una cuenta de Microsoft así como para una cuenta profesional o educativa. Si Bing no puede determinar si un usuario es un participante válido, los usuarios pueden ir a la página [Explorar Microsoft Search](https://www.bing.com/business/explore), donde se les redirigirá automáticamente a la página de inicio de sesión de su organización.
  
Los usuarios pueden acceder a Microsoft Search solo a través de una cuenta profesional o educativa. Deben iniciar sesión con las mismas credenciales que usan para acceder a los servicios de Office 365, como Outlook o SharePoint. No puede usarse una cuenta personal de Microsoft para iniciar sesión en Microsoft Search.
  
Los usuarios no pueden iniciar sesión en Bing con una cuenta de Microsoft y una cuenta profesional o educativa al mismo tiempo.
  
## <a name="single-sign-on"></a>Inicio de sesión único

Si un usuario ya se ha autenticado con su cuenta profesional o educativa en otro servicio, como Outlook o SharePoint, se iniciará sesión automáticamente en Microsoft Search cuando vayan a Bing en el mismo explorador. Además, cuando el usuario cierre sesión en Microsoft Search, se cerrará sesión automáticamente en otros servicios en el mismo explorador.
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>Comunica con la nube de confianza desde el explorador

Cuando un usuario inicia sesión con su cuenta de trabajo o educativa, Bing descargará las bibliotecas del cliente necesarias en el explorador para permitir los resultados de Microsoft Search. Después, cuando busquen, el código del explorador llama a la nube de Office 365 para obtener resultados del trabajo. Para ello, Microsoft Search usa una API dedicada que cumple con el nivel C (SOC2 tipo 1) de acuerdo con las [Marco de cumplimiento para las regulaciones y estándares del sector](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) de Office 365 (descargar PDF). Esto significa que los resultados y los datos de trabajo nunca fluyen a través de sistemas de Bing no compatibles. 
  
## <a name="permissions"></a>Permisos

Los resultados de trabajo recuperados de cargas de trabajo de Office 365, como SharePoint y OneDrive para la Empresa, tienen restricciones re seguridad aplicadas en el origen. Los usuarios no pueden ver recursos como documentos de Word o presentaciones de PowerPoint que no puedan ver y acceder a través de Office 365. Solo pueden ver sus propios archivos y archivos que el autor ha compartido con ellos explícita o implícitamente (a través de la pertenencia a un grupo, por ejemplo) en SharePoint.
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Protege las consultas de usuario de la parte pública de Bing

Como las búsquedas relacionadas con el trabajo pueden ser confidenciales, Microsoft Search ha implementado un conjunto de medidas de confianza sobre cómo se manejan por parte del elemento de resultados web públicos de Bing.
  
Independientemente de si una consulta de usuario contiene uno o varios resultados de trabajo en la respuesta devuelta, se toman las siguientes medidas:
  
- Registro 
  - Todos los registros de búsqueda correspondientes al tráfico de Microsoft Search se anonimizan. Se conservan durante 18 meses.
  - Las consultas almacenadas en estos registros del sistema solo se usarán para modelar y probar características públicas como sugerencias automáticas u otras funciones relativas a búsquedas para resultados cuando se cumplan una serie de restricciones y umbrales de frecuencia, a fin de proporcionarnos la seguridad de que estas consultas son comunes y no específicas para una organización concreta. La consulta debe aparecer un número de veces significativo en datos correlativos que no procedan de usuarios de Microsoft Search y no debe activar únicamente resultados de búsqueda corporativos. Las consultas que no cumplan estos requisitos se almacenarán separadas del tráfico público no relativo a Microsoft Search.
  - El acceso restringido se administra a través de diferentes mecanismos seguros, incluyendo grupos de seguridad y otras capas dentro del sistema de ingeniería.
- Historial de búsqueda    
  - Cuando haya iniciado sesión con una cuenta profesional o educativa, el historial de búsqueda de un usuario no estará disponible en otros equipos o dispositivos.
 
- Publicidad   
  - Las consultas de búsqueda empresariales nunca se comparten o sugieren a los anunciantes.
  - Los anuncios nunca están dirigidos a un usuario en función de su identidad de trabajo u organización.
    
## <a name="gdpr"></a>RGPD

La [entrada de blog del 21 de mayo de 2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) de Microsoft refleja nuestro compromiso con el cumplimiento de RGPD y cómo Microsoft ayuda a las empresas y organizaciones con sus propias obligaciones de cumplimiento RGPD. Puede encontrar detalles adicionales en las [preguntas más frecuentes del centro de confianza](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs) de Microsoft. Las consultas de Microsoft Search que funcionan con datos de clientes de la organización dentro de los servicios en línea también cumplen con los compromisos del procesador indicados en el artículo 28 como se refleja en las [preguntas más frecuentes del centro de confianza](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Con respecto a las consultas de Microsoft Search que vayan a la parte pública de Bing, Microsoft es un controlador de datos y ha implementado medidas para anonimizar las consultas como se describe en la RGPD.