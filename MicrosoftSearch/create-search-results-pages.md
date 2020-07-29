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
ms.openlocfilehash: 9b168dccaa6126148c877b5841b91c63f7bdc2ac
ms.sourcegitcommit: 5fb46a04e86fb49477f8ce7ab3caa1b503215b8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503247"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Crear una página de resultados de búsqueda personalizada en SharePoint Online

Una forma de personalizar la experiencia de búsqueda en SharePoint es crear una página de resultados de búsqueda personalizada para un sitio. Esto le permite usar una página que haya creado, en lugar de la predeterminada en la página de resultados de Microsoft Search. Esto le proporciona más flexibilidad en el aspecto de la experiencia de los resultados de búsqueda para los usuarios.

>[!NOTE]
> Para realizar cambios en la página predeterminada de resultados de búsqueda de Microsoft que está disponible de forma predeterminada, consulte [customize the search results page](customize-search-page.md).

Con una página de resultados personalizada puede crear una página nueva que se puede usar para controlar el diseño y el diseño de los resultados de la búsqueda para que sean compatibles con las necesidades de la organización. Puede usar cualquier elemento Web integrado, elementos Web de búsqueda de código abierto de la comunidad de patrones y prácticas de SharePoint, así como cualquier elemento web personalizado que haya desarrollado mediante SharePoint Framework.

## <a name="configure-a-results-page"></a>Configurar una página de resultados

Para configurar una página de resultados personalizada en SharePoint Online, siga los pasos que se indican a continuación:

1. Vaya al sitio donde desearía configurar una página de resultados personalizada y vaya a configuración del **sitio > configuración de la colección de sitios > configuración de búsqueda**.

2. En configuración de búsqueda, desactive la opción seleccionar para **usar la misma configuración de página de resultados que mi principal**, seleccione **enviar consultas a una página de resultados personalizada**y proporcione un valor para la **dirección URL de la página de resultados:**.A continuación, guarde los cambios. La dirección URL que use aquí debe ser para la página que ha creado para usar como página de resultados personalizada.

>[!NOTE]
> La página de resultados personalizada debe estar en el mismo dominio que el sitio, pero no es necesario que esté en la misma colección de sitios.  

Como alternativa, puede usar el [comando set-PnPSearchSettings de PowerShell PNP de SharePoint](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) para establecer el valor en lugar de usar la página Configuración del sitio.

Una vez establecida, se muestra la página de resultados de búsqueda personalizada al buscar mediante el cuadro de búsqueda de Microsoft que aparece en la barra de navegación de la parte superior de la página y se usa cuando se escribe búsqueda desde páginas de sitio o la Página principal del sitio. No se usa cuando se busca en una lista, biblioteca o en la página contenidos del sitio. Puede usar el vínculo para ampliar la búsqueda de resultados de búsqueda en listas y bibliotecas para llegar a la página de resultados personalizados.

## <a name="change-the-layout-of-your-custom-results-page"></a>Cambiar el diseño de la página de resultados personalizados

Se puede usar un diseño de página denominado **HeaderlessSearchResults** para que la página de resultados de búsqueda aparezca más cerca de nuestra experiencia de resultados de búsqueda.Este nuevo diseño solo puede estar activo para las páginas que están configuradas como la página de resultados de búsqueda personalizada.

Para establecer el diseño de página, puede usar el [comando set-PnPClientSidePageSharePoint PNP PowerShell](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) con-LayoutType HeaderlessSearchResults.

## <a name="use-sharepoint-framework-query-extensions"></a>Usar las extensiones de consulta de SharePoint Framework

Las páginas de resultados de búsqueda personalizadas también pueden usar la [extensión de consulta de SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions) para modificar la consulta antes de que se envíe al motor de búsqueda.

## <a name="additional-resources"></a>Recursos adicionales

Para obtener más información acerca de la página de resultados personalizados, consulte nuestra [sesión de personalización de búsqueda y personalización de búsqueda de encendido 2019](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions).

Para los proyectos de código abierto, introducción a las API de Microsoft Search y más ejemplos de personalización y extensibilidad, visite [Microsoft Search en github](https://github.com/microsoft-search).
