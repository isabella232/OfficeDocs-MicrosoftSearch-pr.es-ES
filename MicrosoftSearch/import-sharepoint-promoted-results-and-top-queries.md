---
title: Importar resultados de SharePoint promocionados y consultas principales
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
description: Usar consultas de búsqueda de SharePoint para crear resultados de trabajo para Microsoft Search
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508757"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="ded33-103">Importar resultados de SharePoint promocionados y consultas principales</span><span class="sxs-lookup"><span data-stu-id="ded33-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="ded33-104">Para aprovechar las consultas de los usuarios y los resultados más probables que haya creado en SharePoint, Microsoft Search incluye dos herramientas para importar esta información como marcadores sugeridos:</span><span class="sxs-lookup"><span data-stu-id="ded33-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="ded33-105">Importar reglas de consulta de resultados promocionados de SharePoint</span><span class="sxs-lookup"><span data-stu-id="ded33-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="ded33-106">Importe estas reglas, denominadas más probables anteriormente, como marcadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="ded33-106">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="ded33-107">Para que estén disponibles para los usuarios, publíquelos.</span><span class="sxs-lookup"><span data-stu-id="ded33-107">To make them available to your users, publish them.</span></span> <span data-ttu-id="ded33-108">El tiempo de publicación varía en función del número de marcadores que seleccione.</span><span class="sxs-lookup"><span data-stu-id="ded33-108">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="ded33-109">Importar las consultas principales de SharePoint con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ded33-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="ded33-110">Descargue las consultas principales desde SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ded33-110">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="ded33-111">El script de PowerShell le pedirá sus credenciales de administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ded33-111">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="ded33-112">Ejecute una búsqueda de SharePoint para cada una de las consultas principales para obtener el resultado de la búsqueda más arriba.</span><span class="sxs-lookup"><span data-stu-id="ded33-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="ded33-113">Agregue marcadores sugeridos al portal de administración.</span><span class="sxs-lookup"><span data-stu-id="ded33-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="ded33-114">Las consultas más importantes de SharePoint son candidatas excelentes para los marcadores.</span><span class="sxs-lookup"><span data-stu-id="ded33-114">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="ded33-115">Use el script de PowerShell para importarlos como marcadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="ded33-115">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="ded33-116">Este script hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ded33-116">This script will:</span></span>
    
<span data-ttu-id="ded33-117">Para obtener información acerca de los requisitos, ejemplos y parámetros disponibles, descargue el script y revise el archivo Léame.</span><span class="sxs-lookup"><span data-stu-id="ded33-117">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="ded33-118">Una vez ejecutado el script de PowerShell, un administrador o editor debe revisar los marcadores sugeridos y realizar las modificaciones necesarias antes de que se publiquen.</span><span class="sxs-lookup"><span data-stu-id="ded33-118">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

