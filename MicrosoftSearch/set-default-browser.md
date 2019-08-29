---
title: Establecer explorador predeterminado
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
ROBOTS: NOINDEX
description: Configure Microsoft Edge o Internet Explorer como explorador predeterminado para los usuarios de Búsqueda de Microsoft.
ms.openlocfilehash: ed145a1811aba0b58158ed04dd3bf8dc089a0682
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639743"
---
# <a name="make-microsoft-edge-the-default-browser"></a>Hacer de Microsoft Edge el explorador predeterminado
  
Para proporcionar a los usuarios la mejor experiencia con Búsqueda de Microsoft, puede hacer de Microsoft Edge el explorador predeterminado. Esto solo establece Microsoft Edge como explorador predeterminado para los usuarios en su organización; los usuarios pueden seleccionar individualmente un explorador diferente.
  
  
## <a name="windows-8-and-later"></a>Windows 8 y versiones posteriores

Estas instrucciones muestran cómo establecer Microsoft Edge o Internet Explorer como explorador predeterminado para equipos que ejecutan Windows 8 o posterior. Los usuarios podrán cambiar el explorador después de establecer esta directiva.
  
### <a name="step-1-create-the-default-associations-file"></a>PASO 1: Cree el archivo de asociaciones predeterminadas
Cree el archivo de asociaciones predeterminadas en la carpeta SYSVOL del controlador del dominio.

1. Abra una consola de administración de PowerShell.
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a>PASO 2. Agregue o edite el archivo de asociaciones predeterminadas

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. Edite las siguientes entradas (.htm, .html, http, https) y quite otras entradas si no son necesarias.
  - **Microsoft Edge**
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a>Paso 3. Edite la Directiva de grupo

1. Abra la **Consola de administración de directivas de grupo (gpmc.msc)** y cambie a editar una directiva existente o crear una nueva.
1. Vaya a **Configuración del equipo\Plantillas administrativas\Componentes de Windows\Explorador de archivos**.
1. Haga doble clic en **Establecer un archivo de configuración de asociaciones predeterminadas**, establézcalo en **Habilitado** y especifique la ruta de acceso a AppAssoc.xml (por ejemplo: %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Aplique el GPO resultante vinculándolo al dominio apropiado.

  
## <a name="windows-7"></a>Windows 7

1. Configure el equipo local que se usará para establecer el GPO
    
1. Abra **Panel de control\Programas\Programas predeterminados\Establecer programas predeterminados** y establezca Internet Explorer como predeterminado. 
    
2. Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.
    
1. Vaya a **\<Equipo/Configuración\> de usuario\Directivas\Preferencias\Configuración de Windows**.
    
2. Haga clic derecho en **Registro\Nuevo** y seleccione **Asistente de registro**.
    
3. En la ventana del Explorador de registro, seleccione **Equipo local** y haga clic en **Siguiente**.
    
4. Vaya a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** y seleccione el valor ProgId. Asegúrese de que el valor tiene un aspecto similar al siguiente: 
    
    ![Seleccione el valor ProgId en Editar cadena](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. Vaya a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** y seleccione el valor ProgId. Asegúrese de que el valor tiene un aspecto similar al siguiente: 
    
    ![Seleccione ProgId para HTTPS en Editar cadena](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. Aplique el GPO resultante vinculándolo al dominio correspondiente.
    
