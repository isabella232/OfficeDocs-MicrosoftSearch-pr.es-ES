---
title: Establecer explorador predeterminado
ms.author: dawholl
author: dawholl
manager: kellis
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
description: Obtenga información sobre cómo configurar un explorador predeterminado para su empresa con Microsoft Search.
ms.openlocfilehash: 08c61bf6dd68f8044f3f79a0b22829a8f7f6b8ef
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727847"
---
# <a name="set-default-browser"></a>Establecer explorador predeterminado

  
La configuración de la página principal, motor de búsqueda y explorador predeterminados ayudará a los usuarios a descubrir las funciones de Microsoft Search, fomentar su uso y proporcionar una experiencia más fluida.
  
Para establecer el explorador predeterminado para su organización, siga los pasos siguientes.
  
## <a name="windows-8-and-above"></a>Windows 8 y versiones posteriores

Para configurar Internet Explorer o Microsoft Edge como explorador predeterminado, siga estos pasos:
  
### <a name="create-default-associations-file"></a>Cree el archivo de asociaciones predeterminadas

1. Abra una consola de administración de PowerShell.
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
Estos pasos intentan crear el archivo de asociaciones predeterminadas en la carpeta SYSVOL del controlador del dominio.
  
### <a name="add-or-edit-the-default-associations-file"></a>Agregue o edite el archivo de asociaciones predeterminadas

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. Edite las siguientes entradas (.htm, .html, http, https) y quite otras entradas si no son necesarias.
    
  - **Microsoft Edge**
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. Abra la Consola de administración de directivas de grupo (gpmc.msc) y cambie a editar una directiva existente o crear una nueva.
    
1. Vaya a **Configuración del equipo\Plantillas administrativas\Componentes de Windows\Explorador de archivos**.
    
2. Haga doble clic en **Establecer un archivo de configuración de asociaciones predeterminadas**, establézcalo en **Habilitado** y especifique la ruta de acceso a AppAssoc.xml (por ejemplo: %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)
    
4. Aplique el GPO resultante vinculándolo al dominio correspondiente.
    
Los usuarios podrán cambiar el explorador después de establecer esta directiva.
  
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
    
Los usuarios podrán cambiar el explorador después de establecer esta directiva.