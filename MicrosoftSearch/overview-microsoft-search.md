---
title: Introducción a Búsqueda de Microsoft
ms.author: jeffkizn
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
description: Obtenga información general sobre lo que es Microsoft Search, sus ventajas y qué aplicaciones admiten Microsoft Search.
ms.openlocfilehash: a7250bccd3f77eb3ad2f3c91bdfd176a2141fd98
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508818"
---
# <a name="overview-of-microsoft-search"></a>Introducción a Búsqueda de Microsoft

Microsoft Search le ayuda a encontrar lo que necesita para completar lo que está trabajando. Tanto si busca personas, archivos, gráficos de organizaciones, sitios o respuestas a preguntas comunes, puede usar Microsoft Search durante toda la jornada laboral para obtener respuestas.

Microsoft Search ayuda a los usuarios a encontrar las respuestas, las personas y el contenido adecuados para completar sus tareas en la aplicación en la que ya están trabajando.

- Los usuarios obtienen resultados pertinentes en el **contexto** de la aplicación desde la que buscan. Por ejemplo, cuando buscan en [Microsoft Outlook,](https://www.microsoft.com/outlook)encuentran correos electrónicos y no sitios [de SharePoint.](http://sharepoint.com/) Cuando buscan en SharePoint, encuentran sitios, páginas y archivos.
- Independientemente de la aplicación con la que trabajan, Búsqueda de Microsoft es **personal**. Microsoft Search usa información de [Microsoft Graph](https://developer.microsoft.com/graph/) para mostrar resultados relevantes para cada usuario. Usuarios diferentes pueden ver resultados diferentes, aunque busquen las mismas palabras. Solo ven resultados a los que ya tienen acceso, Microsoft Search no cambia los permisos.
- Los usuarios no necesitan recordar dónde se encuentra la información. Por ejemplo, un usuario está trabajando en [Microsoft Word](https://products.office.com/word) y desea reutilizar la información de una presentación que un compañero compartió desde [su OneDrive](https://onedrive.live.com/about/). No es necesario cambiar a OneDrive y buscar esa presentación, simplemente pueden buscar desde Word.
- Cuando en [Bing](https://bing.com), los usuarios obtienen resultados desde su organización además de los resultados públicos de la Web.

## <a name="what-users-see"></a>Qué ven los usuarios

En [Bing,](https://bing.com)los usuarios usan el mismo cuadro de búsqueda que para las búsquedas web. En las aplicaciones de Office, los usuarios buscan el cuadro Búsqueda de Microsoft en la barra de encabezado. Tiene el siguiente aspecto:

![Capturas de pantalla de ventanas de aplicaciones con el cuadro de Búsqueda de Microsoft en la barra del encabezado](media/Headings_520.png)

Cuando los usuarios  hacen clic en el cuadro Búsqueda, la búsqueda sugiere resultados basados en su actividad anterior en Office 365 y en función del contenido que está en tendencia en su organización. Los archivos en los que estaban trabajando recientemente, los comandos que han usado recientemente, así como las personas con las que colaboran son ejemplos de actividad que la búsqueda considera. A medida que los usuarios empiezan a escribir en el **cuadro** De búsqueda, los resultados sugeridos se actualizan. Los usuarios pueden abrir los resultados de búsqueda directamente desde **el cuadro** De búsqueda. Este es un ejemplo de una búsqueda en [SharePoint](http://sharepoint.com/).

![Capturas de pantalla del cuadro de Búsqueda de Microsoft con una consulta y los resultados sugeridos](media/SERP_text_520.png)

Si las sugerencias del cuadro de búsqueda no son las que buscan los usuarios, **Entrar** abre la lista completa de resultados. Pueden usar metadatos como quién modificó por última vez el elemento y cuándo, dónde se encuentra el elemento, así como obtener una vista previa de él para determinar si es lo que buscan.

![Capturas de pantalla de página de resultados de Búsqueda de Microsoft](media/search_box.png)

## <a name="benefits-of-microsoft-search"></a>Ventajas de Búsqueda de Microsoft

**Búsquedas en Microsoft 365 desde cualquier cuadro de Búsqueda de Microsoft** : los usuarios pueden buscar desde cualquier cuadro de Búsqueda de Microsoft y volver rápidamente a lo estaban haciendo. Microsoft Search reúne resultados de orígenes de datos en Office 365, [incluidos SharePoint,](http://sharepoint.com/) [Microsoft OneDrive para](https://onedrive.live.com/about/business/)la Empresa y [Microsoft Exchange Server](https://products.office.com/exchange/microsoft-exchange-server).

**Fácil de buscar:** Microsoft Search sugiere resultados basados en la actividad anterior de los usuarios en Office 365, justo en el **cuadro** Búsqueda.

**Encontrar archivos compartidos**: Búsqueda de Microsoft usa una comprensión avanzada de consultas para hacer más fácil la búsqueda de archivos compartidos. Los usuarios pueden encontrar fácilmente archivos en los que están colaborando.

**Mostrar contenido relevante**: Proporcione la información y las respuestas que los usuarios necesitan para completar las tareas, por ejemplo, directivas, beneficios, recursos, herramientas, etc. También puede dirigirse a grupos específicos, como nuevos empleados, trabajadores remotos o distintas geografías.

**Administrar a través de todas las aplicaciones**: Búsqueda de Microsoft está **activada** de forma predeterminada y cualquier administración que realice se aplica a Búsqueda de Microsoft en todas las aplicaciones.

## <a name="tailoring-microsoft-search-to-your-organization"></a>Personalizar Búsqueda de Microsoft para su organización

Como administrador, puede crear una experiencia de Microsoft Search increíble para los usuarios.

**Mostrar contenido útil:** las respuestas proporcionan resultados rápidos y relevantes para las consultas de búsqueda basadas en palabras clave. [Planee el contenido](plan-your-content.md).

**Agregar contenido externo:** los conectores de Microsoft Graph le permiten agregar contenido externo al índice. Use conectores para enriquecer la experiencia de búsqueda con datos y archivos de fuera de Microsoft 365. [Información general sobre los conectores de Microsoft Graph](connectors-overview.md)

**Personalizar la experiencia del usuario:** puede personalizar la experiencia del usuario mediante el uso de verticales y otras configuraciones. [Personalizar la página búsqueda de Microsoft](customize-search-page.md)

## <a name="what-content-is-searched"></a>Qué contenido se busca

Microsoft Search muestra el contenido que su organización ha almacenado en Microsoft 365 o indexado a través de conectores. Microsoft Search no busca entre inquilinos ni muestra resultados del contenido compartido por otras organizaciones. Si su organización ha configurado un entorno híbrido de SharePoint mediante la búsqueda híbrida en la nube, Microsoft Search devuelve los resultados de búsqueda de contenido de SharePoint local y en línea, incluido cualquier contenido externo que haya conectado al entorno de SharePoint Server. [Más información sobre los entornos híbridos de búsqueda](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint).

Los usuarios obtienen los mismos resultados de búsqueda que obtienen de otras ubicaciones y también obtienen resultados de Internet.

## <a name="how-microsoft-search-works"></a>Cómo funciona Microsoft Search

Cuando un usuario realiza una búsqueda, Búsqueda de Microsoft procesa la consulta y analiza el objetivo de búsqueda en frases más grandes mediante Inteligencia Artificial (IA) para obtener información sobre las frases superfluas comunes que los usuarios añaden a sus consultas, pero que no afectan a su intención de búsqueda. Por ejemplo, cuando un usuario busca "más información sobre cómo cambiar la contraseña", se extraen las palabras menos importantes de la consulta y se activa la búsqueda basándose en las más relevantes, como "cambiar contraseña".  
Los resultados de búsqueda para los que el usuario tiene **permisos** se muestran en la página de resultados de la búsqueda. Búsqueda de Microsoft utiliza algoritmos de clasificación inteligente para ordenar los resultados según su relevancia.

## <a name="how-microsoft-search-in-bing-protects-your-company-data"></a>Cómo Microsoft Search en Bing protege los datos de la empresa

[Seguridad y privacidad para Microsoft Search en Bing](security-for-search.md)

## <a name="see-also"></a>Vea también

[Configurar Búsqueda de Microsoft](setup-microsoft-search.md)
