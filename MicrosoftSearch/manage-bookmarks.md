---
title: Administrar marcadores
ms.author: dawholl
author: dawholl
manager: jeffkizn
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
ms.openlocfilehash: fee855e3d3fe780021530488dbaa5a864dcba2d8
ms.sourcegitcommit: 9daa3c8f6eeab502b28975a308d4d1014a00eb25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49718652"
---
# <a name="manage-bookmarks"></a>Administrar marcadores

Los marcadores ayudan a los usuarios a encontrar rápidamente sitios y herramientas importantes con solo una búsqueda. Cada marcador incluye un título, una dirección URL, un conjunto de palabras clave descriptivas para desencadenar el marcador y una categoría.

## <a name="what-makes-a-great-bookmark"></a>Qué hace un gran marcador

Un marcador estupendo tiene cuatro elementos clave:

1. Un **título** seguro e informativo. El objetivo no es más de 8 palabras o unos 60 caracteres como máximo. Desea que los usuarios haga clic en el título y vean el contenido, pero evitar clickbait obvios:
    - Bueno: Pruebe los favoritos de la Tasty de la semana en el menú de cafetería. El título es claro, conciso e interesante, pero podría ser más prometedor.
    - Mejor: el menú cafetería de esta semana. No se ve afectada ni tiene un sonido similar al de un anuncio.
    - Evite: no le va a creer lo que llega al menú de la cafetería esta semana. Usa clickbait clichés que suena como un anuncio.
2. Una **Descripción** sucinta, alrededor de 300 caracteres, que resume el propósito o la funcionalidad del recurso vinculado.
3. Una colección de **palabras clave** que ayudarán a los usuarios a encontrar el marcador cuando lo busquen. Se recomienda un mínimo de cinco palabras clave como mínimo. Además, incluya variaciones que puedan usar las personas de su organización, por ejemplo, el menú de la cena, los menús de la comida y el menú de café podrían ser variantes del menú de cafetería.
4. Un conjunto útil de **categorías** que facilitan la ordenación y el filtrado de marcadores en el centro de administración. Los usuarios nunca ven las categorías asignadas.

## <a name="create-bookmark-answers"></a>Crear respuestas a marcadores

En el [centro de administración de Microsoft 365](https://admin.microsoft.com/), vaya a [marcadores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) y elija cómo desea crear nuevos marcadores:

- Agregar marcadores
- Importar resultados de SharePoint
- Agregar marcadores predeterminados y marcadores sugeridos
- Importar marcadores
- Publicar o revisar los marcadores recomendados

### <a name="add-bookmarks"></a>Agregar marcadores

Los administradores y editores de búsqueda pueden agregar marcadores en el centro de administración de Microsoft 365. Los marcadores se pueden publicar o guardar en borrador. Al publicar un marcador, se actualiza inmediatamente el índice de búsqueda para que los usuarios puedan empezar a detectarlo y usarlo directamente. También puede programar un marcador especificando la fecha y la hora en que se publicará.

- **Publicado**: los marcadores están disponibles para los usuarios de la organización a través de Microsoft Search.
- **Borrador**: los marcadores guardados como borradores no están disponibles para los usuarios. Use este estado si usted u otras partes interesadas quieren revisar o actualizar los marcadores antes de publicarlos.
- **Programado**: marcadores que se publicarán en la fecha y hora especificadas.

Puede usar la extensión del explorador del creador de contenido de Microsoft Search para agregar fácilmente marcadores. Para instalar la extensión del explorador, vaya al sitio que desea agregar como marcador y haga clic en agregar en la extensión.
Instale la extensión para Edge y Chrome:

- Para el cromo de cromo o cromo: vaya al [almacén Web de Chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) y agregue la extensión.
- Para perimetral heredado: vaya a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) y agregue la extensión.

### <a name="import-sharepoint-results"></a>Importar resultados de SharePoint

Si su organización ha configurado los resultados promocionados en SharePoint, puede importar los títulos, las direcciones URL y las descripciones de los resultados promovidos de su inquilino a Microsoft Search y hacer que el contenido importado esté disponible para los usuarios. En la mayoría de los casos, la importación de los resultados de SharePoint dura solo unos minutos. Si va a importar un gran número de resultados, puede tardar hasta 48 horas. Esta es una forma sencilla de rellenar rápidamente los resultados de búsqueda y hacer que sea más eficaz para los usuarios. Se recomienda usar los resultados promocionados de SharePoint como referencia para comprender cómo nombrar y crear resultados de búsqueda relevantes.

