---
title: Haga el contenido fácil de encontrar con Búsqueda de Microsoft
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Cree marcadores, ubicaciones y preguntas y respuestas para hacer fácil de encontrar el contenido de su organización.
ms.openlocfilehash: 77b6507c7643e6cf2176f37a9a2cf0def1c640ba
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973727"
---
# <a name="make-content-easy-to-find"></a>Haga el contenido fácil de encontrar

Búsqueda de Microsoft ayuda a los usuarios a encontrar contenido relevante. Es una forma segura de realizar búsquedas de contenido en su intranet y en la Web. Este tipo de integración en la Web y las organizaciones solo está disponible en Microsoft. Con la Búsqueda de Microsoft, los administradores pueden usar sus conocimientos de una organización para facilitar a los usuarios la búsqueda de contenido relevante. 

## <a name="components-that-find-content"></a>Componentes que encuentran contenido
En Búsqueda de Microsoft, los administradores crean [Marcadores,](manage-bookmarks.md) [PowerApps,](integrate-powerapps.md) [preguntas&A](manage-qas.md)y [Ubicaciones](manage-locations.md) que facilitan la búsqueda de contenido. Cada uno de estos componentes incluye un título, una dirección URL y un conjunto de palabras clave que lo activan.

## <a name="bookmarks"></a>Marcadores
Puede crear [marcadores en](manage-bookmarks.md) unos pocos pasos. Cada marcador incluye un título, una dirección URL y un conjunto de palabras clave que lo desencadenan. Un marcador puede tener varias palabras clave y varios marcadores pueden compartir la misma palabra clave. Pero las palabras clave reservadas no se pueden compartir. Al crear o modificar un marcador, el índice de búsqueda se actualiza y el marcador está inmediatamente disponible para los usuarios.

