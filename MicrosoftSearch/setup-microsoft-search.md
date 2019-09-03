---
title: Configurar Búsqueda de Microsoft
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 08/06/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar Búsqueda de Microsoft por primera vez.
ms.openlocfilehash: 7c80701e83fea7b9b93e4e01f98fd1eeedbfa749
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639509"
---
# <a name="set-up-microsoft-search"></a>Configurar Búsqueda de Microsoft

Búsqueda de Microsoft ofrece una interfaz intuitiva para ayudar a los usuarios a encontrar información como archivos y documentos, sitios internos y herramientas empresariales, personas y grupos, ubicaciones y direcciones, conversaciones y respuestas mediante un acceso seguro a todas las fuentes de datos, incluidos correos electrónicos, archivos, archivos de SharePoint, contenidos de OneDrive y otros recursos compartidos, así como de internet en la organización del usuario.

Para obtener más información sobre las características de la Búsqueda de Microsoft, vea [Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).

## <a name="get-started"></a>Introducción

La Búsqueda de Microsoft está activada de forma predeterminada para todas las aplicaciones de Microsoft compatibles, como parte de Microsoft 365. Todo lo que un usuario debe hacer es iniciar sesión con una cuenta profesional o educativa y usar un explorador con Bing como proveedor de búsquedas predeterminado.

Puede administrar la Búsqueda de Microsoft desde el Centro de administración de Microsoft 365.

1. En el Centro de administración de Microsoft 365 vaya a **Configuración** > **Microsoft**.

**Nota:** si NO ve la Búsqueda de Microsoft en **Configuración**, active el interruptor **Probar la versión preliminar** en la esquina superior derecha de cualquier página del centro de administración.

Como administrador debe considerar algunos aspectos que pueden hacer que la experiencia de Búsqueda de Microsoft en su organización sea eficiente e intuitiva.

## <a name="step-1-check-access-level-of-your-users"></a>Paso 1: Comprobar el nivel de acceso de los usuarios

La Búsqueda de Microsoft respeta la configuración de seguridad del origen de contenido. Lo que los usuarios ven en los resultados de búsqueda depende de sus permisos y niveles de acceso. Revise el nivel de acceso de los usuarios de su organización para asegurarse de que los usuarios solo encuentran el contenido al que tienen permiso para acceder.

