---
title: Administración de comentarios de los usuarios
ms.author: lebhansa
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
description: Revisar y actuar sobre los comentarios de los usuarios en Búsqueda de Microsoft
ms.openlocfilehash: 37ea70862cd4881170288339427f5ab1f150bf31
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702016"
---
# <a name="managing-user-feedback"></a>Administración de comentarios de los usuarios

Crear una gran experiencia de búsqueda para los usuarios es una asociación entre Microsoft y el administrador de búsqueda. Los comentarios de los usuarios nos permiten evaluar continuamente el producto y ajustarlo para la mejor experiencia. Algunos comentarios, sin embargo, se abordan mejor por usted.

Ahora ofrecemos herramientas que le permitirán revisar y administrar los comentarios que los usuarios proporcionan en la experiencia de búsqueda.

## <a name="how-users-submit-feedback"></a>Cómo envían los usuarios comentarios

A medida que los usuarios de la organización usan Búsqueda de Microsoft, es posible que tengan comentarios sobre la experiencia. Cuando hacen clic en un vínculo de comentarios en la página de resultados, pueden clasificar sus comentarios e incluir comentarios adicionales.

![Formulario de comentarios globales.](media/feedback/feedback-global-dialog.png)

Los usuarios también tienen la opción de enviar su consulta y otra información de diagnóstico, junto con la categoría y los comentarios, a Microsoft. [Obtenga más información](https://privacy.microsoft.com/en-US/privacystatement) sobre privacidad y cómo protegemos estos datos. Los datos de diagnóstico contienen la información más crítica que Microsoft necesita para usar el elemento de comentarios para la mejora del producto.

La mayoría de los envíos de comentarios aparecen [en](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) la sección Comentarios del centro Búsqueda de Microsoft administración. Los comentarios enviados con **I want to suggest an internal link** category aparecen como un marcador sugerido en la sección [Marcadores](https://admin-ignite.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) y se pueden ver filtrando en **Estado** sugerido.

## <a name="review-feedback"></a>Comentarios de revisión

En la [página Comentarios,](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) puede revisar y exportar los comentarios que los usuarios de su organización han enviado durante los últimos 30 días. Una vez que un usuario envía comentarios, aparecerá en esta lista en 20 minutos. Puede usar el botón actualizar para asegurarse de que está viendo los datos más actuales

Mediante el uso de un filtro, puede ver comentarios para tipos de respuesta específicos. También puede filtrar por origen y intervalo de fechas.

Puede usar el cuadro de búsqueda encima de la lista de comentarios para buscar comentarios en una consulta específica.

En la lista de comentarios, la columna Verbatim indica qué comentarios del usuario también incluyen un comentario o sugerencia. Para leerlo, haga clic en la consulta para abrir **el** panel Detalles.

>[!NOTE]
>Durante el lanzamiento inicial en las experiencias de búsqueda de administrador y usuario final, los elementos de comentarios pueden tardar hasta dos semanas en aparecer en el portal de administración.

## <a name="update-feedback-state"></a>Estado de comentarios de actualización

A medida que lleguen los comentarios, estará en un estado *Nuevo* y permanecerá allí hasta que lo cambie a *Resuelto* o *Duplicado*.

Para cambiar este estado:

1. Junto a la consulta, seleccione **Más opciones** (tres puntos verticales).
1. En el menú, seleccione **Marcar como resuelto** o Marcar como **duplicado.**
1. La lista se actualizará y mostrará el estado actualizado.

También puede actualizar el estado de varios elementos, solo selecciónelos y, a continuación, seleccione Más opciones junto a cualquiera de esos elementos.

## <a name="export-feedback"></a>Exportar comentarios

Si desea compartir comentarios de búsqueda con otros usuarios o retenerlos durante más de 30 días, haga clic en **Exportar.** Se descargará automáticamente .csv un archivo de .csv denominado Comentarios con la fecha, como "Feedbacks_10_31_2020.csv".

## <a name="send-user-feedback-to-microsoft"></a>Enviar comentarios de los usuarios a Microsoft

De forma predeterminada, todos los comentarios de los usuarios se envían a Microsoft y se le su adición. Para dejar de enviar comentarios a Microsoft, haga **clic** en Administrar configuración y desactive la casilla Enviar automáticamente comentarios de usuario **a Microsoft.** Este cambio puede tardar hasta 24 horas en tener efecto.

Si has decidido no enviar comentarios a Microsoft automáticamente, puedes enviar comentarios individuales a Microsoft.

1. Seleccione los comentarios que desea compartir.
1. En la barra de acciones, seleccione Más (tres puntos) y haga clic en **Enviar comentarios a Microsoft**.

1. El estado de la columna Enviado a Microsoft cambiará a Pendiente. Cuando se envíen los comentarios, cambiará a Sí.

Si compartes comentarios de forma automática o manual, nunca incluye consultas ni otra información de diagnóstico para los usuarios que optaron por no incluir esta información.

## <a name="suggestions-on-how-to-use-feedback"></a>Sugerencias sobre cómo usar comentarios

Como administrador de búsqueda, debe comprender las personas principales de la organización y los tipos de contenido con los que las personas suelen interactuar y buscar. Con este conocimiento, puede usar los comentarios para realizar mejoras dirigidas a la experiencia de búsqueda de los usuarios.

1. "No he encontrado lo que estaba buscando" y se pueden usar comentarios similares para identificar el contenido que los usuarios desean, pero actualmente no se incluye en el índice de búsqueda. Determinar esto a menudo requiere investigación e inferencia en función de la comprensión de los usuarios. Una vez encontrado, decida qué métodos de incluir ese contenido serían los más adecuados:
    1. Los marcadores son útiles para los orígenes de contenido que tienen una página de aterrizaje de alta calidad y una variedad limitada de términos de búsqueda, de modo que la comunidad de usuarios obtiene un resultado de alta calidad del marcador y, a continuación, puede encontrar eficazmente lo que está buscando.
    1. P&A son útiles para respuestas individuales que son bastante frecuentes, pero que no cambian.
    1. Los conectores son útiles para orígenes de contenido con una amplia variedad de contenido y una amplia variedad de términos de búsqueda.
1. "Los resultados tardaron demasiado tiempo en cargarse" & "He encontrado un problema" pueden ser indicadores de un problema más amplio. Buscar estos comentarios diariamente puede ayudar y, si aparecen varios casos, puedes comprobar la experiencia de búsqueda por ti mismo y abrir un caso de soporte técnico con Microsoft si es necesario. Este tipo de comentarios también es importante para Microsoft y es una excelente razón para enviarnos todos los comentarios.
1. "Quiero sugerir un vínculo interno" se puede evaluar para agregarse como marcadores o contenido conectado. Su primer pensamiento debe ser un marcador; si el marcador tiene un uso alto, puede considerar la posibilidad de incorporar contenido a través de un conector para habilitar una experiencia de búsqueda aún más enriqueciendo.
