---
title: Administración de las respuestas de acrónimo en Microsoft Search
ms.author: v-pamcna
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Respuestas de crear y actualizar acrónimos en Microsoft Search
ms.openlocfilehash: aa857cefe9a2a40a8519a91829e327d01a3f2391
ms.sourcegitcommit: 25cdb5e6111ec6bc6c130a36aa5f13a6328e1092
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928233"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>La administración de acrónimos responde en Microsoft Search

Los empleados a menudo se encontraban con acrónimos y abreviaturas desconocidos que usa su organización o equipo. Los términos específicos de organizaciones o equipos pueden ser nuevos para los usuarios que se mueven de un equipo a otro, los que trabajan con equipos de asociados internos o nuevos empleados.

Las organizaciones no siempre tienen una referencia única para su terminología estándar. La ausencia de una sola referencia hace que sea difícil encontrar definiciones o expansiones para estos acrónimos. Microsoft Search resuelve ese problema con acrónimos.

## <a name="what-users-experience"></a>Qué experiencia tienen los usuarios
Microsoft Search los usuarios pueden obtener definiciones con acrónimos en [Bing](https://Bing.com), [Microsoft Office 365](https://Office.com)y [Microsoft SharePoint Online](https://products.office.com/sharepoint/collaboration). En los cuadros de **búsqueda** de las barras de encabezado, los usuarios escriben consultas como estos ejemplos:

- *Qué es* DNN
- *Definir* DNN
- *Definición* de DNN
- *Expandir* DNN
- *Expansión* DNN
- *Significado de* DNN
- DNN *significa*

Los resultados que se sugieren incluyen todos los significados de DNN que están presentes en la organización del usuario.

> [!NOTE]
> Los usuarios deben escribir una consulta que incluya las *palabras clave* especificadas en el acrónimo para activar sus respuestas correspondientes. Las consultas de acrónimo no distinguen entre mayúsculas y minúsculas. 

## <a name="set-up-acronyms-answers"></a>Configurar las respuestas de los acrónimos
En el centro de [Administración](https://admin.microsoft.com)de Microsoft 365, vaya a **configuración** > **acrónimos**de**Microsoft Search** >y, a continuación, seleccione **Agregar acrónimos**. 

Microsoft Search consulta dos orígenes de datos para proporcionar a los acrónimo respuestas a las búsquedas de los usuarios:

1.  **Acrónimos editoriales**. LO proporcionan los administradores de TI en el [centro de administración](https://admin.microsoft.com).
2.  **Acrónimos extraídos**. Extraída por Microsoft Search desde el correo electrónico y los documentos personales del usuario y los datos disponibles públicamente dentro de la organización.

### <a name="set-up-editorial-acronyms"></a>Configurar acrónimos editoriales
Los administradores de TI pueden configurar acrónimos editoriales en la [ficha acrónimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) del [centro de administración de Microsoft 365]( https://admin.microsoft.com). Puede Agregar acrónimos desde cualquier sitio o repositorio interno al centro de administración. Los acrónimos editoriales se pueden agregar al estado **publicado** o **borrador** :

**Estado publicado**. Los acrónimos están disponibles para los empleados de la organización a través de Microsoft Search.

> [!NOTE]
> Los acrónimos agregados al estado publicado pueden tardar hasta tres días en estar disponibles en Microsoft Search.

**Estado de borrador**. Si los administradores quieren revisar las respuestas de acrónimos antes de que estén disponibles en Microsoft Search, pueden agregar los acrónimos al estado borrador. Los acrónimos agregados al estado de borrador no están disponibles en Microsoft Search. Los administradores deben agregar los acrónimos a estado publicado para que estén disponibles.

Los administradores pueden agregar acrónimos de forma individual o en bloque para importarlos en un archivo CSV. Cargue un archivo CSV con los campos que se muestran en la tabla siguiente:

| Acrónimo (obligatorio) | Expansión (obligatoria) | Descripción  | Origen | Estado (obligatorio) |
| --------- | --------- | ---------- | --------- |--------- |
| *XXX* | *Abreviatura de ortografía* |  | *URL* | *Publicado o borrador* |

### <a name="csv-fields"></a>Campos CSV
**Acrónimo**. Contiene la forma corta o el acrónimo real. Un ejemplo es *DNN*.

**Expansión**. Contiene la expansión del acrónimo. Un ejemplo es una *red neuronal profunda*.

**Descripción**. Breve descripción del acrónimo que proporciona a los usuarios una visión rápida de cuál es el acrónimo y su media de expansión. Por ejemplo, *una red neuronal profunda es una red neuronal con cierto nivel de complejidad, una red neuronal con más de dos capas*.

**Origen**. La dirección URL de la página o sitio web al que desea que vayan los usuarios para obtener más información sobre el acrónimo.

**Estado**. Este campo puede tener dos valores:

- **Borrador**. Agrega el acrónimo al estado de borrador.
- **Publicado**. Agrega el acrónimo al estado publicado y lo hace disponible en Microsoft Search.

### <a name="mined-acronyms"></a>Acrónimos extraídos
Puede que sea un reto para los administradores agregar todos los acrónimos que se usan en una organización a las respuestas. Esta característica puede encontrar acrónimos que los administradores de búsqueda aún no conocen. Para ello, Microsoft Search también retiene acrónimos de estos recursos:

- Mensajes de correo electrónico de los usuarios.
- Documentos en [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/) y [Microsoft OneNote](http://www.onenote.com/).
- Documentos públicos de la organización a los que los usuarios tienen acceso en SharePoint, OneDrive o OneNote.

Microsoft Search se asegura de que solo los usuarios con acceso y permisos a un documento puedan ver los acrónimos que se han extraído. Los acrónimos se han extraído de la bandeja de entrada de un usuario y se almacenan en el usuario. Solo el usuario puede tener acceso a los acrónimos extraídos de la bandeja de entrada del usuario.

> [!NOTE]
> No se necesita configurar el administrador de TI para acrónimos que se han extraído.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes
**P: ¿cómo se clasifican los datos editoriales y extraídos?**

**A:** La característica clasifica actualmente los acrónimos editoriales superiores a los acrónimos extraídos.

**P: ¿Cuánto tiempo tardan los acrónimos de editorial en estar visibles en Microsoft Search después de publicarlos?**

**A:**  Los acrónimos agregados al estado publicado tardan hasta tres días en estar disponibles en Microsoft Search. 

**P: ¿Cómo responden los usuarios que desencadenan acrónimos?**

**A: para**obtener las respuestas de acrónimo, los usuarios deben escribir patrones de consulta específicos en un cuadro de **búsqueda** de [Bing](https://bing.com), [Office 365](https://Office.com)o [SharePoint](https://products.office.com/sharepoint/collaboration) . Algunos ejemplos de consultas que buscan respuestas para el término *DNN* son los siguientes:

- *Qué es* DNN
- *Definir* DNN
- *Definición* de DNN
- *Expandir* DNN
- *Expansión* DNN
- *Significado de* DNN
- DNN *significa*

**P: ¿Cuánto tiempo tardan los acrónimos extraídos en aparecer después de recibir o enviar un nuevo correo electrónico o documento?**

**A:** Los acrónimos extraídos de un nuevo documento o de correo electrónico pueden tardar hasta siete días en aparecer en los resultados de Microsoft Search.

**P: ¿es necesario que los documentos estén en un formato específico para que la extracción los recoja?**

**A:** No. Admitimos todos los tipos de archivo excepto Image, folders y zip.

**P: ¿Microsoft Mine acrónimo de los documentos en todos los idiomas?**

**A**: Microsoft solo admite la extracción de documentos en inglés. La compatibilidad con otros idiomas se agregará en fases.

**P: ¿Qué sucede si mi organización no quiere mostrar acrónimos que se han extraído? ¿Puedo dejar de mostrar acrónimos que se han extraído en los resultados de búsqueda?**

**A: para**desactivar la presentación de acrónimos extraídos en los resultados de la búsqueda, cree un vale de soporte al cliente siguiendo las instrucciones en [contacto soporte técnico for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).
Después de crear un vale de soporte técnico, tarda hasta 48 horas en acrónimos extraídos para dejar de aparecer en los resultados de la búsqueda. 

**P: ¿Cuándo veo las respuestas de acrónimos en [Office 365](https://Office.com) y [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**

**A**: las respuestas de acrónimos solo están disponibles actualmente en Microsoft Search en [Bing](https://bing.com). Se implementarán en Office 365 y SharePoint Online en 2020.
