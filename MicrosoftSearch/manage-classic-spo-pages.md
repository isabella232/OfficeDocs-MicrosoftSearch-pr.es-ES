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
# <a name="classic-pages-and-microsoft-search"></a><span data-ttu-id="e5f2c-103">Páginas clásicas y Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="e5f2c-103">Classic pages and Microsoft Search</span></span>

<span data-ttu-id="e5f2c-104">Los sitios de SharePoint creados antes de los sitios modernos usan un cuadro de búsqueda clásico y una experiencia de resultados de búsqueda clásica.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-104">SharePoint sites created prior to modern sites use a classic search box and classic search results experience.</span></span> <span data-ttu-id="e5f2c-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span></span>

<span data-ttu-id="e5f2c-106">Se recomienda usar Microsoft Search para todos los sitios, incluidos los clásicos, pero si los sitios clásicos usan páginas maestras personalizadas o ha personalizado la experiencia de resultados de búsqueda clásica, detectaremos automáticamente estas personalizaciones y no cambiaremos a Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-106">Using Microsoft Search is recommended for all sites, including classic, but if your classic sites use custom master pages and/or you have customized your classic search results experience, we will auto-detect these customizations and not switch to Microsoft Search.</span></span>

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a><span data-ttu-id="e5f2c-107">Sitios clásicos que cambiarán automáticamente a Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="e5f2c-107">Classic sites that will automatically switch to Microsoft Search</span></span>

<span data-ttu-id="e5f2c-108">Los sitios clásicos empezarán a usar Microsoft Search si todos los siguientes son verdaderos:</span><span class="sxs-lookup"><span data-stu-id="e5f2c-108">Classic sites will start using Microsoft Search if all of the following are true:</span></span>

* <span data-ttu-id="e5f2c-109">El sitio se basa en la plantilla de sitio de grupo (como STS#0 y STS#1).</span><span class="sxs-lookup"><span data-stu-id="e5f2c-109">The site is based on the team site template (like STS#0 and STS#1).</span></span>
* <span data-ttu-id="e5f2c-110">El sitio no tiene activada la característica de publicación.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-110">The site does not have the publishing feature turned on.</span></span>
* <span data-ttu-id="e5f2c-111">El sitio no usa una página maestra personalizada (una página maestra diferente a oslo.master o seattle.master).</span><span class="sxs-lookup"><span data-stu-id="e5f2c-111">The site does not use a custom master page (a different master page than oslo.master or seattle.master).</span></span>
* <span data-ttu-id="e5f2c-112">No hay ninguna regla de consulta activa que no sea la adición de resultados promocionados para el sitio, la colección de sitios o el espacio empresarial en el origen de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-112">There are no active query rules other than those adding promoted results for the site, site collection or tenant on the default result source.</span></span>
* <span data-ttu-id="e5f2c-113">No hay tipos de resultados personalizados para el sitio o la colección de sitios en el origen de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-113">There are no custom result types for the site or the site collection on the default result source.</span></span>
* <span data-ttu-id="e5f2c-114">El sitio o la colección de sitios no se descartan del modificador mediante la configuración *SearchBoxInNavBar* que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-114">The site or the site collection is not opted out of the switch using the *SearchBoxInNavBar* setting described below.</span></span>

<span data-ttu-id="e5f2c-115">Después del cambio a Microsoft Search, las páginas clásicas del sitio empezarán a mostrar el cuadro de búsqueda en la barra de navegación del conjunto de aplicaciones y quitarán el cuadro de búsqueda clásico de la página.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-115">After the switch to Microsoft Search, classic pages in the site will start to show the search box in the suite navigation bar and remove the classic search box from the page.</span></span> <span data-ttu-id="e5f2c-116">A continuación, cuando un usuario busca un término, los resultados se mostrarán con la experiencia de búsqueda moderna de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-116">Then, when a user searches for a term, the results will be displayed using the modern search experience of Microsoft Search.</span></span>

## <a name="staying-with-the-classic-search-experience"></a><span data-ttu-id="e5f2c-117">Mantenerse con la experiencia de búsqueda clásica</span><span class="sxs-lookup"><span data-stu-id="e5f2c-117">Staying with the classic search experience</span></span>

<span data-ttu-id="e5f2c-118">Si el sitio cumple los criterios enumerados anteriormente, pero no desea que cambie a la experiencia de Microsoft Search, puede optar por no usar los siguientes comandos, como propietario del sitio o de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-118">If your site meets the criteria listed above, but you do not want it to switch to the Microsoft Search experience, you can opt out using the following commands, as the site or site collection owner.</span></span>

<span data-ttu-id="e5f2c-119">Puede usar este comando en cualquier momento, antes o después de que se produce el cambio, por lo que es fácil volver a la experiencia de búsqueda que tenía anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-119">You can use this command at any time, before or after the switch happens, so it is easy to go back to the search experience you had previously.</span></span>

<span data-ttu-id="e5f2c-120">Para ejecutar los comandos siguientes, usará PowerShell con extensiones de PowerShell pnP de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-120">To run the commands below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="e5f2c-121">Puede instalar y obtener más información sobre cómo empezar [aquí](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="e5f2c-121">You can install and learn more about how to get started [here](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="e5f2c-122">Iniciar sesión en su sitio o colección de sitios mediante este comando:</span><span class="sxs-lookup"><span data-stu-id="e5f2c-122">You will sign in to your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

<span data-ttu-id="e5f2c-123">Para mantener la experiencia de búsqueda clásica de un sitio, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e5f2c-123">To stay with classic search experience for a site, run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

<span data-ttu-id="e5f2c-124">Como alternativa, si desea establecerlo para todos los sitios de una colección de sitios, puede usar este comando:</span><span class="sxs-lookup"><span data-stu-id="e5f2c-124">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a><span data-ttu-id="e5f2c-125">Optar por Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="e5f2c-125">Opting into Microsoft Search</span></span>

<span data-ttu-id="e5f2c-126">Para aquellos sitios que no cumplen los criterios enumerados anteriormente o para sitios específicos de una colección de sitios que optaron por permanecer en el clásico, puede habilitar manualmente la experiencia de Búsqueda de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5f2c-126">For those sites that do not meet the criteria listed above, or for specific sites in a site collection that opted to stay in classic, you can manually enable the Microsoft Search experience.</span></span>

<span data-ttu-id="e5f2c-127">Para cambiar esta configuración para un sitio específico, puede usar este comando:</span><span class="sxs-lookup"><span data-stu-id="e5f2c-127">To change this setting for a specific site, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

<span data-ttu-id="e5f2c-128">Si desea establecerlo para todos los sitios de una colección de sitios, puede usar este comando:</span><span class="sxs-lookup"><span data-stu-id="e5f2c-128">If you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> <span data-ttu-id="e5f2c-129">Solo puede habilitar Microsoft Search manualmente para un sitio de grupo o un sitio de publicación (identificadores de plantilla que contienen "STS", "CMSPUBLISHING", "BLANKINTERNET" y "GROUP").</span><span class="sxs-lookup"><span data-stu-id="e5f2c-129">You can manually enable Microsoft Search only for a Team Site or Publishing Site (template ids that contain "STS", "CMSPUBLISHING", "BLANKINTERNET" and "GROUP").</span></span>