---
title: Haga el contenido fácil de encontrar con Búsqueda de Microsoft
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Cree marcadores, ubicaciones y preguntas y respuestas para hacer fácil de encontrar el contenido de su organización.
ms.openlocfilehash: 605610264e2068deb6215c3157efc24cf0b0a2fd
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626832"
---
# <a name="make-content-easy-to-find"></a>Haga el contenido fácil de encontrar

Búsqueda de Microsoft ayuda a los usuarios a encontrar contenido relevante. Es una forma segura de buscar en el contenido de la intranet y de la Web. Este tipo de integración en la web y las organizaciones solo está disponible en Microsoft. Con Microsoft Search, los administradores pueden usar su conocimiento de una organización para que los usuarios puedan encontrar fácilmente el contenido relevante. 

## <a name="components-that-find-content"></a>Componentes que encuentran contenido
En Microsoft Search, los administradores crean [marcadores](manage-bookmarks.md), [PowerApps](integrate-powerapps.md), [Q&a](manage-qas.md)y [ubicaciones](manage-locations.md) que facilitan la búsqueda de contenido. Cada uno de estos componentes incluye un título, una dirección URL y un conjunto de palabras clave que lo activan.

## <a name="bookmarks"></a>Marcadores
Puede crear [marcadores](manage-bookmarks.md) en tan solo unos pocos pasos. Cada marcador incluye un título, una dirección URL y un conjunto de palabras clave que lo desencadenan. Un marcador puede tener varias palabras clave y varios marcadores pueden compartir la misma palabra clave. Pero las palabras clave reservadas no se pueden compartir. Al crear o modificar un marcador, el índice de búsqueda se actualiza y el marcador está inmediatamente disponible para los usuarios.

