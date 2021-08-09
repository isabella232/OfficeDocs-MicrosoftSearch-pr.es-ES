---
title: Búsqueda de federación de Dynamics 365 (versión preliminar)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Administrar cómo aparece el contenido de Dynamics 365 en los resultados de búsqueda
ms.openlocfilehash: 65d6d27028f46751270cb3a50a154063de4fbab72d917f94aa8925693ac9ea2b
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533655"
---
# <a name="dynamics-365-federation-search-preview"></a>Búsqueda de federación de Dynamics 365 (versión preliminar)

## <a name="microsoft-search-federation-and-connectors"></a>Búsqueda de Microsoft Federación y conectores

Para ayudar a Búsqueda de Microsoft más útil, estamos presentando Búsqueda de Microsoft Federación. Con la búsqueda federada, las organizaciones pueden hacer que los datos de estos escenarios puedan ser accesibles en Búsqueda de Microsoft:

* Datos en sistemas que están sujetos a estrictos requisitos de cumplimiento
* Datos que no pueden salir de los límites del sistema
* Datos confidenciales almacenados localmente que su organización no quiere indizar en la nube

Los datos a los que se accede a través de una conexión de búsqueda federada no se indizan en Búsqueda de Microsoft. Además, con conectores integrados de Microsoft, es fácil configurar conexiones de búsqueda federadas. Nuestro conector de Dynamics 365 está actualmente en versión preliminar. Si está interesado en unirse a la vista previa, háganoslo saber en [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).

## <a name="dynamics-365-federation-connector"></a>Conector de federación de Dynamics 365

Microsoft Dynamics 365 es una línea de aplicaciones empresariales inteligentes diseñadas para la planeación de recursos empresariales y la administración de relaciones con el cliente. Con la federación de Dynamics 365, Búsqueda de Microsoft proporciona una experiencia de búsqueda sin problemas, lo que permite a los usuarios encontrar fácilmente los datos empresariales y de clientes más relevantes almacenados en Dynamics 365. El conector de federación de Dynamics 365 proporciona algunas ventajas clave:

* **Fácil de administrar:** Proceso simplificado para configurar y mantener la conexión de búsqueda a una instancia de Dynamics 365.
* **Fácil de usar:** Los usuarios pueden encontrar fácilmente y rápidamente información clave almacenada en Dynamics 365, incluidas cuentas, contactos, oportunidades abiertas y mucho más.
* **Contenido más enriquecido:** Para que los resultados de búsqueda de Dynamics 365 sea más útil, incluyen información clave como clientes potenciales, contactos y detalles de cuenta.
* **Protección de datos integrada:** Los resultados de Dynamics 365 solo aparecerán para los usuarios que tengan acceso a la instancia conectada.
* **Experiencia de búsqueda unificada:** Para mantener una experiencia coherente, los resultados de Dynamics 365 son coherentes en todos los puntos de entrada de búsqueda. Donde quiera que busque, tendrá los mismos resultados con la misma apariencia.

## <a name="what-users-experience"></a>Qué experiencia tienen los usuarios

Las respuestas de Dynamics 365 aparecen en los resultados de búsqueda en todos los lienzos de Búsqueda de Microsoft, incluidos SharePoint Online, Bing y Office.

:::image type="content" alt-text="Captura de pantalla de las respuestas de Dynamics 365 en SharePoint, Bing y Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

Desde la respuesta, es fácil ver más resultados de búsqueda de Dynamics 365 mediante el vínculo **Más resultados de Dynamics 365.** Lleva a los usuarios a una página de resultados de Dynamics 365 dedicada con más resultados relevantes para su consulta.

:::image type="content" alt-text="Captura de pantalla de Dynamics 365 vertical y resultados en SharePoint, Bing y Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

Al hacer clic o pulsar en cualquier resultado se abre Dynamics 365 y se muestra la información detallada.

:::image type="content" alt-text="Captura de pantalla de la página de detalles en Dynamics 365" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

Independientemente de dónde los usuarios inicien su búsqueda, su experiencia será coherente y les permitirá encontrar rápidamente los resultados más relevantes de Dynamics 365. Consulte nuestro vídeo de Microsoft Build 2021 para ver una demostración.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4P83t]

## <a name="supported-query-patterns"></a>Patrones de consulta admitidos

Tanto las consultas de idioma natural como de nombre de producto se admiten al Búsqueda de Microsoft para buscar resultados de Dynamics 365. Además, las consultas de Dynamics 365 no distinguen mayúsculas de minúsculas. Use patrones de lenguaje natural para buscar contactos, cuentas y oportunidades (por nombre de cliente o ubicación) y otras consultas usadas con frecuencia. Estos son algunos ejemplos:

* Quién es el contacto de Contoso
* Oportunidades abiertas para Contoso
* Qué son las oportunidades abiertas en Seattle
* Cuáles son las cuentas de Seattle
* Cuáles son los contactos en Seattle
* ¿Cuáles son mis clientes potenciales cerrar este mes?
* Llamada telefónica de prioridad alta
* Mensajes de correo electrónico que faltan de contactos

Los patrones de nombres de producto admiten un rango de aplicaciones de Dynamics 365 y desencadenarán resultados de Dynamics 365 independientemente de dónde aparezcan en una consulta:

* D365
* Dynamics 365
* Dynamics365
* Dynamics CRM
* Dynamics Sales
* Servicio al cliente de Dynamics
* Dynamics Service
* Dynamics Field Service

## <a name="configure-the-dynamics-365-connector"></a>Configurar el conector de Dynamics 365

Con esta configuración sencilla, puede habilitar la experiencia de búsqueda de federación de Dynamics 365 para los usuarios de su organización.

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [Orígenes de datos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).

2. En la sección Aplicaciones y servicios de Microsoft,  en Microsoft Dynamics 365, seleccione Administrar para abrir el panel de Microsoft Dynamics 365.

3. Habilite el conector para su organización.

4. En la **lista Extremos,** seleccione el entorno de Dynamics 365.

5. En el **identificador de conexión,** escriba un identificador único para esta conexión.

6. Revise y active la casilla de consentimiento.

7. Seleccione **Guardar para** finalizar la configuración de conexión.

:::image type="content" alt-text="Captura de pantalla del panel de configuración de Dynamics 365 en el Centro de administración de Microsoft 365" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

Una vez completada la instalación, las respuestas y verticales de Dynamics 365 solo aparecerán para los usuarios con una licencia válida de Dynamics 365 y acceso al entorno de Dynamics 365 conectado. En cualquier momento, puede volver a esta configuración y cambiar el entorno del extremo de conexión o desactivar la conexión.
