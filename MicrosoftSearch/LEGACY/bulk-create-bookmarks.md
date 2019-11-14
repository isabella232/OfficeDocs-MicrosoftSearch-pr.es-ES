---
title: Crear marcadores en masa
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
ROBOTS: NoIndex
description: Crear muchos marcadores a la vez con herramientas de importación para el portal de administración de Microsoft Search
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311929"
---
# <a name="bulk-create-bookmarks"></a>Crear marcadores en masa

> [!IMPORTANT]
> Este artículo se aplica al portal de administración de Búsqueda de Microsoft en Bing. Estamos pasando el portal al Centro de administración de Microsoft 365. Luego, se quitará el portal de Búsqueda de Microsoft en Bing. Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar. [Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).
    
Descargue y use la plantilla. csv para crear, editar y guardar marcadores de forma masiva. Para editar de forma masiva los marcadores existentes, expórtelo del portal de administración, realice las modificaciones necesarias y, a continuación, impórtelas.
  
1. En la esquina superior derecha de la sección Marcadores, haga clic en **importar**
    
2. Haga clic en **Descargar plantilla de marcadores (. csv)**
    
3. Guarde y abra el archivo .csv
    
4. Agregar el contenido y la configuración del marcador y guardar el archivo

    El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación
    
5. En la esquina superior derecha de la sección Marcadores, haga clic en **importar**
    
6. En el panel importar marcadores, haga clic en **examinar** y navegue hasta el archivo. csv que desea importar. 
    
7. Haga clic en **Importar**

## <a name="prevent-import-errors"></a>Evitar errores de importación      
Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos. Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse. Realice los cambios necesarios e intente importar de nuevo el archivo.

> [!NOTE]
> Hasta que se resuelvan todos los errores, no podrá crear ni editar ningún marcador. 

Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:
- Incluye la fila de encabezado que se encontraba en la plantilla de importación
- Incluye todas las columnas que se encontraban en la plantilla de importación
- El orden de las columnas es el mismo que el orden en la plantilla de importación
- Estas columnas pueden estar vacías: Id., Última modificación y Última modificación realizada por
- La columna Estado no puede estar vacía, puesto que esta información es necesaria  
En función del campo Estado, los marcadores se guardarán como borradores, sugeridos o programados, o se publicarán automáticamente.

Además, si incluye el identificador de un marcador existente, se reemplazará con la información del archivo de importación.

Para los socios que administran varias organizaciones, puede exportar sus marcadores de una organización e importarlos en otro. Pero, debe eliminar todos los datos de la columna Id. antes de la importación.

Para obtener más información sobre los campos obligatorios y recomendados, vea [Create bookmarks](create-bookmarks.md).
