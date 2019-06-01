---
title: Importar resultados y consultas principales promocionados de SharePoint
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/8/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
ROBOTS: NOINDEX
description: Use consultas de búsqueda de SharePoint para crear resultados de trabajo para Búsqueda de Microsoft
ms.openlocfilehash: 1538c57a7b4138b36fe62e3076feb58d746b2b3e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591606"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="6b94e-103">Importar resultados promocionados y consultas principales de SharePoint</span><span class="sxs-lookup"><span data-stu-id="6b94e-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b94e-104">Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing</span><span class="sxs-lookup"><span data-stu-id="6b94e-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="6b94e-105">Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se quitará.</span><span class="sxs-lookup"><span data-stu-id="6b94e-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="6b94e-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="6b94e-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="6b94e-107">[Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="6b94e-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="6b94e-108">Para sacar provecho de las consultas de los usuarios y los resultados más probables que haya creado en SharePoint, Búsqueda de Microsoft incluye dos herramientas para importar esta información como marcadores sugeridos: </span><span class="sxs-lookup"><span data-stu-id="6b94e-108">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="6b94e-109">Importar reglas de consulta de resultados promocionados de SharePoint</span><span class="sxs-lookup"><span data-stu-id="6b94e-109">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="6b94e-110">Importe estas reglas, anteriormente denominadas resultados más probables, como marcadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="6b94e-110">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="6b94e-111">Para que estén disponibles para los usuarios, publíquelas.</span><span class="sxs-lookup"><span data-stu-id="6b94e-111">To make them available to your users, publish them.</span></span> <span data-ttu-id="6b94e-112">El tiempo de publicación varía según el número de marcadores que seleccione.</span><span class="sxs-lookup"><span data-stu-id="6b94e-112">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="6b94e-113">Importar las consultas principales de SharePoint con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b94e-113">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="6b94e-114">Descargue las consultas principales de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6b94e-114">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="6b94e-115">El script de PowerShell le pedirá sus credenciales de administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6b94e-115">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="6b94e-116">Ejecute una búsqueda de SharePoint para cada una de las consultas principales para obtener el resultado de búsqueda superior.</span><span class="sxs-lookup"><span data-stu-id="6b94e-116">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="6b94e-117">Agregar marcadores sugeridos al portal de administración.</span><span class="sxs-lookup"><span data-stu-id="6b94e-117">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="6b94e-118">Las consultas principales de SharePoint son excelentes candidatos para los marcadores.</span><span class="sxs-lookup"><span data-stu-id="6b94e-118">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="6b94e-119">Use el script de PowerShell para importarlos como marcadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="6b94e-119">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="6b94e-120">Este script hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6b94e-120">This script will:</span></span>
    
<span data-ttu-id="6b94e-121">Descargue el script y abra el archivo Léame para obtener información sobre los requisitos, ejemplos y parámetros disponibles.</span><span class="sxs-lookup"><span data-stu-id="6b94e-121">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="6b94e-122">Después que se ejecute el script de PowerShell, un administrador o editor debe revisar los marcadores sugeridos y realizar los cambios necesarios antes de que se publiquen.</span><span class="sxs-lookup"><span data-stu-id="6b94e-122">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

