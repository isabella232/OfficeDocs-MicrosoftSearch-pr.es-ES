---
title: Administración de las respuestas de acrónimo en Microsoft Search
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Respuestas de crear y actualizar acrónimos en Microsoft Search
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728010"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>La administración de acrónimos responde en Microsoft Search

Los usuarios a menudo se encontraban con acrónimos y abreviaturas desconocidos que usa su organización o equipo. Los términos específicos de organizaciones o equipos pueden ser nuevos para los usuarios que se mueven de un equipo a otro, trabajan con equipos de asociados internos o son nuevos en la organización.

Las organizaciones no siempre tienen una referencia única para su terminología estándar. La ausencia de una sola referencia hace que sea difícil encontrar definiciones o expansiones para estos acrónimos. Microsoft Search resuelve ese problema con acrónimos.

## <a name="what-users-experience"></a>Qué experiencia tienen los usuarios

Microsoft Search los usuarios pueden obtener definiciones con acrónimos en [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)y [Office 365](https://Office.com). En el cuadro de **búsqueda** , los usuarios escriben consultas como estos ejemplos:

- *Qué es* DNN
- *Definir* DNN
- *Definición* de DNN
- *Expandir* DNN
- *Expansión* DNN
- *Significado de* DNN
- DNN *significa*

El resultado incluye todos los significados de DNN que están presentes en la organización del usuario.

> [!NOTE]
> Los usuarios deben escribir una consulta que incluya las *palabras clave* especificadas en el acrónimo para activar sus respuestas correspondientes. Las consultas de acrónimo no distinguen entre mayúsculas y minúsculas.

## <a name="set-up-acronyms-answers"></a>Configurar las respuestas de los acrónimos

En el [centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**acrónimos**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)y, después, seleccione **Agregar acrónimo**.

Microsoft Search consulta dos orígenes de datos para proporcionar a los acrónimo respuestas a las búsquedas de los usuarios:

1. **Admin-creados**. LO proporcionan los administradores de TI en el [centro de administración](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).
2. **Sistema-creados**. Descubierto por Microsoft Search desde el correo electrónico y los documentos de los usuarios y los datos disponibles públicamente dentro de la organización.

### <a name="set-up-admin-curated-acronyms"></a>Configurar acrónimos creados de administración

Los administradores de búsqueda pueden agregar acrónimos en la [pestaña acrónimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) del  [centro de administración de Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch). Puede Agregar acrónimos desde cualquier sitio o repositorio interno al centro de administración. Estos acrónimos se pueden agregar al estado **publicado** o **borrador** :

**Estado publicado**. Los acrónimos están disponibles para los usuarios de la organización a través de Microsoft Search.

> [!NOTE]
> Los acrónimos agregados al estado publicado pueden tardar hasta tres días en estar disponibles en Microsoft Search.

**Estado de borrador**. Si desea revisar un acrónimo antes de que esté disponible en Microsoft Search, puede Agregar el acrónimo en un estado de borrador. Los acrónimos en el estado de borrador no aparecerán en los resultados de la búsqueda. Tendrá que mover el acrónimo al estado publicado para que aparezca en los resultados de la búsqueda.

Puede Agregar acrónimos de forma individual o en bloque para importarlos en un archivo CSV. Cargue un archivo CSV con los campos que se muestran en la tabla siguiente:

| Acrónimo (obligatorio) | Expansión (obligatoria) | Descripción  | Origen | Estado (obligatorio) |
| --------- | --------- | ---------- | --------- |--------- |
| *XXX* | *Abreviatura de ortografía* |  | *URL* | *Publicado o borrador* |

### <a name="csv-fields"></a>Campos CSV

**Acrónimo**. Contiene la forma corta o el acrónimo real. Un ejemplo es *DNN*.

**Expansión**. Contiene la expansión del acrónimo. Un ejemplo es una *red neuronal profunda*.

**Descripción**. Breve descripción del acrónimo que proporciona a los usuarios más información sobre el acrónimo y su expansión. Por ejemplo, *una red neuronal profunda es una red neuronal con cierto nivel de complejidad, una red neuronal con más de dos capas*.

**Origen**. La dirección URL de la página o sitio web al que desea que vayan los usuarios para obtener más información sobre el acrónimo.

**Estado**. Este campo puede tener dos valores:

- **Borrador**. Agrega el acrónimo al estado de borrador.
- **Publicado**. Agrega el acrónimo al estado publicado y lo hace disponible en Microsoft Search.

### <a name="system-curated-acronyms"></a>Acrónimos del sistema creados

Puede que sea un reto para los administradores agregar todos los acrónimos que se usan en una organización a las respuestas. Esta característica puede encontrar acrónimos que los administradores de búsqueda aún no conocen. Para ello, Microsoft Search también detecta y curates acrónimos de estos orígenes:

- Mensajes de correo electrónico de los usuarios
- Documentos en [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)y [Microsoft OneNote](https://www.onenote.com/)
- Documentos públicos de la organización a los que los usuarios tienen acceso en SharePoint, OneDrive o OneNote

Microsoft Search se asegura de que solo los usuarios con acceso y permisos a un documento puedan ver los acrónimos que se detectan en él. Cuando se encuentra un acrónimo en el buzón de un usuario, el usuario solo puede ver ese acrónimo.

> [!NOTE]
> No se necesita ninguna configuración para los acrónimos admin-creados.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**P: ¿cómo se clasifican los datos de administrador-creados y del sistema creados?**

**A:** La clasificación de los resultados puede variar de una persona a otra, ya que los resultados se personalizan para cada usuario. Ninguna de estas categorías siempre tendrá prioridad sobre la otra.

**P: ¿Cuánto tiempo se tarda en ver los acrónimos creados de administración en Microsoft Search después de publicarlos?**

**A:**  Los acrónimos agregados al estado publicado tardan hasta tres días en estar disponibles en Microsoft Search.

**P: ¿Cómo responden los usuarios que desencadenan acrónimos?**

**A: para** obtener respuestas de acrónimos, los usuarios deben escribir patrones de consulta específicos en un cuadro de **búsqueda** de [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365](https://Office.com) .

**P: ¿Cuánto tiempo tardan los acrónimos del sistema creados en aparecer después de recibir o enviar un nuevo correo electrónico o documento?**

**A:** Los acrónimos que se encuentran en un nuevo documento o correo electrónico pueden tardar hasta siete días en aparecer en los resultados de la búsqueda de Microsoft.

**P: ¿es necesario que los documentos estén en un formato específico para que la extracción los recoja?**

**A:** No. Admitimos todos los tipos de archivo excepto Image, folders y zip.

**P: ¿Microsoft detectará acrónimos de los documentos en todos los idiomas?**

**A**: Microsoft solo admite la extracción de documentos en inglés. La compatibilidad con otros idiomas se agregará en fases.

**P: ¿Qué sucede si mi organización no quiere mostrar acrónimos del sistema creados? ¿Puedo dejar de mostrar este tipo de acrónimo en mis resultados de búsqueda?**

**A: para** desactivar los acrónimos del creados del sistema en los resultados de la búsqueda, cree un vale de soporte al cliente siguiendo las instrucciones en [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).
Después de crear un vale de soporte técnico, tarda hasta 48 horas para que los acrónimos del creados del sistema dejen de aparecer en los resultados de la búsqueda.
