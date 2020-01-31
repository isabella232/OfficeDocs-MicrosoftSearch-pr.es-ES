---
title: Vista previa de conectores
ms.author: mounika.narayanan
author: monaray
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
ms.openlocfilehash: 52bf174875bf3e262c0cb71d53ec209e481ee0b7
ms.sourcegitcommit: 1e8dc8e10722ed26ba85cbb5e8c9df62f3625de6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41578691"
---
# <a name="microsoft-graph-connectors-preview"></a>Vista previa de conectores de Microsoft Graph

Los conectores de Microsoft Graph y las API de Microsoft Search (consulta e índice) están actualmente en estado de versión preliminar. Para obtener acceso a la funcionalidad de los conectores, debe solicitar participar en el programa de vista previa enviando el <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">formulario de registro de vista previa de conectores de Microsoft Graph</a>. Se trata de una vista previa temprana y no hay garantía de nivel de servicio. Animamos a los clientes a probar la funcionalidad de los conectores y a proporcionar comentarios. No se recomienda usar conectores para fines de producción durante el período de versión preliminar.

## <a name="set-up-targeted-release"></a>Configurar versión de destino
Para probar los conectores, debe tener establecida la opción **Release dirigida** para todos los usuarios de la organización. Los requisitos de la versión dirigida se aplican independientemente de los siguientes entornos de vista previa que elija.
Para obtener más información sobre la opción de lanzamiento de destino y cómo configurarla, consulte <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">configurar las opciones estándar o de versión de destino en Office 365</a>.

## <a name="choose-a-preview-environment"></a>Elegir un entorno de vista previa 
Para probar los conectores, las API de indización y las API de búsqueda, recomendamos estos dos métodos:
1. **Inquilino de prueba**.  Le recomendamos que use un inquilino de prueba para probar la vista previa de conectores de Microsoft Graph.
2. **Colección de sitios de prueba**. Si no tiene un inquilino de prueba, puede crear una colección de sitios de prueba para probar la funcionalidad de los conectores. Para mostrar los resultados de los conectores sin afectar a las páginas de búsqueda en ninguna otra parte de la organización, personalice la experiencia de búsqueda de solo esa colección de sitios.

## <a name="preview-limitations"></a>Limitaciones de la vista previa
La versión preliminar tiene las siguientes limitaciones: 
* El rendimiento de la recopilación se limita a unos cuatro elementos por segundo.
* No hay compatibilidad con las actualizaciones del esquema. Después de crear una configuración de conexión, no hay forma de actualizar el esquema. Solo puede eliminar y volver a crear la conexión.
* El contenido indizado solo se muestra en la página de resultados de búsqueda bajo una vertical personalizada. Esta restricción se aplica al contenido con tipos personalizados.
* Antes de la disponibilidad general, es posible que sea necesario eliminar y volver a crear todas las conexiones que configuró durante el período de versión preliminar. Estas conexiones ya no funcionarán si son incompatibles con los cambios realizados para mejorar el producto.
* Hay un límite de conexiones. Cada inquilino puede crear hasta 10 conexiones.
