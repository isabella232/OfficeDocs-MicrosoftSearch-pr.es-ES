---
title: Asignación de identidades que no son de AAD
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Pasos sobre cómo asignar identidades que no sean AAD
ms.openlocfilehash: cd7d0eb17678d69ec1966e4472b38c1f18c30809
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367662"
---
# <a name="map-your-non-azure-ad-identities"></a>Asignar las identidades que no son de Azure AD  

Este artículo le guiará por los pasos necesarios para asignar sus identidades que no son de Azure AD a sus identidades de Azure AD, de modo que los usuarios de la lista de control de acceso (ACL) con identidades que no son de Azure AD puedan ver los resultados de la búsqueda del conector en su ámbito.

Estos pasos solo son relevantes para los administradores de búsqueda que configuran los conectores de [ServiceNow](servicenow-connector.md) o [Salesforce](salesforce-connector.md) por Microsoft con los permisos de búsqueda de "solo personas con acceso a este origen de datos" y el tipo de identidad "no es AAD".

>[!NOTE]
>Si está configurando un conector de Salesforce y **solo selecciona personas con acceso a este origen de datos y el** tipo de identidad **AAD** en la pantalla de permisos de búsqueda, consulte el artículo [map Your Identities de Azure ad](map-aad.md) para conocer los pasos sobre cómo asignar identidades de Azure ad.  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a>Pasos para asignar las propiedades que no son de Azure AD

### <a name="1-select-an-azure-ad-user-property"></a>1. seleccionar una propiedad de usuario de Azure AD  

Puede seleccionar la propiedad de usuario de Azure AD para la que está creando la asignación. Esta es la propiedad de destino de la que pretende asignar las identidades que no son de Azure AD.  

Puede seleccionar una de las siguientes propiedades de Azure AD:

| Propiedad de Azure AD    | Definición           | Ejemplo         |
| :------------------- | :------------------- |:--------------- |
| Nombre principal de usuario (UPN)  | Un UPN consta de un prefijo UPN (el nombre de la cuenta de usuario) y un sufijo UPN (un nombre de dominio DNS). El prefijo se une con el sufijo mediante el símbolo "@". | us1@contoso.onmicrosoft.com |
| IDENTIFICADOR de Azure AD                 | Un identificador de Azure AD para un usuario determinado es el único GUID del usuario.                 | 58006c96-9e6e-45ea-8c88-4a56851eefad            |
| IDENTIFICADOR de seguridad (SID) de Active Directory                  | El SID (identificador de seguridad) es un identificador único que Active Directory usa para identificar objetos como entidad de seguridad.                  | S-1-5-21-453406510-812318184-4183662089             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a>2. Seleccione las propiedades de usuario que no son de Azure AD para asignar

Puede seleccionar las propiedades que no son de Azure AD extraídas del origen de datos para aplicar expresiones regulares. Para obtener más información sobre dónde encontrar estas propiedades en su origen de datos, consulte las páginas de [ServiceNow](servicenow-connector.md) y [Salesforce](salesforce-connector.md) .  

Puede seleccionar una propiedad de usuario que no sea de Azure AD en la lista desplegable y proporcionar una expresión regular que se aplicará a esos valores de propiedad de usuario. Para obtener más información acerca de las expresiones regulares, consulte [referencia de expresiones regulares]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).  

A continuación se muestran algunos ejemplos de expresiones regulares y sus salidas que se aplican a una cadena de muestra: 

| Cadena de muestra                  | Expresión regular                 | Resultado de la expresión regular de la cadena de muestra           |
| :------------------- | :------------------- |:---------------|
| Alexis Vasquez  | .* | Alexis Vasquez |
| Alexis Vasquez                 | ..$                 | Easy            |
| Alexis Vasquez                  | (\w +) $                  | Vasquez             |

Puede Agregar tantas propiedades de usuario que no sean de Azure AD como quiera que sean expresiones. Puede aplicar diferentes expresiones regulares a la misma propiedad de usuario si la fórmula final garantiza que.  

### <a name="3-create-formula-to-complete-mapping"></a>3. crear una fórmula para completar la asignación

Puede combinar los resultados de las expresiones regulares aplicadas a cada una de las propiedades de usuario que no sean de Azure AD para formar la propiedad de Azure AD seleccionada en el paso 1.

En el cuadro de fórmula, " {0} " corresponde a la salida de la expresión regular aplicada a la *primera* propiedad que no es de Azure ad que seleccionó. " {1} " corresponde a la salida de la expresión regular aplicada a la *segunda* propiedad que no es de Azure ad que haya seleccionado. " {2} " corresponde a la salida de la expresión regular aplicada a la *tercera* propiedad que no es de Azure ad, y así sucesivamente.  

A continuación se muestran algunos ejemplos de fórmulas con salidas de expresión regular de ejemplo y resultados de fórmulas: 

| Fórmula de ejemplo                  | Valor de {0} en usuario de ejemplo                 | Valor de {1} en usuario de ejemplo           | Resultado de la fórmula                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso. com  | Name | Apellido |firstname.lastname@contoso.com
| {0}@domain. com                 | identificado                 |             |userid@domain.com

Después de proporcionar la fórmula, puede hacer clic opcionalmente en **vista previa** para ver una vista previa de 5 usuarios aleatorios del origen de datos con sus correspondientes asignaciones de usuario aplicadas. El resultado de la vista previa incluye el valor de las propiedades de usuario que no son de Azure AD seleccionadas en el paso 2 para esos usuarios y el resultado de la fórmula final que se proporciona en el paso 3 para ese usuario. También indica si los resultados de la fórmula podrían resolverse en un usuario de Azure AD del espacio empresarial a través de un icono de "éxito" o "error".  

>[!NOTE]
>Todavía puede continuar con la creación de la conexión si una o más asignaciones de usuario tienen el estado "error" después de hacer clic en **vista previa**. La vista previa muestra 5 usuarios aleatorios y sus asignaciones desde el origen de datos. Si la asignación que proporciona no asigna todos los usuarios, es posible que experimente este caso.

## <a name="sample-non-azure-ad-mapping"></a>Ejemplo de asignación que no es de Azure AD

Vea la siguiente instantánea para obtener una muestra de asignación que no es de Azure AD.

![Instantánea de ejemplo de cómo rellenar la página de asignación que no es de Azure AD](media/non-aad-mapping.png)

## <a name="limitations"></a>Limitaciones  

- Solo se admite una asignación para todos los usuarios. No se admiten las asignaciones condicionales.  

- No puede cambiar la asignación una vez publicada la conexión.  

- Actualmente solo se admiten expresiones de Regex basadas en las propiedades de usuario no AAD para la transformación.

- Solo hay 3 identidades de Azure AD a las que puede elegir asignar (UPN, identificador de Azure AD y SID de AD).