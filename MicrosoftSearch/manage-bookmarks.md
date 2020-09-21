---
title: Administrar marcadores
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
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Crear y actualizar marcadores y formas de editar en masa los resultados de marcadores para Microsoft Search
ms.openlocfilehash: eb65121b53ab110b91880a65a5146d868f3a7405
ms.sourcegitcommit: d88226f9c3a99540a591dc0a26408bb9960cf39a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2020
ms.locfileid: "48134171"
---
# <a name="manage-bookmarks"></a>Administrar marcadores

Puede crear un marcador en unos pocos pasos. Cada marcador incluye un título, una dirección URL y un conjunto de palabras clave que lo desencadenan. También puede Agregar categorías a un marcador que se puede usar para ordenar y filtrar en el portal de administración. Un marcador puede tener varias palabras clave y los marcadores pueden compartir la misma palabra clave, pero la palabra clave Reserved no se puede compartir. Cuando se crea o modifica un marcador, el índice de búsqueda se actualiza inmediatamente y el marcador está disponible para los usuarios inmediatamente.

Si su organización configura los resultados promocionados en SharePoint, puede importar los resultados promocionados en **Microsoft Search** y hacer que el contenido importado esté disponible para los usuarios. Esta es una forma sencilla de rellenar rápidamente los resultados de búsqueda tan pronto como **Búsqueda de Microsoft** esté configurado y hacerlo más eficaz para los usuarios. Se recomienda usar los resultados promocionados de SharePoint como referencia para comprender cómo nombrar y crear resultados de búsqueda relevantes.

## <a name="add-or-edit-a-single-bookmark"></a>Agregar o modificar un marcador único

1. En el [centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**marcadores**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Para agregar un marcador, seleccione **Agregar**.
Para modificar un marcador, seleccione el marcador en la lista de marcadores relevantes.
1. Al agregar o editar la información, la vista previa se actualizará automáticamente.
1. Guarde los cambios.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Agregar o editar el marcador mediante las extensiones del navegador

Los administradores de búsqueda pueden crear fácilmente búsquedas de contenido mediante las extensiones del navegador. Instale la extensión del explorador, vaya al sitio que desea agregar como marcador y agregue el marcador.

Actualmente, las extensiones del navegador están disponibles para Edge y Chrome.

- Para descargar las extensiones de servidor perimetral, vaya a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) y descargue la aplicación.
- Para descargar extensiones de Chrome, vaya a [almacén Web de Chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) y descargue la aplicación.

## <a name="bulk-add-or-edit-bookmarks"></a>Agregar o editar marcadores en bloque

Use la característica de importación o exportación para crear o editar en masa marcadores. Permite agregar o editar un gran número de marcadores de forma rápida y fácil. Úselo para:

- Agregar marcadores en bloque: introduzca la información en el archivo de plantilla del marcador y, a continuación, impórtelo.
- Editar marcadores en bloque: exporte los marcadores a un archivo CSV; a continuación, edite la información de los marcadores en el archivo CSV exportado e importe el archivo CSV actualizado.
- Importar sitios promocionados desde SharePoint.
- Realizar copia de seguridad de marcadores: exporte los marcadores a un archivo CSV.

Para importar o exportar marcadores:

1. En la esquina superior derecha de la página **Marcadores**, seleccione **Importar**.
Seleccione **Exportar** para descargar todos los marcadores existentes en un archivo CSV.
1. En el panel derecho, elija la opción Importar mediante archivo CSV o desde SharePoint.
Descargue el archivo de plantilla para obtener una lista de la información y los campos requeridos.
1. Agregue o edite la información de los marcadores en el archivo de plantilla y, a continuación, guárdelo en su equipo.
1. En el panel **Importar marcadores**, haga clic en **Examinar** y, a continuación, en el archivo CSV que desea importar.
1. Seleccione **Importar**.

Estos son algunos puntos importantes sobre el archivo de plantilla:

- No modificar nunca los datos de estos campos: *ID*, *última modificación*y *última modificación por*
- Si incluye el *identificador* de un marcador existente, se reemplazará con la información del archivo de importación.
- En el caso de los marcadores existentes con el mismo título o dirección URL, el marcador se actualizará con información en el archivo de importación.
- No todos los campos del archivo de plantilla son necesarios y hay campos obligatorios que varían según el estado del marcador.
- Según el campo de *Estado* , los marcadores se guardarán como borrador, sugerido, programado, o se publicarán automáticamente.
- Para los socios que administran varias organizaciones, puede exportar sus marcadores de una organización e importarlos en otro. Sin embargo, debe quitar los datos de la columna *ID* antes de importar.

### <a name="prevent-import-errors"></a>Evitar errores de importación

Si hay datos obligatorios que faltan o no son válidos, recibirá un mensaje de error y se generará un archivo de registro con información adicional acerca de las filas y columnas que se deben corregir. Realice cualquier cambio necesario y pruebe a importar de nuevo el archivo. No puede importar o guardar los marcadores hasta que se hayan solucionado todos los errores.

Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:

- Incluye todas la fila de encabezado y todas las columnas que había en la plantilla de importación
- El orden de las columnas es el mismo que en la plantilla de importación
- Todas las columnas tienen valores, excepto los tres que pueden estar vacíos: *ID*, *Last Modified*y *Last Modified by*
- La columna *Estado* no está vacía; se trata de información necesaria.

Para evitar errores de duplicación de marcadores a marcadores:

- No use direcciones URL duplicadas para marcadores diferentes. Si una dirección URL está asignada a otro marcador e intenta agregarla de nuevo desde un archivo de importación, recibirá un error. Esto también se aplica a las direcciones URL duplicadas para otros tipos de respuestas.
- Al actualizar los marcadores existentes, use la columna *identificador de marcador* . Puede actualizar cualquier otra propiedad de un marcador existente, como palabra clave o descripción, pero debe asegurarse de que el *identificador del marcador* se encuentra en la columna correspondiente del archivo de importación. Si el *identificador de marcador* está presente, no se tratará como nueva adición y no se procesará como un error.

## <a name="power-apps"></a>PowerApps

Ayude a los usuarios a completar tareas, como especificar el tiempo de vacaciones o los gastos de informes, agregando las aplicaciones Power App existentes a sus marcadores.

### <a name="power-apps-explained"></a>Explicación de Power apps

Power apps es un servicio que le permite crear aplicaciones empresariales que se ejecutan en un explorador o en un teléfono o tableta sin una experiencia de codificación necesaria. Las aplicaciones de energía funcionan en cualquier explorador y en cualquier dispositivo y tardan menos de un minuto en agregarse. Para obtener más información sobre las aplicaciones de energía, consulte:

- [Aprendizaje guiado](https://docs.microsoft.com/learn/browse/?terms=power%20apps)
- [Documentación](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Página principal de Power apps](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-power-app-to-a-bookmark"></a>Agregar una aplicación de energía a un marcador

1. Busque el [identificador de aplicación de la aplicación de energía](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que quiera agregar.
1. En el [centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**marcadores**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Agregue un marcador o busque un marcador existente al que quiera agregar una **aplicación Power** .
1. En **configuración de marcadores**, seleccione **Power App**y escriba o pegue el **identificador de aplicación**.
    El alto y el ancho se ajustan automáticamente en función de la orientación que se seleccionó cuando se creó la aplicación de energía. Los marcadores admiten orientaciones verticales y horizontales. La vista previa del marcador muestra una PowerApp totalmente funcional para facilitar la prueba.
1. Seleccione **Publicar** o **Guardar como borrador**.
