---
title: Administrar el acceso a archivos y sitios
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Información general sobre cómo los administradores pueden garantizar que el acceso a los sitios y archivos esté correctamente restringido en su organización.
ms.openlocfilehash: c85cce6208743b884cce86cc11c46aab3e01254d
ms.sourcegitcommit: 70c48e470262099feb79553e36593521cc5e7abc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2021
ms.locfileid: "58835028"
---
# <a name="manage-access-to-files-and-sites"></a>Administrar el acceso a archivos y sitios

No todos los archivos o sitios deben estar disponibles para todos los usuarios de la organización. Los administradores y los usuarios pueden administrar el acceso a información confidencial o confidencial mediante soluciones que mejor abordan sus problemas específicos. Si los controles de acceso adecuados no se aplican de forma coherente, puede dar como resultado algo a lo que nos referimos como "sobresharing". Al facilitar la búsqueda de información compartida en la organización, se puede obtener acceso involuntariamente a archivos y sitios con restricciones incorrectas mediante Búsqueda de Microsoft.

Los administradores de búsqueda no pueden resolver estos problemas de sobresaharing. Los archivos y sitios sin acceso restringido se mostrarán en los resultados de búsqueda interna y a través de otras vías de detección. Sin embargo, cuando haya controles para evitar la sobresharing, se cerrarán todas las vías, incluida la búsqueda.

## <a name="solutions-to-prevent-oversharing"></a>Soluciones para evitar la sobrecoseción

Usa las herramientas, las directivas y las técnicas siguientes para restringir u ofuscar el acceso a la información para ayudar a evitar la sobresharing. La implementación de estas soluciones requerirá probablemente acceso de administrador global, de cumplimiento o de seguridad. También recomendamos una campaña interna para educar a los usuarios sobre cómo proteger correctamente, etiquetar y conceder permisos a sus sitios y archivos.

### <a name="public-sites-or-sites-with-public-owners"></a>Sitios públicos o sitios con propietarios públicos

Un modo en que los archivos se pueden compartir con todos los usuarios de la organización es a través de sitios públicos o sitios con propietarios públicos. Las etiquetas de confidencialidad pueden impedir que los usuarios creen sitios o grupos públicos. Para ello, configura todas las etiquetas para crear grupos privados y requiere una etiqueta para grupos. Para obtener más información, vea Usar etiquetas de confidencialidad para proteger el contenido en [Microsoft Teams, Microsoft 365 grupos y SharePoint sitios](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). Deberá definir un proceso independiente para que los usuarios soliciten o creen grupos públicos.

Otra opción es definir quién puede crear grupos Microsoft 365 en la organización. Para obtener más información, vea [Create a group for users who need to create Microsoft 365 groups](/microsoft-365/solutions/manage-creation-of-groups#step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups). Un administrador global tendrá que configurar un proceso para que los usuarios envíen solicitudes de creación de grupos. También le recomendamos que informe a los usuarios sobre este cambio.

Si no es posible para la organización restringir la capacidad de crear grupos, puede supervisar la actividad, incluida la creación de grupos, a través de la auditoría. Para obtener más información acerca de la auditoría básica y avanzada, vea [Auditing solutions in Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview).

### <a name="shared-files"></a>Archivos compartidos

Para restringir el acceso a todos los archivos clasificados como confidenciales para empresas, puede definir y aplicar clasificaciones de datos para su organización. Los datos de ejemplo tendrán que recopilarse para ayudar a entrenar a los nuevos clasificadores. Para obtener más información acerca de los requisitos previos y los permisos, vea [Learn about data classification](/microsoft-365/compliance/data-classification-overview).

Para restringir el acceso de archivos a los miembros de un grupo específico, como los ejecutivos, puede crear etiquetas personalizadas en el ámbito de un grupo de seguridad. A continuación, cuando un miembro del grupo de seguridad aplica la etiqueta, restringe automáticamente el acceso al grupo. Para obtener más información sobre las etiquetas personalizadas, vea [Crear](/microsoft-365/compliance/create-sensitivity-labels) y configurar etiquetas de confidencialidad y sus directivas y Restringir el acceso al contenido mediante etiquetas de confidencialidad [para aplicar cifrado.](/microsoft-365/compliance/encryption-sensitivity-labels)

Para garantizar que los documentos y los correos electrónicos estén etiquetados correctamente, los administradores también pueden establecer una directiva de etiqueta predeterminada y requerir que los usuarios los etiqueten. Para más información, consulte [Requerir que los usuarios apliquen una etiqueta al correo electrónico y a los documentos.](/microsoft-365/compliance/sensitivity-labels-office-apps#require-users-to-apply-a-label-to-their-email-and-documents)

También puede minimizar la sobresharing de archivos impidiendo que los archivos recientes aparezcan al buscar. Esto se puede hacer en un nivel de grupo o para todos los usuarios de la organización. Para impedir que los archivos recientes aparezcan para un grupo, vea [Personalización de](/graph/insights-customize-item-insights-privacy)la privacidad de información de elementos en Microsoft Graph . Un miembro del grupo podrá ver sus propios archivos recientes, pero otros recibirán un mensaje de que no se encuentran resultados. Para desactivar los archivos recientes para todos los usuarios de la organización, deberá desactivar Delve. Para obtener más información, vea [Control access to Delve](/sharepoint/delve-for-office-365-admins#control-access-to-delve).

> [!Note]
> Los usuarios aún podrán encontrar archivos compartidos con ellos en Búsqueda de Microsoft resultados. Personalizar la información de elementos o desactivar Delve solo impide que los archivos aparezcan en la lista de archivos recientes de un usuario.

### <a name="sites-and-files-between-groups"></a>Sitios y archivos entre grupos

Para restringir el uso compartido de archivos y sitios entre grupos, por ejemplo, un equipo de finanzas que administra proyectos confidenciales con un equipo de marketing, puede definir e implementar directivas de barrera de información. Estas barreras también impiden otros aspectos de la comunicación y la colaboración en Microsoft Teams, SharePoint y OneDrive. Para obtener más información, [vea Learn about information barriers in Microsoft 365](/microsoft-365/compliance/information-barriers).

## <a name="get-access-insights"></a>Obtener información de acceso

El gobierno de acceso proporciona información sobre los sitios con los documentos más confidenciales y los sitios sobrecompartidos de la organización. Para obtener información general, vea [What's new in Security and Compliance in SharePoint and OneDrive](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/what-s-new-in-security-and-compliance-in-sharepoint-and-onedrive/ba-p/1696705). Tendrás que designar a [tu organización](https://forms.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) para esta versión preliminar.
