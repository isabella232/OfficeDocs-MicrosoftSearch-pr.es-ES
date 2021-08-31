---
title: Conector SQL Graph oracle para Búsqueda de Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configure el conector de SQL Graph oracle para Búsqueda de Microsoft.
ms.openlocfilehash: 1fe45fa6f92b16290148ef72282418c41942a3c7
ms.sourcegitcommit: e5d56d6ce1cd285c5af3e0472ce169cb34883017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "58470018"
---
<!---Previous ms.author:vivg --->

# <a name="oracle-sql-graph-connector"></a>Conector de SQL Graph Oracle

El conector de SQL Graph oracle permite a su organización detectar e indizar datos de una base de datos de Oracle local. El conector indiza el contenido especificado en Búsqueda de Microsoft. Para mantener el índice actualizado con los datos de origen, admite rastreos incrementales e completos periódicos. Con el conector de SQL Oracle, también puede restringir el acceso a los resultados de búsqueda para determinados usuarios.

> [!NOTE]
> Lea el [**artículo Setup for your Graph connector para**](configure-connector.md) comprender las instrucciones generales Graph de configuración de conectores.

Este artículo está para cualquier persona que configure, ejecute y monitore un conector de SQL Graph Oracle. Complementa el proceso de configuración general y muestra instrucciones que solo se aplican al conector SQL Graph Oracle. En este artículo también se incluye información sobre [solución de problemas](#troubleshooting) y [limitaciones.](#limitations)

## <a name="before-you-get-started"></a>Antes de empezar

### <a name="install-the-graph-connector-agent"></a>Instalar el agente Graph conector de conexión

Para tener acceso a los datos de terceros locales, debe instalar y configurar el agente de conector Graph local. Consulte [Install the Graph connector agent para](graph-connector-agent.md) obtener más información.  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

Para conectar el conector SQL oracle a un origen de datos, debe configurar el servidor de base de datos que desea rastrear y el agente de conector Graph local. A continuación, puede conectarse a la base de datos con el método de autenticación necesario.

Para oracle SQL, debe especificar el nombre de nombre de host, puerto y servicio (base de datos) junto con el método de autenticación preferido, el nombre de usuario y la contraseña.

> [!NOTE]
> La base de datos debe ejecutar oracle database version 11g o posterior para que el conector pueda conectarse. El conector es compatible con la base de datos de Oracle hospedada Windows plataformas de vm de Linux y Azure.

Para buscar en el contenido de la base de datos, debe especificar SQL al configurar el conector. Estas SQL necesitan nombrar todas las columnas de base de datos que desea indizar (es decir, las propiedades de origen), incluidas las combinaciones de SQL que deben realizarse para obtener todas las columnas. Para restringir el acceso a los resultados de búsqueda, debe especificar listas de control de acceso (ACL) dentro de SQL consultas al configurar el conector.

## <a name="step-3a-full-crawl-required"></a>Paso 3a: Rastreo completo (obligatorio)

En este paso, se configura la consulta SQL que ejecuta un rastreo completo de la base de datos. El rastreo completo selecciona todas las columnas o propiedades donde desea seleccionar las opciones **Query**, **Search** o **Retrieve**. También puede especificar columnas de ACL para restringir el acceso de los resultados de búsqueda a usuarios o grupos específicos.

> [!Tip]
> Para obtener todas las columnas que necesita, puede unir varias tablas.

![Script que muestra OrderTable y AclTable con propiedades de ejemplo.](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Seleccionar columnas de datos (obligatorio) y columnas acl (opcional)

En el ejemplo se muestra la selección de cinco columnas de datos que contienen los datos de la búsqueda: OrderId, OrderTitle, OrderDesc, CreatedDateTime e IsDeleted. Para establecer permisos de vista para cada fila de datos, puede seleccionar opcionalmente estas columnas de ACL: AllowedUsers, AllowedGroups, DeniedUsers y DeniedGroups. Para todas estas columnas de datos, puede seleccionar las opciones **consulta**, **buscar** o **recuperar**.

Seleccione columnas de datos como se muestra en esta consulta de ejemplo: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Para administrar el acceso a los resultados de búsqueda, puede especificar una o más columnas de ACL en la consulta. El SQL permite controlar el acceso por nivel de registro. Puede elegir tener el mismo control de acceso para todos los registros de una tabla. Si la información de acl se almacena en una tabla independiente, es posible que deba hacer una combinación con dichas tablas en la consulta.

A continuación se describe el uso de cada una de las columnas acl de la consulta anterior. En la siguiente lista se explican los cuatro mecanismos **de control de acceso**.

* **AllowedUsers:** esta opción especifica la lista de id. de usuario que podrán tener acceso a los resultados de la búsqueda. En el siguiente ejemplo, lista de usuarios: john@contoso.com, keith@contoso.com y lisa@contoso.com solo tendrían acceso a un registro con OrderId = 12.
* **AllowedGroups:** esta opción especifica el grupo de usuarios que podrán acceder a los resultados de la búsqueda. En el ejemplo siguiente, los grupos sales-team@contoso.com solo tendrían acceso al registro con OrderId = 12.
* **DeniedUsers:** esta opción especifica la lista de usuarios que no **tienen** acceso a los resultados de búsqueda. En el siguiente ejemplo, los usuarios john@contoso.com y keith@contoso.com no tienen acceso al registro con OrderId = 13, mientras que todos los demás tienen acceso a este registro.
* **DeniedGroups:** esta opción especifica el grupo de usuarios que no tienen **acceso** a los resultados de búsqueda. En el siguiente ejemplo, los grupos engg-team@contoso.com y pm-team@contoso.com no tienen acceso al registro con OrderId = 15, mientras que todos los demás tienen acceso a este registro.  

![Datos de ejemplo que muestran OrderTable y AclTable con propiedades de ejemplo.](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Tipos de datos admitidos

En la tabla siguiente se resumen los tipos de datos admitidos por el conector de SQL Oracle. La tabla también resume el tipo de datos de indización para el tipo SQL datos admitido. Para obtener más información acerca de los Graph de microsoft compatibles con tipos de datos para la indización, consulte la documentación sobre tipos [de recursos de propiedad](/graph/api/resources/property?preserve-view=true&view=graph-rest-beta#properties).

| Categoría | Tipo de datos de origen | Tipo de datos de indización |
| ------------ | ------------ | ------------ |
| Tipo de datos Number | NUMBER(p,0) | int64 (para p <= 18) <br> double (para p > 18) |
| Tipo de datos de número de punto flotante | NUMBER(p,s) <br> FLOAT(p) | double |
| Tipo de datos Date | DATE <br> TIMESTAMP <br> TIMESTAMP(n) | datetime |
| Tipo de datos de carácter | CHAR(n) <br> VARCHAR <br> VARCHAR2 <br> LONG <br> CLOB <br> NCLOB | string |
| Tipo de datos de caracteres Unicode | NCHAR <br> NVARCHAR | string |
| Tipo de datos RowID | ROWID <br> UROWID | string |

Para cualquier otro tipo de datos actualmente no compatible directamente, la columna debe convertirse explícitamente en un tipo de datos admitido.

### <a name="watermark-required"></a>Marca de agua (obligatorio)

Para evitar sobrecargar la base de datos, el conector por lotes y reanuda las consultas de rastreo completo con una columna de marca de agua de rastreo completo. Al usar el valor de la columna de marca de agua, se captura cada lote posterior y se reanuda la consulta desde el último punto de control. Básicamente, este es un mecanismo para controlar la actualización de datos para rastreos completos.

Cree fragmentos de código de consulta para marcas de agua como se muestra en estos ejemplos:

* `WHERE (CreatedDateTime > @watermark)`. Cite el nombre de la columna de marca de agua con la palabra clave reservada `@watermark` . Solo puede ordenar la columna de marca de agua en orden ascendente.
* `ORDER BY CreatedDateTime ASC`. Ordene en la columna de marca de agua en orden ascendente.

En la configuración que se muestra en la siguiente imagen, `CreatedDateTime` se encuentra la columna de marca de agua seleccionada. Para capturar el primer lote de filas, especifique el tipo de datos de la columna de marca de agua. En este caso, el tipo de datos es `DateTime` .

![Configuración de columna de marca de agua.](media/MSSQL-watermark.png)

La primera consulta captura el primer **número N** de filas mediante: "CreatedDateTime > 1 de enero de 1753 00:00:00" (valor mínimo del tipo de datos DateTime). Después de capturar el primer lote, el valor más alto de devuelto en el lote se guarda como punto de control si las filas se ordenan `CreatedDateTime` en orden ascendente. Un ejemplo es el 1 de marzo de 2019 03:00:00. A continuación, se captura el siguiente lote de filas **N** mediante "CreatedDateTime > March 1, 2019 03:00:00" en la consulta.

### <a name="skipping-soft-deleted-rows-optional"></a>Omitir filas eliminadas temporalmente (opcional)

Para excluir las filas eliminadas temporalmente en la base de datos para que no se indexe, especifique el nombre y el valor de la columna de eliminación temporal que indica que la fila se ha eliminado.

![Configuración de eliminación temporal: "Columna de eliminación temporal" y "Valor de la columna de eliminación temporal que indica una fila eliminada".](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Rastreo completo: administrar permisos de búsqueda

Seleccione Administrar permisos para elegir las **distintas** columnas de control de acceso (ACL) que especifican el mecanismo de control de acceso. Seleccione el nombre de columna que especificó en la consulta completa SQL rastreo.

Se espera que cada una de las columnas acl sea una columna de varios valores. Estos valores de identificador múltiples se pueden separar mediante separadores como punto y coma (;), coma (,), y así sucesivamente. Debe especificar este separador en el campo **separador de** valores.

Se admiten los siguientes tipos de id. para usar como ACL:

* **Nombre principal de usuario (UPN):** un nombre principal de usuario (UPN) es el nombre de un usuario del sistema en un formato de dirección de correo electrónico. Un UPN (por ejemplo: john.doe@domain.com) consta del nombre de usuario (nombre de inicio de sesión), separador (símbolo @) y nombre de dominio (sufijo UPN).
* **Azure Active Directory (AAD):** en Azure AD, cada usuario o grupo tiene un identificador de objeto similar a 'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b'
* Id. de seguridad de **Active Directory (AD):** en una configuración de AD local, todos los usuarios y grupos tienen un identificador de seguridad único inmutable que tiene un aspecto similar a 'S-1-5-21-3878594291-2115959936-132693609-65242.'

![Configuración de permisos de búsqueda para configurar listas de control de acceso.](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Paso 3b: Rastreo incremental (opcional)

En este paso opcional, proporcione una consulta SQL para ejecutar un rastreo incremental de la base de datos. Con esta consulta, el conector SQL determina los cambios realizados en los datos desde el último rastreo incremental. Al igual que en el rastreo completo, seleccione entre las opciones **Query**, **Search** o **Retrieve**. Especifique el mismo conjunto de columnas acl que especificó en la consulta de rastreo completa.

Los componentes de la siguiente imagen son similares a los componentes de rastreo completos con una excepción. En este caso, "ModifiedDateTime" es la columna de marca de agua seleccionada. Revise los [pasos de rastreo completos](#step-3a-full-crawl-required) para obtener información sobre cómo escribir la consulta de rastreo incremental y vea la siguiente imagen como un ejemplo.

![Script de rastreo incremental que muestra las propiedades OrderTable, AclTable y example que se pueden usar.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Paso 4: Asignar etiquetas de propiedades

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-5-manage-schema"></a>Paso 5: Administrar esquema

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-search-permissions"></a>Paso 6: Administrar permisos de búsqueda

Puede elegir usar las [ACL](#full-crawl-manage-search-permissions) especificadas en la pantalla de rastreo completa o puede invalidarlas para que el contenido sea visible para todos.

## <a name="step-7-choose-refresh-settings"></a>Paso 7: Elegir la configuración de actualización

El conector de SQL oracle admite programaciones de actualización para rastreos completos e incrementales. Se recomienda establecer ambos.

Una programación de rastreo completa busca filas eliminadas que se sincronizaron previamente con el índice de Búsqueda de Microsoft y las filas que se movieron fuera del filtro de sincronización. Cuando se conecta por primera vez a la base de datos, se ejecuta un rastreo completo para sincronizar todas las filas recuperadas de la consulta de rastreo completa. Para sincronizar nuevas filas y realizar actualizaciones, debe programar rastreos incrementales.

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!--- ## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md). -->

## <a name="troubleshooting"></a>Solución de problemas

Debajo hay una lista de errores comunes observados al configurar el conector y sus posibles razones.

| Paso de configuración | Mensaje de error | Posibles motivos |
| ------------ | ------------ | ------------ |
| Configuración de la base de datos | Error del servidor de base de datos: se ha producido el tiempo de espera de la solicitud de conexión | Nombre de host no válido <br> Host no accesible |
| Configuración de la base de datos | Error del servidor de base de datos: ORA-12541: TNS: Sin escucha | Puerto no válido |
| Configuración de la base de datos | Error del servidor de base de datos: ORA-12514: TNS: el agente de escucha no conoce actualmente el servicio solicitado en el descriptor del conector | Nombre de servicio (base de datos) no válido |
| Configuración de la base de datos | Error del servidor de base de datos: Error de inicio de sesión para el usuario ' `user` '. | Nombre de usuario o contraseña no válidos |

## <a name="limitations"></a>Limitaciones

El conector SQL oracle tiene estas limitaciones en la versión preliminar:

* La base de datos local debe ejecutar Oracle Database versión 11g o posterior.
* Las ACL solo se admiten mediante un nombre principal de usuario (UPN), Azure Active Directory (Azure AD) o seguridad de Active Directory.
* No se admite la indización de contenido enriquecido dentro de las columnas de base de datos. Ejemplos de este contenido son HTML, JSON, XML, blobs y análisis de documentos que existen como vínculos dentro de las columnas de la base de datos.