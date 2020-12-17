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
# <a name="classic-pages-and-microsoft-search"></a><span data-ttu-id="ddc00-103">Páginas clásicas y Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="ddc00-103">Classic pages and Microsoft Search</span></span>

<span data-ttu-id="ddc00-104">Los sitios de SharePoint creados antes de los sitios modernos usan un cuadro de búsqueda clásico y una experiencia de resultados de búsqueda clásica.</span><span class="sxs-lookup"><span data-stu-id="ddc00-104">SharePoint sites created prior to modern sites use a classic search box and classic search results experience.</span></span> <span data-ttu-id="ddc00-105">Se va a implementar una característica que utilizará las páginas clásicas predeterminadas para empezar a usar la experiencia de búsqueda moderna que usa Microsoft Search, que proporciona resultados personalizados con mayor relevancia.</span><span class="sxs-lookup"><span data-stu-id="ddc00-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span></span>

<span data-ttu-id="ddc00-106">Se recomienda usar Microsoft Search para todos los sitios, incluidos los clásicos, pero si los sitios clásicos usan páginas maestras personalizadas o ha personalizado la experiencia de resultados de búsqueda clásica, se detectarán automáticamente estas personalizaciones y no se cambiará a Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="ddc00-106">Using Microsoft Search is recommended for all sites, including classic, but if your classic sites use custom master pages and/or you have customized your classic search results experience, we will auto-detect these customizations and not switch to Microsoft Search.</span></span>

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a><span data-ttu-id="ddc00-107">Sitios clásicos que cambiarán automáticamente a Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="ddc00-107">Classic sites that will automatically switch to Microsoft Search</span></span>

<span data-ttu-id="ddc00-108">Los sitios clásicos se iniciarán con Microsoft Search si se cumplen todas las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="ddc00-108">Classic sites will start using Microsoft Search if all of the following are true.</span></span>

* <span data-ttu-id="ddc00-109">El sitio se basa en la plantilla de sitio de grupo (como STS # 0 y STS # 1).</span><span class="sxs-lookup"><span data-stu-id="ddc00-109">The site is based on the team site template (like STS#0 and STS#1).</span></span>
* <span data-ttu-id="ddc00-110">El sitio no tiene activada la característica de publicación.</span><span class="sxs-lookup"><span data-stu-id="ddc00-110">The site does not have the publishing feature turned on.</span></span>
* <span data-ttu-id="ddc00-111">El sitio no usa una página maestra personalizada (una página maestra diferente a la de Oslo. Master o Seattle. Master).</span><span class="sxs-lookup"><span data-stu-id="ddc00-111">The site does not use a custom master page (a different master page than oslo.master or seattle.master).</span></span>
* <span data-ttu-id="ddc00-112">No hay ninguna regla de consulta activa que agregue resultados promocionados para el sitio, la colección de sitios o el inquilino en el origen de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ddc00-112">There are no active query rules other than those adding promoted results for the site, site collection or tenant on the default result source.</span></span>
* <span data-ttu-id="ddc00-113">No hay tipos de resultados personalizados para el sitio o la colección de sitios en el origen de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ddc00-113">There are no custom result types for the site or the site collection on the default result source.</span></span>
* <span data-ttu-id="ddc00-114">El sitio o la colección de sitios a la que pertenece no ha decidido salir del conmutador con la configuración SearchBoxInNavBar que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="ddc00-114">The site or the site collection it is part of has not opted out of the switch using the SearchBoxInNavBar setting described below.</span></span>

<span data-ttu-id="ddc00-115">Después de cambiar a Microsoft Search, las páginas clásicas del sitio se iniciarán para mostrar el cuadro de búsqueda en la barra de navegación del conjunto y quitar el cuadro de búsqueda clásico de la página.</span><span class="sxs-lookup"><span data-stu-id="ddc00-115">After the switch to Microsoft Search, classic pages in the site will start to show the search box in the suite navigation bar and remove the classic search box from the page.</span></span> <span data-ttu-id="ddc00-116">A continuación, cuando un usuario busca un término, los resultados se mostrarán con la experiencia de búsqueda moderna de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="ddc00-116">Then, when a user searches for a term, the results will be displayed using the modern search experience of Microsoft Search.</span></span>

## <a name="staying-with-the-classic-search-experience"></a><span data-ttu-id="ddc00-117">Mantener la experiencia de búsqueda clásica</span><span class="sxs-lookup"><span data-stu-id="ddc00-117">Staying with the classic search experience</span></span>

<span data-ttu-id="ddc00-118">Si su sitio cumple los criterios enumerados anteriormente, pero no quiere que cambie a la experiencia de Microsoft Search, puede optar por usar los siguientes comandos, como el propietario del sitio o de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="ddc00-118">If your site meets the criteria listed above, but you do not want it to switch to the Microsoft Search experience, you can opt out using the following commands, as the site or site collection owner.</span></span>

<span data-ttu-id="ddc00-119">Puede usar este comando en cualquier momento, antes o después de que se produzca el cambio, de modo que sea fácil volver a la experiencia de búsqueda que tenía anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ddc00-119">You can use this command at any time, before or after the switch happens, so it is easy to go back to the search experience you had previously.</span></span>

<span data-ttu-id="ddc00-120">Para ejecutar los comandos siguientes, deberá usar PowerShell con extensiones de PowerShell de PnP de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ddc00-120">To run the commands below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="ddc00-121">Puede instalar y obtener más información sobre cómo empezar [aquí](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="ddc00-121">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="ddc00-122">Deberá iniciar sesión en el sitio o en la colección de sitios con este comando:</span><span class="sxs-lookup"><span data-stu-id="ddc00-122">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials
```

<span data-ttu-id="ddc00-123">Para seguir con la experiencia de búsqueda clásica de un sitio, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ddc00-123">To stay with classic search experience for a site, run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

<span data-ttu-id="ddc00-124">Como alternativa, si desea establecerla para todos los sitios de una colección de sitios, puede usar este comando:</span><span class="sxs-lookup"><span data-stu-id="ddc00-124">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a><span data-ttu-id="ddc00-125">Optar por Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="ddc00-125">Opting into Microsoft Search</span></span>

<span data-ttu-id="ddc00-126">Para los sitios que no cumplen los criterios enumerados anteriormente o para sitios específicos de una colección de sitios que han optado por permanecer en clásico, puede habilitar manualmente la experiencia de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="ddc00-126">For those sites that do not meet the criteria listed above, or for specific sites in a site collection that opted to stay in classic, you can manually enable the Microsoft Search experience.</span></span>

<span data-ttu-id="ddc00-127">Para cambiar esta configuración para un sitio específico, puede usar este comando:</span><span class="sxs-lookup"><span data-stu-id="ddc00-127">To change this setting for a specific site, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

<span data-ttu-id="ddc00-128">Si desea establecerla para todos los sitios de una colección de sitios, puede usar este comando:</span><span class="sxs-lookup"><span data-stu-id="ddc00-128">If you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> <span data-ttu-id="ddc00-129">Puede habilitar manualmente Microsoft Search solo para un sitio de grupo o un sitio de publicación (identificadores de plantilla que contienen "STS", "CMSPUBLISHING", "BLANKINTERNET" y "GROUP").</span><span class="sxs-lookup"><span data-stu-id="ddc00-129">You can manually enable Microsoft Search only for a Team Site or Publishing Site (template ids that contain "STS", "CMSPUBLISHING", "BLANKINTERNET" and "GROUP").</span></span>
