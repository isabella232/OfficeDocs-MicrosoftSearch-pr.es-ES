---
title: Probar el inicio de sesión único
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
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
description: Reduzca el número de veces que se solicita a los usuarios de Windows 10 que inicien sesión en Microsoft Search y Office 365
ms.openlocfilehash: 9fa7e067a5d72b7044981491f8526e6de727cfae
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626895"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="26594-103">Probar el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="26594-103">Test single sign-on</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26594-104">Este artículo se aplica al portal de administración de Búsqueda de Microsoft en Bing</span><span class="sxs-lookup"><span data-stu-id="26594-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="26594-105">Estamos pasando el portal al Centro de administración de Microsoft 365. Luego, se quitará el portal de Búsqueda de Microsoft en Bing.</span><span class="sxs-lookup"><span data-stu-id="26594-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="26594-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="26594-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="26594-107">[Introducción a Microsoft Search (Búsqueda de Microsoft)](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="26594-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="26594-p102">El inicio de sesión único reduce el número de veces que se pide a los usuarios que inicien sesión. Las pruebas de inicio de sesión único con un pequeño grupo de usuarios le ayudará a identificar los problemas de configuración de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="26594-p102">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="26594-110">Para los usuarios de Chrome en Windows 10, el inicio de sesión único solo funcionará si la extensión de inicio de sesión de Windows 10 y AAD para Chrome está instalada.</span><span class="sxs-lookup"><span data-stu-id="26594-110">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="26594-111">Descargar la extensión de inicio de sesión de Windows 10 y AAD para Chrome</span><span class="sxs-lookup"><span data-stu-id="26594-111">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="26594-112">Le recomendamos que cree una directiva de grupo para instalar automáticamente esta extensión.</span><span class="sxs-lookup"><span data-stu-id="26594-112">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="26594-113">Vaya al portal de administración de Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="26594-113">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="26594-114">En el panel de navegación, haga clic en **Herramientas**</span><span class="sxs-lookup"><span data-stu-id="26594-114">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="26594-115">En la lista de herramientas, descargue la **extensión de inicio de sesión de Windows 10 y AAD para Chrome**</span><span class="sxs-lookup"><span data-stu-id="26594-115">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="26594-116">Comparta la extensión con usuarios de Chrome en Windows 10</span><span class="sxs-lookup"><span data-stu-id="26594-116">Share the extension with Chrome users on Windows 10</span></span>

  

