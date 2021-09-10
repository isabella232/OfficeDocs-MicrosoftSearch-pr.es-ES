---
title: Administración del cuadro de búsqueda en SharePoint sitios
ms.author: keremy
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
description: Cómo personalizar la experiencia del cuadro de búsqueda en SharePoint búsqueda
ms.openlocfilehash: b5d58dd5a241ccf2ada556c44ec0ea5479ea2e2b
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973826"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Configuración del cuadro de búsqueda SharePoint sitios

Una de las varias maneras en Búsqueda de Microsoft puede personalizarse en sitios de SharePoint es adaptar el modo en que funciona el cuadro de búsqueda de la barra de navegación del conjunto de aplicaciones en SharePoint para que se adapte mejor a sus necesidades.

Para otras opciones de personalización, vea [Changing the Búsqueda de Microsoft results page to add custom verticals, result types and layouts](customize-search-page.md), y Creating a custom search results [page](create-search-results-pages.md).

> [!NOTE]
> El cuadro de búsqueda de la barra de navegación del conjunto de opciones no está disponible para todos los clientes en este momento, pero estas opciones aún se pueden establecer ahora y tendrán efecto cuando esté disponible.

Para las tareas que se enumeran a continuación, usará PowerShell SharePoint extensiones de PowerShell pnP. Puede instalar y obtener más información sobre cómo empezar [aquí](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Iniciará sesión en su sitio o colección de sitios con este comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Cambiar el ámbito de búsqueda

Al crear un nuevo sitio en SharePoint Online hoy y escribir en el cuadro de búsqueda, se le muestra la página de Búsqueda de Microsoft resultados. Esta página muestra los resultados del sitio actual de forma predeterminada y le permite expandir el ámbito de la búsqueda al concentrador al que está asociado el sitio actual (si lo hay) o a toda la organización.

El ámbito que usa el cuadro de búsqueda, de forma predeterminada, depende del tipo de sitio.

* Los sitios normales buscan en el sitio actual.
* Los sitios de concentradores buscan en todos los sitios del concentrador.
* Los sitios de inicio buscan en todo el contenido.

En algunos casos, es posible que desee cambiar estos valores predeterminados para buscar siempre en toda la organización o en todo el centro al que está asociado un sitio, sin necesidad de hacer clic adicional.

Como propietario del sitio, puede cambiar estos valores predeterminados mediante el siguiente comando:

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Después de ejecutar este comando, el sitio que anteriormente mostraba los resultados del sitio actual de forma predeterminada empezará a mostrar resultados de toda la organización.

Para volver a la configuración predeterminada, vuelva a ejecutar el comando con el valor "DefaultScope". Para buscar en el concentrador, use "Concentrador" como valor de SearchScope.

Esta configuración se aplica en el nivel de sitio individual. No hay ninguna configuración equivalente para las colecciones de sitios.

## <a name="show-or-hide-the-search-box"></a>Mostrar u ocultar el cuadro de búsqueda

Puedes elegir ocultar el cuadro de búsqueda de la barra de navegación del conjunto de aplicaciones si quieres impedir que los usuarios busquen o usar una implementación de cuadro de búsqueda personalizada.

Para cambiar esta configuración para un sitio determinado, use este comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Como alternativa, si desea establecerlo para todos los sitios de una colección de sitios, puede usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Después de ejecutar estos comandos, el cuadro de búsqueda ya no aparecerá en la barra de navegación de la parte superior de la página. Para volver a mostrar el cuadro de búsqueda, vuelva a ejecutar los comandos con el valor proporcionado al parámetro "SearchBoxInNavBar" en "Inherit".

Hay varios puntos a tener en cuenta:

* Esta configuración solo se aplica al cuadro de búsqueda de la barra de navegación del conjunto de opciones. No se aplica a los cuadros de búsqueda que están en la página ni a los cuadros de búsqueda de las páginas clásicas.

* Una vez deshabilitado el cuadro de búsqueda en la barra de navegación, si desea la funcionalidad de búsqueda en el sitio, tendrá que proporcionarlo usted mismo mediante un elemento web personalizado o una extensión SharePoint Framework web.

* Esta solución también quitará el cuadro de búsqueda de las listas y bibliotecas del sitio. La solución de búsqueda personalizada tendrá que tener en cuenta las búsquedas contextuales para SharePoint listas y bibliotecas, además de la búsqueda en todo el sitio.

* Si aplica la configuración al sitio raíz de su dominio, la página SharePoint inicio también dejará de mostrar el cuadro de búsqueda.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Cambiar la sugerencia que se muestra en el cuadro de búsqueda

Puede cambiar la sugerencia que muestra el cuadro de búsqueda para un sitio o colección de sitios determinados. Este es el texto que aparece en el cuadro de búsqueda antes de empezar a escribirlo. Esto puede ayudar a guiar a los usuarios sobre qué esperar de la búsqueda si ha configurado una página de resultados personalizada o ha cambiado el comportamiento de la búsqueda de otras maneras.

> [!NOTE]
> Para poder realizar este cambio, debe permitir la ejecución de scripts personalizados en el sitio en cuestión como administrador de inquilinos, lo que no está permitido de forma predeterminada. Consulte para https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script obtener más información. Puede permitir la ejecución de scripts personalizados, realizar el cambio y, a continuación, revertir a la falta de permitir scripts para el sitio si es necesario.

Para cambiar esta configuración para un sitio determinado, ejecute el siguiente comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

Como alternativa, si desea establecerlo para todos los sitios de una colección de sitios, puede usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Para volver al texto de marcador de posición predeterminado, establezca el valor en blanco ("").