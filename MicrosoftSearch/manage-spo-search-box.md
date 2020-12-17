---
title: Administrar el cuadro de búsqueda en los sitios de SharePoint
ms.author: keremy
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
description: Cómo personalizar la experiencia del cuadro de búsqueda en los sitios de SharePoint
ms.openlocfilehash: 6ebd084aadb38acb5475b7e43d7c4092ffc09eb8
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700968"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Configuración del cuadro de búsqueda en sitios de SharePoint

Una de las distintas formas en que Microsoft Search puede personalizarse en los sitios de SharePoint es personalizar el modo en que el cuadro de búsqueda de la barra de navegación de la Suite funciona en los sitios de SharePoint para ajustarse mejor a sus necesidades.

Para otras opciones de personalización, vea [cambiar la página de resultados de búsqueda de Microsoft para agregar verticales personalizados, tipos de resultados y diseños](customize-search-page.md)y [crear una página de resultados de búsqueda personalizada](create-search-results-pages.md).

> [!NOTE]
> El cuadro de búsqueda de la barra de navegación de Suite no está disponible para todos los clientes en este momento, pero estas opciones todavía pueden establecerse y tendrán efecto cuando esté disponible.

Para las tareas que se enumeran a continuación, usará PowerShell con extensiones de PowerShell de PnP de SharePoint. Puede instalar y obtener más información sobre cómo empezar [aquí](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Deberá iniciar sesión en el sitio o en la colección de sitios con este comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Cambiar el ámbito de la búsqueda

Cuando se crea un nuevo sitio en SharePoint Online y se escribe en el cuadro de búsqueda, se le lleva a la página de resultados de búsqueda de Microsoft. Esta página muestra los resultados de su sitio actual de forma predeterminada y le permite ampliar el ámbito de la búsqueda al concentrador al que está asociado el sitio actual (si hay alguno) o a toda la organización.

De forma predeterminada, el ámbito que usa el cuadro de búsqueda depende del tipo de sitio.

* Búsqueda de sitios regulares en el sitio actual.
* Sitios de concentradores busque en todos los sitios del concentrador.
* Sitios principales busca en todo el contenido.

En algunos casos, es posible que desee cambiar estos valores predeterminados para que siempre se busque en toda la organización o en el concentrador al que está asociado un sitio, sin necesidad de hacer clic adicional.

Como propietario de un sitio, puede cambiar estos valores predeterminados mediante el siguiente comando:

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Después de ejecutar este comando, el sitio que anteriormente mostraba los resultados del sitio actual de forma predeterminada empezará a mostrar resultados de toda la organización.

Para volver a la configuración predeterminada, ejecute el comando de nuevo con el valor "DefaultScope". Para buscar en el concentrador, use "Hub" como el valor de SearchScope.

Esta configuración se aplica en el nivel de sitio individual. No hay una configuración equivalente para las colecciones de sitios.

## <a name="show-or-hide-the-search-box"></a>Mostrar u ocultar el cuadro de búsqueda

Puede elegir ocultar el cuadro de búsqueda de la barra de navegación de Suite si desea evitar que los usuarios busquen o usen una implementación de cuadro de búsqueda personalizada.

Para cambiar esta configuración en un sitio determinado, use este comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Como alternativa, si desea establecerla para todos los sitios de una colección de sitios, puede usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Después de ejecutar estos comandos, el cuadro de búsqueda ya no aparecerá en la barra de navegación de la parte superior de la página. Para volver a mostrar el cuadro de búsqueda, ejecute los comandos de nuevo con el valor proporcionado al parámetro "SearchBoxInNavBar" en "inherit".

Hay varios puntos a tener en cuenta:

* Esta configuración solo se aplica al cuadro de búsqueda de la barra de navegación del conjunto de aplicaciones. No se aplica a los cuadros de búsqueda que se encuentran en la página ni a los cuadros de búsqueda de las páginas clásicas.

* Una vez que haya deshabilitado el cuadro de búsqueda en la barra de navegación, si desea una funcionalidad de búsqueda en el sitio, tendrá que proporcionarlo con un elemento web personalizado o con una extensión de SharePoint Framework.

* Esta solución también quitará el cuadro de búsqueda de las listas y bibliotecas del sitio. La solución de búsqueda personalizada debe tener en cuenta las búsquedas contextuales de las listas y bibliotecas de SharePoint, además de la búsqueda en todo el sitio.

* Si aplica la configuración al sitio raíz de su dominio, la página de inicio de SharePoint también dejará de mostrar el cuadro de búsqueda.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Cambio de la sugerencia mostrada en el cuadro de búsqueda

Puede cambiar la sugerencia que muestra el cuadro de búsqueda para un sitio o una colección de sitios determinados. Este es el texto que aparece en el cuadro de búsqueda antes de empezar a escribir en él. Esto puede ayudar a los usuarios a saber lo que cabe esperar de la búsqueda si ha configurado una página de resultados personalizada o cambiado el comportamiento de la búsqueda de otras formas.

> [!NOTE]
> Para poder realizar este cambio, debe permitir la ejecución de scripts personalizados en el sitio en cuestión como administrador de inquilinos, que no se permite de forma predeterminada. https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-scriptPara obtener más información, consulte. Puede permitir la ejecución de scripts personalizados, realizar el cambio y, a continuación, revertir a no permitir scripts para el sitio si es necesario.

Para cambiar esta configuración en un sitio determinado, ejecute el siguiente comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

Como alternativa, si desea establecerla para todos los sitios de una colección de sitios, puede usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Para volver al texto del marcador de posición predeterminado, establezca el valor en blanco ("").
