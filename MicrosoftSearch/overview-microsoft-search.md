---
title: Introducción a Búsqueda de Microsoft
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Obtenga información general sobre lo que es Microsoft Search, sus ventajas y las aplicaciones compatibles con Microsoft Search.
ms.openlocfilehash: 938cf8875d9cc707041b950c6c13bab27e366670
ms.sourcegitcommit: ef1eb2bdf31dccd34f0fdc4aa7a0841ebd44f211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2019
ms.locfileid: "39663073"
---
# <a name="overview-of-microsoft-search"></a>Introducción a Búsqueda de Microsoft

Microsoft Search le ayuda a encontrar lo que necesita para completar el trabajo en el que está trabajando. Tanto si está buscando personas, archivos, organigramas, sitios o respuestas en preguntas comunes, puede usar Microsoft Search en su día laborable para obtener respuestas.

Búsqueda de Microsoft ayuda a los usuarios a encontrar respuestas correctas, personas y contenido para completar sus tareas en la aplicación en la que están trabajando.

- Los usuarios obtienen resultados pertinentes en el **contexto** de la aplicación desde la que buscan. Por ejemplo, cuando buscan en [Microsoft Outlook](https://www.microsoft.com/outlook), buscan los mensajes de correo electrónico y no los sitios de [SharePoint](http://sharepoint.com/) . Cuando buscan en SharePoint, encuentran sitios, páginas y archivos.
- Independientemente de la aplicación con la que trabajan, Búsqueda de Microsoft es **personal**. Microsoft Search usa información de [Microsoft Graph](https://developer.microsoft.com/graph/) para mostrar los resultados que son relevantes para cada usuario. Usuarios diferentes pueden ver resultados diferentes, aunque busquen las mismas palabras. Solo verán resultados a los que ya tienen acceso, Búsqueda de Microsoft no cambia los permisos.
- Los usuarios no necesitan recordar dónde se encuentra la información. Por ejemplo, un usuario trabaja en [Microsoft Word](https://products.office.com/word) y desea volver a usar la información de una presentación compartida por un compañero desde su [OneDrive](https://onedrive.live.com/about/). No es necesario cambiar a OneDrive y buscar esa presentación, simplemente pueden buscar desde Word.
- Cuando en [Bing](https://bing.com), los usuarios obtienen resultados desde su organización además de los resultados públicos de la Web.

## <a name="what-users-see"></a>Qué ven los usuarios

En [Bing](https://bing.com), los usuarios usan el mismo cuadro de búsqueda que para las búsquedas Web. En las aplicaciones de Office, los usuarios encuentran el cuadro de búsqueda de Microsoft en la barra de encabezado. Tiene el siguiente aspecto:

![Capturas de pantalla de ventanas de aplicaciones con el cuadro de Búsqueda de Microsoft en la barra del encabezado](media/Headings_520.png)

Cuando los usuarios hacen clic en el cuadro de **búsqueda** , la búsqueda sugiere resultados en función de su actividad anterior en Office 365 y en función del contenido que se tendencias en la organización. Los archivos en los que se ha trabajado recientemente, los comandos que se han usado recientemente, así como personas con las que colaboran son ejemplos de actividades que la búsqueda tiene en cuenta. A medida que los usuarios comienzan a escribir en el cuadro de **búsqueda** , se actualizan los resultados sugeridos. Los usuarios pueden abrir los resultados de la búsqueda directamente desde el cuadro de **búsqueda** . A continuación, se muestra un ejemplo de una búsqueda en [SharePoint](http://sharepoint.com/).

![Capturas de pantalla del cuadro de Búsqueda de Microsoft con una consulta y los resultados sugeridos](media/SERP_text_520.png)

Si las sugerencias que aparecen en el cuadro de búsqueda no son lo que los usuarios buscan, **Escriba** abre la lista completa de resultados. Pueden usar metadatos, como quién modificó por última vez el elemento y cuándo, o dónde encuentran los elementos, así como obtener una vista previa para determinar si es lo buscan.

![Capturas de pantalla de página de resultados de Búsqueda de Microsoft](media/search_box.png)

## <a name="benefits-of-microsoft-search"></a>Ventajas de Búsqueda de Microsoft

**Búsquedas en Microsoft 365 desde cualquier cuadro de Búsqueda de Microsoft** : los usuarios pueden buscar desde cualquier cuadro de Búsqueda de Microsoft y volver rápidamente a lo estaban haciendo. Microsoft Search reúne los resultados de los orígenes de datos en Office 365, incluidos [SharePoint](http://sharepoint.com/), [Microsoft OneDrive para la empresa](https://onedrive.live.com/about/business/)y [Microsoft Exchange Server](https://products.office.com/exchange/microsoft-exchange-server).

**Búsqueda sencilla** : Microsoft Search sugiere resultados en función de la actividad anterior de los usuarios en Office 365, directamente en el cuadro de **búsqueda** .

**Encontrar archivos compartidos**: Búsqueda de Microsoft usa una comprensión avanzada de consultas para hacer más fácil la búsqueda de archivos compartidos. Los usuarios pueden encontrar fácilmente archivos en los que están colaborando.

**Mostrar contenido relevante**: Proporcione la información y las respuestas que los usuarios necesitan para completar las tareas, por ejemplo, directivas, beneficios, recursos, herramientas, etc. También puede dirigirse a grupos específicos, como nuevas contrataciones, trabajadores remotos o distintas ubicaciones geográficas.

**Administrar a través de todas las aplicaciones**: Búsqueda de Microsoft está **activada** de forma predeterminada y cualquier administración que realice se aplica a Búsqueda de Microsoft en todas las aplicaciones.

## <a name="tailoring-microsoft-search-to-your-organization"></a>Personalizar Búsqueda de Microsoft para su organización

Como administrador, puede crear una sorprendente experiencia de búsqueda de Microsoft para sus usuarios. 

**Mostrar contenido útil** : las respuestas proporcionan resultados rápidos y autoritativos para las consultas de búsqueda basadas en palabras clave. [Hacer que el contenido sea fácil de encontrar](make-content-easy-to-find.md).

**Agregar contenido externo** : los conectores de Microsoft Graph le permiten incorporar contenido externo en el índice. Use conectores para enriquecer la experiencia de búsqueda con datos y archivos desde fuera de Microsoft 365. [Información general sobre los conectores de Microsoft Graph](connectors-overview.md)

**Personalización de la experiencia del usuario** : puede personalizar la experiencia del usuario mediante el uso de verticales y otras configuraciones. [Personalización de la página de búsqueda de Microsoft](customize-search-page.md)

## <a name="what-content-is-searched"></a>¿Qué contenido se busca?

Microsoft Search muestra el contenido que su organización ha almacenado en Microsoft 365 o que se ha indizado mediante conectores. Microsoft Search no realiza búsquedas en espacios empresariales ni muestra resultados del contenido compartido por otras organizaciones. Si su organización ha configurado un entorno híbrido de SharePoint con la búsqueda híbrida en la nube, Búsqueda de Microsoft devuelve resultados de contenido de SharePoint local y de la web, incluido cualquier contenido externo que haya conectado a su entorno de SharePoint Server. [Más información sobre los entornos híbridos de búsqueda](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint).

Los usuarios obtendrán los mismos resultados de búsqueda empresarial que obtienen de otras ubicaciones y también obtendrán resultados de Internet.

## <a name="how-does-microsoft-search-work"></a>¿Cómo funciona Búsqueda de Microsoft?

Cuando un usuario realiza una búsqueda, Búsqueda de Microsoft procesa la consulta y analiza el objetivo de búsqueda en frases más grandes mediante Inteligencia Artificial (IA) para obtener información sobre las frases superfluas comunes que los usuarios añaden a sus consultas, pero que no afectan a su intención de búsqueda. Por ejemplo, cuando un usuario busca "más información sobre cómo cambiar la contraseña", se extraen las palabras menos importantes de la consulta y se activa la búsqueda basándose en las más relevantes, como "cambiar contraseña".  
Los resultados de búsqueda para los que el usuario tiene **permisos** se muestran en la página de resultados de la búsqueda. Búsqueda de Microsoft utiliza algoritmos de clasificación inteligente para ordenar los resultados según su relevancia.

## <a name="microsoft-search-in-bing-protects-enterprise-searches"></a>Búsqueda de Microsoft en Bing protege las búsquedas empresariales

Cuando un usuario escribe una consulta de búsqueda en Microsoft Search en Bing, se producen dos solicitudes de búsqueda simultáneas:

- Una búsqueda de los recursos internos de la organización.
- Una búsqueda independiente de resultados públicos de Bing.com. 

Como las búsquedas empresariales pueden ser confidenciales, Microsoft Search ha implementado un conjunto de medidas de confianza que describen cómo `Bing.com` se controla la búsqueda independiente de resultados públicos.

### <a name="logging"></a>Registro
- Todos `Bing.com` los registros de búsqueda que pertenecen a Microsoft Search en el tráfico de Bing no se asocian a la identidad del lugar de trabajo.
- Si se alcanza un conjunto de restricciones o umbrales de frecuencia que nos garantiza que la consulta no es específica para una organización determinada, la consulta se considerará como se describe en la sección servicios de Bing de la [declaración de privacidad](https://privacy.microsoft.com/privacystatement). Por ejemplo, estas consultas se usarán para modelar y entrenar características públicas, como la sugerencia autosugerir o las búsquedas relacionadas.
- Las consultas que no cumplan el conjunto de restricciones o umbrales de frecuencia se almacenarán por separado del tráfico público que no sea de Búsqueda de Microsoft.
### <a name="advertising"></a>Publicidad 
La publicidad que `Bing.com` se muestra en relación con las búsquedas empresariales está relacionada únicamente con el contenido de las consultas de búsqueda. Los anuncios nunca se dirigen a los usuarios en función de su identidad laboral.

## <a name="see-also"></a>Vea también

[Configurar Búsqueda de Microsoft](setup-microsoft-search.md)

[Haga el contenido fácil de encontrar](make-content-easy-to-find.md)
