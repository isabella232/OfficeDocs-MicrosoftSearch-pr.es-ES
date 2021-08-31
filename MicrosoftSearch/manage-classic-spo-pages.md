---
title: Páginas clásicas en SharePoint Online y Búsqueda de Microsoft
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
description: Usar Búsqueda de Microsoft en páginas SharePoint clásicas
ms.openlocfilehash: 5b9c40da63ccf3b28cf2d61282763d3d4f62f867
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702043"
---
# <a name="classic-pages-and-microsoft-search"></a>Páginas clásicas y Búsqueda de Microsoft

SharePoint sitios creados antes de los sitios modernos usan un cuadro de búsqueda clásico y una experiencia de resultados de búsqueda clásica. Implementaremos una característica que usará las páginas clásicas predeterminadas para empezar a usar la experiencia de búsqueda moderna que usa Búsqueda de Microsoft, que proporciona resultados personalizados con mayor relevancia.

Se recomienda usar Búsqueda de Microsoft para todos los sitios, incluidos los clásicos, pero si los sitios clásicos usan páginas maestras personalizadas o ha personalizado la experiencia de resultados de búsqueda clásica, detectaremos automáticamente estas personalizaciones y no cambiaremos a Búsqueda de Microsoft.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Sitios clásicos que cambiarán automáticamente a Búsqueda de Microsoft

Los sitios clásicos empezarán a Búsqueda de Microsoft si todos los siguientes son verdaderos:

* El sitio se basa en la plantilla de sitio de grupo (como STS#0 y STS#1).
* El sitio no tiene activada la característica de publicación.
* El sitio no usa una página maestra personalizada (una página maestra diferente a oslo.master o seattle.master).
* No hay ninguna regla de consulta activa que no sea la adición de resultados promocionados para el sitio, la colección de sitios o el espacio empresarial en el origen de resultados predeterminado.
* No hay tipos de resultados personalizados para el sitio o la colección de sitios en el origen de resultados predeterminado.
* El sitio o la colección de sitios no se descartan del modificador mediante la configuración *SearchBoxInNavBar* que se describe a continuación.

Después de cambiar a Búsqueda de Microsoft, las páginas clásicas del sitio empezarán a mostrar el cuadro de búsqueda en la barra de navegación del conjunto de programas y quitarán el cuadro de búsqueda clásico de la página. A continuación, cuando un usuario busca un término, los resultados se mostrarán con la experiencia de búsqueda moderna de Búsqueda de Microsoft.

## <a name="staying-with-the-classic-search-experience"></a>Mantenerse con la experiencia de búsqueda clásica

Si el sitio cumple los criterios enumerados anteriormente, pero no desea que cambie a la experiencia de Búsqueda de Microsoft, puede optar por no usar los siguientes comandos, como propietario del sitio o de la colección de sitios.

Puede usar este comando en cualquier momento, antes o después de que se produce el cambio, por lo que es fácil volver a la experiencia de búsqueda que tenía anteriormente.

Para ejecutar los comandos siguientes, usará PowerShell con SharePoint de PowerShell pnP. Puede instalar y obtener más información sobre cómo empezar [aquí](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Iniciar sesión en su sitio o colección de sitios mediante este comando:

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

## <a name="opting-into-microsoft-search"></a>Optar por la Búsqueda de Microsoft

Para los sitios que no cumplen los criterios mencionados anteriormente, o para sitios específicos de una colección de sitios que optaron por permanecer en el clásico, puede habilitar manualmente la experiencia Búsqueda de Microsoft sitio.

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
> Puede habilitar manualmente Búsqueda de Microsoft solo para un sitio de grupo o un sitio de publicación (identificadores de plantilla que contienen "STS", "CMSPUBLISHING", "BLANKINTERNET" y "GROUP").