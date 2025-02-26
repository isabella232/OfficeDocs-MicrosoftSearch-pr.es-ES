---
title: Informes de uso de búsqueda
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.topic: article
ms.service: mssearch
audience: Admin
ms.audience: Admin
ms.date: 09/24/2021
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Revisar Búsqueda de Microsoft de uso
ms.openlocfilehash: 1f2afa6e2c7691aa3284ae017913827761981529
ms.sourcegitcommit: ca6f0488b842e7fc0d98c7b84b2b8bc5817d3e7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2021
ms.locfileid: "60224871"
---
# <a name="microsoft-search-usage-reports"></a>Búsqueda de Microsoft Informes de uso

Los informes de uso de búsqueda le permiten comprender mejor cómo funciona la búsqueda en su organización. Los conocimientos generados a partir de estos informes le ayudarán a realizar acciones que harán que la búsqueda sea una experiencia más útil y agradable para los usuarios.

> [!IMPORTANT]
> Búsqueda de Microsoft informes de uso están actualmente en versión preliminar

Los informes de uso de [Búsqueda de Microsoft](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) incluyen gráficos y tablas generados a partir de búsquedas que se ejecutan desde SharePoint Home (el sitio con dirección URL que termina en /SharePoint.aspx), Office.com y Búsqueda de Microsoft en Bing cuadros de búsqueda. Puede ver datos de los últimos 31 días, por día o mensualmente del año anterior. Estos informes se están implementando, por lo que llevará tiempo acumular los datos históricos.

> [!div class="mx-imgBorder"]
> ![Panel de informes de uso de búsqueda.](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Información general sobre los informes de búsqueda

| Informe | Descripción |
|:-----|:-----|
|Volumen de consulta|Este informe muestra el número de consultas de búsqueda realizadas. Use este informe para identificar tendencias de volumen de consulta de búsqueda y para determinar períodos de actividad de búsqueda alta y baja.|
|Principales consultas|Este informe muestra las consultas de búsqueda más populares. Una consulta se agrega a este informe cuando se busca al menos tres veces con un clic en un resultado. Use este informe para comprender qué tipos de información buscan los usuarios.|
|Consultas abandonadas|Este informe muestra consultas de búsqueda populares que reciben un clic bajo. Utilice este informe para identificar las consultas de búsqueda que pueden crear la insatisfacción en los usuarios y para mejorar la capacidad de detección de contenido. A continuación, puede determinar si crear una respuesta, como un marcador, o ingerir contenido nuevo a través de un conector Graph es la acción correcta.|
|Sin consultas de resultados|Este informe muestra las consultas de búsqueda populares que no han devuelto ningún resultado. Utilice este informe para identificar las consultas de búsqueda que pueden crear la insatisfacción en los usuarios y para mejorar la capacidad de detección de contenido. A continuación, puede determinar si crear una respuesta, como un marcador, o ingerir contenido nuevo a través de un conector Graph es la acción correcta.|

>[!NOTE]
>Actualmente hay un problema conocido en el que las consultas que se satisfacen con una respuesta como un marcador se cuentan como una consulta abandonada.

## <a name="viewing-reports"></a>Visualización de informes

Al navegar a la página de informes de uso, todos los informes están disponibles para verlos. Puede usar el filtro de fecha para elegir un día o mes específicos que se va a ver.

La descarga de un informe le permitirá ver informes de un intervalo de tiempo más amplio. Haga clic en la flecha de descarga y seleccione **los últimos 31 días** o **los últimos 12 meses.** El informe se descarga como una Excel hoja de cálculo. Si seleccionó los últimos 31 días, la hoja de cálculo tendrá una pestaña individual para cada día. La descarga de los últimos 12 meses tendrá una pestaña para cada mes.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**Cuando selecciono los últimos 31 días o los últimos 12 meses, ¿por qué tengo que elegir un día específico o un mes específico?**

La vista de calendario, hoy en día, en los informes de uso de búsqueda de Microsoft es un proceso de dos pasos. Primero seleccione el intervalo de fechas del menú desplegable (pasados 31 días o pasados 12 meses) y, a continuación, seleccione el día o mes de inicio.

Las tablas de consulta superiores, abandonadas y con errores muestran los resultados del día o del mes que elija.

**¿Cuándo voy a ver los datos agregados de los últimos 7 días, los últimos 30 días, etc....?**

Estamos considerando este tipo de agregación y simplificando el filtrado del intervalo de datos para versiones futuras de estos informes.

**¿Por qué no puedo ver un desglose de los informes de uso de diferentes aplicaciones (orígenes)?**

Actualmente, el filtrado por origen no está disponible. Los informes combinan búsquedas de SharePoint inicio y Office.com. Nuestra próxima versión incluirá el filtrado de origen para que pueda ver métricas específicas de cada aplicación.

**¿Qué otro filtrado para informes de uso viene?**

Estamos trabajando en más filtros que ayudarán a dar sentido al uso de la búsqueda en un nivel más detallado de la organización. Por ejemplo, podrá ver el volumen de consulta de un departamento o una zona geográfica específica.
