---
title: Administrar respuestas acrónimos en Microsoft Search
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
description: Crear y actualizar respuestas de acrónimos en Microsoft Search
ms.openlocfilehash: 5677ff6915c9e43e2559964c40086cb360a05db7
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031372"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Administrar respuestas de acrónimos en Microsoft Search

A menudo, los usuarios se topar con acrónimos y abreviaturas desconocidos usados por su organización o equipo. Los términos que son específicos de organizaciones o equipos pueden ser nuevos para las personas que se mueven de un equipo a otro, trabajan con equipos asociados internos o son nuevos en la organización.

Las organizaciones no siempre tienen una sola referencia para su terminología estándar. La falta de una sola referencia hace que sea difícil encontrar definiciones o expansiones para estos acrónimos. Microsoft Search resuelve ese problema con acrónimos.

## <a name="what-users-experience"></a>Qué experiencia tienen los usuarios

Los usuarios de Microsoft Search pueden obtener definiciones con acrónimos en [Bing,](https://Bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)y [Office 365](https://Office.com). En el **cuadro Buscar,** los usuarios escriben consultas como estos ejemplos:

- *Qué es* DNN
- *Definir* DNN
- Definición *de* DNN
- *Expandir* DNN
- Expansión *de* DNN
- *Significado de* DNN
- DNN *significa*

El resultado incluye todos los significados de DNN que están presentes en la organización del usuario.

> [!NOTE]
> Los usuarios deben escribir una consulta que incluya las palabras clave *especificadas* del acrónimo para desencadenar sus respuestas correspondientes. Las consultas de acrónimos no distinguen mayúsculas de minúsculas.

## <a name="set-up-acronyms-answers"></a>Configurar respuestas acrónimos

En el [Centro de administración de Microsoft 365,](https://admin.microsoft.com)vaya a [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)y, a continuación, **seleccione Agregar acrónimos**.

Microsoft Search consulta dos orígenes de datos para proporcionar acrónimos respuestas a las búsquedas de los usuarios:

1. **Curada por el administrador.** Proporcionado por los administradores de TI en el [Centro de administración.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)
2. **System-curated**. Detectado por Microsoft Search a partir del correo electrónico y los documentos de los usuarios y los datos disponibles públicamente en la organización.

### <a name="set-up-admin-curated-acronyms"></a>Configurar acrónimos seleccionados por el administrador

Los administradores de búsqueda pueden agregar acrónimos en la pestaña [Acrónimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) del Centro de administración  [de Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch). Puede agregar acrónimos desde cualquier sitio o repositorio interno al Centro de administración. Estos acrónimos se pueden agregar al **estado Publicado** o **Borrador:**

**Estado publicado**. Los acrónimos están disponibles para los usuarios de la organización a través de Microsoft Search.

> [!NOTE]
> Los acrónimos agregados al estado publicado pueden tardar hasta tres días en estar disponibles en Microsoft Search.

**Estado de borrador**. Si desea revisar un acrónimo antes de que esté disponible en Microsoft Search, puede agregar el acrónimo en estado Borrador. Las siglas en estado Borrador no aparecerán en los resultados de la búsqueda. Deberá mover el acrónimo al estado Publicado para que aparezca en los resultados de la búsqueda.

Puede agregar acrónimos individualmente o importarlos masivamente en un archivo CSV. Cargue un archivo CSV con los campos que se muestran en la tabla siguiente:

| Acrónimo (obligatorio) | Expansión (obligatoria) | Url | Descripción  | Estado (obligatorio) | Last Modified | Last Modified By | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Abreviatura desletreada* | *Source* |  | *Publicado o Borrador* |  |  |  |

### <a name="csv-fields"></a>Campos CSV

**Acrónimo**. Contiene el formulario corto o acrónimo real. Un ejemplo es *DNN*.

**Expansión**. Contiene la expansión del acrónimo. Un ejemplo es *Deep Neural Network*.

**Descripción**. Una breve descripción del acrónimo que proporciona a los usuarios más información sobre el acrónimo y su expansión. Por ejemplo, una red neuronal profunda es una red neuronal con un cierto nivel de complejidad, una red *neuronal con más de dos capas.*

**Origen**. Dirección URL de la página o sitio web donde desea que los usuarios vayan para obtener más información sobre el acrónimo.

**Estado**. Este campo puede tener dos valores:

- **Borrador**. Agrega el acrónimo al estado Borrador.
- **Publicado**. Agrega el acrónimo al estado Publicado y lo hace disponible en Microsoft Search.

### <a name="system-curated-acronyms"></a>Acrónimos seleccionados por el sistema

Puede ser un desafío para los administradores agregar todas las siglas usadas dentro de una organización a Respuestas. Esta característica puede encontrar acrónimos que los administradores de búsqueda ni siquiera conocen. Para ello, Microsoft Search también detecta y cura acrónimos de estos orígenes:

- Mensajes de correo electrónico de los usuarios
- Documentos en [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)y [Microsoft OneNote](https://www.onenote.com/)
- Documentos públicos de la organización a los que los usuarios tienen acceso en SharePoint, OneDrive o OneNote

Microsoft Search se asegura de que solo los usuarios con acceso y permisos a un documento puedan ver las siglas que se detectan en él. Cuando se encuentra un acrónimo en el buzón de un usuario, solo ese usuario puede ver ese acrónimo.

> [!NOTE]
> No se necesita ninguna configuración para acrónimos seleccionados por el administrador.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**P: ¿Cómo se clasifican los datos seleccionados por el administrador y los del sistema?**

**A:** La clasificación de los resultados puede variar de una persona a otra, ya que los resultados son personalizados para cada usuario. Ninguna de estas categorías siempre tendrá prioridad sobre la otra.

**P: ¿Cuánto tiempo se necesita para que los acrónimos seleccionados por el administrador sean visibles en Microsoft Search después de su publicación?**

**A:**  Los acrónimos agregados al estado publicado tardan hasta tres días en estar disponibles en Microsoft Search.

**P: ¿Cómo desencadenan los usuarios las respuestas a las siglas?**

**A**: Para obtener respuestas de acrónimos, los usuarios deben escribir patrones de consulta específicos en un cuadro de búsqueda de [Bing,](https://bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365.](https://Office.com) 

**P: ¿Cuánto tiempo se necesita para que aparezcan las siglas del sistema después de recibir o enviar un nuevo correo electrónico o documento?**

**A:** Las siglas encontradas en un nuevo correo electrónico o documento pueden tardar hasta siete días en aparecer en los resultados de microsoft Search.

**P: ¿Los documentos deben tener un formato específico para que la minería los resalte?**

**A:** No. Se admiten todos los tipos de archivo excepto los archivos de imagen, carpetas y zip.

**P: ¿Detectará Microsoft acrónimos de documentos en todos los idiomas?**

**A**: Microsoft solo admite la minería de documentos en inglés. La compatibilidad con otros idiomas se agregará en fases.

**P: ¿Qué ocurre si mi organización no quiere mostrar acrónimos seleccionados por el sistema? ¿Puedo dejar de mostrar este tipo de acrónimo en mis resultados de búsqueda?**

**A**: Para desactivar la presentación de acrónimos seleccionados por el sistema en los resultados de la búsqueda, cree un vale de soporte al cliente siguiendo las instrucciones del soporte técnico de contacto para [productos empresariales](/microsoft-365/admin/contact-support-for-business-products).
Después de crear un vale de soporte técnico, los acrónimos seleccionados por el sistema tardan hasta 48 horas en dejar de aparecer en los resultados de la búsqueda.