---
title: Crear ubicaciones de forma masiva
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
ROBOTS: NoIndex
description: Agregar muchas ubicaciones a la vez con herramientas de importación para el portal de administración de Microsoft Search
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948982"
---
# <a name="bulk-create-locations"></a>Crear ubicaciones de forma masiva

> [!IMPORTANT]
> Este artículo se aplica al portal de administración de Búsqueda de Microsoft en Bing. Estamos pasando el portal al Centro de administración de Microsoft 365. Luego, se quitará el portal de Búsqueda de Microsoft en Bing. Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar. [Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).
    
Descargue y use la plantilla. csv para crear, editar y guardar ubicaciones en masa. 
  
1. En la esquina superior derecha de la sección ubicaciones, haga clic en **importar** .
    
2. Haga clic en **Descargar ubicación de plantilla (. csv)**
    
3. Guarde y abra el archivo .csv
    
4. Agregar el contenido de ubicación y guardar el archivo

    El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación
    
5. En la esquina superior derecha de la sección ubicaciones, haga clic en **importar** .
    
6. En el panel ubicaciones de importación, haga clic en **examinar** y navegue hasta el archivo. csv que desea importar. 
    
7. Haga clic en **Importar**

Los campos de las plantillas de ubicaciones de importación y exportación son los mismos. Puede exportar, editar en masa e importar las ediciones o empezar con una plantilla vacía para crear en masa nuevas ubicaciones. Para editar en masa las ubicaciones existentes, exportas del portal de administración, realice las modificaciones necesarias y, a continuación, impórtelas.

## <a name="prevent-import-errors"></a>Evitar errores de importación  
Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos. Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse. Realice los cambios necesarios e intente importar de nuevo el archivo.
  
> [!NOTE]
> Hasta que se resuelvan todos los errores, no podrá crear ni editar ninguna ubicación. 

Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:
- Incluye la fila de encabezado que se encontraba en la plantilla de importación
- Incluye todas las columnas que se encontraban en la plantilla de importación
- El orden de las columnas es el mismo que el orden en la plantilla de importación
- Estas columnas pueden estar vacías: ID, última modificación, última modificación por y lat/long  
Intentaremos determinar lat/long en función de la dirección si el campo está vacío
- La columna Estado no puede estar vacía, puesto que esta información es necesaria  
Según el campo de estado, las ubicaciones se guardarán como borrador, sugerida, programada o se publicarán automáticamente.

Además, si incluye el identificador de una ubicación existente, se reemplazará con la información del archivo de importación.

Para los asociados que administran varias organizaciones, puede exportar sus ubicaciones de una organización e importarlas a otra. Pero, debe eliminar todos los datos de la columna Id. antes de la importación.
  
Para obtener más información acerca de los campos obligatorios y recomendados, vea [Agregar una ubicación](add-a-location.md).

  

