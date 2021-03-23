---
title: Páginas clásicas en SharePoint Online y Microsoft Search
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
description: Uso de Microsoft Search en páginas clásicas de SharePoint
ms.openlocfilehash: 33215c730d34c14f8ce1d55e93730615688f1e2a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031435"
---
# <a name="classic-pages-and-microsoft-search"></a>Páginas clásicas y Microsoft Search

Los sitios de SharePoint creados antes de los sitios modernos usan un cuadro de búsqueda clásico y una experiencia de resultados de búsqueda clásica. We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.

Se recomienda usar Microsoft Search para todos los sitios, incluidos los clásicos, pero si los sitios clásicos usan páginas maestras personalizadas o ha personalizado la experiencia de resultados de búsqueda clásica, detectaremos automáticamente estas personalizaciones y no cambiaremos a Microsoft Search.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Sitios clásicos que cambiarán automáticamente a Microsoft Search

Los sitios clásicos empezarán a usar Microsoft Search si todos los siguientes son verdaderos:

* El sitio se basa en la plantilla de sitio de grupo (como STS#0 y STS#1).
* El sitio no tiene activada la característica de publicación.
* El sitio no usa una página maestra personalizada (una página maestra diferente a oslo.master o seattle.master).
* No hay ninguna regla de consulta activa que no sea la adición de resultados promocionados para el sitio, la colección de sitios o el espacio empresarial en el origen de resultados predeterminado.
* No hay tipos de resultados personalizados para el sitio o la colección de sitios en el origen de resultados predeterminado.
* El sitio o la colección de sitios no se descartan del modificador mediante la configuración *SearchBoxInNavBar* que se describe a continuación.

Después del cambio a Microsoft Search, las páginas clásicas del sitio empezarán a mostrar el cuadro de búsqueda en la barra de navegación del conjunto de aplicaciones y quitarán el cuadro de búsqueda clásico de la página. A continuación, cuando un usuario busca un término, los resultados se mostrarán con la experiencia de búsqueda moderna de Microsoft Search.

## <a name="staying-with-the-classic-search-experience"></a>Mantenerse con la experiencia de búsqueda clásica

Si el sitio cumple los criterios enumerados anteriormente, pero no desea que cambie a la experiencia de Microsoft Search, puede optar por no usar los siguientes comandos, como propietario del sitio o de la colección de sitios.

Puede usar este comando en cualquier momento, antes o después de que se produce el cambio, por lo que es fácil volver a la experiencia de búsqueda que tenía anteriormente.

Para ejecutar los comandos siguientes, usará PowerShell con extensiones de PowerShell pnP de SharePoint. Puede instalar y obtener más información sobre cómo empezar [aquí](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Iniciar sesión en su sitio o colección de sitios mediante este comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

Para mantener la experiencia de búsqueda clásica de un sitio, ejecute el siguiente comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Como alternativa, si desea establecerlo para todos los sitios de una colección de sitios, puede usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Optar por Microsoft Search

Para aquellos sitios que no cumplen los criterios enumerados anteriormente o para sitios específicos de una colección de sitios que optaron por permanecer en el clásico, puede habilitar manualmente la experiencia de Búsqueda de Microsoft.

Para cambiar esta configuración para un sitio específico, puede usar este comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Si desea establecerlo para todos los sitios de una colección de sitios, puede usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> Solo puede habilitar Microsoft Search manualmente para un sitio de grupo o un sitio de publicación (identificadores de plantilla que contienen "STS", "CMSPUBLISHING", "BLANKINTERNET" y "GROUP").