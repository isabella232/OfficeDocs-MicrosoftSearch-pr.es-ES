---
title: Crear una página de resultados de búsqueda personalizada en SharePoint Online
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Crear su propia página de resultados de búsqueda para un sitio de SharePoint Online
ms.openlocfilehash: b5abb25f15795389dd8b6d5683ac336af7422e0a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031642"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Crear una página de resultados de búsqueda personalizada en SharePoint Online

Una forma de personalizar la experiencia de búsqueda en SharePoint es crear una página de resultados de búsqueda personalizada para un sitio. Esto le permite usar una página que creó, en lugar del valor predeterminado en la página de resultados de Microsoft Search. Esto le ofrece más flexibilidad sobre cómo la experiencia de resultados de búsqueda busca a los usuarios.

>[!NOTE]
> Para realizar cambios en la página predeterminada de resultados de Microsoft Search que está disponible de forma predeterminada, consulte [Personalizar la página de resultados de búsqueda](customize-search-page.md).

Con una página de resultados personalizada puede crear una nueva página que se puede usar para controlar el diseño y el diseño de los resultados de búsqueda para satisfacer las necesidades de su organización. Puede usar elementos web integrados, elementos web de búsqueda de código abierto de la comunidad de patrones y prácticas de SharePoint, así como cualquier elemento web personalizado que haya desarrollado con SharePoint Framework.

## <a name="configure-a-results-page"></a>Configurar una página de resultados

Para configurar una página de resultados personalizada en SharePoint Online, siga estos pasos:

1. Vaya al sitio donde desea configurar una página de resultados personalizada y vaya a Configuración del sitio > configuración de la colección de **sitios > configuración de búsqueda**.

2. En Configuración de búsqueda, desactive la selección de Usar la misma configuración de página de resultados que mi elemento primario **,** elija Enviar consultas **a** una página de resultados personalizada y proporcione un valor para dirección URL de página **de resultados:**. A continuación, guarde los cambios. La dirección URL que use aquí debe ser para la página que creó para usarla como página de resultados personalizada.

>[!NOTE]
> La página de resultados personalizada debe estar en el mismo dominio que el sitio, pero no tiene que estar en la misma colección de sitios.  

Como alternativa, puede usar el comando [Set-PnPSearchSettings SharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) para establecer el valor en lugar de usar la página Configuración del sitio.

Una vez establecida, la página de resultados de búsqueda personalizada se muestra cuando se busca con el cuadro Búsqueda de Microsoft que aparece en la barra de navegación de la parte superior de la página y se usa al escribir la búsqueda desde las páginas del sitio o la página principal del sitio. No se usa al buscar en una lista, biblioteca o en la página de contenido del sitio. Puede usar el vínculo para expandir la búsqueda desde los resultados de búsqueda en listas y bibliotecas para llegar a la página de resultados personalizada.

## <a name="change-the-layout-of-your-custom-results-page"></a>Cambiar el diseño de la página de resultados personalizada

Se puede usar un diseño de página **denominado HeaderlessSearchResults** para hacer que la página de resultados de búsqueda parezca más cercana a nuestra experiencia de resultados de búsqueda fuera de la caja. Este nuevo diseño solo puede estar activo para las páginas que se establecen como la página de resultados de búsqueda personalizada.

Para establecer el diseño de página, puede usar el comando [Set-PnPClientSidePageSharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) con -LayoutType HeaderlessSearchResults.

## <a name="use-sharepoint-framework-query-extensions"></a>Usar extensiones de consulta de SharePoint Framework

Las páginas de resultados de búsqueda personalizadas también pueden usar la extensión de consulta de [SharePoint Framework](/sharepoint/dev/spfx/building-search-extensions) para modificar la consulta antes de que se envíe al motor de búsqueda.

## <a name="additional-resources"></a>Recursos adicionales

Para obtener más información sobre la página de resultados personalizados, consulte nuestra [sesión Ignite 2019 Search Customization and Development](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions).

Para proyectos de código abierto, introducción a nuestras API de Microsoft Search y más ejemplos de personalización y extensibilidad, visite [Microsoft Search en GitHub](https://github.com/microsoft-search).