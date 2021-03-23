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
ms.openlocfilehash: 98128297047d50e2d418a8ed062066ab9e86749e
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031624"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Preguntas más frecuentes

Aquí tiene una lista de las preguntas más frecuentes.

> [!TIP]
> ¿No encuentra aquí una respuesta a su pregunta? Formule su pregunta en el comentario de este artículo.

## <a name="is-advanced-query-understanding-supported"></a>¿Se ofrece la comprensión de consultas avanzadas?

Sí, Microsoft Search analiza la intención de consulta de frases más grandes. Esta característica usa inteligencia artificial para aprender frases superfluas comunes que los usuarios agregan a sus consultas que no afectan a su intención de búsqueda. Por ejemplo, cuando un usuario busca información sobre cómo cambiar mi *contraseña,* extraemos las palabras menos importantes de la consulta y desencadenamos en función de las relevantes, como cambiar contraseña *.*
  
Esta característica no invalidará las palabras clave establecidas en el Centro de administración de [Microsoft 365](https://admin.microsoft.com).
  
## <a name="can-you-search-for-files-on-premises"></a>¿Puedo buscar archivos locales?

Sí. Puede buscar archivos de [SharePoint](http://sharepoint.com/) locales si tiene una implementación híbrida de SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>¿Cómo hago que Bing sea el motor de búsqueda predeterminado para los usuarios de mi organización?

Estas son las instrucciones para configurar el motor de búsqueda predeterminado, la página principal predeterminada y el explorador predeterminado para ofrecer a los usuarios la mejor experiencia con Microsoft Search en [Bing:](https://Bing.com)

- [Establecer Microsoft Edge como explorador predeterminado](/deployedge/edge-default-browser)
- [Establezca Bing como el motor de búsqueda predeterminado](set-default-search-engine.md)
- [Establezca Bing.com como la página principal de la empresa](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>¿Cómo se protegen mis resultados de búsqueda?

Se requiere [la autenticación de Azure Active Directory](/azure/active-directory/) para obtener acceso a los resultados de la nube de confianza. Los usuarios autenticados solo verán el contenido al que tengan acceso. Las consultas de búsqueda no están identificadas y los registros se separan del tráfico de búsqueda de [Bing](https://Bing.com) público cuando se usa Microsoft Search en Bing.

## <a name="can-i-search-across-federated-organizations"></a>¿Puedo buscar en organizaciones federadas?

No.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>¿Dónde puedo obtener información sobre la seguridad, el cumplimiento y la privacidad de Office 365?

Los detalles se pueden encontrar en las páginas [del Centro de confianza para Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>¿Los usuarios pueden ganar puntos de Microsoft Rewards con su cuenta profesional o educativa?

Búsqueda de Microsoft necesita que los usuarios de la empresa inicien sesión con una cuenta profesional o educativa. Sin embargo, los usuarios no podrán unirse ni iniciar sesión en el programa Microsoft Rewards con esas cuentas. Sin embargo, hay una instancia en la que un usuario de la empresa puede ver puntos de recompensas. Esto puede suceder cuando un usuario de Búsqueda de Microsoft tiene una cuenta de recompensas que se creó con una [cuenta de Microsoft](https://www.microsoft.com/welcome?rtc=1). (La dirección de correo electrónico asociada a una cuenta de Microsoft puede ser de Outlook.com, Hotmail.com, Gmail, Yahoo u otros proveedores). Si los usuarios inician sesión alternadamente con su cuenta profesional y una cuenta de Microsoft en la misma sesión de navegador, podrían acumular puntos en su cuenta de recompensas. Los usuarios pueden dejar de acumular puntos mientras buscan con Búsqueda de Microsoft borrando sus cookies.

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>¿Pueden los usuarios invitados aprovechar Microsoft Search en mi organización?

Microsoft 365 permite una colaboración enriquecte con personas ajenas a su organización a través [del acceso de invitados.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Estos usuarios podrán realizar operaciones de búsqueda en documentos, sitios, grupos, listas y bibliotecas. Sin embargo, los usuarios invitados no tendrán la experiencia completa y personalizada de Microsoft Search y es posible que deba aprovechar el cuadro de búsqueda en la página en lugar del cuadro de Búsqueda de Microsoft unificado en el encabezado.