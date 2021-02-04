---
title: Conector de Oracle SQL Graph para Microsoft Search
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
description: Configure el conector de Oracle SQL Graph para Microsoft Search.
ms.openlocfilehash: 01e4cd6b04d2997ea11ef006e94ea09b03280f41
ms.sourcegitcommit: 6a7f36769e92b714588b47efb0c185eddabe6953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099339"
---
<!---Previous ms.author:vivg --->

# <a name="oracle-sql-graph-connector"></a>Conector de Oracle SQL Graph

El conector SQL Graph de Oracle permite a su organización detectar e indizar datos de una base de datos de Oracle local. El conector indiza el contenido especificado en Microsoft Search. Para mantener el índice actualizado con los datos de origen, admite rastreos periódicos completos e incrementales. Con el conector SQL Oracle, también puede restringir el acceso a los resultados de la búsqueda para determinados usuarios.

> [!NOTE]
> Lea el [**artículo sobre el programa de instalación del conector de Graph**](configure-connector.md) para comprender el proceso de configuración general de los conectores de Graph.

Este artículo está dirigido a cualquier persona que configure, ejecute y monitore un conector de Oracle SQL Graph. Complementa el proceso de configuración general y muestra instrucciones que se aplican solo al conector de Oracle SQL Graph. En este artículo también se incluye información sobre [la solución de problemas](#troubleshooting) y las [limitaciones.](#limitations)

## <a name="before-you-get-started"></a>Antes de empezar

### <a name="install-the-graph-connector-agent"></a>Instalar el agente de conector de Graph

Para obtener acceso a los datos de terceros locales, debe instalar y configurar el agente de conector de Graph. Consulte [Instalar el agente del conector de Graph](on-prem-agent.md) para obtener más información.  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

Para conectar el conector SQL oracle a un origen de datos, debe configurar el servidor de base de datos que desea rastrear y el agente de conector de Graph local. A continuación, puede conectarse a la base de datos con el método de autenticación necesario.

Para el conector SQL Oracle, debe especificar el nombre de host, el puerto y el servicio (base de datos) junto con el método de autenticación preferido, el nombre de usuario y la contraseña.

> [!NOTE]
> La base de datos debe ejecutar la versión 11g o posterior de la base de datos de Oracle para que el conector pueda conectarse. El conector admite la base de datos de Oracle hospedada en plataformas windows, Linux y Azure VM.

Para buscar en el contenido de la base de datos, debe especificar SQL al configurar el conector. Estas SQL necesitan nombrar todas las columnas de base de datos que desea indizar (es decir, las propiedades de origen), incluidas las combinaciones de SQL que deben realizarse para obtener todas las columnas. Para restringir el acceso a los resultados de la búsqueda, debe especificar listas de control de acceso (ACL) en las SQL al configurar el conector.

## <a name="step-3a-full-crawl-required"></a>Paso 3a: Rastreo completo (obligatorio)

En este paso, configurará la consulta de SQL que ejecuta un rastreo completo de la base de datos. El rastreo completo selecciona todas las columnas o propiedades donde desea seleccionar las opciones **Query**, **Search** o **Retrieve**. También puede especificar columnas acl para restringir el acceso de los resultados de búsqueda a grupos o usuarios específicos.

> [!Tip]
> Para obtener todas las columnas que necesita, puede unir varias tablas.

![Script que muestra OrderTable y AclTable con propiedades de ejemplo](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Seleccionar columnas de datos (obligatorio) y columnas acl (opcional)

En el ejemplo se muestra la selección de cinco columnas de datos que contienen los datos de la búsqueda: OrderId, OrderTitle, OrderDesc, CreatedDateTime e IsDeleted. Para establecer permisos de vista para cada fila de datos, opcionalmente puede seleccionar estas columnas acl: AllowedUsers, AllowedGroups, DeniedUsers y DeniedGroups. Para todas estas columnas de datos, puede seleccionar las opciones **para Consultar,** **Buscar** o **Recuperar**.

Seleccione columnas de datos como se muestra en esta consulta de ejemplo: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Para administrar el acceso a los resultados de la búsqueda, puede especificar una o más columnas acl en la consulta. El SQL permite controlar el acceso por nivel de registro. Puede elegir tener el mismo control de acceso para todos los registros de una tabla. Si la información de ACL se almacena en una tabla independiente, es posible que deba realizar una combinación con dichas tablas en la consulta.

A continuación se describe el uso de cada una de las columnas acl de la consulta anterior. En la siguiente lista se explican los cuatro **mecanismos de control de acceso.**

* **AllowedUsers:** esta opción especifica la lista de id. de usuario que podrán tener acceso a los resultados de la búsqueda. En el siguiente ejemplo, la lista de usuarios: john@contoso.com, keith@contoso.com y lisa@contoso.com solo tendrían acceso a un registro con OrderId = 12.
* **AllowedGroups:** esta opción especifica el grupo de usuarios que podrán tener acceso a los resultados de la búsqueda. En el ejemplo siguiente, los grupos sales-team@contoso.com solo tendrían acceso al registro con OrderId = 12.
* **DeniedUsers:** esta opción especifica la lista de usuarios que **no tienen** acceso a los resultados de la búsqueda. En el ejemplo siguiente, los usuarios john@contoso.com y keith@contoso.com no tienen acceso al registro con OrderId = 13, mientras que todos los demás tienen acceso a este registro.
* **DeniedGroups:** esta opción especifica el grupo de usuarios que **no tienen** acceso a los resultados de la búsqueda. En el ejemplo siguiente, los grupos engg-team@contoso.com y pm-team@contoso.com no tienen acceso al registro con OrderId = 15, mientras que todos los demás tienen acceso a este registro.  

![Datos de ejemplo que muestran OrderTable y AclTable con propiedades de ejemplo](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Tipos de datos admitidos

En la tabla siguiente se resumen los tipos de datos admitidos por el conector de SQL Oracle. La tabla también resume el tipo de datos de indización para el tipo SQL datos admitido. Para obtener más información sobre los tipos de datos admitidos por los conectores de Microsoft Graph para la indización, consulte la documentación sobre los tipos de [recursos de propiedad.](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true)

| Categoría | Tipo de datos de origen | Tipo de datos de indización |
| ------------ | ------------ | ------------ |
| Tipo de datos Number | NUMBER(p,0) | int64 (para p <= 18) <br> double (para p > 18) |
| Tipo de datos número de punto flotante | NUMBER(p,s) <br> FLOAT(p) | double |
| Tipo de datos Date | DATE <br> TIMESTAMP <br> TIMESTAMP(n) | datetime |
| Tipo de datos de carácter | CHAR(n) <br> VARCHAR <br> VARCHAR2 <br> LONG <br> TAPB <br> NCLOB | cadena |
| Tipo de datos de carácter Unicode | NCHAR <br> NVARCHAR | cadena |
| Tipo de datos RowID | ROWID <br> UROWID | cadena |

Para cualquier otro tipo de datos actualmente no admitido directamente, la columna debe convertirse explícitamente en un tipo de datos admitido.

### <a name="watermark-required"></a>Marca de agua (obligatorio)

Para evitar la sobrecarga de la base de datos, el conector por lotes y reanuda las consultas de rastreo completo con una columna de marca de agua de rastreo completo. Mediante el uso del valor de la columna de marca de agua, se captura cada lote posterior y se reanudan las consultas desde el último punto de control. Básicamente, este es un mecanismo para controlar la actualización de datos para rastreos completos.

Cree fragmentos de código de consulta para marcas de agua, como se muestra en estos ejemplos:

* `WHERE (CreatedDateTime > @watermark)`. Cite el nombre de la columna de marca de agua con la palabra clave reservada `@watermark` . Solo puede ordenar la columna de marca de agua en orden ascendente.
* `ORDER BY CreatedDateTime ASC`. Ordenar en la columna de marca de agua en orden ascendente.

En la configuración que se muestra en la siguiente imagen, `CreatedDateTime` se encuentra la columna de marca de agua seleccionada. Para capturar el primer lote de filas, especifique el tipo de datos de la columna de marca de agua. En este caso, el tipo de datos es `DateTime` .

![Configuración de columna de marca de agua](media/MSSQL-watermark.png)

La primera consulta recupera el primer **número N** de filas mediante: "CreatedDateTime > January 1, 1753 00:00:00" (valor mínimo del tipo de datos DateTime). Después de capturar el primer lote, el valor más alto devuelto en el lote se guarda como punto de control si las filas se ordenan `CreatedDateTime` en orden ascendente. Un ejemplo es el 1 de marzo de 2019 a las 03:00:00. A continuación, se recupera el siguiente lote de **N** filas mediante "CreatedDateTime > march 1, 2019 03:00:00" en la consulta.

### <a name="skipping-soft-deleted-rows-optional"></a>Omitir filas eliminadas temporalmente (opcional)

Para excluir las filas eliminadas temporalmente de la base de datos para que no se indicen, especifique el nombre y el valor de la columna de eliminación temporal que indica que la fila se ha eliminado.

![Configuración de eliminación temporal: "Columna de eliminación temporal" y "Valor de la columna de eliminación temporal que indica una fila eliminada"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Rastreo completo: administrar permisos de búsqueda

Seleccione Administrar permisos para elegir las **distintas** columnas de control de acceso (ACL) que especifican el mecanismo de control de acceso. Seleccione el nombre de columna que especificó en la consulta de rastreo SQL completa.

Se espera que cada una de las columnas acl sea una columna de varios valores. Estos valores de id. múltiples se pueden separar mediante separadores como punto y coma (;), coma (,), y así sucesivamente. Debe especificar este separador en el campo **separador de** valores.

Se admiten los siguientes tipos de id. para usarlos como ACL:

* **Nombre principal de usuario (UPN):** un nombre principal de usuario (UPN) es el nombre de un usuario del sistema en un formato de dirección de correo electrónico. Un UPN (por ejemplo: john.doe@domain.com) consta del nombre de usuario (nombre de inicio de sesión), el separador (el símbolo @) y el nombre de dominio (sufijo UPN).
* **Identificador de Azure Active Directory (AAD):** en Azure AD, cada usuario o grupo tiene un identificador de objeto similar a 'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b'
* Identificador de seguridad de **Active Directory (AD):** en una configuración local de AD, cada usuario y grupo tiene un identificador de seguridad único inmutable que tiene un aspecto similar a "S-1-5-21-3878594291-2115959936-132693609-65242".

![Opciones de permisos de búsqueda para configurar listas de control de acceso](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Paso 3b: Rastreo incremental (opcional)

En este paso opcional, proporcione una consulta SQL para ejecutar un rastreo incremental de la base de datos. Con esta consulta, el conector SQL determina los cambios realizados en los datos desde el último rastreo incremental. Al igual que en el rastreo completo, seleccione entre las opciones **Consulta,** **Búsqueda** o **Recuperar**. Especifique el mismo conjunto de columnas acl que especificó en la consulta de rastreo completo.

Los componentes de la siguiente imagen son similares a los componentes de rastreo completo con una excepción. En este caso, "ModifiedDateTime" es la columna de marca de agua seleccionada. Revise los [pasos de rastreo completos](#step-3a-full-crawl-required) para obtener información sobre cómo escribir la consulta de rastreo incremental y vea la siguiente imagen como ejemplo.

![Script de rastreo incremental que muestra OrderTable, AclTable y propiedades de ejemplo que se pueden usar.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Paso 4: Asignar etiquetas de propiedad

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-5-manage-schema"></a>Paso 5: Administrar esquema

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-search-permissions"></a>Paso 6: Administrar permisos de búsqueda

Puede elegir usar las [ACL](#full-crawl-manage-search-permissions) especificadas en la pantalla de rastreo completo o puede invalidarlas para que el contenido sea visible para todos los usuarios.

## <a name="step-7-choose-refresh-settings"></a>Paso 7: Elegir la configuración de actualización

El conector de SQL Oracle admite programaciones de actualización para rastreos completos e incrementales. Se recomienda establecer ambos.

Una programación de rastreo completo encuentra las filas eliminadas que se sincronizaron previamente con el índice de Microsoft Search y las filas que se movieron fuera del filtro de sincronización. Cuando se conecta por primera vez a la base de datos, se ejecuta un rastreo completo para sincronizar todas las filas recuperadas de la consulta de rastreo completo. Para sincronizar nuevas filas y realizar actualizaciones, debe programar rastreos incrementales.

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="next-steps-customize-the-search-results-page"></a>Pasos siguientes: Personalizar la página de resultados de búsqueda

Cree sus propios tipos de resultados y verticales, para que los usuarios finales puedan ver los resultados de la búsqueda desde nuevas conexiones. Sin este paso, los datos de la conexión no se mostrarán en la página de resultados de búsqueda.

Para obtener más información acerca de cómo crear verticales y MRT, vea Personalización de la página de [resultados de búsqueda.](customize-search-page.md)

## <a name="troubleshooting"></a>Solución de problemas

Debajo hay una lista de errores comunes observados al configurar el conector y sus posibles motivos.

| Paso de configuración | Mensaje de error | Posibles motivos |
| ------------ | ------------ | ------------ |
| Configuración de la base de datos | Error del servidor de bases de datos: Se ha producido un tiempo de espera de la solicitud de conexión | Nombre de host no válido <br> Host inaccesible |
| Configuración de la base de datos | Error del servidor de bases de datos: ORA-12541: TNS: sin escucha | Puerto no válido |
| Configuración de la base de datos | Error del servidor de base de datos: ORA-12514: TNS: la escucha no conoce actualmente el servicio solicitado en el descriptor del conector | Nombre de servicio (base de datos) no válido |
| Configuración de la base de datos | Error del servidor de bases de datos: Error de inicio de sesión para el usuario ' `user` '. | Nombre de usuario o contraseña no válidos |

## <a name="limitations"></a>Limitaciones

El conector SQL Oracle tiene estas limitaciones en la versión preliminar:

* La base de datos local debe ejecutar Oracle Database versión 11g o posterior.
* Las ACL solo se admiten con un nombre principal de usuario (UPN), Azure Active Directory (Azure AD) o Seguridad de Active Directory.
* No se admite la indización de contenido enriquecido dentro de las columnas de base de datos. Algunos ejemplos de este contenido son HTML, JSON, XML, blobs y análisis de documentos que existen como vínculos dentro de las columnas de base de datos.
