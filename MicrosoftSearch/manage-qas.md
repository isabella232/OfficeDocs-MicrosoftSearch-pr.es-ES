---
title: Administrar preguntas y respuestas
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Busque y actualice las respuestas individualmente o use las herramientas Búsqueda de Microsoft disponibles para editar preguntas&Como todas a la vez.
ms.openlocfilehash: 2ee42e3feaf5c14b2af820360f753ecc2e116f9b
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973736"
---
# <a name="manage-qas"></a>Administrar preguntas y respuestas

Crear un preguntas y respuestas es similar a crear marcadores. P&Como le permite responder a las preguntas del usuario en lugar de simplemente proporcionar un vínculo a una página web. También puede dar formato a la respuesta en texto enriquecido. Si un marcador y una pregunta&A comparten la misma palabra clave, el resultado del marcador se muestra primero. Al igual que los marcadores, el&índice A se actualiza inmediatamente después de agregar o cambiar una&A.

## <a name="add-or-edit-a-single-qa"></a>Agregar o modificar una pregunta y respuesta única

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**Preguntas&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Para agregar una pregunta&A, seleccione **Agregar**.
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

## <a name="add-or-edit-qas-using-browser-extensions"></a>Agregar o editar preguntas&Como usar extensiones del explorador

Los administradores de búsqueda pueden crear fácilmente búsquedas de contenido mediante las extensiones del navegador. Instale la extensión del explorador y, a continuación, vaya al sitio desde el que desea generar una pregunta&A. A continuación, puede crear la&A e incluir un vínculo al sitio de origen.

Actualmente, las extensiones del explorador están disponibles para Microsoft Edge y Chrome.

- Para descargar extensiones para Edge (heredado), vaya a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Para descargar extensiones Chrome o Edge (Chromium), vaya a la tienda [web de Chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="bulk-add-or-edit-qas"></a>Agregar o editar preguntas y respuestas en bloque

Los administradores pueden usar las características Importar y exportar para crear o editar de forma masiva preguntas&Como.

Use la Import/Export para:

- Agregar de forma masiva&como: agregue detalles en el archivo de plantilla&A y, a continuación, impórlo.
- Edición masiva de preguntas&Como: exportar preguntas&En cuanto a un archivo .csv, edite el&de preguntas y respuestas en el archivo exportado y, a continuación, importe el archivo.
- Copia de seguridad de&como: exportar preguntas&como a un .csv archivo.

Para importar o exportar preguntas&Como:

1. En la esquina superior derecha de la pestaña Preguntas y respuestas, seleccione **Importar**.
Seleccione **Exportar** para descargar todas las preguntas&como en un .csv archivo.
1. En el panel derecho, seleccione la opción para importar mediante un .csv archivo. Descargue el archivo de plantilla para obtener una lista de los campos y detalles necesarios.
1. Agregue o edite preguntas&Detalles del archivo de plantilla y guárdelo en el equipo.
1. En el **panel Importar&A,** seleccione Examinar y, a continuación, seleccione el .csv archivo que desea importar. 
1. Seleccione **Importar**.

Sugerencias importantes de archivo de plantilla:

- Nunca modifique los datos de los campos: **Id**, **última modificación** y **modificado por**
- Si incluye el **Id** de un marcador, este se reemplazará con la información del archivo de importación.
- Si hay un marcador existente que tiene el mismo título o dirección URL, el marcador se actualizará con información en el archivo de importación.
- No todos los campos del archivo de plantilla son necesarios y los campos necesarios varían según el estado del marcador.
- Según el campo **Estado,** los marcadores se guardan como borrador *,* *sugeridos* o *programados,* o se publican automáticamente.
- Para socios que administran varias organizaciones: puede exportar los marcadores de una organización e importarlos a otra. Sin embargo, debe eliminar los datos de la columna **Id** antes de la importación.

> [!NOTE]
> No puede importar preguntas&como si hubiera algún error en el archivo de plantilla. Para evitar errores, asegúrese de que el archivo de importación tiene el formato correcto e incluya toda la información necesaria.

Para obtener más información sobre cómo evitar errores, vea [Prevent import errors](manage-bookmarks.md#prevent-import-errors).
