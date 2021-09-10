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
ms.openlocfilehash: c19442e1d89ddfe65a772213a8b0225ca680d699
ms.sourcegitcommit: 3e069fd920b5fcdfe97a0261930447e9e87d9013
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973842"
---
# <a name="manage-access-to-files-and-sites"></a>Administrar el acceso a archivos y sitios

No todos los archivos o sitios deben estar disponibles para todos los usuarios de la organización. Los administradores y los usuarios pueden administrar el acceso a información confidencial o confidencial mediante soluciones que mejor abordan sus problemas específicos. Si los controles de acceso adecuados no se aplican de forma coherente, puede dar como resultado algo a lo que nos referimos como "sobresharing". Al facilitar la búsqueda de información compartida en la organización, se puede acceder a los archivos y sitios con restricciones incorrectas de forma involuntaria mediante Búsqueda de Microsoft.

Los administradores de búsqueda no pueden resolver estos problemas de sobresaharing. Los archivos y sitios sin acceso restringido se mostrarán en los resultados de búsqueda interna y a través de otras vías de detección. Sin embargo, cuando haya controles para evitar la sobresharing, se cerrarán todas las vías, incluida la búsqueda.

## <a name="solutions-to-prevent-oversharing"></a>Soluciones para evitar la sobrecoseción

Use las herramientas, las directivas y las técnicas siguientes para restringir u ofuscar el acceso a la información para ayudar a evitar la sobresharing. Es probable que la implementación de estas soluciones requiera acceso de administrador global, de cumplimiento o de seguridad. También recomendamos una campaña interna para educar a los usuarios sobre cómo proteger correctamente, etiquetar y conceder permisos a sus sitios y archivos.

### <a name="public-sites-or-sites-with-public-groups-as-owners"></a>Sitios públicos o sitios con grupos públicos como propietarios

Un modo en que los archivos se pueden compartir con todos los usuarios es a través de sitios públicos o sitios con grupos públicos como propietarios. Las etiquetas de confidencialidad pueden impedir que los usuarios creen sitios o grupos públicos. Para obtener más información acerca de cómo configurar todas las etiquetas para crear grupos o sitios privados y cómo crear una etiqueta para grupos o sitios, vea Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios [SharePoint.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Otra opción es controlar quién puede crear grupos Microsoft 365 en la organización. Para obtener más información, vea [Create a group for users who need to create Microsoft 365 Groups](/microsoft-365/solutions/manage-creation-of-groups#step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups).

Al implementar cualquiera de estas soluciones, también le recomendamos que configure un proceso para que los usuarios soliciten la creación de grupos públicos e informen a los usuarios sobre el cambio.

Si no es posible restringir la capacidad de crear grupos para su organización, puede supervisar las actividades, incluida la creación de grupos, a través de la auditoría. Para obtener más información acerca de la auditoría básica y avanzada, vea [Auditing solutions in Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview).

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
