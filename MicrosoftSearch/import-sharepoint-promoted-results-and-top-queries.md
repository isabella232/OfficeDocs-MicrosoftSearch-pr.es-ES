---
title: Importación SharePoint promocionados principales consultas y resultados
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
description: Use las consultas de búsqueda de SharePoint para crear resultados de trabajo de Microsoft Search
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379267"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="c892e-103">Importación SharePoint promocionados principales consultas y resultados</span><span class="sxs-lookup"><span data-stu-id="c892e-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="c892e-104">Para poder aprovechar las consultas de los usuarios y los resultados más probables se ha creado en SharePoint, Microsoft Search incluye dos herramientas para importar esta información como marcadores sugeridos:</span><span class="sxs-lookup"><span data-stu-id="c892e-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="c892e-105">Importación SharePoint promocionados reglas de consulta de resultados</span><span class="sxs-lookup"><span data-stu-id="c892e-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="c892e-p101">Importar estas reglas, denominado anteriormente las opciones más probables, como marcadores sugeridos. Para que estén disponibles para los usuarios, publicarlos. Publicación de tiempo varía según el número de marcadores que seleccione.</span><span class="sxs-lookup"><span data-stu-id="c892e-p101">Import these rules, previously called Best Bets, as suggested bookmarks. To make them available to your users, publish them. Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="c892e-109">Importar principales consultas de SharePoint con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c892e-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="c892e-p102">Descargue las consultas principales de la base de SharePoint. La secuencia de comandos de PowerShell le pedirá que sus credenciales de administrador de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c892e-p102">Download the top queries from your SharePoint. The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="c892e-112">Ejecutar una búsqueda de SharePoint para cada uno de los principales consultas para obtener los resultados de búsqueda principales.</span><span class="sxs-lookup"><span data-stu-id="c892e-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="c892e-113">Agregar marcadores sugeridos para el portal de administración.</span><span class="sxs-lookup"><span data-stu-id="c892e-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="c892e-p103">Las consultas principales de SharePoint son candidatos excelentes para marcadores. Use el script de PowerShell para importarlos como marcadores sugeridos. Esta secuencia de comandos hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c892e-p103">Your top SharePoint queries are excellent candidates for bookmarks. Use the PowerShell script to import them as suggested bookmarks. This script will:</span></span>
    
<span data-ttu-id="c892e-p104">Para obtener información acerca de los requisitos, ejemplos y parámetros disponibles, descargue la secuencia de comandos y revise el archivo Léame. Después de la secuencia de comandos de PowerShell se ejecuta, un administrador o editor debe revisar los marcadores sugeridos y realice las modificaciones necesarias antes de publicarlas.</span><span class="sxs-lookup"><span data-stu-id="c892e-p104">For information about requirements, examples, and available parameters, download the script and review the README file. After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

