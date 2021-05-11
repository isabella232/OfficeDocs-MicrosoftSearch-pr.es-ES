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
ms.openlocfilehash: 614fa241f353533b1c1e181904eb961fd55d0dfa
ms.sourcegitcommit: ea784081bc9c3ae7981a87a493d3a74503859dda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306074"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Preguntas más frecuentes

Aquí tiene una lista de las preguntas más frecuentes.

> [!TIP]
> ¿No encuentra aquí una respuesta a su pregunta? Formule su pregunta en el comentario de este artículo.

## <a name="is-advanced-query-understanding-supported"></a>¿Se ofrece la comprensión de consultas avanzadas?

Sí, Microsoft Search analiza la intención de consulta de frases más grandes. Esta característica usa inteligencia artificial para aprender frases superfluas comunes que los usuarios agregan a sus consultas que no afectan a su intención de búsqueda. Por ejemplo, cuando un usuario busca información sobre cómo cambiar mi *contraseña,* extraemos las palabras menos importantes de la consulta y desencadenamos en función de las relevantes, como cambiar contraseña *.*
  
Esta característica no invalidará las palabras clave establecidas en [el centro Microsoft 365 administración](https://admin.microsoft.com).
  
## <a name="can-you-search-for-files-on-premises"></a>¿Puedo buscar archivos locales?

Sí. Puede buscar archivos locales [SharePoint](http://sharepoint.com/) si tiene una implementación híbrida de SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>¿Cómo hago que Bing sea el motor de búsqueda predeterminado para los usuarios de mi organización?

Estas son las instrucciones para configurar el motor de búsqueda predeterminado, la página principal predeterminada y el explorador predeterminado para ofrecer a los usuarios la mejor experiencia con Microsoft Search en [Bing:](https://Bing.com)

- [Establecer Microsoft Edge como el explorador predeterminado](/deployedge/edge-default-browser)
- [Establezca Bing como el motor de búsqueda predeterminado](set-default-search-engine.md)
- [Establezca Bing.com como la página principal de la empresa](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>¿Cómo se protegen mis resultados de búsqueda?

Se [requiere](/azure/active-directory/) Azure Active Directory autenticación para obtener acceso a los resultados de la nube de confianza. Los usuarios autenticados solo verán el contenido al que tengan acceso. Las consultas de búsqueda no están identificadas y los registros se separan del tráfico [Bing](https://Bing.com) búsqueda pública cuando se usa Microsoft Search en Bing.

## <a name="can-i-search-across-federated-organizations"></a>¿Puedo buscar en organizaciones federadas?

No.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>¿Dónde puedo obtener información sobre Office 365 seguridad, cumplimiento y privacidad?

Los detalles se pueden encontrar en las páginas [del Centro de confianza para Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>¿Pueden los usuarios invitados aprovechar Microsoft Search en mi organización?

Microsoft 365 colaboración enriquecte con personas externas a su organización a través [del acceso de invitados.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Estos usuarios podrán realizar operaciones de búsqueda en documentos, sitios, grupos, listas y bibliotecas. Sin embargo, los usuarios invitados no tendrán la experiencia completa y personalizada de Microsoft Search y es posible que deba aprovechar el cuadro de búsqueda en la página en lugar del cuadro de Búsqueda de Microsoft unificado en el encabezado.