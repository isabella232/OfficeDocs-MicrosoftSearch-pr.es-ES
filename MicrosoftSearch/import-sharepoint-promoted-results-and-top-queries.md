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
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importar resultados de SharePoint promocionados y consultas principales

Para aprovechar las consultas de los usuarios y los resultados más probables que haya creado en SharePoint, Microsoft Search incluye dos herramientas para importar esta información como marcadores sugeridos: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importar reglas de consulta de resultados promocionados de SharePoint

Importe estas reglas, denominadas más probables anteriormente, como marcadores sugeridos. Para que estén disponibles para los usuarios, publíquelos. El tiempo de publicación varía en función del número de marcadores que seleccione.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importar las consultas principales de SharePoint con PowerShell

- Descargue las consultas principales desde SharePoint. El script de PowerShell le pedirá sus credenciales de administrador de SharePoint.
    
- Ejecute una búsqueda de SharePoint para cada una de las consultas principales para obtener el resultado de la búsqueda más arriba.
    
- Agregue marcadores sugeridos al portal de administración.
    
- Las consultas más importantes de SharePoint son candidatas excelentes para los marcadores. Use el script de PowerShell para importarlos como marcadores sugeridos. Este script hará lo siguiente:
    
Para obtener información acerca de los requisitos, ejemplos y parámetros disponibles, descargue el script y revise el archivo Léame. Una vez ejecutado el script de PowerShell, un administrador o editor debe revisar los marcadores sugeridos y realizar las modificaciones necesarias antes de que se publiquen.

  

