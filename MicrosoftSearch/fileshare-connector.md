---
title: Conector de uso compartido de archivos
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de recurso compartido de archivos para Microsoft Search
ms.openlocfilehash: c11c407016315e638205adddddd17d90bbe6b33d
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367771"
---
# <a name="file-share-connector"></a>Conector de uso compartido de archivos

Con el conector de archivo del gráfico de archivos compartidos, los usuarios de la organización pueden buscar recursos compartidos de archivos de Windows locales.

Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de recursos compartidos de archivos. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.

## <a name="install-graph-connector-agent"></a>Instalar el agente de conector de Graph

Para indizar los recursos compartidos de archivos de Windows, debe instalar y registrar el software del [agente de conector de Graph](on-prem-agent.md) .

## <a name="content-requirements"></a>Requisitos de contenido

### <a name="file-types"></a>Tipos de archivo

Se puede indizar y buscar el contenido de los siguientes formatos: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, DAB, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS y ZIP. Solo se indiza el contenido textual de estos formatos. Se omite todo el contenido multimedia. En el caso de los archivos que no pertenecen a este formato, los metadatos se indizan por sí solos.

### <a name="file-size-limits"></a>Límites de tamaño de archivo

El tamaño máximo de archivo admitido es 100 MB. Los archivos que superan los 100 MB no se indizan. El límite de tamaño posterior al proceso es de 4 MB. El procesamiento se detiene cuando el tamaño de un archivo alcanza 4 MB. Por lo tanto, es posible que algunas frases presentes en el archivo no funcionen para la búsqueda.

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos

En la página **conectar con origen de datos** , seleccione **recurso compartido de archivos** y proporcione el nombre, el identificador de conexión y la descripción. En la página siguiente, especifique la ruta de acceso al recurso compartido de archivos y seleccione el agente de conectores de Graph instalado previamente. Escriba las credenciales de una cuenta de usuario de [Microsoft Windows](https://microsoft.com/windows) con acceso de lectura a todos los archivos en el recurso compartido de archivos.

## <a name="preserve-last-access-time"></a>Conservar la hora del último acceso

Cuando el conector intenta rastrear un archivo, se actualiza el campo "hora del último acceso" en sus metadatos. Si depende de ese campo para cualquier solución de archivado y copia de seguridad y no desea actualizarlo cuando el conector tenga acceso a él, puede configurar esta opción en la página **Configuración avanzada** .

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda

Puede restringir el permiso para buscar cualquier archivo basado en compartir listas de control de acceso o en listas de control de acceso del sistema de archivos de tecnología (NTFS). Si desea usar compartir listas de control de acceso, seleccione la opción adecuada en la página **Configuración avanzada** . Si desea usar las listas de control de acceso de NTFS, seleccione la opción correspondiente en la página **administrar permisos de búsqueda** .

## <a name="assign-property-labels"></a>Asignar etiquetas de propiedad

Puede asignar una propiedad de origen a cada etiqueta eligiendo en un menú de opciones. Aunque este paso no es obligatorio, tener algunas etiquetas de propiedades mejorará la relevancia de la búsqueda y garantizará resultados de búsqueda más precisos para los usuarios finales.

## <a name="manage-schema"></a>Administrar esquema

En la pantalla **administrar esquema** , tiene la opción de cambiar los atributos de esquema (**consultable**, **búsquedas**, **recuperables** y **refinables**) asociados con las propiedades, agregar alias opcionales y elegir la propiedad de **contenido** .

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización

El intervalo de programación de actualización predeterminada recomendado es de 15 minutos, pero puede cambiarlo según sus preferencias.
