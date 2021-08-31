---
title: Introducción a Búsqueda de Microsoft
ms.author: jeffkizn
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
description: Obtenga información general sobre lo que Búsqueda de Microsoft, sus ventajas y qué aplicaciones admiten Búsqueda de Microsoft.
ms.openlocfilehash: 29a6db642ac9cc787b8cbec45aec609f55722206
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701944"
---
# <a name="overview-of-microsoft-search"></a>Introducción a Búsqueda de Microsoft

Búsqueda de Microsoft ayuda a encontrar lo que necesita para completar lo que está trabajando. Tanto si busca personas, archivos, gráficos de organizaciones, sitios o respuestas a preguntas comunes, puede usar Búsqueda de Microsoft durante la jornada laboral para obtener respuestas.

Búsqueda de Microsoft ayuda a los usuarios a encontrar las respuestas, las personas y el contenido adecuados para completar sus tareas en la aplicación en la que ya están trabajando.

- Los usuarios obtienen resultados pertinentes en el **contexto** de la aplicación desde la que buscan. Por ejemplo, cuando buscan en [Microsoft Outlook](https://www.microsoft.com/outlook), encuentran correos electrónicos y no [SharePoint](http://sharepoint.com/) sitios. Cuando buscan en SharePoint, encuentran sitios, páginas y archivos.
- Independientemente de la aplicación con la que trabajan, Búsqueda de Microsoft es **personal**. Búsqueda de Microsoft información de Microsoft Graph [para](https://developer.microsoft.com/graph/) mostrar resultados relevantes para cada usuario. Usuarios diferentes pueden ver resultados diferentes, aunque busquen las mismas palabras. Solo ven resultados a los que ya tienen acceso, Búsqueda de Microsoft no cambia los permisos.
- Los usuarios no necesitan recordar dónde se encuentra la información. Por ejemplo, un usuario está trabajando en [Microsoft Word](https://products.office.com/word) y desea volver a usar la información de una presentación que un compañero compartió desde su [OneDrive](https://onedrive.live.com/about/). No es necesario cambiar a OneDrive y buscar esa presentación, simplemente pueden buscar desde Word.
- Cuando en [Bing](https://bing.com), los usuarios obtienen resultados desde su organización además de los resultados públicos de la Web.

## <a name="what-users-see"></a>Qué ven los usuarios

En [Bing](https://bing.com), los usuarios usan el mismo cuadro de búsqueda que para las búsquedas web. En las Office, los usuarios encuentran el Búsqueda de Microsoft en la barra de encabezado. Tiene este aspecto:

![Capturas de pantalla de las ventanas de la aplicación Búsqueda de Microsoft cuadro en la barra de encabezado.](media/Headings_520.png)

Cuando los usuarios hacen clic en **el** cuadro Búsqueda, la búsqueda sugiere resultados basados en su actividad anterior en Office 365 y en función del contenido que está en tendencia en su organización. Los archivos en los que estaban trabajando recientemente, los comandos que han usado recientemente, así como las personas con las que colaboran son ejemplos de actividad que la búsqueda considera. A medida que los usuarios empiezan a escribir en el **cuadro** De búsqueda, los resultados sugeridos se actualizan. Los usuarios pueden abrir los resultados de búsqueda directamente desde **el cuadro** De búsqueda. Este es un ejemplo de una búsqueda en [SharePoint](http://sharepoint.com/).

![Capturas de pantalla del Búsqueda de Microsoft con una consulta y resultados sugeridos.](media/SERP_text_520.png)

Si las sugerencias del cuadro de búsqueda no son las que buscan los usuarios, **Entrar** abre la lista completa de resultados. Pueden usar metadatos como quién modificó por última vez el elemento y cuándo, dónde se encuentra el elemento, así como obtener una vista previa de él para determinar si es lo que buscan.

![Capturas de pantalla de la Búsqueda de Microsoft de resultados.](media/search_box.png)

## <a name="benefits-of-microsoft-search"></a>Ventajas de Búsqueda de Microsoft

**Búsquedas en Microsoft 365 desde cualquier cuadro de Búsqueda de Microsoft** : los usuarios pueden buscar desde cualquier cuadro de Búsqueda de Microsoft y volver rápidamente a lo estaban haciendo. Búsqueda de Microsoft reúne los resultados de orígenes de datos de Office 365, incluidos [SharePoint](http://sharepoint.com/), [Microsoft OneDrive para](https://onedrive.live.com/about/business/)empresas y [Microsoft Exchange Server](https://products.office.com/exchange/microsoft-exchange-server).

**Fácil de buscar:** Búsqueda de Microsoft resultados basados en la actividad anterior de los usuarios en Office 365, justo en el **cuadro** Búsqueda.

**Encontrar archivos compartidos**: Búsqueda de Microsoft usa una comprensión avanzada de consultas para hacer más fácil la búsqueda de archivos compartidos. Los usuarios pueden encontrar fácilmente archivos en los que están colaborando.

**Mostrar contenido relevante**: Proporcione la información y las respuestas que los usuarios necesitan para completar las tareas, por ejemplo, directivas, beneficios, recursos, herramientas, etc. También puede dirigirse a grupos específicos, como nuevos empleados, trabajadores remotos o distintas geografías.

**Administrar a través de todas las aplicaciones**: Búsqueda de Microsoft está **activada** de forma predeterminada y cualquier administración que realice se aplica a Búsqueda de Microsoft en todas las aplicaciones.

## <a name="tailoring-microsoft-search-to-your-organization"></a>Personalizar Búsqueda de Microsoft para su organización

Como administrador, puede crear una experiencia Búsqueda de Microsoft para los usuarios.

**Mostrar contenido útil:** las respuestas proporcionan resultados rápidos y relevantes para las consultas de búsqueda basadas en palabras clave. [Planee el contenido](plan-your-content.md).

**Agregar contenido externo:** Microsoft Graph Connectors le permiten agregar contenido externo al índice. Use conectores para enriquecer la experiencia de búsqueda con datos y archivos de fuera de Microsoft 365. [Conectores de información general de Microsoft Graph](connectors-overview.md)

**Personalizar la experiencia del usuario:** puede personalizar la experiencia del usuario mediante el uso de verticales y otras configuraciones. [Personalizar la Búsqueda de Microsoft web](customize-search-page.md)

## <a name="what-content-is-searched"></a>Qué contenido se busca

Búsqueda de Microsoft muestra el contenido que la organización ha almacenado en Microsoft 365 o indizado a través de conectores. Búsqueda de Microsoft busca entre inquilinos ni muestra los resultados del contenido compartido por otras organizaciones. Si su organización ha configurado un entorno híbrido de SharePoint mediante la búsqueda híbrida en la nube, Búsqueda de Microsoft devuelve los resultados de búsqueda tanto de contenido SharePoint en línea como local, incluido cualquier contenido externo que haya conectado al entorno de SharePoint Server. [Más información sobre los entornos híbridos de búsqueda](/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint).

Los usuarios obtienen los mismos resultados de búsqueda que obtienen de otras ubicaciones y también obtienen resultados de Internet.

## <a name="how-microsoft-search-works"></a>Cómo Búsqueda de Microsoft funciona

Cuando un usuario realiza una búsqueda, Búsqueda de Microsoft procesa la consulta y analiza el objetivo de búsqueda en frases más grandes mediante Inteligencia Artificial (IA) para obtener información sobre las frases superfluas comunes que los usuarios añaden a sus consultas, pero que no afectan a su intención de búsqueda. Por ejemplo, cuando un usuario busca "más información sobre cómo cambiar la contraseña", se extraen las palabras menos importantes de la consulta y se activa la búsqueda basándose en las más relevantes, como "cambiar contraseña".  
Los resultados de búsqueda para los que el usuario tiene **permisos** se muestran en la página de resultados de la búsqueda. Búsqueda de Microsoft utiliza algoritmos de clasificación inteligente para ordenar los resultados según su relevancia.

## <a name="how-microsoft-search-in-bing-protects-your-company-data"></a>Cómo Búsqueda de Microsoft en Bing protege los datos de su empresa

[Seguridad y privacidad para Búsqueda de Microsoft en Bing](security-for-search.md)

## <a name="see-also"></a>Vea también

[Configurar Búsqueda de Microsoft](setup-microsoft-search.md)