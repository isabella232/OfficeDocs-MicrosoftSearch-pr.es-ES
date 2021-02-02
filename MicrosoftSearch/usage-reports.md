---
title: Informes de uso de búsqueda
ms.author: ankmis
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
description: Revisar los informes de uso de Microsoft Search
ms.openlocfilehash: ad349e60794f219fa757861081b12a33c6806091
ms.sourcegitcommit: 25b82bce1eaec5803111161b04ee9fd9e82a0bd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "50072243"
---
# <a name="microsoft-search-usage-reports"></a>Informes de uso de Microsoft Search

Los informes de uso de búsqueda permiten comprender mejor cómo funciona la búsqueda en la organización. La información generada a partir [](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find) de estos informes le ayudará a facilitar la búsqueda de contenido y a realizar acciones que hagan que la búsqueda sea más útil y agradable para los usuarios.

Los [informes de uso de Microsoft Search](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) incluyen gráficos y tablas generados a partir de búsquedas que se ejecutan desde la página principal de SharePoint y Office.com de búsqueda. Puede ver los datos de los últimos 31 días, por día o mensualmente del año anterior. Estos informes solo se están implementando, por lo que llevará tiempo acumular los datos históricos.

Una versión anterior de esta página incluía datos de las búsquedas ejecutadas para Búsqueda de Microsoft en Bing en Bing.com. Esos datos se integrarán en estos informes pronto, pero por ahora, aún puede ver esos informes haciendo clic en el vínculo de la parte inferior de la página para ver las consultas principales de **Bing** y la distribución de impresiones.

> [!div class="mx-imgBorder"]
> ![Panel de informes de uso de búsqueda](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Introducción a los informes de búsqueda

| Informe | Descripción |
|:-----|:-----|
|Volumen de consultas|Este informe muestra el número de consultas de búsqueda realizadas. Use este informe para identificar tendencias de volumen de consultas de búsqueda y para determinar períodos de actividad de búsqueda alta y baja.|
|Principales consultas|Este informe muestra las consultas de búsqueda más populares. Use este informe para comprender qué tipos de información buscan los usuarios.|
|Consultas abandonadas|Este informe muestra las consultas de búsqueda más populares que reciben un clic bajo. Utilice este informe para identificar las consultas de búsqueda que pueden crear la insatisfacción en los usuarios y para mejorar la capacidad de detección de contenido. A continuación, puede determinar si la acción correcta es crear una respuesta, como un marcador, o ingerir contenido nuevo a través de un conector de Graph.|
|Sin consultas de resultados|Este informe muestra las consultas de búsqueda populares que no han devuelto ningún resultado. Utilice este informe para identificar las consultas de búsqueda que pueden crear la insatisfacción en los usuarios y para mejorar la capacidad de detección de contenido. A continuación, puede determinar si la acción correcta es crear una respuesta, como un marcador, o ingerir contenido nuevo a través de un conector de Graph.|

## <a name="viewing-reports"></a>Visualización de informes

Cuando navega a la página de informes de uso, todos los informes están disponibles para verlos. Puede usar el filtro de fecha para elegir un día o mes específico para ver.

La descarga de un informe le permitirá ver informes de un intervalo de tiempo más amplio. Haga clic en la flecha de descarga y **seleccione los últimos 31 días** o los **últimos 12 meses.** El informe se descarga como una hoja de cálculo de Excel. Si seleccionó los últimos 31 días, la hoja de cálculo tendrá una pestaña individual para cada día. Los últimos 12 meses de descarga tendrán una pestaña para cada mes.

Para ver las consultas principales de Bing y los informes de distribución de impresiones, haga clic en el vínculo de la página.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**Cuando selecciono los últimos 31 días o los últimos 12 meses, ¿por qué tengo que elegir un día específico o un mes específico?**

La vista de calendario, hoy en día, en los informes de uso de búsqueda de Microsoft es un proceso de dos pasos. En primer lugar, seleccione el intervalo de fechas de la lista desplegable (últimos 31 días o últimos 12 meses) y, a continuación, seleccione el día o mes de inicio.

Las tablas de consulta superiores, abandonadas y con errores muestran los resultados del día o del mes que elija.

**Cuándo se verán los datos agregados de los últimos 7 días, los últimos 30 días, etc. ¿Como los informes de consultas principales de Bing?**

Estamos considerando este tipo de agregación y simplificando el filtrado del rango de datos para versiones futuras de estos informes.

**¿Por qué no puedo ver un desglose de los informes de uso de diferentes aplicaciones (orígenes)?**

Actualmente, el filtrado por origen no está disponible. Los informes combinan búsquedas desde la página principal de SharePoint Office.com. La próxima versión incluirá filtrado de origen para que pueda ver métricas específicas de cada aplicación.

**What other filtering for usage reports is coming?**

Estamos trabajando en filtros adicionales que ayudarán a tener sentido del uso de la búsqueda en un nivel más granular de su organización. Por ejemplo, podrá ver el volumen de consultas de un departamento o zona geográfica específicos.

**¿Por qué Microsoft Search en Bing informa en una página independiente?**

Modernizar la búsqueda en aplicaciones de Office 365 a Microsoft Search nos ha requerido unirse a sistemas anteriormente distintos, incluida la generación de informes. Esto lleva tiempo y creemos que era más importante sacar estos informes ahora en lugar de esperar hasta que podamos completar la integración de los datos de Bing. Una vez completada la integración, los datos de todos los puntos de conexión de búsqueda se incluirán en los mismos informes.