Si su organización ha **promovido los resultados** configurados en [SharePoint](http://sharepoint.com/), puede importar esos resultados a Búsqueda de Microsoft. Con los resultados promocionados, puede rellenar rápidamente los resultados de búsqueda, poner el contenido a disposición de los usuarios y hacer que Búsqueda de Microsoft sea más eficaz en cuanto lo configure. Le recomendamos que use los resultados promocionados de SharePoint como referencia para comprender cómo nombrar y crear resultados de búsqueda relevantes. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Agregar o editar marcadores mediante extensiones del explorador
Los administradores de búsqueda pueden crear fácilmente búsquedas de contenido mediante las extensiones del navegador. Para agregar el sitio como marcador, instale la extensión del explorador. A continuación, vaya al sitio y agrégrelo como marcador. Para obtener más información, vea [Administrar marcadores](manage-bookmarks.md).

Actualmente, las extensiones de explorador están [disponibles para Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) y Google [Chrome:](https://www.google.com) 
- Para descargar la extensión perimetral, vaya a la [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Para descargar la extensión de Chrome, vaya a la [tienda web de Chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="powerapps"></a>PowerApps

Al agregar [PowerApps existentes](integrate-powerapps.md) a los [marcadores,](manage-bookmarks.md)los usuarios pueden completar tareas como especificar el tiempo de vacaciones o informar de los gastos. 

Con [PowerApps,](integrate-powerapps.md)puedes crear aplicaciones empresariales que se ejecuten en un explorador o en un teléfono o tableta. No se requiere experiencia de codificación. PowerApps funciona en cualquier explorador y en cualquier dispositivo. Se necesitan menos de un minuto para agregar. Para obtener más información sobre PowerApps, consulte estos artículos:
- [Aprendizaje guiado](/learn/browse/?products=powerapps)
- [Documentación de PowerApps](/powerapps/maker/canvas-apps/get-sessionid)
- [Inicio de PowerApps](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Agregar una PowerApp a un marcador

1. Busca el [identificador de](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) la aplicación para la PowerApp que quieras agregar.
1. En el Microsoft 365 [de administración,](https://admin.microsoft.com)vaya **a Configuración**  >  **Búsqueda de Microsoft**. 
1. Agregue un marcador o busque un marcador al que desee agregar una PowerApp.
1. En **Configuración de marcador,** seleccione **Power App**. A **continuación, seleccione Agregar una aplicación power**.
1. Escriba el **identificador de la aplicación**. El alto y el ancho se ajustan automáticamente. [Los marcadores](manage-bookmarks.md) pueden admitir orientaciones verticales y horizontales, pero actualmente no se puede cambiar el tamaño. Para facilitar la prueba, la vista previa del marcador muestra una PowerApp totalmente funcional.
1. Seleccione **Publicar** o **Guardar como borrador**.

## <a name="qa"></a>Preguntas y respuestas

Crear una [pregunta&A](manage-qas.md) es como crear [marcadores.](manage-bookmarks.md) Con preguntas&A, puede proporcionar respuestas a las preguntas de los usuarios en lugar de solo un vínculo a la página web. Puede dar formato a las respuestas en texto enriquecido mediante las herramientas disponibles. Si un marcador y una pregunta&A comparten la misma palabra clave, el resultado del marcador se muestra primero. Al igual que los marcadores, el&índice A se actualiza inmediatamente después de agregar o cambiar una&A. 

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
> No puede importar preguntas&Elementos A si hay errores en el archivo de plantilla. Para evitar errores, asegúrese de que el archivo de importación tiene el formato correcto e incluye toda la información necesaria. Vea más información sobre cómo evitar [errores de importación](#prevent-import-errors).

## <a name="locations"></a>Ubicaciones

Con [Ubicaciones,](manage-locations.md)los usuarios pueden encontrar direcciones y localizar los edificios de la organización. La **característica** Ubicaciones proporciona una ubicación precisa para oficinas, campus y edificios, así como indicaciones y navegación. Para obtener mejores resultados, los administradores deben agregar todas las ubicaciones importantes de sus organizaciones a Búsqueda de Microsoft. A [diferencia de bookmarks](manage-bookmarks.md) [y preguntas&A,](manage-qas.md)el índice Locations no se actualiza inmediatamente. Las ubicaciones nuevas o modificadas pueden tardar varias horas en aparecer en los resultados de la búsqueda.

## <a name="get-started"></a>Comenzar
Para averiguar qué necesitan los usuarios y facilitar la detección de esa información, pruebe algunos de estos métodos:

- Use los registros de búsqueda de intranet para determinar los sitios y páginas que obtienen la mayor parte del tráfico.
- Determine las herramientas, sitios y aplicaciones que se usan de forma diaria o semanal.
- Busque vínculos directos a prestaciones para empleados.
- Busque directivas y procesos que los usuarios deben conocer
- Decida a quién se pondrán en contacto los usuarios para obtener soporte técnico y cómo lo hacen.
- Obtenga información que sea necesaria de forma periódica, ya sea de forma estacional o basada en ciclos de negocio. Un ejemplo son las personas que buscan herramientas para reservar el tiempo libre o las actualizaciones financieras trimestrales.
- Recopilar directivas para usuarios regionales o móviles. Los ejemplos son ventajas que varían según la ubicación.
- Determine los sitios internos y la información de las búsquedas web comunes. Algunos ejemplos son tráfico, información de transporte público, meteorología local, descuentos disponibles de socios corporativos y programas de salud y fitness.
- Busque información sobre eventos, conferencias o retiradas patrocinados por la empresa.
- Investigue los problemas y preguntas frecuentes (FAQ) y respuestas comunes en TI, recursos humanos y soporte técnico.

## <a name="involve-smes-and-users"></a>Implicar a pymes y usuarios
En una organización, los usuarios buscan una variedad de temas simples a complejos. Ejemplos sencillos son las direcciones de oficina y los beneficios de los empleados. Los ejemplos complejos son nuevos procesos de trabajo, información técnica y contenido de procedimientos. Para crear o encontrar una gran variedad de contenido, necesita experiencia en diferentes campos, temas y tecnologías. 

La mayoría de los administradores de búsqueda no tienen conocimientos específicos sobre cada tema. Para escalar la cantidad de contenido disponible sin ayuda de recursos externos, busque experiencia y conocimientos de otros usuarios de su organización.

### <a name="get-content-from-smes"></a>Obtener contenido de pymes
Aproveche los expertos en la materia (PYME) de su organización, incluidos los expertos de recursos humanos, soporte técnico, ventas, tecnología y otras áreas clave. Las pymes pueden aportar contenido directamente si los agrega como editores Búsqueda de Microsoft usuario. 

### <a name="involve-your-users"></a>Implique a los usuarios
Pida a los usuarios que sugieran recursos para los marcadores. Pida también a los usuarios que informen de errores como vínculos rotos o no válidos.

## <a name="set-up-components"></a>Configurar componentes
Para agregar o editar [marcadores únicos o masivos,](manage-bookmarks.md)preguntas&[A](manage-qas.md)y [Ubicaciones](manage-locations.md), siga los pasos de las secciones siguientes. 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Agregar o editar un único marcador, preguntas&A o componente de ubicación
1. En el Microsoft 365 [de administración,](https://admin.microsoft.com)vaya **a Configuración**  >  **Búsqueda de Microsoft**. Seleccione la pestaña con nombre del componente. La **pestaña Marcadores** está seleccionada de forma predeterminada.
1. Para agregar un componente, seleccione **Agregar nuevo**. 
1. Para editar un componente, seleccione el marcador en la lista de componentes correspondiente. 
1. Al agregar o editar la información, la vista previa se actualizará automáticamente.

### <a name="bulk-add-or-edit-components"></a>Agregar o editar componentes en masa
Con las **características de** importación **y** exportación, los administradores de búsqueda pueden crear o editar en masa [Marcadores,](manage-bookmarks.md) [preguntas&A](manage-qas.md)y [Ubicaciones](manage-locations.md). Esta característica es útil cuando un administrador desea agregar o editar muchos componentes. 

Las características de importación y exportación proporcionan estas funciones:
- **Agregar en masa**. Agregue detalles en el archivo de plantilla del componente y, a continuación, impórlo.
- **Edición masiva**. Exporte componentes a un archivo CSV, edite los detalles del marcador en el CSV exportado y, a continuación, importe el CSV actualizado.
- **Importar sitios promocionados desde [SharePoint](http://sharepoint.com/)**. Esta característica solo se aplica a [bookmarks](manage-bookmarks.md).
- **Copia de seguridad**. Exportar componentes a un archivo CSV.

Para importar o exportar componentes, siga estos pasos:
1. En la esquina superior derecha de la pestaña con nombre del componente, seleccione **Importar**. 
1. Para descargar todos los componentes existentes en un archivo CSV, seleccione **Exportar**.
1. En el panel derecho, elija la opción para importar mediante un archivo CSV o desde [SharePoint](http://sharepoint.com/).
1. Para obtener una lista de los campos y detalles necesarios, descargue el archivo de plantilla del componente. 
1. Agregue o edite detalles del componente en el archivo de plantilla. A continuación, guárdelo en el equipo. 
1. En el panel **Importar** del componente, seleccione **Examinar**. A continuación, seleccione el archivo CSV que desee y seleccione **Importar**.

### <a name="template-guidelines"></a>Directrices de plantilla
Tenga en cuenta estas directrices y restricciones cuando trabaje con archivos de plantilla:
- Nunca edite los datos en estos campos: *Id,* *Last Modified* y Last *Modified By*.
- Si incluye el *identificador de* un marcador existente, se reemplaza por la información del archivo de importación.
- Si hay un marcador con el mismo título o dirección URL en el archivo existente, el marcador se actualiza con información en el archivo de importación.
- No todos los campos del archivo de plantilla son obligatorios y los campos obligatorios varían en función del estado del marcador.
- Según el campo *Estado,* los marcadores se guardan como **borrador,** **sugerido** o **programado**. De lo contrario, se publican automáticamente.
- Si administra varias organizaciones, puede exportar los marcadores de una organización e importarlos a otra. Sin embargo, debe eliminar los datos de la columna *Id* antes de la importación.

> [!Note]
> No puede importar elementos de componente si hay errores en el archivo de plantilla. Para evitar errores, asegúrese de que el archivo de importación tiene el formato correcto e incluye toda la información necesaria.

### <a name="prevent-import-errors"></a>Evitar errores de importación

Recibe un mensaje de error si falta algún dato necesario o no es válido. Un archivo de registro genera con más información sobre las filas y columnas que se deben corregir. Realice las modificaciones necesarias e intente volver a importar el archivo. No puede importar ni guardar ningún marcador hasta que se resuelvan todos los errores.

Para evitar errores, asegúrese de que el archivo de importación tiene el formato correcto y cumple estos requisitos:
- Se incluyen la fila de encabezado y todas las columnas de la plantilla de importación.
- El orden de columna es el mismo que la plantilla de importación.
- Todas las columnas tienen valores, excepto las tres que pueden estar vacías: *Id,* *Last Modified* y Last *Modified By*. 
- La *columna* Estado no está vacía.

### <a name="titles-and-descriptions"></a>Títulos y descripciones
Los títulos y descripciones conectados ayudan a los usuarios a determinar si los resultados responden a su consulta de búsqueda. Los títulos y descripciones buenos reflejan el propósito principal del resultado. Un ejemplo es el título **Childcare benefits** con la descripción Obtenga información sobre *las ventajas para ayudar a pagar los costos de cuidado infantil.* Con estos datos conectados,  los usuarios que buscan cuidado infantil pueden encontrar beneficios de soporte monetario y obtener un vínculo para obtener más información.

### <a name="keywords"></a>Palabras clave
Con palabras clave, los usuarios de la organización pueden buscar y encontrar contenido relevante. Debe asociar términos de palabra clave con sus resultados de búsqueda relacionados. Búsqueda de Microsoft sugiere palabras clave basadas en el título y la dirección URL del contenido. Para identificar más palabras clave, obtenga respuestas a estas preguntas:

1. **¿Qué términos de búsqueda pueden encontrar la información que identificó?** Consulte cualquier terminología existente en su organización, así como variaciones, acrónimos, temas y temas relacionados.
1. **¿Qué variaciones o palabras usan las personas para hablar de esta información?** Pida al equipo de soporte técnico que proporcione esas palabras clave.

Por ejemplo, si crea un resultado que se vincula a una herramienta para enviar solicitudes de vacaciones, las palabras clave **vacaciones** y **enviar** solicitud de vacaciones son buenas opciones para incluir. Los usuarios de la organización también pueden buscar información relacionada con las vacaciones con **vacaciones** o **tiempo libre**. Para facilitar a los usuarios la búsqueda de contenido  relevante, agregue esas palabras clave y otras como enviar solicitud de vacaciones y **solicitar tiempo de espera**.

### <a name="reserved-keywords"></a>Palabras clave reservadas
 Una palabra reservada es un término único o una frase que desencadena un resultado. A diferencia de otras palabras clave, las palabras clave reservadas solo se asocian con un resultado. Use las palabras reservadas con moderación para permitir que Búsqueda de Microsoft aprenda en función del uso.

Un ejemplo es un marcador de un sitio para enviar las horas. Si **el tiempo de** registro es una palabra  clave reservada, los usuarios de la organización que buscan tiempo de registro verán ese sitio como el único marcador en el cuadro Búsqueda de Microsoft registro. 

### <a name="group-related-content-with-keywords"></a>Agrupar contenido relacionado con palabras clave
Si desea que los usuarios encuentren conjuntos de contenido relacionado cuando busquen un término específico, asigne la misma palabra clave a todo el contenido relacionado. Un ejemplo es una búsqueda de procesos y herramientas en torno a los cambios de estado de vida. Para agrupar respuestas en la actualización de beneficios, información fiscal y cambios de nombre y alias, incluya una palabra clave como **el matrimonio**.

### <a name="search-settings"></a>Configuración de búsqueda
Con la configuración de búsqueda, puede adaptar el contenido y dirigirse a grupos específicos de usuarios. Estos Búsqueda de Microsoft control de configuración cuando aparece un resultado de búsqueda y quién puede verlo:

- **Fecha**. Para controlar cuándo el contenido está disponible o no disponible, establezca una fecha de inicio y una fecha de finalización. Por ejemplo, el material que distingue el tiempo aparece en los resultados de búsqueda cuando es relevante.
- **País o región**. Puede seleccionar países o regiones, de modo que solo los usuarios de esas ubicaciones vean determinado contenido. Por ejemplo, la información específica del país aparece solo en los resultados de búsqueda en esos países.
- **La configuración** de grupo hace que los resultados estén disponibles solo para los miembros de grupos seleccionados. Por ejemplo, si crea sitios que se relacionan solo con los empleados del departamento de recursos humanos, asigne esta configuración al grupo de seguridad de RECURSOS humanos adecuado.
- **Dispositivo u sistema operativo**. Seleccione tipos de dispositivos o sistemas operativos, por lo que solo los usuarios que busquen en esos dispositivos o usen esos sistemas verán ese marcador.
- **Variaciones dirigidas**. Esta configuración varía el contenido de un marcador en función del dispositivo y la ubicación de un usuario.

## <a name="test-your-content"></a>Probar el contenido
Después de crear [marcadores](manage-bookmarks.md) y [preguntas&A](manage-qas.md), compruebe estos resultados:
- Aparece el marcador correcto o&A.
- Todos los contenidos agrupados con palabras clave aparecen juntos según lo planeado.
- No aparece nada inesperado en las respuestas de búsqueda.
- El marcador o preguntas&A tiene suficiente información.

Los usuarios y las pymes que contribuyen a la creación de contenido pueden ayudar a probar y validar los resultados de la búsqueda.

## <a name="review-and-update-periodically"></a>Revise y actualice periódicamente
La información relevante [como Marcadores](manage-bookmarks.md) [y preguntas&A](manage-qas.md) debe mantenerse actualizada. Siga estos pasos con regularidad:
- Corregir o quitar direcciones URL rotas e no válidas.
- Quite marcadores o preguntas&A que ya no sean relevantes.
- Compruebe si ha habido cambios en herramientas, nombres de sitios o nombres de equipos.
- Tenga en cuenta si el marcador o&A es lo suficientemente autoritativo o necesita una descripción más clara.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Obtener información sobre marcadores, preguntas&A y ubicaciones

Búsqueda de Microsoft muestra cuántos [marcadores,](manage-bookmarks.md) [preguntas&A](manage-qas.md)y [Ubicaciones](manage-locations.md) se publican, programan o sugieren. El [panel Ideas muestra](./usage-reports.md) marcadores, preguntas&A y totales de ubicación por estado:

- **Publicados**: el número de resultados publicados que están disponibles para los usuarios
- **Programados**: el número de resultados programados en el proceso de publicación
- **Sugeridos**: el número de sugerencias de los usuarios

Marcadores [sugeridos,](manage-bookmarks.md) [preguntas&A](manage-qas.md)y [Ubicaciones](manage-locations.md) son un buen indicador de las diferencias en el contenido. Le ayudan a comprender lo que buscan los usuarios, pero no encuentran. Estos datos pueden indicar que necesita crear más marcadores, preguntas&A o Ubicaciones. O es posible que necesite actualizar el contenido existente mediante palabras clave mejores, palabras clave reservadas y cadenas de búsqueda para que el contenido sea más detectable.

### <a name="review-top-search-queries"></a>Revise las consultas de búsqueda más populares

Para averiguar qué búsquedas generaron más impresiones en los últimos 90 días, revise las consultas de búsqueda superiores. *Impression* significa cuántas veces se ha visto una página en los resultados de búsqueda. La **tarjeta Consultas** principales del panel de [Ideas](./usage-reports.md) muestra las 25 búsquedas de usuario principales para cada tipo de resultado, el número total de búsquedas y la tasa de clics (CTR). Con este informe, puede identificar el volumen de consulta de búsqueda y determinar las consultas con actividad de búsqueda alta y baja.

El recuento de búsquedas bajo puede indicar la insatisfacción del usuario. Los usuarios no buscan ese contenido o usan palabras clave diferentes para encontrarlo. La CTR muestra la frecuencia con la que los usuarios seleccionan los resultados promovidos y el nivel de utilidad de sus reglas de consulta y sus resultados para los usuarios. Un CTR bajo indica que los usuarios encuentran el contenido, pero no satisface sus necesidades. En estos casos, revise el contenido. Para alinear el contenido con las consultas de búsqueda, asegúrese de que coincide con los títulos, descripciones y palabras clave de búsqueda y actualización de los usuarios. 

### <a name="analyze-impressions-by-result-type"></a>Analizar impresiones por tipo de resultado.

Los gráficos fáciles de  leer en la tarjeta de distribución De impresión [del panel](./usage-reports.md) de Ideas muestran impresiones en varios períodos de tiempo. La escala de tiempo muestra el número diario de impresiones para un tipo de resultado. Con estos gráficos, puede determinar qué tipo de resultado se usa con más frecuencia o con poca frecuencia. El uso poco frecuente de un tipo de resultado determinado no significa necesariamente que el tipo de resultado no sea bueno. Únicamente indica cómo utilizan los usuarios los resultados de búsqueda.

 Si los usuarios prefieren un tipo de resultado determinado, es posible que cree más resultados de búsqueda del mismo tipo. Para asegurarse de que las palabras clave son adecuadas, revise las palabras clave de los tipos de resultados con un uso bajo. Con este informe, también puede ver cambios en el comportamiento del usuario con el tiempo.