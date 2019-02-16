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
description: Agregar muchas ubicaciones a la vez con herramientas de importación para el portal de administración de Microsoft Search
ms.openlocfilehash: eb51b93ceaa560e5142ac46d316ba745c614fe34
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068414"
---
# <a name="bulk-create-locations"></a>Crear ubicaciones de forma masiva

Descargue y use la plantilla. csv para crear, editar y guardar ubicaciones en masa. 
  
1. En la esquina superior derecha de la sección ubicaciones, haga clic en **importar** .
    
2. Haga clic en **Descargar ubicación de plantilla (. csv)**
    
3. Guardar y abrir el archivo. csv
    
4. Agregar el contenido de ubicación y guardar el archivo
    
5. En la esquina superior derecha de la sección ubicaciones, haga clic en **importar** .
    
6. En el panel ubicaciones de importación, haga clic en **examinar** y navegue hasta el archivo. csv que desea importar. 
    
7. Haga clic en **importar**

Los campos de las plantillas de ubicaciones de importación y exportación son los mismos. Puede exportar, editar en masa e importar las ediciones o empezar con una plantilla vacía para crear en masa nuevas ubicaciones. Para editar en masa las ubicaciones existentes, exportas del portal de administración, realice las modificaciones necesarias y, a continuación, impórtelas.

# <a name="prevent-import-errors"></a>Impedir errores de importación  
Recibirá un error si faltan datos necesarios o no son válidos. Según el error, es posible que se genere un archivo de registro con más información sobre las filas y las columnas que deben corregirse. Realice las modificaciones necesarias e intente importar el archivo de nuevo.
  
> [!NOTE]
> Hasta que se resuelvan todos los errores, no podrá crear ni editar ninguna ubicación. 

Para ayudar a evitar errores, asegúrese de que el archivo de importación tiene el formato correcto:
- Incluye la fila de encabezado que estaba en la plantilla de importación
- Incluye todas las columnas que estaban en la plantilla de importación
- El orden de las columnas es el mismo que el de la plantilla de importación
- Estas columnas pueden estar vacías: ID, última modificación, última modificación por y lat/long  
Intentaremos determinar lat/long en función de la dirección si el campo está vacío
- La columna Estado no puede estar vacía, se requiere esta información  
Según el campo de estado, las ubicaciones se guardarán como borrador, sugerida, programada o se publicarán automáticamente.

Además, si incluye el identificador de una ubicación existente, se reemplazará con la información del archivo de importación.

En el caso de organizaciones con varios inquilinos, puede exportar sus ubicaciones de un inquilino e importarlas a otro. Sin embargo, debe quitar todos los datos de la columna ID antes de importar.
  
Para obtener más información acerca de los campos obligatorios y recomendados, vea [Agregar una ubicación](add-a-location.md).

  