### <a name="add-default-and-suggested-bookmarks"></a>Agregar marcadores predeterminados y sugeridos

Hemos incluido algunos marcadores predeterminados sugeridos que los usuarios pueden encontrar útiles, incluidos marcadores para recursos humanos, ventajas, soporte técnico de ti, administración de contraseñas y mucho más. Revise, actualice y publique estos marcadores sugeridos para proporcionar resultados de alta calidad a los usuarios inmediatamente.

Los usuarios también pueden sugerir marcadores que quieran que se agreguen mediante vínculos de comentarios en Microsoft Search. Las recomendaciones aparecerán como marcadores sugeridos.

### <a name="import-bookmarks"></a>Importar marcadores

Use la característica importar para agregar o editar un gran número de marcadores de forma rápida y sencilla. Úselo para:

- Agregar marcadores en masa: agregue detalles en el archivo de plantilla de marcador y, a continuación, impórtelo.
- Edición en masa de marcadores: exporte marcadores a un archivo. csv, edite los detalles del marcador en el archivo exportado y, a continuación, importe el archivo editado.

Algunos puntos importantes sobre el archivo de plantilla:

- No modificar nunca los datos de estos campos: *ID*, *última modificación* y *última modificación por*
- Si incluye el *identificador* de un marcador existente, se reemplazará con la información del archivo de importación.
- En el caso de los marcadores existentes con el mismo título o dirección URL, el marcador se actualizará con información en el archivo de importación.
- No todos los campos del archivo de plantilla son necesarios y hay campos obligatorios que varían según el estado del marcador.
- Según el campo de *Estado* , los marcadores se guardarán como borrador, sugerido, programado, excluido o se publicarán automáticamente.
- Para los socios que administran varias organizaciones, puede exportar sus marcadores de una organización e importarlos en otro. Sin embargo, debe quitar los datos de la columna *ID* antes de importar.

### <a name="prevent-import-errors"></a>Evitar errores de importación

Si hay datos obligatorios que faltan o no son válidos, recibirá un mensaje de error y se generará un archivo de registro con información adicional acerca de las filas y columnas que se deben corregir. Realice cualquier cambio necesario y pruebe a importar de nuevo el archivo. No puede importar o guardar los marcadores hasta que se hayan solucionado todos los errores.

Para evitar errores, asegúrese de que el archivo de importación tiene el formato adecuado y de que:

- Incluye todas la fila de encabezado y todas las columnas que había en la plantilla de importación
- El orden de las columnas es el mismo que en la plantilla de importación
- Todas las columnas tienen valores, excepto los tres que pueden estar vacíos: *ID*, *Last Modified* y *Last Modified by*
- La columna *Estado* no está vacía; se trata de información necesaria.
- Al importar marcadores publicados, sugeridos, programados o borradores, se necesitan las columnas *título*, *dirección URL* y *palabras clave* .
- Al importar marcadores excluidos, la columna *URL* es obligatoria.

Para evitar errores de duplicación de marcadores a marcadores:

- No use direcciones URL duplicadas para marcadores diferentes. Si una dirección URL está asignada a otro marcador e intenta agregarla de nuevo desde un archivo de importación, recibirá un error. Esto también se aplica a las direcciones URL duplicadas para otros tipos de respuestas.
- Al actualizar los marcadores existentes, use la columna *identificador de marcador* . Puede actualizar cualquier otra propiedad de un marcador existente, como palabra clave o descripción, pero debe asegurarse de que el *identificador del marcador* se encuentra en la columna correspondiente del archivo de importación. Si el *identificador de marcador* está presente, no se tratará como nueva adición y no se procesará como un error.

### <a name="publish-or-review-recommended-bookmarks"></a>Publicar o revisar los marcadores recomendados

Para reducir el esfuerzo manual necesario para agregar marcadores, Microsoft Search puede evaluar los vínculos de SharePoint en su organización y recomendar los marcadores, y puede revisarlos antes de publicarlos o configurarlos para que los publique automáticamente. No se necesita ninguna configuración para los marcadores recomendados, están habilitados y configurados para la publicación automática de forma predeterminada. Para cambiar esta configuración en cualquier momento, seleccione **administrar marcadores** para abrir el panel Configuración de marcadores.

![Captura de pantalla de la configuración de marcadores recomendada en el portal de administración de Microsoft 365](media/bookmarks-recommendedsettings.png)

