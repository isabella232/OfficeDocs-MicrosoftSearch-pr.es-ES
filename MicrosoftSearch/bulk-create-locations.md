---
title: Crear ubicaciones en masa
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
description: Agregue varias ubicaciones a la vez con las herramientas de importación para el portal de administración de Búsqueda de Microsoft
ms.openlocfilehash: 186f6973de1ff87b62b5f07a47eb41acdd842010
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591399"
---
# <a name="bulk-create-locations"></a>Crear ubicaciones en masa

> [!IMPORTANT]
> Este artículo se aplica al portal de administración de Búsqueda de Microsoft in Bing. Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se quitará. Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar. [Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).
    
Descargue y use la plantilla .csv para crear, editar y guardar ubicaciones en masa. 
  
1. En la esquina superior derecha de la sección Ubicaciones, haga clic en **Importar**
    
2. Haga clic en **Descargar plantilla de ubicaciones (.csv)**
    
3. Guarde y abra el archivo .csv
    
4. Agregue el contenido de la ubicación y guarde el archivo

    El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación
    
5. En la esquina superior derecha de la sección Ubicaciones, haga clic en **Importar**
    
6. En el panel Importar ubicaciones, haga clic en **Examinar** y vaya al archivo .csv que quiere importar 
    
7. Haga clic en **Importar**

Los campos de las plantillas de ubicaciones de importación y exportación son los mismos. Puede exportar, editar en masa e importar los cambios, o bien puede empezar con una plantilla vacía para crear nuevas ubicaciones en masa. Si necesita editar en masa ubicaciones existentes, expórtelas desde el Portal de administración, haga los cambios necesarios y, después, impórtelas.

# <a name="prevent-import-errors"></a>Evitar errores de importación  
Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos. Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse. Realice los cambios necesarios e intente importar de nuevo el archivo.
  
> [!NOTE]
> Hasta que se resuelvan todos los errores, no podrá crear o editar las ubicaciones. 

Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:
- Incluye la fila de encabezado que se encontraba en la plantilla de importación
- Incluye todas las columnas que se encontraban en la plantilla de importación
- El orden de las columnas es el mismo que el orden en la plantilla de importación
- Estas columnas pueden estar vacías: Id., Última modificación, Última modificación realizada por y Lat/Long  
Si el campo está vacío, intentaremos determinar lat/long en función de la dirección
- La columna Estado no puede estar vacía, puesto que esta información es necesaria  
En función del campo Estado, las ubicaciones se guardarán como borradores, sugeridas o programadas, o se publicarán automáticamente.

Además, si incluye el Id. de una ubicación existente, este se reemplazará con la información del archivo de importación.

Para organizaciones con múltiples espacios empresariales, se pueden exportar las ubicaciones de un espacio empresarial e importarlas en otro. Pero, debe eliminar todos los datos de la columna Id. antes de la importación.
  
Para obtener más información sobre los campos necesarios y recomendados, vea [Agregar una ubicación](add-a-location.md).

  

