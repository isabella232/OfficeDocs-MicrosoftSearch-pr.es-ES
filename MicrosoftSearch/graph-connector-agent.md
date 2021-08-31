---
title: Agente local
ms.author: rusamai
author: rsamai
manager: jameslau
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Agente on-prem
ms.openlocfilehash: 9994b84c8db05b6b269edb6f5b6f463ab8da1529
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702142"
---
# <a name="microsoft-graph-connector-agent"></a>Agente Graph conector de Microsoft

El uso de conectores locales requiere que instale el *software de agente Graph conector de Microsoft.* Permite la transferencia de datos segura entre los datos locales y las API del conector. Este artículo le guía a través de la instalación y configuración del agente.

## <a name="installation"></a>Instalación

Descargue la versión más reciente del agente Graph conector desde [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) e instale el software mediante el asistente de instalación. Con la configuración recomendada de la máquina que se describe a continuación, el software puede controlar hasta tres conexiones. Las conexiones posteriores podrían degradar el rendimiento de todas las conexiones del agente.

Configuración recomendada:

* Windows 10, Windows Server 2016 R2 y superiores
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 núcleos, 3 GHz
* 16 GB de RAM, 2 GB de espacio en disco
* Acceso de red al origen de datos e Internet a través de 443

Después de instalar el agente, si los servidores proxy o firewalls de la organización bloquean la comunicación con dominios desconocidos, agregue los siguientes a la lista de permitidos.

1. *.servicebus.windows.net
2. *.events.data.microsoft.com
3. https://<span>login.microsoftonline.</span> com
4. https://<span>gcs.office.</span> com/
5. https://<span>graph.microsoft.</span> com/

>[!NOTE]
>No se admite la autenticación de proxy. Si el entorno tiene un proxy que requiere autenticación, nuestra recomendación es permitir que el agente del conector omita el proxy.

## <a name="create-and-configure-an-app-for-the-agent"></a>Crear y configurar una aplicación para el agente  

En primer lugar, inicie sesión y tenga en cuenta que el privilegio mínimo requerido en la cuenta es el administrador de búsqueda. A continuación, el agente le pedirá que proporcione detalles de autenticación. Sigue los pasos siguientes para crear una aplicación y generar los detalles de autenticación necesarios.

### <a name="create-an-app"></a>Crear una aplicación

1. Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.

2. Vaya a **Azure Active Directory**  ->  **registros de aplicaciones** desde el panel de navegación y seleccione Nuevo **registro**.

3. Proporcione un nombre para la aplicación y seleccione **Registrar**.

4. Anote el identificador de aplicación (cliente).

5. Abra **los permisos de** api desde el panel de navegación y seleccione Agregar un **permiso**.

6. Seleccione **Microsoft Graph** y, a continuación, Permisos de **aplicación**.

7. Busque "ExternalItem.ReadWrite.All" y "Directory.Read.All" en los permisos y seleccione **Agregar permisos**.

8. Seleccione **Conceder consentimiento de administrador para [TenantName]** y confirme **seleccionando Sí**.

9. Compruebe que los permisos están en el estado "concedido".

    :::image type="content" alt-text="Permisos que se muestran como concedidos en verde en la columna de la derecha." source="media/onprem-agent/granted-state.png" lightbox="media/onprem-agent/granted-state.png":::

### <a name="configure-authentication"></a>Configurar la autenticación

Los detalles de autenticación se pueden proporcionar mediante un secreto de cliente o un certificado. Sigue los pasos que prefieras.

#### <a name="configuring-the-client-secret-for-authentication"></a>Configuración del secreto de cliente para la autenticación

1. Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con credenciales de administrador para el inquilino.

2. Abre **Registro de aplicaciones** desde el panel de navegación y ve a la aplicación adecuada. En **Administrar**, seleccione **Certificados y secretos**.

3. Seleccione **Nuevo secreto de cliente** y seleccione un período de expiración para el secreto. Copie el secreto generado y guárdelo porque no se volverá a mostrar.

4. Use este secreto de cliente junto con el identificador de aplicación para configurar el agente. No puede usar espacios en blanco en el **campo Nombre** del agente. Se aceptan caracteres numéricos alfa.

#### <a name="using-a-certificate-for-authentication"></a>Uso de un certificado para la autenticación

Hay tres pasos sencillos para usar la autenticación basada en certificados:

1. Crear u obtener un certificado
2. Upload el certificado a Azure Portal
3. Asignar el certificado al agente

##### <a name="step-1-get-a-certificate"></a>Paso 1: Obtener un certificado

