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
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importación SharePoint promocionados principales consultas y resultados

Para poder aprovechar las consultas de los usuarios y los resultados más probables se ha creado en SharePoint, Microsoft Search incluye dos herramientas para importar esta información como marcadores sugeridos: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importación SharePoint promocionados reglas de consulta de resultados

Importar estas reglas, denominado anteriormente las opciones más probables, como marcadores sugeridos. Para que estén disponibles para los usuarios, publicarlos. Publicación de tiempo varía según el número de marcadores que seleccione.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importar principales consultas de SharePoint con PowerShell

- Descargue las consultas principales de la base de SharePoint. La secuencia de comandos de PowerShell le pedirá que sus credenciales de administrador de SharePoint.
    
- Ejecutar una búsqueda de SharePoint para cada uno de los principales consultas para obtener los resultados de búsqueda principales.
    
- Agregar marcadores sugeridos para el portal de administración.
    
- Las consultas principales de SharePoint son candidatos excelentes para marcadores. Use el script de PowerShell para importarlos como marcadores sugeridos. Esta secuencia de comandos hará lo siguiente:
    
Para obtener información acerca de los requisitos, ejemplos y parámetros disponibles, descargue la secuencia de comandos y revise el archivo Léame. Después de la secuencia de comandos de PowerShell se ejecuta, un administrador o editor debe revisar los marcadores sugeridos y realice las modificaciones necesarias antes de publicarlas.

  