Si los marcadores recomendados están habilitados, el motor de recomendación evaluará los sitios de SharePoint de la organización para identificar los vínculos de tráfico alto. Después de un período de evaluación inicial, los marcadores recomendados se publicarán o agregarán automáticamente a la lista de marcadores sugeridos. A continuación, se iniciará el ciclo siguiente: un período de evaluación de 30 días seguido de la publicación automática o la adición de marcadores sugeridos.

Le recomendamos a los administradores o editores de búsqueda que revisen estos marcadores, que se publican automáticamente o sugeridos de manera regular. Además, los marcadores recomendados nunca incluirán direcciones URL que se encuentren en marcadores publicados, sugeridos, programados o excluidos existentes.

Para asegurarse de que solo los usuarios con acceso verán un marcador recomendado en sus resultados de trabajo, se incluye una característica de comprobación de acceso para todos los marcadores recomendados. Los usuarios que no tienen permisos para obtener acceso a un sitio de SharePoint nunca verán el marcador recomendado para ese sitio. Esta comprobación de acceso está controlada por el valor de la opción **solo los usuarios con acceso a este vínculo** en la configuración de grupos de cada marcador recomendado.

Se detendrá la comprobación de acceso si se cambia la dirección URL en el marcador recomendado o en la configuración de grupos.

Para evitar que el motor de recomendación publique o sugiera un marcador a un sitio en particular, puede Agregar la dirección URL a una lista de excluidos. El motor de recomendaciones nunca publicará ni sugerirá un marcador para un sitio excluido o una página dentro de un sitio excluido.

## <a name="about-keywords-and-reserved-keywords"></a>Palabras clave y palabras clave reservadas

Un marcador puede tener varias palabras clave y los marcadores pueden compartir la misma palabra clave, pero la palabra clave Reserved no se puede compartir. Una palabra clave reservada es un término o frase exclusiva que desencadena un marcador específico. Una palabra clave reservada se puede asociar solo con una respuesta. Use las palabras clave reservadas con moderación.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**P: ¿Cuánto tiempo tarda un marcador en estar visible en Microsoft Search después de publicarlo?**

**A:**  Hay un marcador disponible en Microsoft Search inmediatamente después de la publicación.

**P: ¿Cuánto tiempo tarda un marcador recomendado en aparecer?**

**A:**  Los marcadores recomendados sólo aparecerán en Microsoft Search si están habilitados tanto los marcadores recomendados como la publicación automática. Durante el período de evaluación inicial, el motor de recomendación evaluará el tráfico de SharePoint para identificar los marcadores adecuados y, a continuación, los publicará automáticamente. Una vez publicadas, estarán disponibles inmediatamente en Microsoft Search.

**P: ¿recomienda Microsoft Search los marcadores de sitios en todos los idiomas?**

**A**: sí, Microsoft Search puede recomendar marcadores de cualquier sitio interno de SharePoint, independientemente del idioma.

**P: ¿puedo dejar de mostrar los marcadores recomendados en los resultados de búsqueda?**

**A:** Para dejar de mostrar los marcadores recomendados, desactive la configuración de autopublicación en el centro de administración. Los marcadores recomendados se agregarán a la lista de marcadores sugeridos.

**P: ¿Cómo puedo identificar un marcador recomendado en los resultados de búsqueda o en el centro de administración?**

**A:** En los resultados de la búsqueda, los marcadores recomendados incluyen la frase "sugerida para usted" antes de la dirección URL. En el centro de administración, los marcadores recomendados tendrán el valor "sistema" como propietario.

**P: ¿cómo se administra el acceso a un marcador recomendado?**

**Un**: un motor de acceso con ingeniería de Microsoft determina si la dirección URL del marcador es accesible para un usuario determinado y solo mostrará el marcador recomendado a la audiencia correcta. Sin embargo, si se modifica la dirección URL o se cambia la configuración de los grupos, se deshabilitará el motor de acceso con ingeniería.

**P: ¿Qué ocurre si no se realiza ninguna acción en los marcadores recomendados agregados a la lista de sugerencias?**

**A: para** evitar un gran volumen de marcadores en la lista sugerida, se depurará un marcador recomendado (propietario = sistema) después de 180 días.

**P: ¿Dónde encuentro el identificador de aplicación de una aplicación de energía?**

**A**: vaya al sitio de Power apps y vea el panel de detalles de la aplicación. Obtenga más información sobre cómo [obtener un identificador de aplicación](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id).