Si su organización ha **promocionado los resultados** configurados en [SharePoint](http://sharepoint.com/), puede importar los resultados en Microsoft Search. Con los resultados promovidos, puede rellenar rápidamente los resultados de la búsqueda, poner el contenido a disposición de los usuarios y hacer que Microsoft Search sea más eficaz en cuanto se configura. Le recomendamos que use los resultados promocionados de SharePoint como referencia para comprender cómo nombrar y crear resultados de búsqueda relevantes. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Agregar o editar marcadores mediante extensiones del explorador
Los administradores de búsqueda pueden crear fácilmente búsquedas de contenido mediante las extensiones del navegador. Para agregar el sitio como marcador, instale la extensión del explorador. A continuación, vaya al sitio y agréguelo como un marcador. Para obtener más información, vea [Manage bookmarks](manage-bookmarks.md).

Actualmente, las extensiones del explorador están disponibles para [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) y [Google Chrome](https://www.google.com): 
- Para descargar la extensión de Edge, ve a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Para descargar la extensión Chrome, vaya al [almacén Web de Chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="powerapps"></a>PowerApps

Al agregar el [PowerApps](integrate-powerapps.md) existente a sus [marcadores](manage-bookmarks.md), los usuarios pueden completar tareas como especificar el tiempo de vacaciones o informar sobre gastos. 

Con [PowerApps](integrate-powerapps.md), puede crear aplicaciones empresariales que se ejecuten en un explorador o en un teléfono o una tableta. No se requiere ninguna experiencia de codificación. PowerApps funcionan en cualquier explorador y en cualquier dispositivo. Agregar es menos de un minuto. Para obtener más información acerca de PowerApps, consulte estos artículos:
- [Aprendizaje guiado](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [Documentación de PowerApps](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [PowerApps Home](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Agregar una PowerApp a un marcador

1. Busque el [identificador](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) de la aplicación PowerApp que desea agregar.
1. En el centro de [Administración](https://admin.microsoft.com)de Microsoft 365, vaya a **configuración** > de**Microsoft Search**. 
1. Agregue un marcador o busque un marcador al que desee agregar una PowerApp.
1. En **configuración de marcadores**, seleccione **Power App**. A continuación, seleccione **Agregar una aplicación de energía**.
1. Escriba el **identificador**de la aplicación. El alto y el ancho se ajustan automáticamente. Los [marcadores](manage-bookmarks.md) pueden admitir orientaciones verticales y horizontales, pero actualmente no se puede cambiar el tamaño. Para que sea más fácil probarlo, la vista previa del marcador muestra una PowerApp completamente funcional.
1. Seleccione **Publicar** o **Guardar como borrador**.

## <a name="qa"></a>Preguntas y respuestas

La creación de un [&Q](manage-qas.md) es similar a la creación de [marcadores](manage-bookmarks.md). Con Q&a, puede proporcionar respuestas a las preguntas de los usuarios en lugar de solo un vínculo a la Página Web. Puede dar formato a las respuestas en texto enriquecido mediante las herramientas disponibles. Si un marcador y un Q&A comparten la misma palabra clave, el resultado del marcador se muestra primero. Al igual que los marcadores, el&Q un índice se actualiza inmediatamente después de agregar o cambiar un Q&A. 

### <a name="supported-html-tags"></a>Etiquetas HTML compatibles

Puede usar contenido HTML o agregar etiquetas HTML a su respuesta o descripción. Admitimos estas etiquetas HTML:
 
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

Las etiquetas no admitidas se omiten o se muestran como texto. Asegúrese de que obtiene una vista previa de las tarjetas.

> [!Note]
> No puede importar Q&A Items si hay errores en el archivo de plantilla. Para evitar errores, asegúrese de que el archivo de importación tiene el formato correcto y que incluye toda la información necesaria. Vea más información sobre cómo [evitar errores de importación](#prevent-import-errors).

## <a name="locations"></a>Ubicaciones

Con las [ubicaciones](manage-locations.md), los usuarios pueden buscar direcciones y localizar los edificios de la organización. La característica de **ubicaciones** proporciona una ubicación precisa para las oficinas, Campus y edificios, así como para las direcciones y la navegación. Para obtener los mejores resultados, los administradores deben agregar todas las ubicaciones importantes de sus organizaciones a Microsoft Search. A diferencia de los [marcadores](manage-bookmarks.md) y [Q&A](manage-qas.md), el índice de ubicaciones no se actualiza inmediatamente. Las ubicaciones nuevas o modificadas pueden tardar varias horas en aparecer en los resultados de la búsqueda.

## <a name="get-started"></a>Introducción
Para averiguar qué necesitan sus usuarios y facilitar la detección de la información, pruebe con alguno de estos métodos:

- Use los registros de búsqueda de intranet para determinar los sitios y páginas que obtienen la mayor parte del tráfico.
- Determine las herramientas, sitios y aplicaciones que se usan de forma diaria o semanal.
- Busque vínculos directos a prestaciones para empleados.
- Busque directivas y procesos que los usuarios deben conocer
- Decida quiénes son los usuarios que contactan con soporte técnico y cómo lo hacen.
- Obtenga la información que necesita de forma recurrente, ya sea de manera estacional o basada en ciclos de negocios. Un ejemplo son las personas que buscan herramientas para reservar el tiempo libre o las actualizaciones financieras trimestrales.
- Recopilar directivas para usuarios regionales o móviles. Algunos ejemplos son beneficios que varían según la ubicación.
- Determine los sitios internos y la información de las búsquedas web comunes. Algunos ejemplos son el tráfico, la información de tránsito público, el tiempo local, los descuentos disponibles de los socios corporativos y los programas de salud y bienestar.
- Busque información sobre eventos, conferencias o retiradas patrocinados por la empresa.
- Investigue los problemas y preguntas frecuentes (FAQ) y respuestas comunes en TI, recursos humanos y soporte técnico.

## <a name="involve-smes-and-users"></a>Implicar a PYME y usuarios
En una organización, los usuarios buscan un intervalo de temas simples a complejos. Ejemplos sencillos son las direcciones de oficina y los beneficios de los empleados. Ejemplos complejos son los nuevos procesos de trabajo, información técnica y contenido sobre procedimientos. Para crear o encontrar una amplia variedad de contenido, necesita experiencia en diferentes campos, temas y tecnologías. 

La mayoría de los administradores de búsqueda no tienen conocimientos específicos en cada tema. Para escalar la cantidad de contenido disponible sin ayuda de recursos externos, obtenga conocimientos y experiencia de otros usuarios de su organización.

### <a name="get-content-from-smes"></a>Obtener contenido de las PYME
Aproveche a los expertos en la materia (SME) de su organización, incluidos expertos de recursos humanos, soporte técnico, ventas, tecnología y otras áreas clave. Las PYME pueden aportar contenido directamente si los agrega como editores de Microsoft Search. 

### <a name="involve-your-users"></a>Implique a los usuarios
Pida a los usuarios que sugieran recursos para los marcadores. También se pide a los usuarios que informen sobre errores como vínculos rotos o no válidos.

## <a name="set-up-components"></a>Configurar componentes
Para agregar o editar [marcadores](manage-bookmarks.md)únicos o masivos, [Q&a](manage-qas.md)y [ubicaciones](manage-locations.md), siga los pasos descritos en las secciones siguientes. 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Agregar o editar un solo marcador, un&un o un componente de ubicación
1. En el centro de [Administración](https://admin.microsoft.com)de Microsoft 365, vaya a **configuración** > de**Microsoft Search**. Seleccione la pestaña Nombre del componente. La pestaña **marcadores** está seleccionada de forma predeterminada.
1. Para agregar un componente, seleccione **Agregar nuevo**. 
1. Para editar un componente, seleccione el marcador en la lista de componentes relevantes. 
1. Al agregar o editar la información, la vista previa se actualizará automáticamente.

### <a name="bulk-add-or-edit-components"></a>Adición o edición en masa de componentes
Con las características de **importación** y **exportación** , los administradores de búsqueda pueden crear o editar de forma masiva [marcadores](manage-bookmarks.md), [preguntas&A](manage-qas.md)y [ubicaciones](manage-locations.md). Esta característica es útil cuando un administrador desea agregar o editar muchos componentes. 

Las características de importación y exportación proporcionan estas funciones:
- **Adición en masa**. Agregue detalles en el archivo de plantilla del componente y, a continuación, impórtelo.
- **Edición en masa**. Exporte componentes a un archivo CSV y, a continuación, edite los detalles del marcador en el CSV exportado y, a continuación, importe el CSV actualizado.
- **Importar sitios promocionados desde [SharePoint](http://sharepoint.com/)**. Esta característica solo se aplica a los [marcadores](manage-bookmarks.md).
- **Copia de seguridad**. Exportar componentes a un archivo CSV.

Para importar o exportar componentes, siga estos pasos:
1. En la esquina superior derecha de la pestaña Nombre del componente, seleccione **importar**. 
1. Para descargar todos los componentes existentes en un archivo CSV, seleccione **exportar**.
1. En el panel derecho, elija la opción para importar mediante un archivo CSV o desde [SharePoint](http://sharepoint.com/).
1. Para obtener una lista de los campos y detalles obligatorios, descargue el archivo de plantilla del componente. 
1. Agregue o edite los detalles del componente en el archivo de plantilla. Guárdelo en el equipo. 
1. En el panel de **importación** del componente, seleccione **examinar**. A continuación, seleccione el archivo CSV que quiera y seleccione **importar**.

### <a name="template-guidelines"></a>Instrucciones para plantillas
Tenga en cuenta estas directrices y restricciones al trabajar con archivos de plantilla:
- Nunca modifique datos en estos campos: *ID*, *última modificación*y *última modificación por*.
- Si incluye el *identificador* de un marcador existente, se reemplaza con la información del archivo de importación.
- Si hay un marcador con el mismo título o dirección URL en el archivo existente, el marcador se actualiza con información en el archivo de importación.
- No todos los campos del archivo de plantilla son obligatorios y los campos obligatorios varían en función del estado del marcador.
- Basándose en el campo de *Estado* , los marcadores se guardan como **borradores**, **sugeridos**o **programados**. De lo contrario, se publican automáticamente.
- Si administra varias organizaciones, puede exportar sus marcadores de una organización e importarlos en otro. Sin embargo, debe eliminar los datos de la columna *Id* antes de la importación.

> [!Note]
> No puede importar elementos de componente si hay errores en el archivo de plantilla. Para evitar errores, asegúrese de que el archivo de importación tiene el formato correcto y que incluye toda la información necesaria.

### <a name="prevent-import-errors"></a>Evitar errores de importación

Recibe un mensaje de error si faltan datos necesarios o no son válidos. Un archivo de registro genera con más información acerca de las filas y columnas que se van a corregir. Realice las modificaciones necesarias e intente volver a importar el archivo. No puede importar ni guardar ningún marcador hasta que se resuelvan todos los errores.

Para evitar errores, asegúrese de que el archivo de importación tiene el formato correcto y cumple con los siguientes requisitos:
- Se incluyen la fila de encabezado y todas las columnas de la plantilla de importación.
- El orden de las columnas es el mismo que el de la plantilla de importación.
- Todas las columnas tienen valores, excepto los tres que pueden estar vacíos: *ID*, *Last Modified*y *Last Modified by*. 
- La columna *Estado* no está vacía.

### <a name="titles-and-descriptions"></a>Títulos y descripciones
Los títulos y las descripciones conectados ayudan a los usuarios a determinar si los resultados responden a su consulta de búsqueda. Los títulos y las descripciones de calidad reflejan el propósito principal del resultado. Un ejemplo es el título **Childcare beneficios** con la descripción *obtenga información sobre las ventajas para ayudarle a pagar los costos*de la Childcare. Con estos datos conectados, los usuarios que busquen **Childcare** pueden encontrar ventajas de soporte técnico monetario y obtener un vínculo para obtener más información.

### <a name="keywords"></a>Palabras clave
Con las palabras clave, los usuarios de la organización pueden buscar y buscar contenido relevante. Debe asociar los términos de palabra clave con los resultados de la búsqueda relacionados. Microsoft Search sugiere palabras clave en función del título y la dirección URL de su contenido. Para identificar más palabras clave, Obtenga respuestas a estas preguntas:

1. **¿Qué términos de búsqueda pueden encontrar la información identificada?** Consulte la terminología existente de su organización, así como variaciones, acrónimos, temas y temas relacionados.
1. **¿Qué variantes o palabras usan los usuarios para hablar de esta información?** Pídale al equipo de soporte técnico que le proporcione esas palabras clave.

Por ejemplo, si crea un resultado que vincula a una herramienta para enviar solicitudes de vacaciones, las palabras clave **vacaciones** y **Enviar solicitud de vacaciones** son buenas opciones para incluirlas. Los usuarios de su organización también podrían buscar información relacionada con vacaciones con **vacaciones** o con **tiempo libre**. Para que sea más fácil para los usuarios buscar contenido relevante, agregue las palabras clave y otras personas como **enviar solicitudes de vacaciones** y **solicitar tiempo**de inactividad.

### <a name="reserved-keywords"></a>Palabras clave reservadas
 Una palabra reservada es un término único o una frase que desencadena un resultado. A diferencia de otras palabras clave, las palabras clave reservadas se asocian con un solo resultado. Use las palabras reservadas con moderación para permitir que Búsqueda de Microsoft aprenda en función del uso.

Un ejemplo es un marcador de un sitio para enviar sus horas. Si la **hora del registro** es una palabra clave reservada, los usuarios de la organización que busquen tiempo de **registro** verán ese sitio como el único marcador en el cuadro de búsqueda de Microsoft. 

### <a name="group-related-content-with-keywords"></a>Agrupar contenido relacionado con palabras clave
Si desea que los usuarios encuentren conjuntos de contenido relacionado cuando buscan un término específico, asigne la misma palabra clave a todo el contenido relacionado. Un ejemplo es una búsqueda de procesos y herramientas relacionadas con los cambios de estado de la vida. Para agrupar las respuestas en la actualización de beneficios, información fiscal y cambios de nombre y alias, incluya una palabra clave como **matrimonio**.

### <a name="search-settings"></a>Configuración de búsqueda
Con la configuración de búsqueda, puede adaptar el contenido y dirigirse a grupos específicos de usuarios. Este control de configuración de Microsoft Search cuando aparece un resultado de búsqueda y quién puede verlo:

- **Fecha**. Para controlar si el contenido está disponible o no, establezca una fecha de inicio y una fecha de finalización. Por ejemplo, el material sensible al tiempo aparece en los resultados de la búsqueda cuando es relevante.
- **País o región**. Puede seleccionar países o regiones, por lo que solo los usuarios de esas ubicaciones verán cierto contenido. Por ejemplo, la información específica del país aparece en los resultados de la búsqueda sólo en esos países.
- La configuración de **Grupo** hace que los resultados estén disponibles solo para los miembros de grupos seleccionados. Por ejemplo, si crea sitios que solo están relacionados con los empleados del Departamento de RRHH, asigne esta configuración al grupo de seguridad de recursos humanos correspondiente.
- **Dispositivo o sistema operativo**. Seleccione los tipos de dispositivo o sistemas operativos, de modo que solo los usuarios que realicen búsquedas en esos dispositivos o usen esos sistemas verán ese marcador.
- **Variaciones de destino**. Esta configuración varía el contenido de un marcador en función del dispositivo y la ubicación de un usuario.

## <a name="test-your-content"></a>Probar el contenido
Después de crear [marcadores](manage-bookmarks.md) y [Q&A](manage-qas.md), compruebe estos resultados:
- Aparece el marcador o el&Q correctos.
- Todo el contenido agrupado junto con palabras clave aparece juntos según lo planeado.
- No aparece nada inesperado en las respuestas de búsqueda.
- El marcador o Q&A tiene información suficiente.

Los usuarios y las PYME que contribuyen a la creación de contenido pueden ayudar a probar y validar los resultados de la búsqueda.

## <a name="review-and-update-periodically"></a>Revise y actualice periódicamente
Información autoritativa como [marcadores](manage-bookmarks.md) y [Q&](manage-qas.md) a debe permanecer actualizada. Lleve a cabo estos pasos con regularidad:
- Corrija o quite las direcciones URL no válidas y rotas.
- Quite los marcadores o Q&A que ya no son relevantes.
- Compruebe si ha habido cambios en herramientas, nombres de sitios o nombres de equipos.
- Considere si el marcador o Q&A tiene la autoridad suficiente o necesita una descripción más clara.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Obtener información sobre marcadores, Q&A y ubicaciones

Microsoft Search muestra el número de [marcadores](manage-bookmarks.md), [Q&A](manage-qas.md)y [ubicaciones](manage-locations.md) publicadas, programadas o sugeridas. El [Panel de información](get-insights.md) muestra los totales de marcador, Q&A y ubicación por estado:

- **Publicados**: el número de resultados publicados que están disponibles para los usuarios
- **Programados**: el número de resultados programados en el proceso de publicación
- **Sugeridos**: el número de sugerencias de los usuarios

Los [marcadores](manage-bookmarks.md)sugeridos, [Q&A](manage-qas.md)y las [ubicaciones](manage-locations.md) son un buen indicador de brechas en el contenido. Le ayudan a comprender lo que los usuarios buscan pero no encuentran. Estos datos pueden indicar que necesita crear más marcadores, Q&A o ubicaciones. O bien, es posible que deba actualizar el contenido existente con mejores palabras clave, palabras clave reservadas y cadenas de búsqueda para que el contenido sea más detectable.

### <a name="review-top-search-queries"></a>Revise las consultas de búsqueda más populares

Para averiguar qué búsquedas generaron la mayor cantidad de impresiones en los últimos 90 días, revise las consultas de búsqueda más importantes. *Impresión* significa el número de veces que se vio una página en los resultados de la búsqueda. La tarjeta de **consultas principales** del [Panel de información](get-insights.md) muestra las 25 principales búsquedas de usuario para cada tipo de resultado, el número total de búsquedas y la tasa de clics (CTR). Con este informe, puede identificar el volumen de consultas de búsqueda y determinar las consultas con una actividad de búsqueda alta y baja.

El recuento de búsquedas bajo puede indicar insatisfacción del usuario. Los usuarios no están buscando ese contenido o usan palabras clave diferentes para buscarlo. La CTR muestra la frecuencia con la que los usuarios seleccionan los resultados promovidos y el nivel de utilidad de sus reglas de consulta y sus resultados para los usuarios. Una CTR baja indica que los usuarios encuentran el contenido, pero no satisface sus necesidades. En estos casos, revise el contenido. Para alinear el contenido de las consultas de búsqueda, asegúrese de que coincida con la búsqueda de los usuarios y actualice los títulos, descripciones y palabras clave. 

### <a name="analyze-impressions-by-result-type"></a>Analizar impresiones por tipo de resultado.

Los gráficos de fácil lectura en la tarjeta de **distribución de impresión** del [Panel de información](get-insights.md) muestran impresiones sobre distintos intervalos de tiempo. La escala de tiempo muestra el número diario de impresiones para un tipo de resultado. Con estos gráficos, puede determinar qué tipo de resultado se usa con más frecuencia o con poca frecuencia. Un uso poco frecuente de un tipo de resultado concreto no significa necesariamente que el tipo de resultado no es bueno. Únicamente indica cómo utilizan los usuarios los resultados de búsqueda.

 Si un tipo de resultado determinado es preferido por los usuarios, puede crear más resultados de búsqueda del mismo tipo. Para asegurarse de que las palabras clave son apropiadas, revise las palabras clave de los tipos de resultados con poco uso. Con este informe, también puede ver los cambios en el comportamiento del usuario a lo largo del tiempo.
