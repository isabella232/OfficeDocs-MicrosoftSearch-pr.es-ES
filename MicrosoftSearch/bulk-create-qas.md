---
title: Crear preguntas y respuestas de forma masiva
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
description: Agregue rápidamente respuestas a las preguntas más frecuentes con herramientas de importación en el portal de administración de Microsoft Search
ms.openlocfilehash: 28fcf57c44f809e7f9b0c1b27042f4549067a0f8
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508677"
---
# <a name="bulk-create-qas"></a>Crear preguntas y respuestas de forma masiva

Descargue y use la plantilla. csv para crear o editar en masa Q&As. También es una forma sencilla de guardar de forma masiva borradores de Q&As que necesitan ediciones o actualizaciones adicionales. Si necesita editar en masa Q&As existentes, expórtelo del portal de administración, realice las modificaciones necesarias y, a continuación, impórtelas.
  
1. En la esquina superior derecha de la sección Q&As, haga clic en **importar**
    
2. Haga clic en **Descargar plantilla de Q&A (. csv)**
    
3. Guardar y abrir el archivo. csv
    
4. Agregar el contenido y la configuración de Q&A y guardar el archivo

    El archivo. csv se debe guardar como archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden provocar errores de importación
    
5. En la esquina superior derecha de la sección Q&As, haga clic en **importar**
    
6. En el panel de Q&As de importación, haga clic en **examinar** y navegue hasta el archivo. csv que desea importar. 
    
7. Haga clic en **importar**

# <a name="prevent-import-errors"></a>Impedir errores de importación      
Recibirá un error si faltan datos necesarios o no son válidos. Según el error, es posible que se genere un archivo de registro con más información sobre las filas y las columnas que deben corregirse. Realice las modificaciones necesarias e intente importar el archivo de nuevo.

> [!NOTE]
> Hasta que se resuelvan todos los errores, no puede crear ni editar ninguna Q&As. 

Para ayudar a evitar errores, asegúrese de que el archivo de importación tiene el formato correcto:
- Incluye la fila de encabezado que estaba en la plantilla de importación
- Incluye todas las columnas que estaban en la plantilla de importación
- El orden de las columnas es el mismo que el de la plantilla de importación
- Estas columnas pueden estar vacías: ID, última modificación y última modificación por
- La columna Estado no puede estar vacía, se requiere esta información  
Según el campo de estado, Q&As se guardará como borrador, sugerido, programado o se publicará automáticamente.

Además, si incluye el identificador de un Q&A existente, se reemplazará con la información en el archivo de importación.

Para organizaciones con varios inquilinos, puede exportar su Q&As de un inquilino e importarlo en otro. Sin embargo, debe quitar todos los datos de la columna ID antes de importar.

Para obtener más información acerca de los campos obligatorios y recomendados, consulte [Create Q&As](create-qas.md).

  

