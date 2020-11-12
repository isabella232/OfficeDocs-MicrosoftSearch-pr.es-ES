---
title: Administración de comentarios de los usuarios
ms.author: lebhansa
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
ROBOTS: NoIndex
description: Revisar y actuar sobre los comentarios de los usuarios en Microsoft Search
ms.openlocfilehash: 332410cd29a7256cccd651c3a668fdf3eb473ba4
ms.sourcegitcommit: 102371815e739da33d1711197cdc743ae8124baa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "48996796"
---
# <a name="managing-user-feedback"></a>Administración de comentarios de los usuarios

La creación de una buena experiencia de búsqueda para los usuarios es una colaboración entre Microsoft y el administrador de búsqueda. Los comentarios de los usuarios nos permiten evaluar de forma continua el producto y ajustarlo para obtener la mejor experiencia. Sin embargo, algunos comentarios son los que se le ofrecen mejor.

Ahora estamos ofreciendo herramientas que le permitirán revisar y administrar los comentarios que los usuarios ofrecen en la experiencia de búsqueda.

## <a name="how-users-submit-feedback"></a>Cómo envían comentarios los usuarios

Como los usuarios de la organización usan Microsoft Search, es posible que tengan comentarios sobre la experiencia. Al hacer clic en un vínculo de comentarios de la página de resultados, pueden clasificar sus comentarios e incluir comentarios adicionales.

![Formulario de comentarios global](media/feedback/feedback-global-dialog.png)

Los usuarios también tienen la opción de enviar su consulta y otra información de diagnóstico, junto con la categoría y los comentarios, a Microsoft. [Obtenga más información](https://privacy.microsoft.com/en-US/privacystatement) sobre privacidad y cómo se protegen estos datos. Los datos de diagnóstico contienen la información más importante que Microsoft necesita para usar el elemento de comentarios para mejorar el producto.

La mayoría de los envíos de comentarios aparecen en la sección de [comentarios](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) del centro de administración de búsqueda de Microsoft. Los comentarios enviados con la categoría deseo **sugerir un vínculo interno** aparecen como un marcador sugerido en la sección [marcadores](https://admin-ignite.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) y se pueden ver filtrando según el estado **sugerido** .

## <a name="review-feedback"></a>Revisar comentarios

En la página [comentarios](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) , puede revisar y exportar comentarios que los usuarios de su organización han enviado en los últimos 30 días. Una vez que un usuario envíe comentarios, aparecerá en esta lista en un plazo de 20 minutos. Puede usar el botón actualizar para asegurarse de que está viendo los datos más actuales

Mediante el uso de un filtro, puede ver comentarios sobre tipos de respuesta específicos. También puede filtrar por origen y por intervalo de fechas.

Puede usar el cuadro de búsqueda sobre la lista de comentarios para buscar comentarios en una consulta específica.

En la lista de comentarios, la columna textual indica qué comentarios del usuario también incluyen un comentario o una sugerencia. Para leerlo, haga clic en la consulta para abrir el panel de **detalles** .

## <a name="update-feedback-state"></a>Estado de comentarios de actualización

A medida que lleguen los comentarios, éste estará en un estado *nuevo* y permanecerá ahí hasta que lo cambie a *resuelto* o *duplicado*.

Para cambiar este estado:

1. Junto a la consulta, seleccione **más opciones** (tres puntos verticales).
1. En el menú, seleccione **marcar como resuelto** o **marcar como duplicado.**
1. La lista se actualizará y se mostrará el estado actualizado.

También puede actualizar el estado de varios elementos, simplemente seleccionarlos y, a continuación, seleccionar más opciones a continuación de cualquiera de estos elementos.

## <a name="export-feedback"></a>Exportar comentarios

Si desea compartir los comentarios de búsqueda con otros o conservarlos durante más de 30 días, haga clic en **exportar.** Se descargará automáticamente un archivo. csv denominado comentarios con fecha, como "Feedbacks_10_31_2020.csv".

## <a name="send-user-feedback-to-microsoft"></a>Enviar comentarios de los usuarios a Microsoft

De forma predeterminada, todos los comentarios de los usuarios se envían a Microsoft y se agregan a usted. Para dejar de enviar comentarios a Microsoft, haga clic en **Administrar configuración** y desactive la casilla de verificación **enviar automáticamente comentarios de los usuarios a Microsoft** . Este cambio puede tardar hasta 24 horas en surtir efecto.

Si ha decidido no enviar comentarios a Microsoft de forma automática, podrá seguir enviando comentarios individuales a Microsoft.

1. Seleccione los comentarios que desea compartir.
1. En la barra de acciones, seleccione más (tres puntos) y haga clic en **Enviar comentarios a Microsoft**.

1. El estado de la columna enviado a Microsoft cambiará a pendiente. Cuando se envíen los comentarios, se cambiará a sí.

Si comparte los comentarios de forma automática o manual, nunca incluye consultas y otra información de diagnóstico para los usuarios que opten por no incluir esta información.

## <a name="suggestions-on-how-to-use-feedback"></a>Sugerencias sobre cómo usar los comentarios

Como administrador de búsqueda, debe comprender los principales roles de la organización y los tipos de contenido con los que los usuarios interactúan normalmente y buscar. Con esta comprensión, puede usar comentarios para realizar mejoras dirigidas a la experiencia de búsqueda de los usuarios.

1. "No he encontrado lo que busco" y se pueden usar comentarios similares para identificar el contenido que los usuarios quieren, pero actualmente no está incluido en el índice de búsqueda. La determinación de esto suele llevar a cabo la investigación y la inferencia según la comprensión de los usuarios. Una vez encontrado, decida qué métodos para incluir ese contenido sería más adecuado:
    1. Los marcadores son útiles para orígenes de contenido que tienen una página de inicio de alta calidad y una variedad limitada de términos de búsqueda, de modo que la comunidad de usuarios obtiene un resultado de gran calidad del marcador y, a continuación, encuentra lo que busca.
    1. Q&A son útiles para respuestas individuales que son bastante frecuentes, pero no cambian.
    1. Los conectores son útiles para orígenes de contenido con una amplia variedad de contenido y una amplia variedad de términos de búsqueda.
1. "Los resultados tardaron demasiado en cargarse" & "he encontrado un problema" puede ser un indicador de un problema más amplio. Buscar estos comentarios diariamente puede ayudarle y, si aparecen varios casos, puede comprobar la experiencia de búsqueda para usted mismo y abrir un caso de soporte técnico de Microsoft si es necesario. Este tipo de comentarios también es importante para Microsoft y es una razón excelente para enviarnos comentarios.
1. "Quiero sugerir un vínculo interno" puede evaluarse para agregarse como marcadores o como contenido conectado. El primer pensamiento debe ser un marcador; Si el marcador obtiene un uso elevado, puede considerar la posibilidad de traer contenido a través de un conector para habilitar una experiencia de búsqueda incluso más rica.
