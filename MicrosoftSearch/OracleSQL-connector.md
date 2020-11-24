---
title: Conector SQL de Oracle para Microsoft Search
ms.author: vivg
author: Vivek
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar el conector SQL de Oracle para Microsoft Search.
ms.openlocfilehash: cf7946533b3806bb730cdc6a31f7745ebad2c59d
ms.sourcegitcommit: ac4e261c01262be747341f810d2d1faf220d3961
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2020
ms.locfileid: "49382694"
---
# <a name="oracle-sql-connector"></a>Conector SQL de Oracle

Con el conector SQL de Oracle, su organización puede detectar e indizar datos de una base de datos de Oracle local. El conector indiza el contenido especificado en Microsoft Search. Para mantener el índice actualizado con datos de origen, admite los rastreos completos e incrementales periódicos. Con el conector SQL de Oracle, también puede restringir el acceso a los resultados de búsqueda para determinados usuarios.

Este artículo está destinado a los administradores de Microsoft 365 o a cualquier usuario que configure, ejecute y supervise un conector SQL de Oracle. Se explica cómo configurar las capacidades del conector y el conector, las limitaciones y las técnicas de solución de problemas.

## <a name="install-the-graph-connector-agent"></a>Instalar el agente de conector de Graph
Para poder obtener acceso a los datos locales de terceros, debe instalar y configurar el agente de conector de Graph. Consulte [instalar el agente de conector de Graph](on-prem-agent.md) para obtener más información.  

## <a name="connect-to-a-data-source"></a>Conectarse a un origen de datos
Para conectar el conector SQL de Oracle a un origen de datos, debe configurar el servidor de base de datos que desea rastrear y el agente de conector de Graph local. A continuación, puede conectarse a la base de datos con el método de autenticación necesario.

Para Oracle SQL Connector, debe especificar el nombre de host, el puerto y el nombre de servicio (base de datos) junto con el método de autenticación preferido, el nombre de usuario y la contraseña.

> [!NOTE]
> La base de datos debe ejecutar la versión 11g o posterior de la base de datos de Oracle para que el conector pueda conectarse. El conector admite bases de datos de Oracle hospedadas en plataformas Windows, Linux y de máquinas virtuales de Azure.

Para realizar búsquedas en el contenido de la base de datos, debe especificar consultas SQL cuando configure el conector. Estas consultas SQL deben nombrar todas las columnas de base de datos que desea indizar (es decir, las propiedades de origen), incluidas las combinaciones de SQL que deben realizarse para obtener todas las columnas. Para restringir el acceso a los resultados de la búsqueda, debe especificar listas de control de acceso (ACL) en las consultas SQL cuando configure el conector.

## <a name="full-crawl-required"></a>Rastreo completo (obligatorio)
En este paso, configurará la consulta SQL que ejecuta un rastreo completo de la base de datos. El rastreo completo selecciona todas las columnas o propiedades que desea que se puedan **consultar**, **Buscar** o **recuperar**. También puede especificar columnas ACL para restringir el acceso de los resultados de la búsqueda a usuarios o grupos específicos.

> [!Tip]
> Para obtener todas las columnas que necesita, puede combinar varias tablas.

