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
description: Use consultas de búsqueda de SharePoint para crear resultados de trabajo para Búsqueda de Microsoft
ms.openlocfilehash: 6e55e2000792bdb576a18a0efeb353dc3ea13605
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968455"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="54539-103">Importar resultados y consultas principales promocionados de SharePoint</span><span class="sxs-lookup"><span data-stu-id="54539-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54539-104">Búsqueda de Microsoft en la configuración de Bing ya está disponible en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="54539-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="54539-105">Empiece por [asignar administradores de búsqueda](https://docs.microsoft.com/es-ES/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="54539-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="54539-106">Para sacar provecho de las consultas de los usuarios y los resultados más probables que haya creado en SharePoint, Búsqueda de Microsoft incluye dos herramientas para importar esta información como marcadores sugeridos: </span><span class="sxs-lookup"><span data-stu-id="54539-106">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="54539-107">Importar reglas de consulta de resultados promocionados de SharePoint</span><span class="sxs-lookup"><span data-stu-id="54539-107">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="54539-108">Importe estas reglas, anteriormente denominadas resultados más probables, como marcadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="54539-108">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="54539-109">Para que estén disponibles para los usuarios, publíquelas.</span><span class="sxs-lookup"><span data-stu-id="54539-109">To make them available to your users, publish them.</span></span> <span data-ttu-id="54539-110">El tiempo de publicación varía según el número de marcadores que seleccione.</span><span class="sxs-lookup"><span data-stu-id="54539-110">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="54539-111">Importar las consultas principales de SharePoint con PowerShell</span><span class="sxs-lookup"><span data-stu-id="54539-111">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="54539-112">Descargue las consultas principales de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="54539-112">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="54539-113">El script de PowerShell le pedirá sus credenciales de administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="54539-113">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="54539-114">Ejecute una búsqueda de SharePoint para cada una de las consultas principales para obtener el resultado de búsqueda superior.</span><span class="sxs-lookup"><span data-stu-id="54539-114">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="54539-115">Agregar marcadores sugeridos al portal de administración.</span><span class="sxs-lookup"><span data-stu-id="54539-115">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="54539-116">Las consultas principales de SharePoint son excelentes candidatos para los marcadores.</span><span class="sxs-lookup"><span data-stu-id="54539-116">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="54539-117">Use el script de PowerShell para importarlos como marcadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="54539-117">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="54539-118">Este script hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="54539-118">This script will:</span></span>
    
<span data-ttu-id="54539-119">Descargue el script y abra el archivo Léame para obtener información sobre los requisitos, ejemplos y parámetros disponibles.</span><span class="sxs-lookup"><span data-stu-id="54539-119">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="54539-120">Después que se ejecute el script de PowerShell, un administrador o editor debe revisar los marcadores sugeridos y realizar los cambios necesarios antes de que se publiquen.</span><span class="sxs-lookup"><span data-stu-id="54539-120">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

