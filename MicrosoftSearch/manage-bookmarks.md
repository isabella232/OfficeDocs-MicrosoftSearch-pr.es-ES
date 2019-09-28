---
title: Administrar marcadores
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
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Crear y actualizar marcadores y formas de editar en masa los resultados de marcadores para Microsoft Search
ms.openlocfilehash: 02b9bfecd97210ba8cd5b46bf3bc108bf66b6f01
ms.sourcegitcommit: 3da22a2e09830672ebf199e05a32fa89b75c083b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288977"
---
# <a name="manage-bookmarks"></a>Administrar marcadores

Puede crear un marcador en unos pocos pasos. Cada marcador incluye un título, una dirección URL y un conjunto de palabras clave que lo desencadenan. Un marcador puede contener varias palabras clave y distintos marcadores pueden compartir la misma palabra clave, pero no se pueden compartir las palabras clave reservadas. Al crear o modificar un marcador, el índice de búsqueda se actualiza inmediatamente y el marcador está inmediatamente disponible para los usuarios.

Si su organización ha promovido resultados configurados en SharePoint, puede importar los resultados promocionados a **Microsoft Search** y hacer que el contenido importado esté disponible para los usuarios. Esta es una forma sencilla de rellenar rápidamente los resultados de búsqueda tan pronto como **Búsqueda de Microsoft** esté configurado y hacerlo más eficaz para los usuarios. Le recomendamos que use los resultados promocionados de SharePoint como referencia para comprender cómo nombrar y crear resultados de búsqueda relevantes. 

## <a name="add-or-edit-a-single-bookmark"></a>Agregar o modificar un marcador único
1. Vaya al **Centro de administración de Microsoft 365**.
1. En el panel de navegación, vaya a **Configuración** y, a continuación, seleccione **Búsqueda de Microsoft**.
De forma predeterminada, la ficha **Marcadores** aparece seleccionada.
1. Para agregar un marcador, seleccione **Agregar nuevo**. Para modificar un marcador, seleccione el marcador en la lista de marcadores relevantes. 
1. Al agregar o editar la información, la vista previa se actualizará automáticamente.
1. Guarde los cambios.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Agregar o editar el marcador mediante las extensiones del navegador
Los administradores de búsqueda pueden crear fácilmente búsquedas de contenido mediante las extensiones del navegador. Instale la extensión del explorador y, a continuación, vaya al sitio que desee agregar como marcador y agréguelo como marcador.

Actualmente, las extensiones del navegador están disponibles para Edge y Chrome. 
- Para descargar la extensión de Edge, vaya a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) y descargue la aplicación.
- Para descargar la extensión de Chrome, vaya a [Chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) y descargue la aplicación.

## <a name="bulk-add-or-edit-bookmarks"></a>Agregar o editar marcadores en bloque
El administrador de búsqueda puede usar las características de Importar o Exportar para crear o editar marcadores en bloque. Esta es una característica muy útil cuando un administrador desea agregar o editar un gran número de marcadores. 

Use la característica importar o exportar para:
- Agregar marcadores en bloque: introduzca la información en el archivo de plantilla del marcador y, a continuación, impórtelo.
- Editar marcadores en bloque: exporte los marcadores a un archivo CSV; a continuación, edite la información de los marcadores en el archivo CSV exportado e importe el archivo CSV actualizado.
- Importar sitios promocionados desde SharePoint.
- Realizar copia de seguridad de marcadores: exporte los marcadores a un archivo CSV.

Para importar o exportar marcadores:
1. En la esquina superior derecha de la página **Marcadores**, seleccione **Importar**. Seleccione **Exportar** para descargar todos los marcadores existentes en un archivo CSV.
1. En el panel derecho, elija la opción Importar mediante archivo CSV o desde SharePoint.
Descargue el archivo de plantilla para obtener una lista de la información y los campos requeridos. 
1. Agregue o edite la información de los marcadores en el archivo de plantilla y, a continuación, guárdelo en su equipo. 
1. En el panel **Importar marcadores**, haga clic en **Examinar** y, a continuación, en el archivo CSV que desea importar.
1. Seleccione **Importar**.

Estos son algunos puntos importantes a tener en cuenta en relación con el archivo de plantilla:
- Nunca modifique los datos de los campos: *Id*, *última modificación* y *modificado por*
- Si incluye el *Id* de un marcador, este se reemplazará con la información del archivo de importación.
- Si ya existe un marcador con el mismo título o dirección URL, el marcador se actualizará con la información del archivo de importación.
- No todos los campos del archivo de plantilla son necesarios y hay campos obligatorios que varían según el estado del marcador.
- En función del campo *Estado*, los marcadores se guardarán como borradores, sugeridos o programados, o se publicarán automáticamente.
- Para organizaciones con múltiples cuentas empresariales, se pueden exportar los marcadores de una cuenta empresarial e importarlos en otra. Sin embargo, debe eliminar los datos de la columna *Id* antes de la importación.

### <a name="prevent-import-errors"></a>Evitar errores de importación
Si hay datos obligatorios que faltan o no son válidos, recibirá un mensaje de error y se generará un archivo de registro con información adicional acerca de las filas y columnas que se deben corregir. Realice cualquier cambio necesario y pruebe a importar de nuevo el archivo. No puede importar o guardar los marcadores hasta que se hayan solucionado todos los errores.

Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:
- Incluye todas la fila de encabezado y todas las columnas que había en la plantilla de importación
- El orden de las columnas es el mismo que en la plantilla de importación
- Todas las columnas tienen valores, excepto las tres que pueden estar vacías: *Id*, *Última modificación* y *Modificado por* 
- La columna *Estado* no está vacía, puesto que esta información es necesaria

## <a name="powerapps"></a>PowerApps
Ayude a los usuarios a realizar tareas, como marcar las fechas de las vacaciones o registrar informes de gastos, añadiendo PowerApps existentes a los marcadores. 

### <a name="what-are-powerapps"></a>¿Qué son las PowerApps?
PowerApps es un servicio que le permite crear aplicaciones empresariales que funcionan en un explorador o en una tableta o teléfono sin necesidad de tener conocimientos de programación. Las PowerApps funcionan en cualquier explorador y en cualquier dispositivo y se agregan en menos de un minuto. Para obtener más información sobre PowerApps, consulte:
- 
  [Aprendizaje guiado](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [Documentación](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Inicio de PowerApps](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Agregar una PowerApp a un marcador
1. Busque el [ID de la PowerApp](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que desea agregar.
1. Inicie sesión en el **Centro de administración de Microsoft 365**.
1. En el panel de navegación, vaya a **Configuración** y, a continuación, seleccione **Búsqueda de Microsoft**.
1. Agregue un marcador o busque un marcador al que desee agregar una **PowerApp**.
1. En **Configuración del marcador**, seleccione **Power App** y, a continuación, **Agregar una Power App**.
1. Escriba o pegue el **App ID**.
    El ancho y el alto se ajustan automáticamente. Los marcadores admite la orientación vertical y horizontal, pero, de momento, no se puede cambiar el tamaño. La vista previa del marcador muestra una PowerApp totalmente funcional para facilitar la prueba.
1. Seleccione **Publicar** o **Guardar como borrador**.
