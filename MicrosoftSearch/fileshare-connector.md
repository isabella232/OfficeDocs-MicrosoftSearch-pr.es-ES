---
title: Conector de Gráfico de recurso compartido de archivos para Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurar el conector de Gráfico de recurso compartido de archivos para Microsoft Search
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097425"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>Conector de Gráfico de recurso compartido de archivos

El conector de Gráfico de recursos compartidos de archivos permite a los usuarios de su organización buscar recursos compartidos de archivos locales de Windows.

> [!NOTE]
> Lea el [**artículo sobre el programa de instalación del conector de Graph**](configure-connector.md) para comprender el proceso de configuración general de los conectores de Graph.

## <a name="before-you-get-started"></a>Antes de empezar

### <a name="install-the-graph-connector-agent"></a>Instalar el agente de conector de Graph

Para indizar los recursos compartidos de archivos de Windows, debe instalar y registrar el agente del conector de Graph. Consulte [Instalar el agente del conector de Graph](on-prem-agent.md) para obtener más información.  

### <a name="content-requirements"></a>Requisitos de contenido

### <a name="file-types"></a>Tipos de archivo

Se puede indizar y buscar contenido de los siguientes formatos: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS y ZIP. Solo se indiza el contenido textual de estos formatos. Se omite todo el contenido multimedia. Para cualquier archivo que no pertenezca a este formato, solo se indizan los metadatos.

### <a name="file-size-limits"></a>Límites de tamaño de archivo

El tamaño máximo de archivo admitido es de 100 MB. Los archivos que superan los 100 MB no se indizan. El límite de tamaño máximo posterior al proceso es de 4 MB. El procesamiento se detiene cuando el tamaño de un archivo alcanza los 4 MB. Por lo tanto, es posible que algunas frases presentes en el archivo no funcionen para la búsqueda.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

En la **página Conectar con origen de** datos, seleccione Recurso **compartido** de archivos y proporcione el nombre, el identificador de conexión y la descripción. En la página siguiente, proporcione la ruta de acceso al recurso compartido de archivos y seleccione el agente de conector de Graph instalado anteriormente. Escribe las credenciales de una cuenta [de usuario de Microsoft Windows](https://microsoft.com/windows) con acceso de lectura a todos los archivos del recurso compartido de archivos.

### <a name="preserve-last-access-time"></a>Conservar el último tiempo de acceso

Cuando el conector intenta rastrear un archivo, se actualiza el campo "hora de último acceso" en sus metadatos. Si depende de ese campo para las soluciones de archivado y copia de seguridad y no desea actualizarlo cuando el conector tiene acceso a él, puede configurar esta opción en la página Configuración **avanzada.**

## <a name="step-4-manage-search-permissions"></a>Paso 4: Administrar permisos de búsqueda

Puede restringir el permiso para buscar cualquier archivo basado en listas de control de acceso compartido o listas de control de acceso del Sistema de archivos de nueva tecnología (NTFS). Si desea usar Compartir listas de control de acceso, seleccione la opción adecuada en la **página Configuración** avanzada. Si desea usar listas de control de acceso NTFS, seleccione la opción adecuada en la página Administrar permisos **de** búsqueda.

## <a name="step-5-assign-property-labels"></a>Paso 5: Asignar etiquetas de propiedad

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Paso 6: Administrar esquema

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Paso 7: Elegir la configuración de actualización

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
