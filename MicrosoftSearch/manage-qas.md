---
title: Administrar preguntas y respuestas
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Buscar y actualizar respuestas de forma individual o usar las herramientas de búsqueda de Microsoft disponibles para editarlas todas a la vez
ms.openlocfilehash: 47882deeb95133cfc19f4eec6417fc20fb7203de
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901836"
---
# <a name="manage-qas"></a>Administrar preguntas y respuestas

Con el tiempo, es posible que deba actualizar el contenido y el estado de un Q&A's para mantenerlo relevante.
  
## <a name="filter-qas"></a>Filtrar Q&As

Use la opción de filtro en la esquina superior derecha de la página Q&As para buscar Q&As por fecha y quién los modificó. Por ejemplo, establezca el control deslizante fecha en 30 días y seleccione un administrador o un editor para ver la lista de Q&As que han creado o modificado en ese momento.
  
## <a name="change-qa-content-or-settings"></a>Cambiar el contenido o la configuración de Q&A

1. Vaya al portal de administración de Microsoft Search
    
2. En el panel de navegación, haga clic en **Preguntas y respuestas**
    
3. Para buscar un Q&A, buscar, filtrar o hacer clic en un estado de Q&A para restringir los resultados
    
4. Para cambiar o actualizar una Q&A, haga clic en el título.
    
5. Realizar los cambios o actualizaciones del contenido o la configuración y obtener una vista previa del modo en que aparecerán
    
6. Haga clic en **Guardar**
    
## <a name="bulk-export-and-edit-qas"></a>Exportación en masa y edición Q&As

Nunca modifique datos en estos campos:
  
- Id
    
- Última modificación
    
- Última modificación realizada por
    
ID es un identificador único para cada Q&A y no se debe editar nunca. Los campos última modificación y última modificación por sólo deben usarse para ordenar y buscar Q&As.
  
1. Si desea exportar un subconjunto de sus Q&As, filtre
    
2. En la esquina superior derecha de la página Q&As, haga clic en **exportar** .
    
3. Guardar o abrir el archivo. csv
    
4. Edite los datos en cualquiera de estos campos:
    
   - Question
    
   - URL
      
   - Palabras clave
    
   - Estado
    
   - Descripción de la respuesta
    
   - Palabras clave reservadas
    
   - Fecha de inicio
    
   - Fecha de finalización
    
   - País o región
    
   - Grupos
    
   - Sistema&amp;operativo del dispositivo
    
   - Variaciones de destino
    
5. Guardar el archivo. csv

    El archivo. csv se debe guardar como archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden provocar errores de importación
    
6. En la esquina superior derecha de la página Q&As, haga clic en **importar**
    
7. En el panel de Q&As de importación, haga clic en **examinar** y seleccione el archivo. csv editado. 
    
8. Haga clic en **importar**
    
Recibirá un error si faltan datos necesarios o no son válidos. Según el error, es posible que se genere un archivo de registro con más información sobre las filas y las columnas que deben corregirse. Realice las modificaciones necesarias e intente importar el archivo de nuevo.
  
> [!NOTE]
> Hasta que se resuelvan todos los errores, no puede crear ni editar ninguna Q&As. 
  
No todos los campos son obligatorios y los campos obligatorios varían en función del estado Q&A. Según el campo de estado, Q&As se guardará como borrador, sugerido, programado o se publicará automáticamente. Obtenga más información sobre los campos obligatorios y recomendados en [Create Q&As](create-qas.md).

  

