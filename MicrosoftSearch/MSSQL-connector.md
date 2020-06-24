---
title: Microsoft SQL Server y Azure SQL Connector para Microsoft Search
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configure Microsoft SQL Server o el conector de Azure SQL para Microsoft Search.
ms.openlocfilehash: e664a9a6e389531f8b5735673150839a1b106ce1
ms.sourcegitcommit: 68cd28a84df120473270f27e4eb62de9eae455f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "44850902"
---
# <a name="azure-sql-and-microsoft-sql-server-connectors"></a>Conectores de Azure SQL y Microsoft SQL Server

Con Microsoft SQL Server o Azure SQL Connector, su organización puede detectar e indizar datos de una base de datos de SQL Server local o de una base de datos hospedada en su instancia de SQL de Azure en la nube. El conector indiza el contenido especificado en Microsoft Search. Para mantener el índice actualizado con datos de origen, admite los rastreos completos e incrementales periódicos. Con estos conectores de SQL, también puede restringir el acceso a los resultados de búsqueda para determinados usuarios.

Este artículo está destinado a los administradores de Microsoft 365 o a cualquiera que configure, ejecute y supervise un conector de Microsoft SQL Server. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.

## <a name="install-a-data-gateway-required-for-on-premises-microsoft-sql-server-connector-only"></a>Instalar una puerta de enlace de datos (necesario solo para el conector de Microsoft SQL Server local)
Para obtener acceso a los datos de terceros, debe instalar y configurar una puerta de enlace de Microsoft Power BI. Consulte [instalar una puerta de enlace local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) para obtener más información.  

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos
Para conectar el conector de Microsoft SQL Server a un origen de datos, debe configurar el servidor de base de datos que desea rastrear y la puerta de enlace local. A continuación, puede conectarse a la base de datos con el método de autenticación necesario.

Para Azure SQL Connector, solo tiene que especificar el nombre del servidor o la dirección IP a la que desea conectarse. Azure SQL Connector solo admite la autenticación de Azure Active Directory Open ID Connect (OIDC) para conectarse a la base de datos.

> [!NOTE]
> La base de datos debe ejecutar SQL Server versión 2008 o posterior para que Microsoft SQL Server Connector pueda conectarse.

Para realizar búsquedas en el contenido de la base de datos, debe especificar consultas SQL cuando configure el conector. Estas consultas SQL deben nombrar todas las columnas de base de datos que desea indizar (es decir, las propiedades de origen), incluidas las combinaciones de SQL que deben realizarse para obtener todas las columnas. Para restringir el acceso a los resultados de la búsqueda, debe especificar listas de control de acceso (ACL) en las consultas SQL cuando configure el conector.

## <a name="full-crawl-required"></a>Rastreo completo (obligatorio)
En este paso, configurará la consulta SQL que ejecuta un rastreo completo de la base de datos. El rastreo completo selecciona todas las columnas o propiedades que desea que se puedan **consultar**, **Buscar**o **recuperar**. También puede especificar columnas ACL para restringir el acceso de los resultados de la búsqueda a usuarios o grupos específicos.

> [!Tip]
> Para obtener todas las columnas que necesita, puede combinar varias tablas.

