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
description: Cree varios marcadores a la vez con las herramientas de importación para el portal de administración de Búsqueda de Microsoft
ms.openlocfilehash: 560cda6f94060d428f2d18cc61bd2430cb31b474
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968356"
---
# <a name="bulk-create-bookmarks"></a>Crear marcadores en masa

> [!IMPORTANT]
> Búsqueda de Microsoft en la configuración de Bing ya está disponible en el Centro de administración de Microsoft 365. Empiece por [asignar administradores de búsqueda](https://docs.microsoft.com/es-ES/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) en el centro de administración.
    
Descargue y use la plantilla .csv para crear, editar y guardar marcadores en masa. Si necesita editar en masa marcadores existentes, expórtelos desde el Portal de administración, haga los cambios necesarios y, luego, impórtelos.
  
1. En la esquina superior derecha de la sección Marcadores, haga clic en **Importar**
    
2. Haga clic en **Descargar plantilla de marcadores (.csv)**
    
3. Guarde y abra el archivo .csv
    
4. Agregue el contenido y la configuración de los marcadores y guarde el archivo

    El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación
    
5. En la esquina superior derecha de la sección Marcadores, haga clic en **Importar**
    
6. En el panel Importar marcadores, haga clic en **Examinar** y vaya al archivo .csv que quiere importar 
    
7. Haga clic en **Importar**

# <a name="prevent-import-errors"></a>Evitar errores de importación      
Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos. Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse. Realice los cambios necesarios e intente importar de nuevo el archivo.

> [!NOTE]
> Hasta que se resuelvan todos los errores, no podrá crear o editar los marcadores. 

Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:
- Incluye la fila de encabezado que se encontraba en la plantilla de importación
- Incluye todas las columnas que se encontraban en la plantilla de importación
- El orden de las columnas es el mismo que el orden en la plantilla de importación
- Estas columnas pueden estar vacías: Id., Última modificación y Última modificación realizada por
- La columna Estado no puede estar vacía, puesto que esta información es necesaria  
En función del campo Estado, los marcadores se guardarán como borradores, sugeridos o programados, o se publicarán automáticamente.

Además, si incluye el Id. de un marcador existente, este se reemplazará con la información del archivo de importación.

Para organizaciones con múltiples espacios empresariales, se pueden exportar los marcadores de un espacio empresarial e importarlos en otro. Pero, debe eliminar todos los datos de la columna Id. antes de la importación.

Para obtener más información sobre los campos necesarios y recomendados, vea [Crear marcadores](create-bookmarks.md).
