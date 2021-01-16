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
description: Agente on-prem
ms.openlocfilehash: 31220196849fe90ab2611e9c2b83a1cec0a02b34
ms.sourcegitcommit: a04f1df14a3221776ccd141f6060328612d80e06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876502"
---
# <a name="graph-connector-agent"></a>Agente de conector de Graph

El uso de conectores de Graph locales requiere instalar el software *del agente de conector de Graph.* Permite la transferencia segura de datos entre los datos locales y las API del conector de Graph. Este artículo le guiará a través de la instalación y configuración del agente.

## <a name="installation"></a>Instalación

Descargue aquí la versión más reciente del agente del conector de Graph [e](https://aka.ms/gcadownload) instale el software con el asistente para la instalación. Con la configuración recomendada del equipo que se describe a continuación, el software puede controlar hasta tres conexiones. Las conexiones posteriores pueden degradar el rendimiento de todas las conexiones en el agente.

Configuración recomendada:

* Windows 10, Windows Server 2016 R2 y versiones posteriores
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 núcleos, 3 GHz
* 16 GB de RAM, 2 GB de espacio en disco
* Acceso de red al origen de datos e Internet a través del 443

## <a name="create-and-configure-an-app-for-the-agent"></a>Crear y configurar una aplicación para el agente  

En primer lugar, inicie sesión y tenga en cuenta que el privilegio mínimo requerido en la cuenta es el administrador de búsqueda. A continuación, el agente le pedirá que proporcione los detalles de autenticación. Siga los pasos siguientes para crear una aplicación y generar los detalles de autenticación necesarios.

### <a name="create-an-app"></a>Crear una aplicación

1. Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.
2. Vaya a **Registros de aplicaciones de Azure Active Directory** desde el panel de navegación y seleccione Nuevo  ->   **registro.**
3. Proporcione un nombre para la aplicación y seleccione **Registrar.**
4. Anote el id. de aplicación (cliente).
5. Abra **los permisos de api** en el panel de navegación y seleccione Agregar un **permiso.**
6. Seleccione **Microsoft Graph y,** a continuación, **permisos de aplicación.**
7. Busque "ExternalItem.ReadWrite.All" y "Directory.Read.All" en los permisos y seleccione **Agregar permisos.**
8. Seleccione **Conceder consentimiento de administrador para [TenantName]** y confirme **seleccionando Sí**.
9. Compruebe que los permisos están en el estado "concedido".
     ![Permisos que se muestran en verde en la columna de la derecha.](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>Configurar la autenticación

Los detalles de autenticación se pueden proporcionar mediante un secreto de cliente o un certificado. Siga los pasos que desee.

#### <a name="configuring-the-client-secret-for-authentication"></a>Configuración del secreto de cliente para la autenticación

1. Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.
2. Abra **Registro de aplicaciones** desde el panel de navegación y vaya a la aplicación adecuada. En **Administrar,** seleccione **Certificados y secretos.**
3. Seleccione **nuevo secreto de cliente** y seleccione un período de expiración para el secreto. Copie el secreto generado y guárdelo porque no se volverá a mostrar.
4. Use este secreto de cliente junto con el id. de aplicación para configurar el agente. No puede usar espacios en blanco en el **campo Nombre** del agente. Se aceptan caracteres numéricos alfa.

#### <a name="using-a-certificate-for-authentication"></a>Uso de un certificado para la autenticación

Hay tres pasos sencillos para usar la autenticación basada en certificados:

1. Crear u obtener un certificado
1. Cargar el certificado en Azure Portal
1. Asignar el certificado al agente

##### <a name="step-1-get-a-certificate"></a>Paso 1: Obtener un certificado

El script siguiente se puede usar para generar un certificado autofirmado. Es posible que su organización no permita certificados autofirmados. En ese caso, use esta información para comprender los requisitos y adquirir un certificado de acuerdo con las directivas de su organización.

```Powershell
$dnsName = "<TenantDomain like agent.onmicrosoft.com>" # Your DNS name
$password = "<password>" # Certificate password
$folderPath = "D:\New folder\" # Where do you want the files to get saved to? The folder needs to exist.
$fileName = "agentcert" # What do you want to call the cert files? without the file extension
$yearsValid = 10 # Number of years until you need to renew the certificate
$certStoreLocation = "cert:\LocalMachine\My"
$expirationDate = (Get-Date).AddYears($yearsValid)
$certificate = New-SelfSignedCertificate -DnsName $dnsName -CertStoreLocation $certStoreLocation -NotAfter $expirationDate -KeyExportPolicy Exportable -KeySpec Signature
$certificatePath = $certStoreLocation + '\' + $certificate.Thumbprint
$filePath = $folderPath + '\' + $fileName
$securePassword = ConvertTo-SecureString -String $password -Force -AsPlainText
Export-Certificate -Cert $certificatePath -FilePath ($filePath + '.cer')
Export-PfxCertificate -Cert $certificatePath -FilePath ($filePath + '.pfx') -Password $securePassword
```

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Paso 2: Cargar el certificado en Azure Portal

1. Abra la aplicación y vaya a la sección certificados y secretos desde el panel izquierdo
1. Seleccione "Cargar certificado" y cargue el archivo .cer
1. Abra **el registro de la** aplicación y seleccione Certificados y **secretos** en el panel de navegación. Copie la huella digital del certificado.

![Lista de certificados en miniatura cuando se seleccionan certificados y secretos en el panel izquierdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Paso 3: Asignar el certificado al agente

Si usó el script de ejemplo para generar un certificado, el archivo PFX se puede encontrar en la ubicación identificada en el script.

1. Descarga el archivo pfx del certificado en el equipo del agente.
1. Haz doble clic en el archivo pfx para iniciar el cuadro de diálogo de instalación del certificado.
1. Selecciona "Equipo local" para la ubicación del almacén mientras instalas el certificado.
1. Después de instalar el certificado, abra "Administrar certificados de equipo" a través del menú Inicio
1. Seleccione el certificado recién instalado en "Personal" -> "Certificados"
1. Haga clic con el botón secundario en el certificado y seleccione "Todas las tareas" -> "Administrar claves privadas..." Opción
1. En el cuadro de diálogo de permisos, seleccione la opción Agregar. En el cuadro de diálogo de selección de usuario, escriba: "Servicio NT\GcaHostService" y haga clic en "Aceptar". No haga clic en el botón "Comprobar nombres".
1. Haga clic bien en el cuadro de diálogo de permisos. La máquina de agente ahora está configurada para que el agente genere tokens mediante el certificado.
