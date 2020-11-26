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
ms.openlocfilehash: 763904f8dd96c5db8b0633e36795443502afe7d0
ms.sourcegitcommit: 0ed8ec8b3c4e0f5f669005081fd8b2219f07b4f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420837"
---
# <a name="graph-connector-agent"></a>Agente de conector de Graph

El uso de conectores de gráficos locales requiere la instalación del software del *agente de conector de Graph* . Permite una transferencia de datos segura entre los datos locales y las API de conector de Graph. Este artículo le guiará a través de la instalación y configuración del agente.

## <a name="installation"></a>Instalación

Descargue la última versión [del agente de](https://aka.ms/gcadownload) conector de Graph y instale el software mediante el Asistente para la instalación. Mediante el uso de la configuración recomendada del equipo que se describe a continuación, el software puede administrar hasta tres conexiones. Cualquier conexión posterior podría degradar el rendimiento de todas las conexiones en el agente.

Configuración recomendada:

* Windows 10, Windows Server 2016 R2 y versiones posteriores
* 8 núcleos, 3 GHz
* 16 GB de RAM, 2 GB de espacio en disco
* Acceso de red a origen de datos e Internet mediante 443

## <a name="create-and-configure-an-app-for-the-agent"></a>Crear y configurar una aplicación para el agente  

Antes de usar el agente, debe crear una aplicación y configurar los detalles de autenticación.

### <a name="create-an-app"></a>Crear una aplicación

1. Vaya a [Azure portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.
2. Navegue a **Azure Active Directory**  ->  **registros de aplicaciones** de Azure Active Directory desde el panel de navegación y seleccione **nuevo registro**.
3. Especifique un nombre para la aplicación y seleccione **registrar**.
4. Anote el identificador de la aplicación (cliente).
5. Abra **permisos de API** en el panel de navegación y seleccione **Agregar un permiso**.
6. Seleccione **Microsoft Graph** y, a continuación, permisos de la **aplicación**.
7. Busque "ExternalItem. ReadWrite. All" y "Directory. Read. All" desde los permisos y seleccione **Agregar permisos**.
8. Seleccione **conceder consentimiento de administrador para [TenantName]** y confirme seleccionando **sí**.
9. Compruebe que los permisos estén en el estado "concedido".
     ![Permisos que se muestran como concedidos en verde en la columna derecha.](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>Configurar la autenticación

Se pueden proporcionar detalles de autenticación mediante un secreto de cliente o un certificado. Siga los pasos que desee.

#### <a name="configuring-the-client-secret-for-authentication"></a>Configuración del secreto de cliente para la autenticación

1. Vaya a [Azure portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.
2. Abra el **registro de aplicaciones** en el panel de navegación y vaya a la aplicación correspondiente. En **administrar**, seleccione **certificados y secretos**.
3. Seleccione **nuevo secreto de cliente** y seleccione un período de expiración para el secreto. Copie el secreto generado y guárdelo porque no se volverá a mostrar.
4. Use este secreto de cliente junto con el identificador de aplicación para configurar el agente. No puede usar espacios en blanco en el campo **nombre** del agente. Se aceptan los caracteres alfanuméricos alfanuméricos.

#### <a name="using-a-certificate-for-authentication"></a>Uso de un certificado para la autenticación

Hay tres pasos sencillos para usar la autenticación basada en certificados:

1. Creación u obtención de un certificado
1. Cargar el certificado en el portal de Azure
1. Asignar el certificado al agente

##### <a name="step-1-get-a-certificate"></a>Paso 1: obtener un certificado

El script siguiente se puede usar para generar un certificado autofirmado. Es posible que su organización no permita certificados autofirmados. En ese caso, use esta información para comprender los requisitos y adquirir un certificado de acuerdo con las directivas de la organización.

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Paso 2: cargar el certificado en Azure portal

1. Abra la aplicación y vaya a la sección certificados y secretos del panel izquierdo
1. Seleccione "cargar certificado" y cargue el archivo. cer
1. Abra el **registro de aplicaciones** y seleccione **certificados y secretos** en el panel de navegación. Copie la huella digital del certificado.

![Lista de certificados de thumbrint cuando se selecciona certificados y secretos en el panel izquierdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Paso 3: asignar el certificado al agente

Si usó el script de ejemplo para generar un certificado, el archivo PFX puede encontrarse en la ubicación identificada en el script.

1. Descargue el archivo PFX de certificado en el equipo del agente.
1. Haga doble clic en el archivo PFX para iniciar el cuadro de diálogo de instalación de certificado.
1. Seleccione "equipo local" para la ubicación del almacén mientras instala el certificado.
1. Después de instalar el certificado, abra "administrar certificados de equipo" a través del menú Inicio
1. Seleccione el certificado recién instalado en ' ' personal '-> ' certificados '
1. Haga clic con el botón secundario en el certificado y seleccione "todas las tareas"-> "administrar claves privadas..." Opción
1. En el cuadro de diálogo permisos, seleccione Agregar opción. En el cuadro de diálogo de selección del usuario, escriba: "NT Service\GcaHostService" y haga clic en "Aceptar". No haga clic en el botón Comprobar nombres.
1. Haga clic en aceptar en el cuadro de diálogo permisos. El equipo del agente ya está configurado para que el agente genere los tokens con el certificado.