![Script que muestra los OrderTable y AclTable con propiedades de ejemplo](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Seleccionar columnas de datos (obligatorios) y columnas de ACL (opcional)
En el ejemplo se muestra la selección de cinco columnas de datos que contienen los datos de la búsqueda: IdPedido, OrderTitle, OrderDesc, CreatedDateTime y IsDeleted. Para establecer los permisos de vista para cada fila de datos, puede seleccionar opcionalmente estas columnas de ACL: AllowedUsers, AllowedGroups, DeniedUsers y DeniedGroups. Todas estas columnas de datos pueden **consultarse**, realizar **búsquedas** o **recuperarse**.

Seleccione columnas de datos como se muestra en esta consulta de ejemplo: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`
 
Para administrar el acceso a los resultados de la búsqueda, puede especificar una o más columnas de ACL en la consulta. SQL Connector permite controlar el acceso a nivel de registro. Puede elegir tener el mismo control de acceso para todos los registros de una tabla. Si la información de la ACL se almacena en una tabla independiente, es posible que tenga que realizar una combinación con esas tablas en la consulta.

A continuación se describe el uso de cada una de las columnas de LCA en la consulta anterior. En la lista siguiente se explican los 4 **mecanismos de control de acceso**. 
* **AllowedUsers**: especifica la lista de identificadores de usuario que podrán tener acceso a los resultados de la búsqueda. En el siguiente ejemplo, la lista de usuarios: john@contoso.com, keith@contoso.com y lisa@contoso.com solo tendría acceso a un registro con OrderId = 12. 
* **AllowedGroups**: especifica el grupo de usuarios que podrán tener acceso a los resultados de la búsqueda. En el siguiente ejemplo, Group sales-team@contoso.com sólo tendría acceso a record con OrderId = 12.
* **DeniedUsers**: especifica la lista de usuarios que **no** tienen acceso a los resultados de la búsqueda. En el siguiente ejemplo, los usuarios john@contoso.com y keith@contoso.com no tienen acceso a record with OrderId = 13, mientras que todos los demás tienen acceso a este registro. 
* **DeniedGroups**: especifica el grupo de usuarios que **no** tienen acceso a los resultados de la búsqueda. En el ejemplo siguiente, los grupos engg-team@contoso.com y pm-team@contoso.com no tienen acceso al registro con OrderId = 15, mientras que todos los demás tienen acceso a este registro.  

![Datos de ejemplo que muestran los OrderTable y AclTable con propiedades de ejemplo](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Tipos de datos admitidos
En la tabla siguiente se resumen los tipos de datos admitidos por el conector SQL de Oracle. La tabla también resume el tipo de datos de indización para el tipo de datos de SQL compatible. Para obtener más información sobre los conectores de Microsoft Graph compatibles con los tipos de datos para la indización, consulte la documentación sobre los [tipos de recursos Property](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties). 

| Categoría | Tipo de datos de origen | Tipo de datos de indización |
| ------------ | ------------ | ------------ |
| DataType de número | NÚMERO (p, 0) | Int64 (para p <= 18) <br> Double (para p > 18) |
| Tipo de fuente de número de punto flotante | NÚMERO (p, s) <br> FLOTANTE (p) | double |
| Tipo de datos Date | OBSOLET <br> MARCA <br> TIMESTAMP (n) | datetime |
| Tipo de carácter | CHAR (n) <br> VARCHAR <br> VARCHAR2 <br> DESDE <br> CLOB <br> NCLOB | string |
| Tipo de texto de carácter Unicode | NCHAR <br> NVARCHAR | string |
| Tipo de tipodedatos RowID | PSEUDOCOLUMNA <br> UROWID | string |

Para cualquier otro tipo de datos que actualmente no se admite directamente, la columna debe convertirse explícitamente en un tipo de datos admitido.

### <a name="watermark-required"></a>Marca de agua (obligatorio)
Para evitar la sobrecarga de la base de datos, el conector procesa por lotes y reanuda las consultas de rastreo completo con una columna de marca de agua de rastreo completo. Mediante el valor de la columna marca de agua, se recopilan todos los lotes subsiguientes y la consulta se reanuda desde el último punto de control. Básicamente, se trata de un mecanismo para controlar la actualización de datos de rastreos completos.

Cree fragmentos de código de consulta para las marcas de agua como se muestra en estos ejemplos:
* `WHERE (CreatedDateTime > @watermark)`. Cite el nombre de la columna de marca de agua con la palabra clave Reserved `@watermark` . La columna de marca de agua se puede ordenar en orden ascendente.
* `ORDER BY CreatedDateTime ASC`. Ordena en orden ascendente por la columna marca de agua.

En la configuración que se muestra en la imagen siguiente, `CreatedDateTime` es la columna marca de agua seleccionada. Para recuperar el primer lote de filas, especifique el tipo de datos de la columna marca de agua. En este caso, el tipo de datos es `DateTime` .

![Configuración de columna de marca de agua](media/MSSQL-watermark.png)

La primera consulta recupera el primer **N** número de filas usando: "CreatedDateTime > 1 de enero de 1753 00:00:00" (valor mín. de tipo de datos DateTime). Una vez que se obtiene el primer lote, el valor más alto de `CreatedDateTime` devuelto en el lote se guarda como punto de control si las filas se clasifican en orden ascendente. Un ejemplo es 1 de marzo de 2019 03:00:00. A continuación, se obtiene el siguiente lote de **N** filas con "CreatedDateTime > 1 de marzo de 2019 03:00:00" en la consulta.

### <a name="skipping-soft-deleted-rows-optional"></a>Omitir filas eliminadas temporalmente (opcional)
Para excluir filas eliminadas temporalmente de la base de datos que se va a indizar, especifique el nombre y el valor de la columna de eliminación temporal que indica la fila que se va a eliminar.

![Configuración de eliminación temporal: "eliminar temporalmente la columna" y "valor de la columna eliminación temporal que indica una fila eliminada"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Rastreo completo: administrar permisos de búsqueda
Haga clic en **administrar permisos** para seleccionar las distintas columnas de control de acceso (ACL) que especifican el mecanismo de control de acceso. Seleccione el nombre de columna que especificó en la consulta SQL de rastreo completo. 

Se espera que cada una de las columnas de ACL sea una columna de varios valores. Estos valores de identificador múltiple pueden estar separados por separadores como punto y coma (;), coma (,), etc. Debe especificar este separador en el campo **separador de valores** .
 
Se admiten los siguientes tipos de identificador para usar como ACL: 
* **Nombre principal de usuario (UPN)**: un nombre principal de usuario (UPN) es el nombre de un usuario del sistema en un formato de dirección de correo electrónico. Un UPN (por ejemplo: john.doe@domain.com) consta del nombre de usuario (nombre de inicio de sesión), el separador (el símbolo @) y el nombre de dominio (sufijo UPN). 
* **Identificador de Azure Active Directory (AAD)**: en Azure ad, cada usuario o grupo tiene un identificador de objeto que tiene un aspecto similar a ' e0d3ad3d-0000-1111-2222-3c5f5c52ab9b ' 
* **Identificador de seguridad de Active Directory (ad)**: en una configuración de ad local, todos los usuarios y grupos tienen un identificador de seguridad único e inmutable que tiene un aspecto parecido a-1-5-21-3878594291-2115959936-132693609-65242.

![Configuración de permisos de búsqueda para configurar listas de control de acceso](media/MSSQL-ACL2.png)

## <a name="incremental-crawl-optional"></a>Rastreo incremental (opcional)
En este paso opcional, proporcione una consulta SQL para ejecutar un rastreo incremental de la base de datos. Con esta consulta, SQL Connector determina los cambios realizados en los datos desde el último rastreo incremental. Como en el rastreo completo, seleccione todas las columnas que desea que sean **consultables**, que se puedan **Buscar** o que se puedan **recuperar**. Especifique el mismo conjunto de columnas de ACL que especificó en la consulta de rastreo completo.

Los componentes de la imagen siguiente se parecen a los componentes de rastreo completos con una excepción. En este caso, "ModifiedDateTime" es la columna de marca de agua seleccionada. Revise los [pasos de rastreo completo](#full-crawl-required) para obtener información sobre cómo escribir la consulta de rastreo incremental y ver la siguiente imagen como ejemplo.

![Script de rastreo incremental que muestra las propiedades OrderTable, AclTable y example que se pueden usar.](media/MSSQL-incrcrawl.png)

## <a name="manage-search-permissions"></a>Administrar permisos de búsqueda 
Puede optar por usar las [ACL especificadas en la pantalla de rastreo completo](#full-crawl-manage-search-permissions) o reemplazarlas para que el contenido sea visible para todos los usuarios.

## <a name="set-the-refresh-schedule"></a>Establecer la programación de actualización
El conector SQL de Oracle admite programaciones de actualización para rastreos completos e incrementales. Le recomendamos que configure ambos.

Una programación de rastreo completo busca filas eliminadas que se han sincronizado previamente con el índice de Microsoft Search y las filas que se han sacado del filtro de sincronización. La primera vez que se conecta a la base de datos, se ejecuta un rastreo completo para sincronizar todas las filas recuperadas de la consulta de rastreo completa. Para sincronizar nuevas filas y realizar actualizaciones, debe programar rastreos incrementales.

## <a name="next-steps-customize-the-search-results-page"></a>Pasos siguientes: personalizar la página de resultados de búsqueda
Cree sus propios tipos de resultados y verticales, para que los usuarios finales puedan ver los resultados de la búsqueda de conexiones nuevas. Sin este paso, los datos de la conexión no se mostrarán en la página de resultados de búsqueda.

Para obtener más información sobre cómo crear sus verticales y MRTs, vea [Personalización](customize-search-page.md)de la página de resultados de búsqueda.

## <a name="limitations"></a>Limitaciones
El conector SQL de Oracle tiene estas limitaciones en la versión preliminar:
* La base de datos local debe ejecutar la versión 11g o posterior de la base de datos de Oracle.
* Las ACL solo se admiten con un nombre principal de usuario (UPN), Azure Active Directory (Azure AD) o seguridad de Active Directory. 
* No se admite la indización de contenido enriquecido dentro de las columnas de base de datos. Ejemplos de este tipo de contenido son HTML, JSON, XML, blobs y los analizadores de documentos que existen como vínculos dentro de las columnas de la base de datos.

## <a name="troubleshooting-guide"></a>Guía de solución de problemas
Bajo es una lista de errores comunes observados al configurar el conector y sus posibles motivos.
| Paso de configuración | Mensaje de error | Posibles motivos |
| ------------ | ------------ | ------------ |
| Configuración de la base de datos | Error del servidor de base de datos: tiempo de espera de solicitud de conexión agotado | Nombre de host no válido <br> Host no accesible |
| Configuración de la base de datos | Error del servidor de base de datos: ORA-12541: TNS: no listner | Puerto no válido |
| Configuración de la base de datos | Error del servidor de base de datos: ORA-12514: TNS: listner no conoce actualmente el servicio solicitado en el descriptor del conector | Nombre de servicio (base de datos) no válido |
| Configuración de la base de datos | Error del servidor de base de datos: error de inicio de sesión del usuario ' `user` '. | Nombre de usuario o contraseña no válidos |