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
# <a name="frequently-asked-questions"></a>Preguntas más frecuentes

Aquí tiene una lista de las preguntas más frecuentes.

> [!TIP]
> ¿No encuentra aquí una respuesta a su pregunta? Formule su pregunta en el comentario de este artículo.

## <a name="is-advanced-query-understanding-supported"></a>¿Se ofrece la comprensión de consultas avanzadas?

Sí, Microsoft Search analiza el intento de consulta de frases más grandes. Esta característica utiliza AI para aprender frases superfluas comunes que los usuarios agregan a sus consultas que no afectan su intento de búsqueda. Por ejemplo, cuando un usuario busca información *más información sobre cómo cambiar mi contraseña*, extraemos las palabras menos importantes de la consulta y del desencadenador en función de los aspectos relevantes como *Cambiar contraseña*.
  
Esta característica no reemplaza las palabras clave definidas en el [centro de administración](https://admin.microsoft.com)de Microsoft 365.
  
## <a name="can-you-search-for-files-on-premises"></a>¿Puedo buscar archivos locales?

Sí. Puede buscar en los archivos de [SharePoint](http://sharepoint.com/) locales si tiene una implementación híbrida de SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>¿Cómo hago que Bing sea el motor de búsqueda predeterminado para los usuarios de mi organización?

Estas son las instrucciones para configurar el motor de búsqueda predeterminado, la Página principal predeterminada y el explorador predeterminado para proporcionar a los usuarios la mejor experiencia con Microsoft Search en [Bing](https://Bing.com):

- [Establecer Microsoft Edge como explorador predeterminado](set-default-browser.md)
- [Establezca Bing como el motor de búsqueda predeterminado](set-default-search-engine.md)
- [Establezca Bing.com como la página principal de la empresa](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>¿Cómo se protegen mis resultados de búsqueda?

Requerimos que la autenticación de [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) obtenga acceso a los resultados de la nube de confianza. Los usuarios autenticados solo verán el contenido al que tengan acceso. Las consultas de búsqueda se identifican y los registros se separan del tráfico de búsqueda de [Bing](https://Bing.com) público. Este nivel de protección no está disponible en ningún otro lugar del sector.

## <a name="can-i-search-across-federated-organizations"></a>¿Puedo buscar en organizaciones federadas?

No.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>¿Dónde puedo obtener información sobre la seguridad, el cumplimiento y la privacidad de Office 365?

Puede encontrar información detallada en las [páginas del centro de confianza para Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>¿Los usuarios pueden ganar puntos de Microsoft Rewards con su cuenta profesional o educativa?

Búsqueda de Microsoft necesita que los usuarios de la empresa inicien sesión con una cuenta profesional o educativa. Sin embargo, los usuarios no podrán unirse ni iniciar sesión en el programa Microsoft Rewards con esas cuentas. Sin embargo, hay una instancia en la que un usuario de la empresa puede ver puntos de recompensas. Esto puede suceder cuando un usuario de Búsqueda de Microsoft tiene una cuenta de recompensas que se creó con una [cuenta de Microsoft](https://www.microsoft.com/welcome?rtc=1). (La dirección de correo electrónico asociada a una cuenta de Microsoft puede ser de Outlook.com, Hotmail.com, Gmail, Yahoo u otros proveedores). Si los usuarios inician sesión alternadamente con su cuenta profesional y una cuenta de Microsoft en la misma sesión de navegador, podrían acumular puntos en su cuenta de recompensas. Los usuarios pueden dejar de acumular puntos mientras buscan con Búsqueda de Microsoft borrando sus cookies.
