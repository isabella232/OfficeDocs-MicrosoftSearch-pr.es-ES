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
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importar resultados promocionados y consultas principales de SharePoint

> [!IMPORTANT]
> Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se quitará. Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar. [Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).
    
Para sacar provecho de las consultas de los usuarios y los resultados más probables que haya creado en SharePoint, Búsqueda de Microsoft incluye dos herramientas para importar esta información como marcadores sugeridos:  
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importar reglas de consulta de resultados promocionados de SharePoint

Importe estas reglas, anteriormente denominadas resultados más probables, como marcadores sugeridos. Para que estén disponibles para los usuarios, publíquelas. El tiempo de publicación varía según el número de marcadores que seleccione.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importar las consultas principales de SharePoint con PowerShell

- Descargue las consultas principales de SharePoint. El script de PowerShell le pedirá sus credenciales de administrador de SharePoint.
    
- Ejecute una búsqueda de SharePoint para cada una de las consultas principales para obtener el resultado de búsqueda superior.
    
- Agregar marcadores sugeridos al portal de administración.
    
- Las consultas principales de SharePoint son excelentes candidatos para los marcadores. Use el script de PowerShell para importarlos como marcadores sugeridos. Este script hará lo siguiente:
    
Descargue el script y abra el archivo Léame para obtener información sobre los requisitos, ejemplos y parámetros disponibles. Después que se ejecute el script de PowerShell, un administrador o editor debe revisar los marcadores sugeridos y realizar los cambios necesarios antes de que se publiquen.

  

