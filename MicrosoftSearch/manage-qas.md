---
title: Administrar preguntas y respuestas
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Busque y actualice respuestas de forma individual o use las herramientas de búsqueda de Microsoft disponibles para editar las preguntas más&de una vez.
ms.openlocfilehash: 78a6ee0ff14f3347b0b2e2a65cc1ee0f68500981
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996089"
---
# <a name="manage-qas"></a>Administrar preguntas y respuestas

Crear un preguntas y respuestas es similar a crear marcadores. Q&como le permiten responder las preguntas del usuario en lugar de simplemente ofrecer un vínculo a una página web. También puede dar formato a la respuesta en texto enriquecido. Si un marcador y un&r A comparten la misma palabra clave, el resultado del marcador se muestra en primer lugar. Al igual que los marcadores, los Q&un índice se actualiza inmediatamente después de que se agregue o se modifique un Q&A.

## <a name="add-or-edit-a-single-qa"></a>Agregar o modificar una pregunta y respuesta única

1. Vaya al **Centro de administración de Microsoft 365**.
1. En el panel de navegación, vaya a **configuración**  >  **Microsoft Search**  >  **respuestas**  >  [**Q&a**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Para agregar una pregunta y respuesta, seleccione **Agregar nueva**.
Para editar una pregunta y respuesta, selecciónela en la lista de preguntas y respuestas correspondiente. Al agregar o editar la información, la vista previa se actualizará automáticamente.
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

## <a name="add-or-edit-qas-using-browser-extensions"></a>Agregar o editar el&de preguntas como el uso de las extensiones del explorador

Los administradores de búsqueda pueden crear fácilmente búsquedas de contenido mediante las extensiones del navegador. Instale la extensión del explorador y, a continuación, vaya al sitio desde el que desea generar un Q&a. A continuación, puede crear el&Q e incluir un vínculo al sitio de origen.

Actualmente, las extensiones del explorador están disponibles para Microsoft Edge y Chrome.

- Para descargar extensiones para Edge (heredado), ve a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Para descargar las Extensiones Chrome o Edge (cromo), vaya al [almacén Web de Chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="bulk-add-or-edit-qas"></a>Agregar o editar preguntas y respuestas en bloque

Los administradores pueden usar las características de importación y exportación para crear o editar de forma masiva Q&como.

Use la característica de importación y exportación para:

- Agregar en masa preguntas&como-agregar detalles en el archivo de plantilla Q&y, a continuación, importarlo.
- Edición en masa Q&como-Export Q&como a un archivo. csv, edite la p&una información en el archivo exportado y, a continuación, importe el archivo.
- Realice una copia de seguridad de la&q&como-Export Q en un archivo. csv.

Para importar o exportar preguntas&como:

1. En la esquina superior derecha de la pestaña Preguntas y respuestas, seleccione **Importar**.
Seleccione **exportar** para descargar todos los&Q existentes como en un archivo. csv.
1. En el panel derecho, seleccione la opción para importar mediante un archivo. csv. Descargue el archivo de plantilla para obtener una lista de los campos y detalles obligatorios.
1. Agregar o editar Q&una información en el archivo de plantilla y guárdela en el equipo.
1. En el panel **importar Q&un** panel, seleccione **examinar**y, a continuación, seleccione el archivo. csv que desea importar.
1. Seleccione **Importar**.

Sugerencias importantes del archivo de plantilla:

- Nunca modifique los datos de los campos: **Id**, **última modificación** y **modificado por**
- Si incluye el **Id** de un marcador, este se reemplazará con la información del archivo de importación.
- Si hay un marcador existente con el mismo título o dirección URL, el marcador se actualizará con información en el archivo de importación.
- No todos los campos del archivo de plantilla son obligatorios y los campos obligatorios varían en función del estado del marcador.
- Según el campo de **Estado** , los marcadores se guardan como *borradores*, *sugeridos*o *programados*, o se publican automáticamente.
- Para los asociados que administran varias organizaciones, puede exportar sus marcadores de una organización e importarlos en otro. Sin embargo, debe eliminar los datos de la columna **Id** antes de la importación.

> [!NOTE]
> No puede importar preguntas&como si hubiera errores en el archivo de plantilla. Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado e incluya toda la información necesaria.

Para obtener más información acerca de cómo evitar errores, consulte [evitar errores de importación](manage-bookmarks.md#prevent-import-errors).
