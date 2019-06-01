---
title: Configurar **Búsqueda de Microsoft**
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar Búsqueda de Microsoft por primera vez.
ms.openlocfilehash: 3b872370dc2058c56637b836f8f78b7ed8e6680e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591057"
---
# <a name="set-up-microsoft-search"></a>Configurar Búsqueda de Microsoft

**Búsqueda de Microsoft** ofrece una interfaz intuitiva para ayudar a los usuarios a encontrar información como archivos y documentos, sitios internos y herramientas empresariales, personas y grupos, ubicaciones y direcciones, conversaciones y respuestas mediante un acceso seguro a todas las fuentes de datos, incluidos correos electrónicos, archivos, archivos de SharePoint, contenidos de OneDrive y otros recursos compartidos, así como de internet en la organización del usuario.

Para obtener más información sobre las características de **Búsqueda de Microsoft**, consulte [Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).

## <a name="get-started"></a>Introducción

**Búsqueda de Microsoft** está activado de forma predeterminada para todas las aplicaciones de Microsoft compatibles, como parte de Microsoft 365. Todo lo que un usuario debe hacer es iniciar sesión con una cuenta profesional o educativa y usar un explorador con Bing como proveedor de búsquedas predeterminado.

Usted administra **Búsqueda de Microsoft** desde el **Centro de administración de Microsoft 365**. Inicie sesión con su nombre de usuario con credenciales de administrador y seleccione el icono de **Administrador** de la lista de aplicaciones de Office 365 (haga clic en el icono del **Iniciador de aplicaciones** en la esquina superior izquierda de la lista de aplicaciones). En el **Centro de administración de Microsoft 365**, seleccione **Búsqueda de Microsoft** en **Configuración** en el panel de navegación izquierdo. 

**Nota:** si ve **Búsqueda de Microsoft** en **Configuración** en el **Centro de administración de Microsoft 365**, active el interruptor **Probar la vista previa** en la esquina superior derecha del centro de administración. 

Como administrador debe considerar algunas cosas que pueden hacer que la experiencia de **Búsqueda de Microsoft** en su organización sea eficiente e intuitiva.

### <a name="step-1-check-access-level-of-your-users"></a>Paso 1: Compruebe el nivel de acceso de los usuarios

**Búsqueda de Microsoft** respeta la configuración de seguridad del origen de contenido. Lo que los usuarios ven en los resultados de búsqueda depende de sus permisos y niveles de acceso. Revise el nivel de acceso de los usuarios de su organización para asegurarse de que los usuarios solo encuentran el contenido al que tienen permiso para acceder.

