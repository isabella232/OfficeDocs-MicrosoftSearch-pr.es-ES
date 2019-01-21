---
title: Administrar Q&As
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
description: Buscar y actualizar respuestas individualmente o utilizar las herramientas disponibles de Microsoft Search para editarlos todos a la vez
ms.openlocfilehash: c0f6b42aa1e0ad8c4736d37ec4dcc8cff6025dbc
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379274"
---
# <a name="manage-qas"></a>Administrar Q&As

Con el tiempo, debe actualizar el estado y el contenido para mantener relevantes de un Q&A.
  
## <a name="filter-qas"></a>Filtro Q&As

Use la opción de filtro en la esquina superior derecha de la página Q&As para buscar Q&As por fecha y que modificó. Por ejemplo, establezca el control deslizante de fecha en 30 días y seleccione un administrador o un editor para ver la lista de Q&As se ha creado o cambiado en ese momento.
  
## <a name="change-qa-content-or-settings"></a>Cambiar la configuración o Q&A contenido

1. Vaya al portal de administración de búsqueda de Microsoft
    
2. En el panel de navegación, haga clic en **Q&As**
    
3. Para buscar un Q&A, la búsqueda, el filtro, o haga clic en un estado Q&A para limitar los resultados
    
4. Para cambiar o actualizar un Q&A, haga clic en el título
    
5. Realice los cambios o actualizaciones en el contenido o la configuración y la vista previa de cómo aparecerán
    
6. Haga clic en **Guardar**.
    
## <a name="bulk-export-and-edit-qas"></a>Exportación masiva y editar Q&As

Nunca editar datos en estos campos:
  
- Id
    
- Modificó por última vez
    
- Última modificación realizada por
    
ID es un identificador único para cada Q&A y nunca debe modificarse. Los campos de última modificación y modificado por sólo deben usarse para ordenar y buscar Q&As.
  
1. Si desea exportar un subconjunto de su Q&As, filtrarlos
    
2. En la esquina superior derecha de la página Q&As, haga clic en **Exportar**
    
3. Guardar o abrir el archivo .csv
    
4. Editar datos en cualquiera de estos campos:
    
   - Pregunta
    
   - URL
      
   - Palabras clave
    
   - State
    
   - Descripción de respuesta
    
   - Palabras clave reservadas
    
   - Fecha de inicio
    
   - Fecha de finalización
    
   - País o región
    
   - Grupos
    
   - Dispositivo&amp;OS
    
   - Variantes de destinadas
    
5. Guarde el archivo .csv
    
6. En la esquina superior derecha de la página Q&As, haga clic en **Importar**
    
7. En el panel de Q&As de importación, haga clic en **Examinar** y seleccione el archivo .csv editado 
    
8. Haga clic en **Importar**
    
Obtendrá un error si los datos necesarios están ausente o no válido. Dependiendo del error, se puede generar un archivo de registro con más información acerca de las filas y columnas que deben corregirse. Realice las modificaciones necesarias y, intente importar de nuevo el archivo.
  
> [!NOTE]
> Hasta que se resuelvan todos los errores, no se puede crear o editar cualquier Q&As. 
  
No todos los campos son obligatorios y campos obligatorios varían según el estado de Q&A. Según el campo de estado, Q&As se va a guardar como borrador, sugerida, programado, o se publicará automáticamente. Obtenga más información acerca de los campos necesarios y recomendados de [crear Q&As](create-qas.md).

  

