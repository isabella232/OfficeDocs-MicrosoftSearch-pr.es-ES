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
# <a name="search-box-settings-on-sharepoint-sites"></a><span data-ttu-id="c7b51-103">Configuración del cuadro de búsqueda en sitios de SharePoint</span><span class="sxs-lookup"><span data-stu-id="c7b51-103">Search box settings on SharePoint sites</span></span>

<span data-ttu-id="c7b51-104">Una de las distintas formas en que Microsoft Search puede personalizarse en los sitios de SharePoint es personalizar el modo en que el cuadro de búsqueda de la barra de navegación de la Suite funciona en los sitios de SharePoint para ajustarse mejor a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="c7b51-104">One of the several ways Microsoft Search can be customized on SharePoint sites is to tailor how the search box in the suite navigation bar works in SharePoint sites to best fit your needs.</span></span>

<span data-ttu-id="c7b51-105">Para otras opciones de personalización, vea [cambiar la página de resultados de búsqueda de Microsoft para agregar verticales personalizados, tipos de resultados y diseños](customize-search-page.md)y [crear una página de resultados de búsqueda personalizada](create-search-results-pages.md).</span><span class="sxs-lookup"><span data-stu-id="c7b51-105">For other customization options, see [Changing the Microsoft Search results page to add custom verticals, result types and layouts](customize-search-page.md), and [Creating a custom search results page](create-search-results-pages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c7b51-106">El cuadro de búsqueda de la barra de navegación de Suite no está disponible para todos los clientes en este momento, pero estas opciones todavía pueden establecerse y tendrán efecto cuando esté disponible.</span><span class="sxs-lookup"><span data-stu-id="c7b51-106">The suite navigation bar search box is not available for all customers at this time, but these options can still be set now and they will take effect when it becomes available.</span></span>

<span data-ttu-id="c7b51-107">Para las tareas que se enumeran a continuación, usará PowerShell con extensiones de PowerShell de PnP de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c7b51-107">For the tasks listed below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="c7b51-108">Puede instalar y obtener más información sobre cómo empezar [aquí](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="c7b51-108">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="c7b51-109">Deberá iniciar sesión en el sitio o en la colección de sitios con este comando:</span><span class="sxs-lookup"><span data-stu-id="c7b51-109">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a><span data-ttu-id="c7b51-110">Cambiar el ámbito de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="c7b51-110">Changing the scope of search</span></span>

<span data-ttu-id="c7b51-111">Cuando se crea un nuevo sitio en SharePoint Online y se escribe en el cuadro de búsqueda, se le lleva a la página de resultados de búsqueda de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7b51-111">When you create a new site in SharePoint Online today, and type into the search box, you are taken to the Microsoft Search results page.</span></span> <span data-ttu-id="c7b51-112">Esta página muestra los resultados de su sitio actual de forma predeterminada y le permite ampliar el ámbito de la búsqueda al concentrador al que está asociado el sitio actual (si hay alguno) o a toda la organización.</span><span class="sxs-lookup"><span data-stu-id="c7b51-112">This page shows results from your current site by default and allows you to expand the scope of your search to the hub that the current site is associated with (if there is one), or to the whole organization.</span></span>

<span data-ttu-id="c7b51-113">De forma predeterminada, el ámbito que usa el cuadro de búsqueda depende del tipo de sitio.</span><span class="sxs-lookup"><span data-stu-id="c7b51-113">The scope the search box uses, by default, depends on type of site.</span></span>

* <span data-ttu-id="c7b51-114">Búsqueda de sitios regulares en el sitio actual.</span><span class="sxs-lookup"><span data-stu-id="c7b51-114">Regular sites search over the current site.</span></span>
* <span data-ttu-id="c7b51-115">Sitios de concentradores busque en todos los sitios del concentrador.</span><span class="sxs-lookup"><span data-stu-id="c7b51-115">Hub sites search over all sites in the hub.</span></span>
* <span data-ttu-id="c7b51-116">Sitios principales busca en todo el contenido.</span><span class="sxs-lookup"><span data-stu-id="c7b51-116">Home sites search over all content.</span></span>

<span data-ttu-id="c7b51-117">En algunos casos, es posible que desee cambiar estos valores predeterminados para que siempre se busque en toda la organización o en el concentrador al que está asociado un sitio, sin necesidad de hacer clic adicional.</span><span class="sxs-lookup"><span data-stu-id="c7b51-117">In some cases, you may want to change these defaults to always search over the whole organization, or across the hub a site is associated with, without needing an additional click.</span></span>

<span data-ttu-id="c7b51-118">Como propietario de un sitio, puede cambiar estos valores predeterminados mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c7b51-118">As a site owner, you can change these defaults using the following command:</span></span>

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

<span data-ttu-id="c7b51-119">Después de ejecutar este comando, el sitio que anteriormente mostraba los resultados del sitio actual de forma predeterminada empezará a mostrar resultados de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="c7b51-119">After running this command, the site that was previously showing results from the current site by default will start to show results from the whole organization.</span></span>

<span data-ttu-id="c7b51-120">Para volver a la configuración predeterminada, ejecute el comando de nuevo con el valor "DefaultScope".</span><span class="sxs-lookup"><span data-stu-id="c7b51-120">To go back to the default setting, run the command again with the value “DefaultScope".</span></span> <span data-ttu-id="c7b51-121">Para buscar en el concentrador, use "Hub" como el valor de SearchScope.</span><span class="sxs-lookup"><span data-stu-id="c7b51-121">To search across the Hub, use “Hub” as the SearchScope value.</span></span>

<span data-ttu-id="c7b51-122">Esta configuración se aplica en el nivel de sitio individual.</span><span class="sxs-lookup"><span data-stu-id="c7b51-122">This setting applies at the individual site level.</span></span> <span data-ttu-id="c7b51-123">No hay una configuración equivalente para las colecciones de sitios.</span><span class="sxs-lookup"><span data-stu-id="c7b51-123">There is no equivalent setting for site collections.</span></span>

## <a name="show-or-hide-the-search-box"></a><span data-ttu-id="c7b51-124">Mostrar u ocultar el cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="c7b51-124">Show or hide the search box</span></span>

<span data-ttu-id="c7b51-125">Puede elegir ocultar el cuadro de búsqueda de la barra de navegación de Suite si desea evitar que los usuarios busquen o usen una implementación de cuadro de búsqueda personalizada.</span><span class="sxs-lookup"><span data-stu-id="c7b51-125">You can choose to hide the suite navigation bar search box if you want to prevent your users from searching or to use a custom search box implementation.</span></span>

<span data-ttu-id="c7b51-126">Para cambiar esta configuración en un sitio determinado, use este comando:</span><span class="sxs-lookup"><span data-stu-id="c7b51-126">To change this setting for a given site use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="c7b51-127">Como alternativa, si desea establecerla para todos los sitios de una colección de sitios, puede usar este comando:</span><span class="sxs-lookup"><span data-stu-id="c7b51-127">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="c7b51-128">Después de ejecutar estos comandos, el cuadro de búsqueda ya no aparecerá en la barra de navegación de la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="c7b51-128">After running these commands, the search box will no longer show up in the navigation bar on top of your page.</span></span> <span data-ttu-id="c7b51-129">Para volver a mostrar el cuadro de búsqueda, ejecute los comandos de nuevo con el valor proporcionado al parámetro "SearchBoxInNavBar" en "inherit".</span><span class="sxs-lookup"><span data-stu-id="c7b51-129">To go back to showing the search box, run the commands again with the value provided to "SearchBoxInNavBar" parameter to “Inherit”.</span></span>

<span data-ttu-id="c7b51-130">Hay varios puntos a tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="c7b51-130">There are several points to consider:</span></span>

* <span data-ttu-id="c7b51-131">Esta configuración solo se aplica al cuadro de búsqueda de la barra de navegación del conjunto de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c7b51-131">This setting only applies to the search box in the suite navigation bar.</span></span> <span data-ttu-id="c7b51-132">No se aplica a los cuadros de búsqueda que se encuentran en la página ni a los cuadros de búsqueda de las páginas clásicas.</span><span class="sxs-lookup"><span data-stu-id="c7b51-132">It does not apply to search boxes that are in the page, or to search boxes on classic pages.</span></span>

* <span data-ttu-id="c7b51-133">Una vez que haya deshabilitado el cuadro de búsqueda en la barra de navegación, si desea una funcionalidad de búsqueda en el sitio, tendrá que proporcionarlo con un elemento web personalizado o con una extensión de SharePoint Framework.</span><span class="sxs-lookup"><span data-stu-id="c7b51-133">Once you’ve disabled the search box in the navigation bar, if you want search functionality in your site, you will have to provide it yourself using a custom web part or a SharePoint Framework extension.</span></span>

* <span data-ttu-id="c7b51-134">Esta solución también quitará el cuadro de búsqueda de las listas y bibliotecas del sitio.</span><span class="sxs-lookup"><span data-stu-id="c7b51-134">This solution will remove the search box from lists and libraries for your site as well.</span></span> <span data-ttu-id="c7b51-135">La solución de búsqueda personalizada debe tener en cuenta las búsquedas contextuales de las listas y bibliotecas de SharePoint, además de la búsqueda en todo el sitio.</span><span class="sxs-lookup"><span data-stu-id="c7b51-135">Your custom search solution will need to consider contextual searches for SharePoint lists and libraries, in addition to site-wide search.</span></span>

* <span data-ttu-id="c7b51-136">Si aplica la configuración al sitio raíz de su dominio, la página de inicio de SharePoint también dejará de mostrar el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c7b51-136">If you apply the setting to the root site of your domain, the SharePoint start page will also stop showing the search box.</span></span>

## <a name="changing-the-hint-displayed-in-the-search-box"></a><span data-ttu-id="c7b51-137">Cambio de la sugerencia mostrada en el cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="c7b51-137">Changing the hint displayed in the search box</span></span>

<span data-ttu-id="c7b51-138">Puede cambiar la sugerencia que muestra el cuadro de búsqueda para un sitio o una colección de sitios determinados.</span><span class="sxs-lookup"><span data-stu-id="c7b51-138">You can change the hint the search box shows for a given site or site collection.</span></span> <span data-ttu-id="c7b51-139">Este es el texto que aparece en el cuadro de búsqueda antes de empezar a escribir en él.</span><span class="sxs-lookup"><span data-stu-id="c7b51-139">This is the text that appears in the search box before they start typing into it.</span></span> <span data-ttu-id="c7b51-140">Esto puede ayudar a los usuarios a saber lo que cabe esperar de la búsqueda si ha configurado una página de resultados personalizada o cambiado el comportamiento de la búsqueda de otras formas.</span><span class="sxs-lookup"><span data-stu-id="c7b51-140">This may help guide your users about what to expect from search if you’ve configured a custom results page or changed behavior of search in other ways.</span></span>

> [!NOTE]
> <span data-ttu-id="c7b51-141">Para poder realizar este cambio, debe permitir la ejecución de scripts personalizados en el sitio en cuestión como administrador de inquilinos, que no se permite de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c7b51-141">To be able to make this change, you need to allow running custom scripts on the site in question as a tenant administrator, which is disallowed by default.</span></span> <span data-ttu-id="c7b51-142"> https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-scriptPara obtener más información, consulte.</span><span class="sxs-lookup"><span data-stu-id="c7b51-142">Please see https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script for details.</span></span> <span data-ttu-id="c7b51-143">Puede permitir la ejecución de scripts personalizados, realizar el cambio y, a continuación, revertir a no permitir scripts para el sitio si es necesario.</span><span class="sxs-lookup"><span data-stu-id="c7b51-143">You can allow running custom scripts, make the change, and then revert to disallowing scripts for the site if necessary.</span></span>

<span data-ttu-id="c7b51-144">Para cambiar esta configuración en un sitio determinado, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c7b51-144">To change this setting for a given site run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="c7b51-145">Como alternativa, si desea establecerla para todos los sitios de una colección de sitios, puede usar este comando:</span><span class="sxs-lookup"><span data-stu-id="c7b51-145">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="c7b51-146">Para volver al texto del marcador de posición predeterminado, establezca el valor en blanco ("").</span><span class="sxs-lookup"><span data-stu-id="c7b51-146">To go back to the default placeholder text, set the value to be blank ("").</span></span>
