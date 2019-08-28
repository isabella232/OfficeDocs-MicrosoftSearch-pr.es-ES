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
ROBOTS: NOINDEX
description: Usar consultas de búsqueda de SharePoint para crear resultados de trabajo para Microsoft Search
ms.openlocfilehash: ebfd10f8705ce5b9a36b9c13d549e28a3f1c6b91
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639806"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importar resultados de SharePoint promocionados y consultas principales

> [!IMPORTANT]
> Este artículo se aplica a la búsqueda de Microsoft en el portal de administración de Bing. Estamos moviendo el portal al centro de administración de 365 de Microsoft y, a continuación, se quitará el portal de Microsoft Search en Bing. Le recomendamos que use el centro de administración de Microsoft 365 para empezar. [Información general de Microsoft Search](overview-microsoft-search.md).
    
Para aprovechar las consultas de los usuarios y los resultados más probables que haya creado en SharePoint, Microsoft Search incluye dos herramientas para importar esta información como marcadores sugeridos: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importar reglas de consulta de resultados promocionados de SharePoint

Importe estas reglas, denominadas más probables anteriormente, como marcadores sugeridos. Para que estén disponibles para los usuarios, publíquelos. El tiempo de publicación varía en función del número de marcadores que seleccione.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importar las consultas principales de SharePoint con PowerShell

- Descargue las consultas principales desde SharePoint. El script de PowerShell le pedirá sus credenciales de administrador de SharePoint.
    
- Ejecute una búsqueda de SharePoint para cada una de las consultas principales para obtener el resultado de la búsqueda más arriba.
    
- Agregue marcadores sugeridos al portal de administración.
    
- Las consultas más importantes de SharePoint son candidatas excelentes para los marcadores. Use el script de PowerShell para importarlos como marcadores sugeridos. Este script hace el siguiente trabajo:
    - Agrega marcadores sugeridos basados en consultas Top de SharePoint para mejorar la cobertura de marcadores de Microsoft Search. Este script descarga las consultas principales accesibles desde el portal de administración de SharePoint y, a continuación, las carga como marcadores sugeridos para que un administrador los Revise en el portal de administración de Microsoft Search.
    - De forma predeterminada, el script agrega marcadores sugeridos al inquilino determinado para todos los meses disponibles. Obtiene las consultas principales de un sitio web de administración de SharePoint determinado y las agrega a Microsoft Search como marcadores sugeridos. Los marcadores sugeridos necesitan un administrador/editor para aprobarlos en el portal de administración antes de publicarlos. Al ejecutar este script, se le pedirán las credenciales para obtener acceso al portal de administración de Microsoft Search.
    - El script permite especificar parámetros adicionales. Por ejemplo, puede agregar marcadores sugeridos a un inquilino determinado para las N principales consultas en cada uno de los meses disponibles.
    - Opcionalmente, puede agregar marcadores sugeridos a un inquilino determinado para los meses del año en cuestión. Este comando obtiene las consultas principales para el período de tiempo determinado desde el sitio web de administración de SharePoint y las agrega a Microsoft Search como marcadores sugeridos.
    - Además, hay muchas otras opciones y modos de comando: descargar las consultas principales de SharePoint en una carpeta específica, ejecutar el script en modo seguro, ejecutar el script en modo detallado y un modo de depuración.
    - Descargue el script [aquí](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip). 

Para obtener información acerca de los requisitos, ejemplos y parámetros disponibles, descargue el script y revise el archivo Léame. Una vez ejecutado el script de PowerShell, un administrador o editor debe revisar los marcadores sugeridos y realizar las modificaciones necesarias antes de que se publiquen.