Obtenga más información sobre [planificación de permisos](https://docs.microsoft.com/es-ES/sharepoint/plan-your-permissions-strategy) y [crear niveles de permisos](https://docs.microsoft.com/es-ES/sharepoint/how-to-create-and-edit-permission-levels).

### <a name="step-2-assign-search-admin-and-search-editor"></a>Paso 2: Asigne el Administrador de búsqueda y el Editor de búsqueda

Hay dos nuevos roles en el **Centro de administración de Microsoft**: el Administrador de búsqueda y el Editor de búsqueda.  El Administrador global, que tiene todos los privilegios, asigna roles de administrador a los usuarios, incluido el rol de Administrador de búsqueda. Los Administradores de búsqueda pueden delegar los roles de Administrador de búsqueda y Editor de búsqueda a otros usuarios. Para obtener más información sobre los varios roles de administrador, vea [Roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide).

**Nota:** estos dos roles nuevos, el Administrador de búsqueda y el Editor de búsqueda, están disponibles solo en el **Centro de administración de Microsoft 365**, no en el portal de administración antiguo. 

Los administradores de búsqueda influyen directamente en la experiencia de búsqueda para los usuarios finales. Esto incluye la elección de los tipos de resultados que quiere que se muestren a los usuarios. Puede resultar difícil para una sola persona elegir y crear contenido relevante para los muchos y diferentes temas que los usuarios buscan en una organización. Le recomendamos que aproveche la experiencia y los conocimientos de otros usuarios agregándolos como editores. 

En **Búsqueda de Microsoft**, puede administrar la configuración de búsqueda de su organización y contenido con dos nuevas funciones:
1. **Administrador de búsqueda:** este rol puede crear y administrar el contenido de los resultados de búsqueda y definir la configuración de consulta para mejorar los resultados de búsqueda en la organización. El administrador de búsqueda controla la configuración de **Búsqueda de Microsoft** y designa a los Editores de búsqueda, que crean contenido.
2. **Editor de búsqueda:** crea, administra y elimina el contenido de **Búsqueda de Microsoft** en el Centro de administración de Microsoft 365. Este rol puede crear y administrar contenido editorial como preguntas más frecuentes, lugares y ubicaciones importantes, lugares y ubicaciones frecuentemente buscados, sitios y aplicaciones frecuentemente buscados y usados, etc. Sin embargo, no tiene acceso a la administración de la configuración de búsqueda.

Para asignar roles de administrador, consulte [Asignar derechos de administrador en Office 365 para empresas](https://docs.microsoft.com/es-ES/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).

### <a name="step-3-make-content-easy-to-find"></a>Paso 3: Haga el contenido fácil de encontrar 

**Búsqueda de Microsoft** proporciona a los administradores herramientas que pueden usar para crear una óptima experiencia de búsqueda para los usuarios. En **Búsqueda de Microsoft**, los administradores tienen tres contenidos de búsqueda diferentes, que pueden crear para una mejor experiencia de búsqueda y mejorar la facilidad para encontrar contenido:
- **Marcador:** los marcadores son similares a los resultados promocionados en SharePoint y ayudan a aumentar los mejores resultados posibles para las consultas de sus usuarios en la parte superior de los resultados de búsqueda y facilitar a los usuarios encontrar sitios internos importantes. 
- **Preguntas y respuestas:** las preguntas y respuestas son similares a las preguntas frecuentes; se suelen presentar en un formato de pregunta y respuesta. Las preguntas y respuestas proporcionan la mejor respuesta posible para las preguntas de los usuarios en relación con el trabajo.
- **Ubicación:** las ubicaciones son direcciones que ayudan a los usuarios a localizar edificios, oficinas, campus, etc., de su organización. 

Cuantos más marcadores, preguntas y respuestas, y ubicaciones publique, mayores serán el valor y los beneficios para los usuarios. Sin embargo, muchos de ellos pueden añadir una sobrecarga sustancial a la gestión, puesto que deben ser revisados y actualizados periódicamente para que los resultados sigan siendo relevantes y actualizados.

Estos son algunos ejemplos de contenido que debería considerar como marcadores para los usuarios:
- Información de producto, servicio u organización.
- Contenido informativo que está disponible para todos los usuarios; Por ejemplo, información de la compañía, ayuda para las aplicaciones de Office y Windows, etc. 
- Contenido que las personas de la organización buscan generalmente en su trabajo cotidiano. Las búsquedas comunes relacionadas con el trabajo incluyen prestaciones, informes de horas y gastos, envíos de pedidos de compra y cómo obtener ayuda del departamento de TI. 

Para crear y administrar el contenido de la búsqueda, consulte [Hacer que el contenido sea fácil de encontrar](make-content-easy-to-find.md).

### <a name="step-4-test-single-sign-on"></a>Paso 4: Prueba de inicio de sesión único
**Búsqueda de Microsoft** usa Azure Active Directory (AAD) para autenticar y autorizar el acceso a datos de su organización.  Esto significa que sus usuarios inician sesión automáticamente en su cuenta profesional o educativa cuando usted ha iniciado sesión en una aplicación de Office 365 o en Windows 10.

Se recomienda que los usuarios de **Búsqueda de Microsoft** usen el inicio de sesión único, ya que reduce el número de veces que se pide a los usuarios que inicien sesión. Los administradores deben probar el inicio de sesión único con un grupo pequeño de usuarios, lo que les ayudará a identificar cualquier problema de configuración que genere bloqueos. 

Para los usuarios de Chrome en Windows 10, el inicio de sesión único solo funcionará si la extensión de inicio de sesión de Windows 10 y AAD para Chrome están instalados. Una vez instalados, use la extensión de Chrome para autenticar fácilmente con AAD al iniciar sesión en sitios compatibles, incluidos Office 365 y Bing. Esta función está disponible solo para usuarios autorizados. 

Para descargar e instalar Windows 10 y la extensión de inicio de sesión de AAD para Chrome, vaya a la [Chrome Web Store](https://go.microsoft.com/fwlink/?linkid=2090961).

### <a name="step-5-training-and-communication"></a>Paso 5: Formación y comunicación
Establezca recursos de autoservicio a los que los empleados puedan acceder fácilmente por sí mismos. Esto le ayudará a reducir la carga general sobre usted y sobre su equipo distribuyendo constantemente comunicaciones y asistiendo a la autoformación de los empleados. Proporcione a sus usuarios comunicaciones, preguntas frecuentes, vídeos y formación en vídeo o seminarios web. Estos son algunos vínculos útiles para empezar:
- [Encuentre lo que necesita con Búsqueda de Microsoft en Office](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Centro de aprendizaje de Office 365](https://support.office.com/office-training-center)
- 
  [Búsqueda de Microsoft Center](https://support.office.com/es-ES/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)

### <a name="trying-out-microsoft-search-in-bing"></a>Probar **Búsqueda de Microsoft** en Bing 
El administrador de **Búsqueda de Microsoft** puede desactivar **Búsqueda de Microsoft** en Bing. Si lo desactiva, los usuarios no verán el contenido de la organización en las búsquedas de Bing. De forma predeterminada, **Búsqueda de Microsoft** está activado en Bing. Le recomendamos que mantenga **Búsqueda de Microsoft** activado en Bing para una mejor experiencia de usuario. 

Si desea probar **Búsqueda de Microsoft** en un inquilino de prueba o si desea probar la experiencia de búsqueda antes de que esté disponible para todos los usuarios, puede desactivar **Búsqueda de Microsoft**.
Para activar/desactivar **Búsqueda de Microsoft** en Bing, vaya a **Servicios y complementos** en el **centro de administración de Microsoft 365** y active/desactive **Búsqueda de Microsoft en Bing**.