| Servicio         | Descripción                                                                                                                                                                                                                                         |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Grupos          | [Agregar o quitar a miembros de grupos](https://docs.microsoft.com/office365/admin/create-groups/add-or-remove-members-from-groups)                                                                                                                     |
| Contactos          | Puede ocultar determinados usuarios para que no se busquen en la lista de direcciones al establecer el parámetro `HiddenFromAddressListEnabled` en `true` con el cmdlet [Set-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-user). |
| Microsoft Teams | [Administrar el acceso de los usuarios a Microsoft Teams](https://docs.microsoft.com/microsoftteams/user-access)                                                                                                                                                      |
| OneDrive        | [Administrar el uso compartido](https://docs.microsoft.com/OneDrive/manage-sharing)                                                                                                                                                                                |
| SharePoint      | [Planificación de permisos](https://docs.microsoft.com/es-ES/sharepoint/plan-your-permissions-strategy)<br> [Crear niveles de permisos](https://docs.microsoft.com/es-ES/sharepoint/how-to-create-and-edit-permission-levels)                          |
| OneNote         | No se pueden buscar archivos que estén incrustados en OneNote. [Cambiar los permisos de un bloc de notas de OneDrive](https://support.office.com/article/B9600CCF-045A-40E6-9913-4A7EB02869A5)                                                                    |
| Yammer          | [Configuración de seguridad de Yammer](https://docs.microsoft.com/Yammer/manage-security-and-compliance/yammer-security-settings)                                                                                                                               |

## <a name="step-2-assign-search-admin-and-search-editor"></a>Paso 2: Asignar el administrador de búsqueda y el editor de búsqueda

En la Búsqueda de Microsoft, puede administrar la configuración de búsqueda de su organización y el contenido con la asignación de los siguientes roles a los usuarios:

1. **Administrador de búsqueda:** este rol puede crear y administrar el contenido de los resultados de búsqueda y definir la configuración de consulta para mejorar los resultados de búsqueda en la organización. El administrador de búsqueda administra la configuración de la Búsqueda de Microsoft y puede realizar todas las tareas de administración de contenido que pueda llevar a cabo un editor de búsqueda.
2. **Editor de búsqueda:** crea, administra y elimina el contenido de la Búsqueda de Microsoft en el Centro de administración de Microsoft 365. Este rol puede crear y administrar contenido editorial, como las preguntas más frecuentes, respuestas, lugares y ubicaciones importantes, sitios y aplicaciones frecuentemente buscados y usados, entre otras cosas.

Actualmente, el administrador global debe asignar los roles de administrador de búsqueda y editor de búsqueda. Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/es-ES/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).

Los administradores de búsqueda influyen directamente en la experiencia de búsqueda para los usuarios finales. Esto incluye la elección de los tipos de resultados que quiere que se muestren a los usuarios. Puede resultar difícil para una sola persona elegir y crear contenido relevante para los muchos y diferentes temas que los usuarios buscan en una organización. Le recomendamos que aproveche la experiencia y los conocimientos de los expertos en la materia (SME) y de otros usuarios agregándolos como editores de búsqueda.

## <a name="step-3-make-content-easy-to-find"></a>Paso 3: Hacer que el contenido sea fácil de encontrar

La Búsqueda de Microsoft proporciona a los administradores herramientas que pueden usar para crear una óptima experiencia de búsqueda para los usuarios. En Búsqueda de Microsoft, los administradores tienen tres contenidos de búsqueda diferentes, que pueden crear para una mejor experiencia de búsqueda y mejorar la facilidad para encontrar contenido:

- **Marcadores:** los marcadores son similares a los resultados promocionados en SharePoint y ayudan a aumentar los mejores resultados posibles de las consultas de sus usuarios en la parte superior de los resultados de búsqueda y facilitar a los usuarios la búsqueda de sitios internos importantes.
- **Preguntas y respuestas:** las preguntas y respuestas son similares a las preguntas frecuentes; se suelen presentar en un formato de pregunta y respuesta. Las preguntas y respuestas proporcionan la mejor respuesta posible para las preguntas de los usuarios en relación con el trabajo.
- **Ubicaciones:** las ubicaciones son direcciones que ayudan a los usuarios a localizar edificios, oficinas y campus de su organización.

Cuantos más marcadores, preguntas y respuestas, y ubicaciones publique, mayores serán el valor y los beneficios para los usuarios. Sin embargo, muchos de ellos pueden añadir una sobrecarga sustancial a la gestión, puesto que deben ser revisados y actualizados periódicamente para que los resultados sigan siendo relevantes y actualizados.

Estos son algunos ejemplos de contenido que debería considerar como marcadores para los usuarios:

- Información de producto, servicio u organización.
- Contenido informativo que está disponible para todos los usuarios; Por ejemplo, información de la compañía, ayuda para las aplicaciones de Office y Windows, etc.
- Contenido que las personas de la organización buscan generalmente en su trabajo cotidiano. Las búsquedas comunes relacionadas con el trabajo incluyen prestaciones, informes de horas y gastos, envíos de pedidos de compra y cómo obtener ayuda del departamento de TI.

Para crear y administrar el contenido de la búsqueda, vea [Hacer que el contenido sea fácil de encontrar](make-content-easy-to-find.md).

## <a name="step-4-training-and-communication"></a>Paso 4: Formación y comunicación

Establezca recursos de autoservicio a los que los empleados puedan acceder fácilmente por sí mismos. Esto le ayudará a reducir la carga general sobre usted y sobre su equipo distribuyendo constantemente comunicaciones y asistiendo a la autoformación de los empleados. Proporcione a sus usuarios comunicaciones, preguntas frecuentes, vídeos y formación en vídeo o seminarios web. Estos son algunos vínculos útiles para empezar:

- [Encuentre lo que necesita con Búsqueda de Microsoft en Office](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Centro de aprendizaje de Office 365](https://support.office.com/office-training-center)
- [Búsqueda de Microsoft Center](https://support.office.com/es-ES/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)