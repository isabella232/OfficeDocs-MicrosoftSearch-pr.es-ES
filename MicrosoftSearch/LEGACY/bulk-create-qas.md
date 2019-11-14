---
title: Crear preguntas y respuestas en masa
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
ROBOTS: NoIndex
description: Agregue rápidamente respuestas a las preguntas más frecuentes con herramientas de importación en el portal de administración de Búsqueda de Microsoft
ms.openlocfilehash: 660f5663ff6238f4ab59dab36d51f1311d5c7260
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311899"
---
# <a name="bulk-create-qas"></a>Crear preguntas y respuestas en masa

> [!IMPORTANT]
> Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing Estamos pasando el portal al Centro de administración de Microsoft 365. Luego, se quitará el portal de Búsqueda de Microsoft en Bing. Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar. [Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).
    
Descargue y use la plantilla .csv para crear o editar preguntas y respuestas en masa. También es una forma sencilla de guardar en masa los borradores de preguntas y respuestas que necesitan modificaciones adicionales o actualizaciones. Si necesita editar en masa preguntas y respuestas existentes, expórtelas desde el Portal de administración, haga los cambios necesarios y, luego, impórtelas.
  
1. En la esquina superior derecha de la sección de preguntas y respuestas, haga clic en **Importar**
    
2. Haga clic en **Descargar plantilla de preguntas y respuestas (.csv)**
    
3. Guarde y abra el archivo .csv
    
4. Agregue el contenido y la configuración de preguntas y respuestas y guarde el archivo

    El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación
    
5. En la esquina superior derecha de la sección de preguntas y respuestas, haga clic en **Importar**
    
6. En el panel Importar preguntas y respuestas, haga clic en **Examinar** y vaya al archivo .csv que quiere importar 
    
7. Haga clic en **Importar**

## <a name="prevent-import-errors"></a>Evitar errores de importación      
Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos. Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse. Realice los cambios necesarios e intente importar de nuevo el archivo.

> [!NOTE]
> Hasta que se resuelvan todos los errores, no puede crear o editar las preguntas y respuestas. 

Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:
- Incluye la fila de encabezado que se encontraba en la plantilla de importación
- Incluye todas las columnas que se encontraban en la plantilla de importación
- El orden de las columnas es el mismo que el orden en la plantilla de importación
- Estas columnas pueden estar vacías: Id., Última modificación y Última modificación realizada por
- La columna Estado no puede estar vacía, puesto que esta información es necesaria  
Según el campo Estado, las preguntas y respuestas se guardarán como borradores, sugeridas o programadas o se publicarán automáticamente.

Además, si incluye el Id. de preguntas y respuestas existentes, este se reemplazará con la información del archivo de importación.

En el caso de los socios que administran varias organizaciones, puede exportar su&Q como de una organización e importarla a otra. Pero, debe eliminar todos los datos de la columna Id. antes de la importación.

Para obtener más información sobre los campos necesarios y recomendados, vea [Crear preguntas y respuestas](create-qas.md).

  

