---
title: Asignación de identidades de AAD
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Pasos sobre cómo asignar identidades de AAD
ms.openlocfilehash: d0292d77b3a0936ed60682b8388de1bb82ac43bb
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701971"
---
# <a name="map-your-azure-ad-identities"></a>Asignar las identidades de Azure AD   

En este artículo se le guían los pasos para asignar las identidades de Azure AD a un identificador único para el origen de datos (identidad que no es de Azure AD) para que los usuarios de la lista de control de acceso (ACL) con identidades que no son de Azure AD puedan ver los resultados de búsqueda del conector a su alcance.

Estos pasos solo son relevantes para los administradores de búsqueda que están configurando un conector de [Salesforce](salesforce-connector.md) por Microsoft con permisos de búsqueda para "Solo las personas con acceso a este origen de datos" y el tipo de identidad "AAD". Los siguientes pasos le guían a través de cómo asignar las propiedades de usuario de Azure AD a los id. **de federación de los usuarios.**

>[!NOTE]
>Si va a configurar un  conector de [Salesforce](salesforce-connector.md) y selecciona Solo las personas con acceso a este origen de datos y el tipo de identidad que no son **AAD** en la pantalla de permisos de búsqueda, consulte el artículo Asignar identidades que no son de Azure AD para obtener pasos sobre cómo asignar identidades que no son de Azure [AD.](map-non-aad.md)  

## <a name="steps-for-mapping-your-azure-ad-properties"></a>Pasos para asignar las propiedades de Azure AD

### <a name="1-select-azure-ad-user-properties-to-map"></a>1. Seleccione Propiedades de usuario de Azure AD para asignar

Puede seleccionar las propiedades de Azure AD que necesita asignar al identificador de federación.

Puede seleccionar una propiedad de usuario de Azure AD en el desplegable. También puede agregar tantas propiedades de usuario de Azure AD como quiera si estas propiedades son necesarias para crear la asignación de id. de federación para su organización.

### <a name="2-create-formula-to-complete-mapping"></a>2. Crear fórmula para completar la asignación

Puede combinar los valores de las propiedades de usuario de Azure AD para formar el identificador de federación único.

En el cuadro de fórmula, " {0} " corresponde a la primera *propiedad* de Azure AD seleccionada. " {1} " corresponde a la segunda *propiedad* de Azure AD seleccionada. " {2} " corresponde a la tercera *propiedad* de Azure AD, y así sucesivamente.  

A continuación se muestran algunos ejemplos de fórmulas con salidas de expresión regular de ejemplo y salidas de fórmula:

| Fórmula de ejemplo                  | Valor de la {0} propiedad para un usuario de ejemplo                 | Valor de la {1} propiedad para un usuario de ejemplo           | Salida de fórmula                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso.com  | firstname | lastname |firstname.lastname@contoso.com
| {0}@domain.com                 | userid                 |             |userid@domain.com

Después de proporcionar la fórmula,  opcionalmente puede hacer clic en Vista previa para ver una vista previa de 5 usuarios aleatorios de su origen de datos con sus respectivas asignaciones de usuario aplicadas. El resultado de la vista previa incluye el valor de las propiedades de usuario de Azure AD seleccionadas en el paso 1 para esos usuarios y el resultado de la fórmula final proporcionada en el paso 2 para ese usuario. También indica si el resultado de la fórmula podría resolverse para un usuario de Azure AD en el inquilino a través de un icono "Correcto" o "Error".  

>[!NOTE]
>Todavía puede continuar con la creación de la conexión si una o varias asignaciones de usuario tienen un estado "Error" después de hacer clic en **Vista previa**. La vista previa muestra 5 usuarios aleatorios y sus asignaciones desde el origen de datos. Si la asignación que proporciona no asigna a todos los usuarios, puede que experimente este caso.

## <a name="sample-azure-ad-mapping"></a>Asignación de Azure AD de ejemplo

Vea la instantánea siguiente para obtener una asignación de Azure AD de ejemplo.

![Instantánea de ejemplo de cómo rellenar la página de asignación de Azure AD.](media/aad-mapping.png)

## <a name="limitations"></a>Limitaciones  

- Solo se admite una asignación para todos los usuarios. No se admiten asignaciones condicionales.  

- No puede cambiar la asignación una vez publicada la conexión.  

- Las expresiones basadas en Regex en las propiedades de usuario de Azure AD no se admiten para la transformación de Id. de Azure AD a Federación.