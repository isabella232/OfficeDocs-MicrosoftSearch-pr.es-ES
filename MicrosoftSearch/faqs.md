---
title: Preguntas más frecuentes
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Obtenga respuestas a las preguntas más frecuentes acerca de la búsqueda empresarial y Microsoft Search
ms.openlocfilehash: 8b4de717ab63af8842dc86135748e551ff386a2a
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702160"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Preguntas más frecuentes

Aquí tiene una lista de las preguntas más frecuentes.

> [!TIP]
> ¿No encuentra aquí una respuesta a su pregunta? Formule su pregunta en el comentario de este artículo.

## <a name="is-advanced-query-understanding-supported"></a>¿Se ofrece la comprensión de consultas avanzadas?

Sí, Búsqueda de Microsoft la intención de consulta de frases más grandes. Esta característica usa inteligencia artificial para aprender frases superfluas comunes que los usuarios agregan a sus consultas que no afectan a su intención de búsqueda. Por ejemplo, cuando un usuario busca información sobre cómo cambiar mi *contraseña,* extraemos las palabras menos importantes de la consulta y desencadenamos en función de las relevantes, como cambiar contraseña *.*
  
Esta característica no invalidará las palabras clave establecidas en el [Centro de administración de Microsoft 365](https://admin.microsoft.com).
  
## <a name="can-you-search-for-files-on-premises"></a>¿Puedo buscar archivos locales?

Sí. Puede buscar archivos locales [SharePoint](http://sharepoint.com/) si tiene una implementación híbrida de SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>¿Cómo hago que Bing sea el motor de búsqueda predeterminado para los usuarios de mi organización?

Estas son las instrucciones para configurar el motor de búsqueda predeterminado, la página principal predeterminada y el explorador predeterminado para ofrecer a los usuarios la mejor experiencia con Búsqueda de Microsoft en [Bing:](https://Bing.com)

- [Establecer Microsoft Edge como el explorador predeterminado](/deployedge/edge-default-browser)
- [Establezca Bing como el motor de búsqueda predeterminado](set-default-search-engine.md)
- [Establezca Bing.com como la página principal de la empresa](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>¿Cómo se protegen mis resultados de búsqueda?

Se [requiere](/azure/active-directory/) Azure Active Directory autenticación para obtener acceso a los resultados de la nube de confianza. Los usuarios autenticados solo verán el contenido al que tengan acceso. Al usar Búsqueda de Microsoft en Bing, las consultas de búsqueda se des identificarán y los registros se separarán del tráfico [Bing](https://Bing.com) búsqueda pública.

## <a name="can-i-search-across-federated-organizations"></a>¿Puedo buscar en organizaciones federadas?

No.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>¿Dónde puedo obtener información sobre Office 365 seguridad, cumplimiento y privacidad?

Los detalles se pueden encontrar en las páginas [del Centro de confianza para Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-guest-users-access-microsoft-search-in-my-organization"></a>¿Los usuarios invitados pueden Búsqueda de Microsoft en mi organización?

Microsoft 365 colaboración enriquecte con personas externas a su organización a través [del acceso de invitados.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Estos usuarios pueden buscar documentos, sitios, grupos, listas y bibliotecas. Sin embargo, los usuarios invitados no disponen de la experiencia Búsqueda de Microsoft completa y personalizada y es posible que deba usar el cuadro de búsqueda en la página en lugar del cuadro de Búsqueda de Microsoft unificado en el encabezado.

## <a name="how-do-i-turn-microsoft-search-in-bing-on-or-off"></a>¿Cómo puedo activar Búsqueda de Microsoft en Bing activar o desactivar?

Para la mayoría de las organizaciones, incluida la empresa y la educación, Búsqueda de Microsoft en Bing está en forma predeterminada. Para activar la Búsqueda de Microsoft en Bing, vaya a la [página Configuraciones](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/configurations) de la Centro de administración de Microsoft 365. En Búsqueda de Microsoft en Bing configuración, elija  Cambiar configuración y active Permitir que su organización use Búsqueda de Microsoft **en Bing**. Este cambio tarda hasta 24 horas en tener efecto.

Si esta configuración está desactivada, los usuarios no obtienen resultados internos cuando buscan en Bing, Windows búsqueda o en Microsoft Edge. Desactivar el Búsqueda de Microsoft en Bing no detiene ni impide que se agrega contenido interno al índice de búsqueda. Solo deshabilita los Bing de entrada a Búsqueda de Microsoft. Para encontrar respuestas y resultados internos, los usuarios tendrán que usar otros puntos de entrada, por ejemplo, SharePoint Online o una Office 365 aplicación.
