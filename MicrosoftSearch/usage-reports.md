---
title: Informes de uso de la búsqueda
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
ROBOTS: NoIndex
description: Revisión de los informes de uso de Microsoft Search
ms.openlocfilehash: 5bb2ff5a7821e5772e9fb54f60e5e70508194929
ms.sourcegitcommit: ac4e261c01262be747341f810d2d1faf220d3961
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2020
ms.locfileid: "49382693"
---
# <a name="microsoft-search-usage-reports"></a>Informes de uso de Microsoft Search

Los informes de uso de búsquedas le permiten comprender mejor cómo funciona la búsqueda en su organización. La información que se genera a partir de estos informes le ayudará a que el [contenido sea fácil de encontrar](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find) y emprender acciones que harán que la búsqueda sea una experiencia más útil y agradables para los usuarios.

> [!IMPORTANT]
> Los informes de uso de Microsoft Search están actualmente en versión preliminar.

Los [informes de uso de Microsoft Search](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) incluyen gráficos y tablas generadas a partir de búsquedas que se ejecutan desde la Página principal de SharePoint y los cuadros de búsqueda de Office.com. Puede ver los datos de los últimos 31 días, por día o mensualmente para el año anterior. Estos informes solo se implementan, por lo que se tardará más tiempo en acumular los datos históricos.

Una versión anterior de esta página incluía datos de búsquedas ejecutadas para Microsoft Search en Bing en Bing.com. Los datos se integrarán en estos informes muy pronto, pero por ahora puede ver esos informes haciendo clic en el vínculo en la parte inferior de la página para **ver las consultas principales de Bing y la distribución de impresión**.

![Panel de informes de uso de búsqueda](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Información general sobre los informes de búsqueda

|**Informe**|**Descripción**|
|:-----|:-----|
|Volumen de consultas|Este informe muestra el número de consultas de búsqueda realizadas. Use este informe para identificar tendencias de volumen de consultas de búsqueda y para determinar períodos de actividad de búsqueda alta y baja.|
|Principales consultas|Este informe muestra las consultas de búsqueda más populares. Use este informe para comprender los tipos de información que los usuarios buscan.|
|Consultas abandonadas|Este informe muestra las consultas de búsqueda más populares que reciben clics bajo. Utilice este informe para identificar las consultas de búsqueda que pueden crear la insatisfacción en los usuarios y para mejorar la capacidad de detección de contenido. A continuación, puede determinar si la creación de una respuesta, como un marcador, o la incorporación de contenido nuevo a través de un conector de Graph es la acción adecuada.|
|Ninguna consulta de resultados|Este informe muestra las consultas de búsqueda populares que no han devuelto ningún resultado. Utilice este informe para identificar las consultas de búsqueda que pueden crear la insatisfacción en los usuarios y para mejorar la capacidad de detección de contenido. A continuación, puede determinar si la creación de una respuesta, como un marcador, o la incorporación de contenido nuevo a través de un conector de Graph es la acción adecuada.|

## <a name="viewing-reports"></a>Ver informes

Cuando navegue a la página informes de uso, todos los informes estarán disponibles para su visualización. Puede usar el filtro de fecha para seleccionar un día o un mes específico para su visualización.

La descarga de un informe le permitirá ver los informes a partir de un intervalo de tiempo más amplio. Haga clic en la flecha de descarga y seleccione **últimos 31 días** o **últimos 12 meses**. El informe se descarga como una hoja de cálculo de Excel. Si seleccionó los últimos 31 días, la hoja de cálculo tendrá una pestaña individual para cada día. La descarga de los últimos 12 meses tendrá una pestaña para cada mes.

Para ver los informes de distribución de impresiones y consultas principales de Bing haga clic en el vínculo de la página.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**Cuando selecciono los últimos 31 días o últimos 12 meses, ¿por qué debo elegir un día específico o un mes específico respectivamente.**

La vista Calendario hoy en los informes de uso de Microsoft Search es un proceso de dos pasos. en primer lugar, seleccione el intervalo de fechas en la lista desplegable (últimos 31 días o últimos 12 meses) y, a continuación, seleccione el día o el mes de inicio.

Las tablas de consulta Top, Abandoned y Failed muestran resultados del día o del mes que elija.

**¿Cuándo veo los datos agregados durante los últimos 7 días, los últimos 30 días, etc. como los informes de consultas principales de Bing?**

Estamos considerando este tipo de agregación y la simplificación del filtrado de intervalo de datos para versiones futuras de estos informes.

**¿Por qué no puedo ver un desglose de los informes de uso de diferentes aplicaciones (orígenes)?**

Actualmente, el filtrado por origen no está disponible. Los informes combinan búsquedas desde la Página principal de SharePoint y Office.com. En nuestro próximo lanzamiento se incluirá el filtrado de origen para que pueda ver las métricas específicas de cada aplicación.

**¿Qué otras características de filtrado de los informes de uso vienen?**

Estamos trabajando en filtros adicionales que le ayudarán a mejorar el uso de la búsqueda en un nivel de la organización más granular. Por ejemplo, podrá ver el volumen de consultas de un departamento o zona geográfica específico.

**¿Por qué Microsoft Search en Bing Reports es una página separada?**

La modernización de la búsqueda en las aplicaciones de Office 365 a Microsoft Search ha exigido que se unan sistemas distintos, incluida la generación de informes. Esto lleva tiempo y pensamos que era más importante obtener estos informes ahora frente a la espera hasta que podríamos completar la integración de los datos de Bing. Una vez completada la integración, los datos de todos los extremos de búsqueda se incluirán en los mismos informes.
