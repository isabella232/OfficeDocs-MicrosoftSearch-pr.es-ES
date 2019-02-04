---
title: Probar el inicio de sesión único
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
description: Reduzca el número de veces que se solicita a los usuarios de Windows 10 que inicien sesión en Microsoft Search y Office 365
ms.openlocfilehash: 55d359edac36020ec8cf2aad6b64ca9737ee1066
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612365"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="d7c7b-103">Probar el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="d7c7b-103">Test single sign-on</span></span>

<span data-ttu-id="d7c7b-p101">El inicio de sesión único reduce el número de veces que se pide a los usuarios que inicien sesión. Las pruebas de inicio de sesión único con un pequeño grupo de usuarios le ayudará a identificar los problemas de configuración de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d7c7b-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="d7c7b-106">Para los usuarios de Chrome en Windows 10, el inicio de sesión único solo funcionará si la extensión de inicio de sesión de Windows 10 y AAD para Chrome está instalada.</span><span class="sxs-lookup"><span data-stu-id="d7c7b-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="d7c7b-107">Descargar la extensión de inicio de sesión de Windows 10 y AAD para Chrome</span><span class="sxs-lookup"><span data-stu-id="d7c7b-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="d7c7b-108">Le recomendamos que cree una directiva de grupo para instalar automáticamente esta extensión.</span><span class="sxs-lookup"><span data-stu-id="d7c7b-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="d7c7b-109">Vaya al portal de administración de Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="d7c7b-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="d7c7b-110">En el panel de navegación, haga clic en **Herramientas**</span><span class="sxs-lookup"><span data-stu-id="d7c7b-110">In the navigation pane, click **ADSI Edit**.</span></span>
    
3. <span data-ttu-id="d7c7b-111">En la lista de herramientas, descargue la **extensión de inicio de sesión de Windows 10 y AAD para Chrome**</span><span class="sxs-lookup"><span data-stu-id="d7c7b-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="d7c7b-112">Comparta la extensión con usuarios de Chrome en Windows 10</span><span class="sxs-lookup"><span data-stu-id="d7c7b-112">Share the extension with Chrome users on Windows 10</span></span>

  

