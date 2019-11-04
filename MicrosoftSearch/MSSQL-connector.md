---
title: Conector de Microsoft SQL para Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector de Microsoft SQL para Microsoft Search.
ms.openlocfilehash: a5e0b26277345814ed095b54583ea635341295ad
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "37950025"
---
# <a name="microsoft-sql-server-connector"></a>Conector de Microsoft SQL Server

Con un conector de Microsoft SQL Server, su organización puede detectar e indizar datos de una base de datos de SQL Server local. El conector indiza el contenido especificado en Microsoft Search. Para mantener el índice actualizado con datos de origen, admite los rastreos completos e incrementales periódicos. Con el conector de SQL Server, también puede restringir el acceso a los resultados de búsqueda para determinados usuarios.

Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de Microsoft SQL Server. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.

## <a name="install-a-data-gateway"></a>Instalar una puerta de enlace de datos
Para obtener acceso a los datos de terceros, debe instalar y configurar una puerta de enlace de Microsoft Power BI. Consulte [instalar y la puerta de enlace local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) para obtener más información.  

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos
Para conectar el conector de Microsoft SQL Server a un origen de datos, debe configurar el servidor de base de datos que desea rastrear y la puerta de enlace local. A continuación, puede conectarse a la base de datos con el método de autenticación necesario.

> [!NOTE]
> La base de datos debe ejecutar SQL Server versión 2008 o posterior.

Para realizar búsquedas en el contenido de la base de datos, debe especificar consultas SQL cuando configure el conector. Estas consultas SQL deben nombrar todas las columnas de base de datos que desea indizar (es decir, las propiedades de origen), incluidas las combinaciones de SQL que deben realizarse para obtener todas las columnas. Para restringir el acceso a los resultados de la búsqueda, debe especificar listas de control de acceso (ACL) con consultas SQL cuando configure el conector de Microsoft SQL Server.

## <a name="full-crawl-required"></a>Rastreo completo (obligatorio)
En este paso, configurará la consulta SQL que ejecuta un rastreo completo de la base de datos. El rastreo completo selecciona todas las columnas o propiedades que desea que se puedan **consultar**, **Buscar**o **recuperar**. También puede especificar columnas ACL para restringir el acceso de los resultados de la búsqueda a usuarios o grupos específicos.

> [!Tip]
> Para obtener todas las columnas que necesita, puede combinar varias tablas.

![Script que muestra los OrderTable y AclTable con propiedades de ejemplo](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Seleccionar columnas de datos (obligatorios) y columnas de ACL (opcional)
En el ejemplo se muestra la selección de cinco columnas de datos que contienen los datos de la búsqueda: IdPedido, OrderTitle, OrderDesc, CreatedDateTime y IsDeleted. Para establecer los permisos de vista para cada fila de datos, puede seleccionar opcionalmente estas columnas de ACL: AllowedUsers, AllowedGroups, DeniedUsers y DeniedGroups. Todas estas columnas de datos pueden **consultarse**, realizar **búsquedas**o **recuperarse**.

Seleccione columnas de datos como se muestra en esta consulta de ejemplo:`SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

### <a name="watermark-required"></a>Marca de agua (obligatorio)
Para evitar la sobrecarga de la base de datos, el conector procesa por lotes y reanuda las consultas de rastreo completo con una columna de marca de agua de rastreo completo. Mediante el valor de la columna marca de agua, se recopilan todos los lotes subsiguientes y la consulta se reanuda desde el último punto de control. Básicamente, se trata de un mecanismo para controlar la actualización de datos de rastreos completos.

Cree fragmentos de código de consulta para las marcas de agua como se muestra en estos ejemplos:
* `WHERE (CreatedDateTime > @watermark)`. Cite el nombre de la columna de marca de `@watermark`agua con la palabra clave Reserved. Si el criterio de ordenación de la columna marca de agua es `>`ascendente, use; de lo contrario `<`, use.
* `ORDER BY CreatedDateTime ASC`. Ordene la columna marca de agua en orden ascendente o descendente.

En la configuración que se muestra en la imagen `CreatedDateTime` siguiente, es la columna marca de agua seleccionada. Para recuperar el primer lote de filas, especifique el tipo de datos de la columna marca de agua. En este caso, el tipo de datos `DateTime`es.

![](media/MSSQL-watermark.png)

La primera consulta obtiene la **primera cantidad de** filas usando: "CreatedDateTime > 1 de enero de 1753 00:00:00" (valor mínimo del tipo de datos DateTime). Una vez que se obtiene el primer lote, el valor más `CreatedDateTime` alto de devuelto en el lote se guarda como punto de control si las filas se clasifican en orden ascendente. Un ejemplo es 1 de marzo de 2019 03:00:00. A continuación, se obtiene el siguiente lote de **N** filas con "CreatedDateTime > 1 de marzo de 2019 03:00:00" en la consulta.

### <a name="skipping-soft-deleted-rows-optional"></a>Omitir filas eliminadas temporalmente (opcional)
Para excluir filas eliminadas temporalmente de la base de datos que se va a indizar, especifique el nombre y el valor de la columna de eliminación temporal que indica la fila que se va a eliminar.

![Configuración de eliminación temporal: "eliminar temporalmente la columna" y "valor de la columna eliminación temporal que indica una fila eliminada"](media/MSSQL-softdelete.png)

## <a name="incremental-crawl-optional"></a>Rastreo incremental (opcional)
En este paso opcional, proporcione una consulta SQL para ejecutar un rastreo incremental de la base de datos. Con esta consulta, el conector de Microsoft SQL Server realiza todos los cambios en los datos desde el último rastreo incremental. Como en el rastreo completo, seleccione todas las columnas que desea que sean **consultables**, que se puedan **Buscar**o que se puedan **recuperar**. Especifique el mismo conjunto de columnas de ACL que especificó en la consulta de rastreo completo.

Los componentes de la imagen siguiente se parecen a los componentes de rastreo completos con una excepción. En este caso, "ModifiedDateTime" es la columna de marca de agua seleccionada. Revise los [pasos de rastreo completo](#full-crawl-required) para obtener información sobre cómo escribir la consulta de rastreo incremental y ver la siguiente imagen como ejemplo.

![Script de rastreo incremental que muestra las propiedades OrderTable, AclTable y example que se pueden usar.](media/MSSQL-incrcrawl.png)

## <a name="limitations"></a>Limitaciones
El conector de Microsoft SQL Server tiene estas limitaciones en la versión preliminar:
* La base de datos local debe ejecutar SQL Server versión 2008 o posterior.
* Las ACL solo se admiten con un nombre principal de usuario (UPN), Azure Active Directory (Azure AD) o seguridad de Active Directory.
* No se admite la indización de contenido enriquecido dentro de las columnas de base de datos. Ejemplos de este tipo de contenido son HTML, JSON, XML, blobs y los analizadores de documentos que existen como vínculos dentro de las columnas de la base de datos.

