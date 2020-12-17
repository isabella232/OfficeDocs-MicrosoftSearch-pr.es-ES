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
description: Usar Microsoft Search en páginas clásicas de SharePoint
ms.openlocfilehash: 605e63a30ad166c63320c7e89e1b2745e628e15d
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700977"
---
# <a name="classic-pages-and-microsoft-search"></a>Páginas clásicas y Microsoft Search

Los sitios de SharePoint creados antes de los sitios modernos usan un cuadro de búsqueda clásico y una experiencia de resultados de búsqueda clásica. Se va a implementar una característica que utilizará las páginas clásicas predeterminadas para empezar a usar la experiencia de búsqueda moderna que usa Microsoft Search, que proporciona resultados personalizados con mayor relevancia.

Se recomienda usar Microsoft Search para todos los sitios, incluidos los clásicos, pero si los sitios clásicos usan páginas maestras personalizadas o ha personalizado la experiencia de resultados de búsqueda clásica, se detectarán automáticamente estas personalizaciones y no se cambiará a Microsoft Search.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Sitios clásicos que cambiarán automáticamente a Microsoft Search

Los sitios clásicos se iniciarán con Microsoft Search si se cumplen todas las condiciones siguientes.

* El sitio se basa en la plantilla de sitio de grupo (como STS # 0 y STS # 1).
* El sitio no tiene activada la característica de publicación.
* El sitio no usa una página maestra personalizada (una página maestra diferente a la de Oslo. Master o Seattle. Master).
* No hay ninguna regla de consulta activa que agregue resultados promocionados para el sitio, la colección de sitios o el inquilino en el origen de resultados predeterminado.
* No hay tipos de resultados personalizados para el sitio o la colección de sitios en el origen de resultados predeterminado.
* El sitio o la colección de sitios a la que pertenece no ha decidido salir del conmutador con la configuración SearchBoxInNavBar que se describe a continuación.

Después de cambiar a Microsoft Search, las páginas clásicas del sitio se iniciarán para mostrar el cuadro de búsqueda en la barra de navegación del conjunto y quitar el cuadro de búsqueda clásico de la página. A continuación, cuando un usuario busca un término, los resultados se mostrarán con la experiencia de búsqueda moderna de Microsoft Search.

## <a name="staying-with-the-classic-search-experience"></a>Mantener la experiencia de búsqueda clásica

Si su sitio cumple los criterios enumerados anteriormente, pero no quiere que cambie a la experiencia de Microsoft Search, puede optar por usar los siguientes comandos, como el propietario del sitio o de la colección de sitios.

Puede usar este comando en cualquier momento, antes o después de que se produzca el cambio, de modo que sea fácil volver a la experiencia de búsqueda que tenía anteriormente.

Para ejecutar los comandos siguientes, deberá usar PowerShell con extensiones de PowerShell de PnP de SharePoint. Puede instalar y obtener más información sobre cómo empezar [aquí](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Deberá iniciar sesión en el sitio o en la colección de sitios con este comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials
```

Para seguir con la experiencia de búsqueda clásica de un sitio, ejecute el siguiente comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Como alternativa, si desea establecerla para todos los sitios de una colección de sitios, puede usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Optar por Microsoft Search

Para los sitios que no cumplen los criterios enumerados anteriormente o para sitios específicos de una colección de sitios que han optado por permanecer en clásico, puede habilitar manualmente la experiencia de Microsoft Search.

Para cambiar esta configuración para un sitio específico, puede usar este comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Si desea establecerla para todos los sitios de una colección de sitios, puede usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> Puede habilitar manualmente Microsoft Search solo para un sitio de grupo o un sitio de publicación (identificadores de plantilla que contienen "STS", "CMSPUBLISHING", "BLANKINTERNET" y "GROUP").
