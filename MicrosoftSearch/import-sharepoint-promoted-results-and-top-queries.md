---
title: Importar resultados de SharePoint promocionados y consultas principales
ms.author: dawholl
author: dawholl
manager: kellis
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
description: Use consultas de búsqueda desde SharePoint para crear resultados de trabajo para Búsqueda de Microsoft
ms.openlocfilehash: cfd5fafd0529f537a55e436ef078800a4b9714177e04c63e65e968f16fcf322e
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533828"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importar resultados de SharePoint promocionados y consultas principales

> [!IMPORTANT]
> Este artículo se aplica a la Búsqueda de Microsoft en el portal Bing administración. Estamos pasando el portal al Centro de administración de Microsoft 365. Luego, se quitará el portal de Búsqueda de Microsoft en Bing. Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar. [Introducción a Microsoft Search (Búsqueda de Microsoft)](overview-microsoft-search.md).
    
Para aprovechar las consultas de los usuarios y las opciones más seguras que ha creado en SharePoint, Búsqueda de Microsoft dos herramientas para importar esta información como marcadores sugeridos: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importar SharePoint de consulta de resultados promocionadas

Importe estas reglas, anteriormente denominadas Resultados más recomendados, como marcadores sugeridos. Para que estén disponibles para los usuarios, publirándolos. El tiempo de publicación varía en función del número de marcadores que seleccione.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importar consultas SharePoint con PowerShell

- Descargue las consultas principales de su SharePoint. El script de PowerShell le pedirá las credenciales SharePoint administrador.
    
- Ejecute una SharePoint búsqueda para cada una de las consultas superiores para obtener el resultado de la búsqueda superior.
    
- Agregue marcadores sugeridos al portal de administración.
    
- Las consultas SharePoint principales son excelentes candidatos para marcadores. Use el script de PowerShell para importarlos como marcadores sugeridos. Este script realiza el siguiente trabajo:
    - Agrega marcadores sugeridos basados SharePoint consultas principales para mejorar Búsqueda de Microsoft de marcadores. Este script descarga las consultas principales accesibles desde el portal de administración de SharePoint y, SharePoint continuación, las carga como marcadores sugeridos para que un administrador las revise en el portal de administración de Búsqueda de Microsoft administración.
    - De forma predeterminada, el script agrega marcadores sugeridos a un espacio empresarial determinado durante todos los meses disponibles. Obtiene las consultas principales de un sitio SharePoint de administración y las agrega a Búsqueda de Microsoft como marcadores sugeridos. Los marcadores sugeridos necesitan un administrador/editor para aprobarlos en el portal de administración antes de publicarse. Al ejecutar este script, se le pedirán credenciales para obtener acceso al portal Búsqueda de Microsoft administración.
    - El script permite especificar parámetros adicionales. Por ejemplo, puede agregar marcadores sugeridos a un espacio empresarial determinado para las consultas N principales en cada uno de los meses disponibles.
    - Opcionalmente, puede agregar marcadores sugeridos a un inquilino determinado durante meses en el año determinado. Este comando obtiene las consultas principales para el período de tiempo dado desde SharePoint sitio web de administración y las agrega Búsqueda de Microsoft como marcadores sugeridos.
    - As well, there are numerous other options and command modes: download top queries from SharePoint to a specified folder, run the script in Caja fuerte mode, run the script in Verbose mode, and a Debug mode.
    - Descargue el script [aquí](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip). 

Para obtener información sobre los requisitos, ejemplos y parámetros disponibles, descargue el script y revise el archivo README. Una vez que se ejecuta el script de PowerShell, un administrador o editor debe revisar los marcadores sugeridos y realizar las modificaciones necesarias antes de publicarlos.