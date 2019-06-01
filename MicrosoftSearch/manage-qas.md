---
title: Administrar preguntas y respuestas
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
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
ms.openlocfilehash: 8620842e64a40eb32467c42a289bdec3b67d303b
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591525"
---
# <a name="manage-qas"></a>Administrar preguntas y respuestas

Crear un preguntas y respuestas es similar a crear marcadores. Preguntas y respuestas le permiten responder a la pregunta del usuario en lugar de limitarse a proporcionar un vínculo a una página web. Puede dar formato a la respuesta con texto enriquecido mediante las herramientas disponibles. Si un marcador y una pregunta y respuesta comparten la misma palabra clave, se mostrará primero el resultado del marcador. Al igual que los marcadores, el índice de preguntas y respuestas se actualiza inmediatamente después de añadir o modificar una pregunta y respuesta. 

## <a name="add-or-edit-a-single-qa"></a>Agregar o modificar una pregunta y respuesta única
1. Vaya al **Centro de administración de Microsoft 365**.
1. En el panel de navegación, vaya a **Configuración** y seleccione **Búsqueda de Microsoft**.
1. Seleccione la ficha de **preguntas y respuestas**. De forma predeterminada, aparece seleccionada la primera ficha (**Marcadores**)
1. Para agregar una pregunta y respuesta, seleccione **Agregar nueva**.
Para editar una pregunta y respuesta, selecciónela en la lista de preguntas y respuestas correspondiente.
1. Al agregar o editar la información, la vista previa se actualizará automáticamente.
1. Guarde los cambios.

### <a name="supported-html-tags"></a>Etiquetas HTML compatibles
Puede usar el contenido HTML existente o agregar etiquetas HTML a la respuesta (descripción). Las etiquetas no compatibles se ignoran.  
Se admiten las siguientes etiquetas HTML:
- blockquote
- div
- em
- h1, h2, h3 y h4
- ol, ul y li
- p
- pre
- span
- strong
- table, thead, tbody, tr, th y td
- u
- a
- code
- br
- hr
- img

## <a name="bulk-add-or-edit-qas"></a>Agregar o editar preguntas y respuestas en bloque
Los administradores pueden usar las características de Importar o Exportar para crear o editar preguntas y respuestas en bloque. Esta es una característica muy útil cuando los administradores deben agregar o editar un gran número de preguntas y respuestas. 

Use la característica importar o exportar para:
1. Agregar preguntas y respuestas en bloque: introduzca la información en el archivo de plantilla de preguntas y respuestas y, a continuación, impórtelo.
1. Editar preguntas y respuestas en bloque: exporte las preguntas y respuestas a un archivo CSV; a continuación, edite la información de las preguntas y respuestas en el archivo CSV exportado e importe el archivo CSV.
1. Copia de seguridad de preguntas y respuestas: exporte las preguntas y respuestas a un archivo CSV.

Para importar o exportar preguntas y respuestas:
1. En la esquina superior derecha de la pestaña Preguntas y respuestas, seleccione **Importar**. Seleccione **Exportar** para descargar todas las preguntas y respuestas existentes en un archivo CSV.
1. En el panel derecho, elija la opción Importar mediante archivo CSV.
Descargue el archivo de plantilla para obtener una lista de la información y los campos requeridos. 
1. Agregue o edite la información de preguntas y respuestas en el archivo de plantilla y guárdelo en su equipo. 
1. En el panel **Importar preguntas y respuestas**, haga clic en **Examinar** y, a continuación, en el archivo CSV que desea importar.
1. Seleccione **Importar**.

Estos son algunos puntos importantes en relación con el archivo de plantilla:
- Nunca modifique los datos de los campos: *Id*, *última modificación* y *modificado por*
- Si incluye el *Id* de un marcador, este se reemplazará con la información del archivo de importación.
- Si ya existe un marcador con el mismo título o dirección URL, el marcador se actualizará con la información del archivo de importación.
- No todos los campos del archivo de plantilla son necesarios y hay campos obligatorios que varían según el estado del marcador.
- En función del campo Estado, los marcadores se guardarán como borradores, sugeridos o programados, o se publicarán automáticamente.
- Para organizaciones con múltiples cuentas empresariales, se pueden exportar los marcadores de una cuenta empresarial e importarlos en otra. Sin embargo, debe eliminar los datos de la columna *Id* antes de la importación.

**Nota:** no puede importar preguntas y respuestas si hay cualquier error en el archivo de plantilla. Para evitar errores, asegúrese de que el archivo de importación está correctamente formateado y contiene toda la información necesaria. 

Para obtener más información sobre cómo evitar errores, consulte [Evitar errores de importación](manage-bookmarks.md#prevent-import-errors).