---
title: Agente local
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Agente local
ms.openlocfilehash: 487c5b179e09fd99fa26ae7a237e89ca38b7be4d
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408946"
---
# <a name="on-prem-agent"></a>Agente local

## <a name="graph-connector-agent"></a>Agente de conector de Graph

Los conectores de gráficos locales requieren la instalación del software del *agente de conector de Graph* . Permite una transferencia de datos rápida y segura entre los datos locales y los servicios en la nube. Este artículo le guiará por los pasos necesarios para instalar y configurar el software. Una vez configurada, estará disponible para crear conexiones a los orígenes de datos locales desde el [centro de administración de Microsoft 365](https://admin.microsoft.com).

## <a name="installation"></a>Instalación

Descargue la versión más reciente del agente de conector de Graph con [este vínculo](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) e instale el software mediante el Asistente para la instalación. Con la configuración recomendada del equipo que se describe a continuación, el software puede controlar fácilmente hasta tres conexiones. Cualquier conexión posterior podría degradar el rendimiento.

Configuración recomendada:

* Windows 10, Windows Server 2012 R2 y versiones posteriores
* 8 núcleos, 3 GHz
* 16 GB de RAM, 1 GB de espacio en disco
* Acceso de red a origen de datos e Internet mediante 443

## <a name="creating-app-for-the-agent"></a>Creación de la aplicación para el agente  

La instancia del agente debe alimentarse con algunos parámetros críticos antes de crear conexiones. Estos parámetros incluyen los detalles de autenticación necesarios para usar las API de recopilación de gráficos.  

Pasos para crear aplicaciones para el agente.

1. Vaya a [Azure portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.
2. Navegue a **Azure Active Directory**  ->  **registros de aplicaciones** de Azure Active Directory desde el panel de navegación y seleccione **nuevo registro**.
3. Especifique un nombre para la aplicación y seleccione **registrar**.
4. Anote el identificador de la aplicación (cliente).
5. Abra **permisos de API** en el panel de navegación y seleccione **Agregar un permiso**.
6. Seleccione **Microsoft Graph** y, a continuación, permisos de la **aplicación**.
7. Busque "ExternalItem. ReadWrite. All" y "Directory. Read. All" desde los permisos y seleccione **Agregar permisos**.
8. Seleccione **conceder consentimiento de administrador para [TenantName]** y confirme seleccionando **sí**.
9. Compruebe que los permisos se encuentran en el estado concedido.
     ![Permisos que se muestran como concedidos en verde en la columna derecha.](media/onprem-agent/granted-state.png)

## <a name="configuring-graph-connector-agent"></a>Configuración del agente de conector de Graph

Una vez que haya creado la aplicación para el agente, debe configurar el agente con los detalles de autenticación adecuados.

Los detalles de autenticación se pueden proporcionar en una de las siguientes formas.

### <a name="configuring-the-client-secret-for-authentication"></a>Configuración del secreto de cliente para la autenticación

1. Vaya a [Azure portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.
2. Abra el **registro de aplicaciones** en el panel de navegación y vaya a la aplicación correspondiente. En **administrar**, seleccione **certificados y secretos**.
3. Seleccione **nuevo secreto de cliente** y seleccione un período de expiración para el secreto. Copie el secreto generado y guárdelo porque no se volverá a mostrar.
4. Use este secreto de cliente junto con el identificador de aplicación para configurar el agente. No use espacios en blanco en el campo **nombre** del agente. Se aceptan los caracteres alfanuméricos alfanuméricos.

## <a name="using-thumbprint-certificate-for-authentication"></a>Uso del certificado de huella digital para la autenticación

Si ya ha configurado los detalles de autenticación mediante [la configuración del secreto de cliente para la autenticación](#configuring-the-client-secret-for-authentication) , puede ir directamente a la introducción a la [instalación](configure-connector.md).

1. Abra el **registro de aplicaciones** y seleccione **certificados y secretos** en el panel de navegación. Copie la huella digital del certificado.
![Lista de certificados de thumbrint cuando se selecciona certificados y secretos en el panel izquierdo](media/onprem-agent/certificates.png)
2. Use el secreto de cliente o la huella digital para registrar el agente de conector de Graph.
![Registro del formulario donde se pide el nombre, el identificador de la aplicación, el tipo de credencial y el certificado](media/onprem-agent/register.png)
