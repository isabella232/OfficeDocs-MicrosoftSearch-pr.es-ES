---
title: Crear preguntas y respuestas
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: d432b9d9-3792-47a0-9a13-30a1a83caabc
ROBOTS: NoIndex
description: Formas de crear respuestas a las preguntas más frecuentes para los resultados de trabajo de Microsoft Search
ms.openlocfilehash: 6f9e3b6faca636102fe390f64b6ebc19add1a055
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311892"
---
# <a name="create-qas"></a>Crear preguntas y respuestas

> [!IMPORTANT]
> Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing Estamos pasando el portal al Centro de administración de Microsoft 365. Luego, se quitará el portal de Búsqueda de Microsoft en Bing. Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar. [Introducción a Microsoft Search (Búsqueda de Microsoft)](overview-microsoft-search.md).

Las preguntas más frecuentes proporcionan una respuesta o información a los usuarios incluyendo un vínculo opcional. Lo ideal es que en las preguntas y respuestas se incluyan todos los detalles que los usuarios están buscando para que no tengan que ir al origen. Puede dar formato al contenido de sus preguntas y respuestas e incluir imágenes, listas y tablas.
  
## <a name="create-a-qa"></a>Crear un Preguntas y respuestas

Para obtener información sobre cómo crear títulos, descripciones y palabras clave eficaces entre otros, vea [Planear el contenido](plan-your-content.md).
  
1. Vaya al portal de administración de Microsoft Search
    
2. En el panel de navegación, haga clic en **Preguntas y respuestas**
    
3. En la parte superior de la página, haga clic en **Agregar preguntas y respuestas**.
    
    Aparece la página de Editar preguntas y respuestas, con una vista previa del aspecto que tendrán en Bing. Al agregar la información necesaria, la vista previa se actualizará automáticamente.
    
4. Escriba un **Título**
    
    El título es el encabezado que aparece en el resultado. Puede tener un máximo de 120 caracteres de longitud y recomendamos utilizar un formato de pregunta.
    
5. Si es necesario, escriba la **URL** de la página, sitio o ubicación al que llevará el marcador 
    
    Esto permite que los usuarios que necesitan información adicional puedan acceder más fácilmente al origen para obtener más información.
    
6. Escriba una **descripción de respuesta**
    
    Debería responder a la pregunta que se hace en el título. Puede copiar el contenido HTML existente y pegarlo aquí. Las etiquetas no compatibles se omitirán.
    
7. Use las opciones integradas y etiquetas HTML para dar formato al texto, agregar imágenes, listas, tablas, etc.
    
    Usar la vista previa en la parte superior de la página para ver cómo aparecerán sus etiquetas y formato en Bing. Para obtener información sobre:
    
  - Etiquetas HTML, consulte la siguiente lista de etiquetas HTML compatibles
    
  - Opciones integradas, haga clic en **Guía de markdown** (icono con el signo de interrogación) 
    
8. Escriba las **palabras clave** que quiere que lleven a esta pregunta 
    
    Al igual que un marcador, cuando un usuario busca cualquiera de las palabras clave que se han incluido, esta preguntas y su respuesta se incluirá en los resultados de trabajo. Intente agregar tantas variantes como sea posible, incluyendo el título de la pregunta.
    
9. Seleccione **Hacer coincidir automáticamente palabras clave similares** para expandir el conjunto de palabras clave 
    
    Esto permite una mayor coincidencia de términos de búsqueda y ayuda a garantizar que esta pregunta se incluya en los resultados relevantes.
    
10. Escriba las **palabras clave reservadas**
    
    Si una palabra clave desencadena varias preguntas, Microsoft Search colocará la más popular en la parte superior y mostrará las demás como vínculos relacionados. Use una o varias palabras clave reservadas para asegurarse de que una pregunta aparece como resultado principal. Las palabras clave reservadas no se pueden compartir entre marcadores. Además, no se recomienda compartir palabras reservadas entre marcadores y preguntas. Si un marcador y una preguntas comparten una palabra clave o una palabra clave reservada, el marcador siempre tendrá prioridad y no se mostrará la pregunta.
    
## <a name="add-qa-settings"></a>Agregar la configuración de preguntas y respuestas

La configuración de las preguntas ofrece más control sobre cuándo aparece una preguntas y quién la ve.
  
- Fechas
    
    Establezca una fecha de inicio, así como una fecha de finalización opcional para controlar cuándo se publicará o expirará una pregunta.
    
- País o región
    
    Si selecciona países o regiones, solo los usuarios en esas ubicaciones verán esa pregunta.
    
- Grupos
    
    Use la configuración de Grupos para hacer que un resultado de pregunta esté disponible únicamente para los miembros de un grupo seleccionado. Por ejemplo, si va a crear preguntas que solo conciernen a los empleados del departamento de recursos humanos, puede asignar esta configuración al grupo de seguridad de recursos humanos adecuado.
    
- Dispositivo y sistema operativo
    
    Si selecciona sistemas operativos o tipos de dispositivos, solo los usuarios que busquen en dichos dispositivos o usen esos sistemas verán esa pregunta.
    
- Variaciones dirigidas
    
    Use esta opción para variar el contenido de la pregunta en función del dispositivo y la ubicación de un usuario.
    
## <a name="use-a-browser-extension-to-create-content"></a>Usar una extensión de explorador para crear contenido

Desde la sección Herramientas del portal de administración, descargue e instale la extensión del navegador para creadores de contenido para Microsoft Edge o Chrome. Para usar la extensión, inicie sesión y vaya a un sitio o página que quiera agregar como pregunta. Revise y cambie el contenido sugerido, como las palabras clave, agregue contenido adicional y guarde la pregunta.
  
Si se encuentran varias preguntas y respuestas, revise cada una y determine si desea publicarla, guardarla como borrador o guardar todo como borrador.
  
## <a name="supported-html-tags"></a>Etiquetas HTML compatibles

Puede usar el contenido HTML existente o agregar etiquetas HTML a la descripción de la respuesta. Las etiquetas no compatibles se ignorarán.
  
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

  

