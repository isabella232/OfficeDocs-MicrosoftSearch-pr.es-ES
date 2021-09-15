---
title: Administrar respuestas de acrónimo en Búsqueda de Microsoft
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Crear y actualizar respuestas de acrónimos en Búsqueda de Microsoft
ms.openlocfilehash: b7b3272ba98bbce7d43562811389df0a35e9f7a2
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "59376103"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Administrar respuestas de acrónimos en Búsqueda de Microsoft

A menudo, los usuarios se topar con acrónimos y abreviaturas desconocidos usados por su organización o equipo. Los términos que son específicos de organizaciones o equipos pueden ser nuevos para las personas que se mueven de un equipo a otro, trabajan con equipos asociados internos o son nuevos en la organización.

Las organizaciones no siempre tienen una sola referencia para su terminología estándar. La falta de una sola referencia hace que sea difícil encontrar definiciones para estos acrónimos. Búsqueda de Microsoft resuelve ese problema con acrónimos.

## <a name="what-users-experience"></a>Qué experiencia tienen los usuarios

Búsqueda de Microsoft usuarios pueden obtener definiciones con acrónimos en [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), [Office 365](https://Office.com), Outlook en la Web, Outlook Mobile (Android) y Teams Mobile (iOS y Android). En el **cuadro Buscar,** los usuarios escriben consultas como estos ejemplos:

- *Qué es* DNN
- *Definir* DNN
- Definición *de* DNN
- *Expandir* DNN
- Expansión *de* DNN
- *Significado de* DNN
- DNN *significa*
- DNN *representa*

El resultado incluye todos los significados de DNN que están presentes en la organización del usuario.

> [!NOTE]
> Los usuarios deben escribir una consulta que incluya las palabras clave *especificadas* del acrónimo para desencadenar sus respuestas correspondientes. Las consultas de acrónimos no distinguen mayúsculas de minúsculas.

## <a name="set-up-acronyms-answers"></a>Configurar respuestas acrónimos

En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya [**a Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)y, a continuación, seleccione **Agregar acrónimos**.

Búsqueda de Microsoft consulta dos orígenes de datos para proporcionar respuestas de acrónimos a las búsquedas de los usuarios:

1. **Curada por el administrador.** Proporcionado por los administradores de TI en el [Centro de administración.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)
2. **System-curated**. Detectado por Búsqueda de Microsoft correo electrónico y documentos de los usuarios, así como datos disponibles públicamente dentro de la organización.

### <a name="set-up-admin-curated-acronyms"></a>Configurar acrónimos seleccionados por el administrador

Los administradores de búsqueda pueden agregar acrónimos en la pestaña [Acrónimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) del [centro Búsqueda de Microsoft administración.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) Puede agregar acrónimos desde cualquier sitio o repositorio interno al Centro de administración. Estos acrónimos se pueden agregar al **estado Publicado** o **Borrador:**

**Estado publicado**. Los acrónimos están disponibles para los usuarios de la organización a través de Búsqueda de Microsoft.

> [!NOTE]
> Los acrónimos agregados al estado publicado tardan hasta un día en estar disponibles en Búsqueda de Microsoft.

**Estado de borrador**. Si desea revisar un acrónimo antes de hacerlo disponible en Búsqueda de Microsoft, puede agregar el acrónimo en un estado Borrador. Las siglas en estado Borrador no aparecerán en los resultados de la búsqueda. Deberá mover el acrónimo al estado Publicado para que aparezca en los resultados de la búsqueda.

**Estado excluido**. Si desea evitar que aparezca un acrónimo en Búsqueda de Microsoft, use Excluir un **acrónimo** para agregarlo. Para evitar que se excluya un acrónimo, deberá eliminar el acrónimo excluido y agregarlo o comprobar que está en la lista publicada.

Puede agregar acrónimos individualmente o importarlos masivamente en un archivo CSV. Upload un archivo CSV con los campos que se muestran en la tabla siguiente:

| Acrónimo (obligatorio) | Significa (obligatorio) | Url | Descripción  | Estado (obligatorio) | Last Modified | Last Modified By | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Abreviatura desletreada* | *Source* |  | *Publicado, Borrador o Excluido* |  |  |  |

### <a name="csv-fields"></a>Campos CSV

**Acrónimo**. Contiene el formulario corto o acrónimo real. Un ejemplo es *DNN*.

**Significa**. Contiene la definición del acrónimo. Un ejemplo es *Deep Neural Network*.

**Descripción**. Breve descripción del acrónimo que proporciona a los usuarios más información sobre el acrónimo y su definición. Por ejemplo, una red neuronal profunda es una red neuronal con un cierto nivel de complejidad, una red *neuronal con más de dos capas.*

**Origen**. Dirección URL de la página o sitio web donde desea que los usuarios vayan para obtener más información sobre el acrónimo.

**Estado**. Este campo puede tener dos valores:

- **Borrador**. Agrega el acrónimo al estado Borrador.
- **Publicado**. Agrega el acrónimo al estado Publicado y lo hace disponible en Búsqueda de Microsoft.
- **Excluido**. Agrega el acrónimo al estado Excluido e impide que aparezca en Búsqueda de Microsoft.

### <a name="system-curated-acronyms"></a>Acrónimos seleccionados por el sistema

Puede ser un desafío para los administradores agregar todas las siglas usadas dentro de una organización a Respuestas. Esta característica puede encontrar acrónimos que los administradores de búsqueda ni siquiera conocen. Para ello, Búsqueda de Microsoft también detecta y cura acrónimos de estas fuentes:

- Mensajes de correo electrónico de los usuarios
- Documentos de [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)y [Microsoft OneNote](https://www.onenote.com/)
- Documentos públicos de la organización a los que los usuarios tienen acceso en SharePoint, OneDrive o OneNote

Búsqueda de Microsoft se asegura de que solo los usuarios con acceso y permisos a un documento puedan ver las siglas que se detectan en él. Cuando se encuentra un acrónimo en el buzón de un usuario, solo ese usuario puede ver ese acrónimo.

> [!NOTE]
> No se necesita ninguna configuración para acrónimos seleccionados por el sistema.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**P: ¿Cómo se clasifican los datos seleccionados por el administrador y los del sistema?**

**A:** La clasificación de los resultados puede variar de una persona a otra, ya que los resultados son personalizados para cada usuario. Ninguna de estas categorías siempre tendrá prioridad sobre la otra.

**P: ¿Cómo desencadenan los usuarios las respuestas a las siglas?**

**A:** Para obtener respuestas de acrónimos, los usuarios deben escribir patrones de consulta específicos en un cuadro de búsqueda de [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), [Office 365](https://Office.com), Outlook en la Web, Outlook Mobile (Android) o Teams Mobile (iOS y Android). 

**P: ¿Pueden los usuarios escribir solo el acrónimo al buscar?**

**A:** En Bing, los usuarios ahora pueden encontrar respuestas acrónimos solo buscando un acrónimo, ya no se necesita una palabra clave. Esta misma experiencia se habilitará para otros Búsqueda de Microsoft de entrada en fases.

**P: ¿Cuánto tiempo se necesita para que los acrónimos seleccionados por el administrador sean visibles en Búsqueda de Microsoft después de su publicación?**

**A:** Los acrónimos agregados al estado publicado tardan hasta un día en estar disponibles en Búsqueda de Microsoft.

**P: ¿Cuánto tiempo se necesita para que aparezcan las siglas del sistema después de recibir o enviar un nuevo correo electrónico o documento?**

**A:** Las siglas encontradas en un nuevo correo electrónico o documento pueden tardar hasta siete días en aparecer en Búsqueda de Microsoft resultados.

**P: ¿Qué sucede cuando se excluye y publica un acrónimo?**

**A:** El acrónimo excluido tiene prioridad e impide que el acrónimo publicado aparezca en los resultados de la búsqueda. No elimina ni quita el acrónimo publicado.

**P: ¿Cuánto tiempo se necesita para excluir un acrónimo de los Búsqueda de Microsoft resultados?**

**A:** Un acrónimo excluido tarda hasta un día en dejar de aparecer en los resultados de búsqueda.

**P: Para los acrónimos seleccionados por el sistema, ¿los documentos deben estar en un formato específico?**

**A:** No. Se admiten todos los tipos de archivo excepto los archivos de imagen, carpeta y zip.

**P: ¿Detectará Microsoft acrónimos de documentos en todos los idiomas?**

**A:** Microsoft solo admite acrónimos seleccionados por el sistema de documentos en inglés, español, francés, italiano, alemán y portugués. La compatibilidad con otros idiomas se agregará en fases.

**P: ¿Qué ocurre si mi organización no quiere mostrar acrónimos seleccionados por el sistema? ¿Puedo dejar de mostrar este tipo de acrónimo en mis resultados de búsqueda?**

**A:** Para desactivar la presentación de acrónimos seleccionados por el sistema en los resultados de la búsqueda, cree un vale de soporte al cliente siguiendo las instrucciones en Póngase en contacto con el soporte técnico para [productos empresariales](/microsoft-365/admin/contact-support-for-business-products).
Después de crear un vale de soporte técnico, los acrónimos seleccionados por el sistema tardan hasta 48 horas en dejar de aparecer en los resultados de la búsqueda.
