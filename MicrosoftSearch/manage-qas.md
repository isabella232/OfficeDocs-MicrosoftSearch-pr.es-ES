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
description: Busque y actualice respuestas individualmente o use las herramientas disponibles de Búsqueda de Microsoft para editarlas todas a la vez
ms.openlocfilehash: ee239aa73d4e650289f39d33c63c3e2df4f100cc
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968471"
---
# <a name="manage-qas"></a>Administrar preguntas y respuestas

> [!IMPORTANT]
> Búsqueda de Microsoft en la configuración de Bing ya está disponible en el Centro de administración de Microsoft 365. Empiece por [asignar administradores de búsqueda](https://docs.microsoft.com/es-ES/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) en el centro de administración.
    
Con el tiempo, es posible que deba actualizar el estado y el contenido de preguntas y respuestas para que sigan siendo relevantes.
  
## <a name="filter-qas"></a>Filtrar preguntas y respuestas

Use la opción de filtro situada en la esquina superior derecha de la página Preguntas y respuestas para buscar preguntas y respuestas por fecha y por el usuario que las haya modificado. Por ejemplo, puede establecer el control deslizante de fecha en 30 días y seleccionar un administrador o editor para ver la lista de preguntas y respuestas que se han creado o editado en ese período de tiempo.
  
## <a name="change-qa-content-or-settings"></a>Cambiar el contenido o la configuración de preguntas y respuestas

1. Vaya al portal de administración de Microsoft Search
    
2. En el panel de navegación, haga clic en **Preguntas y respuestas**
    
3. Para buscar una pregunta y su respuesta, puede buscar, filtrar o hacer clic en el estado de la pregunta y su respuesta para restringir los resultados.
    
4. Para cambiar o actualizar una pregunta y su respuesta, haga clic en el título
    
5. Realice los cambios o actualizaciones que desee en el contenido o la configuración y obtenga una vista previa de cómo aparecerán
    
6. Haga clic en **Guardar**
    
## <a name="bulk-export-and-edit-qas"></a>Editar y exportar en masa preguntas y respuestas

No edite nunca los datos de estos campos:
  
- Id
    
- Última modificación
    
- Última modificación realizada por
    
El Id. es un identificador único de cada pregunta y respuesta y nunca debe editarse. Los campos Última modificación y Última modificación realizada por deben usarse solamente para ordenar y buscar preguntas y respuestas.
  
1. Si quiere exportar un subconjunto de preguntas y respuestas, puede filtrarlas
    
2. En la esquina superior derecha de la página Preguntas y respuestas, haga clic en **Exportar**
    
3. Guarde o abra el archivo .csv
    
4. Edite los datos de cualquiera de estos campos:
    
   - Pregunta
    
   - URL
      
   - Palabras clave
    
   - Estado
    
   - Descripción de respuesta
    
   - Palabras clave reservadas
    
   - Fecha de inicio
    
   - Fecha de finalización
    
   - País o región
    
   - Grupos
    
   - Dispositivo&amp;OS
    
   - Variaciones de destino
    
5. Guarde el archivo .csv

    El archivo .csv debe guardarse como un archivo CSV UTF-8, otros tipos de archivo o codificaciones pueden causar errores de importación
    
6. En la esquina superior derecha de la página Preguntas y respuestas, haga clic en **Importar**
    
7. En el panel Importar preguntas y respuestas, haga clic en **Examinar** y seleccione el archivo .csv editado 
    
8. Haga clic en **Importar**
    
Recibirá un mensaje de error si faltan datos necesarios o si estos no son válidos. Según el error, puede generarse un archivo de registro con más información sobre las filas y columnas que deben corregirse. Realice los cambios necesarios e intente importar de nuevo el archivo.
  
> [!NOTE]
> Hasta que se resuelvan todos los errores, no puede crear o editar las preguntas y respuestas. 
  
No todos los campos son necesarios y hay campos obligatorios que varían según el estado de las preguntas y respuestas. Según el campo de estado, las preguntas y respuestas se guardarán como borradores, sugeridas o programadas, o se publicarán automáticamente. Para obtener más información sobre los campos necesarios y recomendados, vea [Crear preguntas y respuestas](create-qas.md).

  