El siguiente script se puede usar para generar un certificado autofirmado. Es posible que su organización no permita certificados autofirmados. En ese caso, use esta información para comprender los requisitos y adquirir un certificado de acuerdo con las directivas de su organización.

```powershell
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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Paso 2: Upload el certificado en Azure Portal

1. Abra la aplicación y vaya a la sección certificados y secretos desde el panel izquierdo.

2. Seleccione **Upload certificado y** cargue el archivo .cer.

3. Abra **Registro de aplicaciones** y seleccione Certificados y **secretos** en el panel de navegación. Copie la huella digital del certificado.

:::image type="content" alt-text="Lista de certificados thumbrint cuando se seleccionan certificados y secretos en el panel izquierdo." source="media/onprem-agent/certificates.png" lightbox="media/onprem-agent/certificates.png":::

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Paso 3: Asignar el certificado al agente

Si usó el script de ejemplo para generar un certificado, el archivo PFX se puede encontrar en la ubicación identificada en el script.

1. Descargue el archivo pfx del certificado en el equipo agente.

2. Haga doble clic en el archivo pfx para iniciar el cuadro de diálogo de instalación del certificado.

3. Seleccione **Equipo local para** la ubicación del almacén al instalar el certificado.

4. Después de instalar el certificado, abra **Administrar certificados de equipo** mediante menú Inicio.

5. Seleccione el certificado recién instalado en **Certificados**  >  **personales**.

6. Haga clic con el botón secundario en el certificado y **seleccione Todas las tareas** Administrar claves  >  **privadas** Opción.

7. En el cuadro de diálogo permisos, seleccione agregar opción. Aparece una nueva ventana. Seleccione la opción "Ubicaciones" en ella. Seleccione la máquina en la que está instalado el agente entre la lista de ubicaciones que se muestran y haga clic en **Aceptar**.

8. En el cuadro de diálogo de selección de usuario, escriba: **Nt Service\GcaHostService** y haga clic en **Aceptar**. No haga clic en el **botón Comprobar nombres.**

9. Haga clic en Aceptar en el cuadro de diálogo permisos. La máquina del agente ahora está configurada para que el agente genere tokens con el certificado.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="installation-failure"></a>Error de instalación

Si se produce un error en la instalación, compruebe los registros de instalación ejecutando: msiexec /i "< path to msi >\GcaInstaller.msi" /L*V "< destination path >\install.log". Si los errores no se pueden resolver, alcanza la compatibilidad MicrosoftGraphConnectorsFeedback@service.microsoft.com con los registros.

### <a name="registration-failure"></a>Error de registro

Si se produce un error al iniciar sesión en la aplicación de configuración con el error "Error de inicio de sesión. Haga clic en el botón iniciar sesión para volver a intentarlo". incluso después de que la autenticación del explorador se realiza correctamente, abra services.msc y compruebe si GcaHostService se está ejecutando. Si no es así, indómalo manualmente.

Si el servicio no se inicia con el error "El servicio no se hizo a causa de un error de inicio de sesión", compruebe si la cuenta virtual NT Service\GcaHostService tiene permiso para iniciar sesión como servicio en el equipo. Consulte [este vínculo para](/windows/security/threat-protection/security-policy-settings/log-on-as-a-service) obtener instrucciones. Si la opción para agregar usuario o grupo está en gris en la Asignación de derechos de usuario o directivas locales, significa que el usuario que intenta agregar esta cuenta no tiene privilegios de administrador en este equipo o que hay una directiva de grupo que lo invalida. La directiva de grupo debe actualizarse para permitir que el servicio host inicie sesión como servicio.

### <a name="connection-failure"></a>Error de conexión

Si se produce un error al crear una conexión con el error "Comprobar nombre de usuario/contraseña y la ruta de acceso de origen de datos" incluso cuando el nombre de usuario y la contraseña proporcionados sean correctos, asegúrese de que la cuenta de usuario tenga derechos de inicio de sesión interactivos en el equipo donde está instalado un agente de conector Graph. Consulte la documentación sobre la administración [de directivas de inicio de sesión](/windows/security/threat-protection/security-policy-settings/allow-log-on-locally#policy-management) para comprobar los derechos de inicio de sesión. Asegúrese también de que el origen de datos y la máquina del agente estén en la misma red.

Si se produce un error en una conexión con el error "1011: el agente de conector de Graph no es accesible ni sin conexión", inicie sesión en el equipo donde está instalado el agente e inicie la aplicación de agente si aún no se está ejecutando. Si la conexión sigue fallando, compruebe que el certificado o secreto de cliente proporcionado al agente durante el registro no ha expirado y tiene permisos necesarios.
