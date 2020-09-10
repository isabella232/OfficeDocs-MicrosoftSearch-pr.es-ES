---
title: Vista previa de conectores
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Obtenga información sobre la vista previa de conectores de Microsoft Graph para Microsoft Search.
ms.openlocfilehash: 81d169074a316b6ab07f47156e0f057e50c12e3e
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422896"
---
# <a name="microsoft-graph-connectors-preview"></a>Vista previa de conectores de Microsoft Graph

Los conectores de las API de Búsqueda de Microsoft (consulta e índice) y Microsoft Graph están actualmente en estado de vista previa. Para obtener acceso a la funcionalidad de los conectores, debe activar la opción de lanzamiento de destino en su espacio empresarial. Se trata de una vista previa temprana y no hay garantía de nivel de servicio. Animamos a los clientes a probar la funcionalidad de los conectores y a proporcionar comentarios. No se recomienda usar conectores para fines de producción durante el período de versión preliminar.

## <a name="set-up-targeted-release"></a>Configurar versión de destino

Para probar los conectores, debe tener establecida la opción **Release dirigida** para todos los usuarios de la organización. Para obtener más información sobre la opción de lanzamiento de destino y cómo configurarla, consulte [configurar las opciones estándar o de versión de destino en Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).

## <a name="choose-a-preview-environment"></a>Elegir un entorno de vista previa

Para probar los conectores, las API de indización y las API de búsqueda, recomendamos estos dos métodos:

1. **Inquilino de prueba**.  Le recomendamos que use un inquilino de prueba para probar la vista previa de conectores de Microsoft Graph.

2. **Colección de sitios de prueba**. Si no tiene un inquilino de prueba, puede crear una colección de sitios de prueba para probar la funcionalidad de los conectores. Para mostrar los resultados de los conectores sin afectar a las páginas de búsqueda en ninguna otra parte de la organización, personalice la experiencia de búsqueda de solo esa colección de sitios.

## <a name="preview-limitations"></a>Limitaciones de la vista previa

La versión preliminar tiene las siguientes limitaciones:

* El rendimiento de la recopilación se limita a unos cuatro elementos por segundo.

* No hay compatibilidad con las actualizaciones del esquema. Después de crear una configuración de conexión, no hay forma de actualizar el esquema. Solo puede eliminar y volver a crear la conexión.

* El contenido indizado solo se muestra en la página de resultados de búsqueda bajo una vertical personalizada. Esta restricción se aplica al contenido con tipos personalizados.

* Es posible que sea necesario eliminar y volver a crear todas las conexiones que configuró durante el período de versión preliminar. Estas conexiones ya no funcionarán si son incompatibles con los cambios realizados para mejorar el producto.

* Hay un límite de conexiones. Cada inquilino puede crear hasta 10 conexiones.

* Tamaño del repositorio de origen. Le recomendamos que obtenga una vista previa de los conectores con un repositorio de origen de unos 200.000 elementos, ya que se trata de nuestro límite de escala de búsqueda probada. Estamos trabajando para mejorar el rendimiento de la búsqueda y esperamos admitir tamaños de repositorios más grandes en un futuro próximo.

* La compatibilidad de edición para la conexión no está disponible. Una vez creada la conexión, no podrá modificarla ni cambiarla. Si necesita cambiar algún detalle, debe eliminar y volver a crear la conexión.

* El contenido del conector solo se puede buscar en vertical personalizados.

* El contenido de los conectores de una sola conexión se puede mostrar en cada vertical personalizada y requiere la creación del tipo de resultado.