![Script que muestra los OrderTable y AclTable con propiedades de ejemplo](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Seleccionar columnas de datos (obligatorios) y columnas de ACL (opcional)
En el ejemplo se muestra la selección de cinco columnas de datos que contienen los datos de la búsqueda: IdPedido, OrderTitle, OrderDesc, CreatedDateTime y IsDeleted. Para establecer los permisos de vista para cada fila de datos, puede seleccionar opcionalmente estas columnas de ACL: AllowedUsers, AllowedGroups, DeniedUsers y DeniedGroups. Todas estas columnas de datos pueden **consultarse**, realizar **búsquedas**o **recuperarse**.

Seleccione columnas de datos como se muestra en esta consulta de ejemplo:`SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`
 
Para administrar el acceso a los resultados de la búsqueda, puede especificar una o más columnas de ACL en la consulta. SQL Connector permite controlar el acceso a nivel de registro. Puede elegir tener el mismo control de acceso para todos los registros de una tabla. Si la información de la ACL se almacena en una tabla independiente, es posible que tenga que realizar una combinación con esas tablas en la consulta.

A continuación se describe el uso de cada una de las columnas de LCA en la consulta anterior. En la lista siguiente se explican los 4 **mecanismos de control de acceso**. 
* **AllowedUsers**: especifica la lista de identificadores de usuario que podrán tener acceso a los resultados de la búsqueda. En el siguiente ejemplo, la lista de usuarios: john@contoso.com, keith@contoso.com y lisa@contoso.com solo tendría acceso a un registro con OrderId = 12. 
* **AllowedGroups**: especifica el grupo de usuarios que podrán tener acceso a los resultados de la búsqueda. En el siguiente ejemplo, Group sales-team@contoso.com sólo tendría acceso a record con OrderId = 12.
* **DeniedUsers**: especifica la lista de usuarios que **no** tienen acceso a los resultados de la búsqueda. En el siguiente ejemplo, los usuarios john@contoso.com y keith@contoso.com no tienen acceso a record with OrderId = 13, mientras que todos los demás tienen acceso a este registro. 
* **DeniedGroups**: especifica el grupo de usuarios que **no** tienen acceso a los resultados de la búsqueda. En el ejemplo siguiente, los grupos engg-team@contoso.com y pm-team@contoso.com no tienen acceso al registro con OrderId = 15, mientras que todos los demás tienen acceso a este registro.  

![](media/MSSQL-ACL1.png)

### <a name="watermark-required"></a>Marca de agua (obligatorio)
Para evitar la sobrecarga de la base de datos, el conector procesa por lotes y reanuda las consultas de rastreo completo con una columna de marca de agua de rastreo completo. Mediante el valor de la columna marca de agua, se recopilan todos los lotes subsiguientes y la consulta se reanuda desde el último punto de control. Básicamente, se trata de un mecanismo para controlar la actualización de datos de rastreos completos.

Cree fragmentos de código de consulta para las marcas de agua como se muestra en estos ejemplos:
* `WHERE (CreatedDateTime > @watermark)`. Cite el nombre de la columna de marca de agua con la palabra clave Reserved `@watermark` . Si el criterio de ordenación de la columna marca de agua es Ascending, use `>` ; de lo contrario, use `<` .
* `ORDER BY CreatedDateTime ASC`. Ordene la columna marca de agua en orden ascendente o descendente.

En la configuración que se muestra en la imagen siguiente, `CreatedDateTime` es la columna marca de agua seleccionada. Para recuperar el primer lote de filas, especifique el tipo de datos de la columna marca de agua. En este caso, el tipo de datos es `DateTime` .

![](media/MSSQL-watermark.png)

La primera consulta obtiene la **primera cantidad de** filas usando: "CreatedDateTime > 1 de enero de 1753 00:00:00" (valor mínimo del tipo de datos DateTime). Una vez que se obtiene el primer lote, el valor más alto de `CreatedDateTime` devuelto en el lote se guarda como punto de control si las filas se clasifican en orden ascendente. Un ejemplo es 1 de marzo de 2019 03:00:00. A continuación, se obtiene el siguiente lote de **N** filas con "CreatedDateTime > 1 de marzo de 2019 03:00:00" en la consulta.

### <a name="skipping-soft-deleted-rows-optional"></a>Omitir filas eliminadas temporalmente (opcional)
Para excluir filas eliminadas temporalmente de la base de datos que se va a indizar, especifique el nombre y el valor de la columna de eliminación temporal que indica la fila que se va a eliminar.

![Configuración de eliminación temporal: "eliminar temporalmente la columna" y "valor de la columna eliminación temporal que indica una fila eliminada"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Rastreo completo: administrar permisos de búsqueda
Haga clic en **administrar permisos** para seleccionar las distintas columnas de control de acceso (ACL) que especifican el mecanismo de control de acceso. Seleccione el nombre de columna que especificó en la consulta SQL de rastreo completo. 

Se espera que cada una de las columnas de ACL sea una columna de varios valores. Estos valores de identificador múltiple pueden estar separados por separadores como punto y coma (;), coma (,), etc. Debe especificar este separador en el campo **separador de valores** .
 
Se admiten los siguientes tipos de identificador para usar como ACL: 
* **Nombre principal de usuario (UPN)**: un nombre principal de usuario (UPN) es el nombre de un usuario del sistema en un formato de dirección de correo electrónico. Un UPN (por ejemplo: john.doe@domain.com) consta del nombre de usuario (nombre de inicio de sesión), el separador (el símbolo @) y el nombre de dominio (sufijo UPN). 
* **Identificador de Azure Active Directory (AAD)**: en AAD, cada usuario o grupo tiene un identificador de objeto que tiene un aspecto similar a ' e0d3ad3d-0000-1111-2222-3c5f5c52ab9b ' 
* **Identificador de seguridad de Active Directory (ad)**: en una configuración de ad local, todos los usuarios y grupos tienen un identificador de seguridad único e inmutable con un aspecto similar a-1-5-21-3878594291-2115959936-132693609-65242 ".

![](media/MSSQL-ACL2.png)

## <a name="incremental-crawl-optional"></a>Rastreo incremental (opcional)
En este paso opcional, proporcione una consulta SQL para ejecutar un rastreo incremental de la base de datos. Con esta consulta, SQL Connector determina los cambios realizados en los datos desde el último rastreo incremental. Como en el rastreo completo, seleccione todas las columnas que desea que sean **consultables**, que se puedan **Buscar**o que se puedan **recuperar**. Especifique el mismo conjunto de columnas de ACL que especificó en la consulta de rastreo completo.

Los componentes de la imagen siguiente se parecen a los componentes de rastreo completos con una excepción. En este caso, "ModifiedDateTime" es la columna de marca de agua seleccionada. Revise los [pasos de rastreo completo](#full-crawl-required) para obtener información sobre cómo escribir la consulta de rastreo incremental y ver la siguiente imagen como ejemplo.

![Script de rastreo incremental que muestra las propiedades OrderTable, AclTable y example que se pueden usar.](media/MSSQL-incrcrawl.png)

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda 
Puede optar por usar las [ACL especificadas en la pantalla de rastreo completo](#full-crawl-manage-search-permissions) o reemplazarlas para que el contenido sea visible para todos los usuarios.

## <a name="limitations"></a>Limitaciones
Los conectores de SQL tienen estas limitaciones en la versión preliminar:
* Conector de Microsoft SQL Server: la base de datos local debe ejecutar SQL Server versión 2008 o posterior.
* Las ACL solo se admiten con un nombre principal de usuario (UPN), Azure Active Directory (Azure AD) o seguridad de Active Directory. 
* No se admite la indización de contenido enriquecido dentro de las columnas de base de datos. Ejemplos de este tipo de contenido son HTML, JSON, XML, blobs y los analizadores de documentos que existen como vínculos dentro de las columnas de la base de datos.
