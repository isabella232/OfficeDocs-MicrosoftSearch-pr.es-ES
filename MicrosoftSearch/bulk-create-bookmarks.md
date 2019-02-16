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
description: Crear muchos marcadores a la vez con herramientas de importación para el portal de administración de Microsoft Search
ms.openlocfilehash: 07694de1f546a1431f371fa24ffc5721ea66337c
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068406"
---
# <a name="bulk-create-bookmarks"></a>Crear marcadores en masa

Descargue y use la plantilla. csv para crear, editar y guardar marcadores de forma masiva. Para editar de forma masiva los marcadores existentes, expórtelo del portal de administración, realice las modificaciones necesarias y, a continuación, impórtelas.
  
1. En la esquina superior derecha de la sección Marcadores, haga clic en **importar**
    
2. Haga clic en **Descargar plantilla de marcadores (. csv)**
    
3. Guardar y abrir el archivo. csv
    
4. Agregar el contenido y la configuración del marcador y guardar el archivo
    
5. En la esquina superior derecha de la sección Marcadores, haga clic en **importar**
    
6. En el panel importar marcadores, haga clic en **examinar** y navegue hasta el archivo. csv que desea importar. 
    
7. Haga clic en **importar**

# <a name="prevent-import-errors"></a>Impedir errores de importación      
Recibirá un error si faltan datos necesarios o no son válidos. Según el error, es posible que se genere un archivo de registro con más información sobre las filas y las columnas que deben corregirse. Realice las modificaciones necesarias e intente importar el archivo de nuevo.

> [!NOTE]
> Hasta que se resuelvan todos los errores, no podrá crear ni editar ningún marcador. 

Para ayudar a evitar errores, asegúrese de que el archivo de importación tiene el formato correcto:
- Incluye la fila de encabezado que estaba en la plantilla de importación
- Incluye todas las columnas que estaban en la plantilla de importación
- El orden de las columnas es el mismo que el de la plantilla de importación
- Estas columnas pueden estar vacías: ID, última modificación y última modificación por
- La columna Estado no puede estar vacía, se requiere esta información  
Según el campo de estado, los marcadores se guardarán como borrador, sugerido, programado, o se publicarán automáticamente.

Además, si incluye el identificador de un marcador existente, se reemplazará con la información del archivo de importación.

En el caso de organizaciones con varios inquilinos, puede exportar sus marcadores de un inquilino e importarlos en otro. Sin embargo, debe quitar todos los datos de la columna ID antes de importar.

Para obtener más información sobre los campos obligatorios y recomendados, vea [Create bookmarks](create-bookmarks.md).
