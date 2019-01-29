---
title: Configuración avanzada de DNS
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
description: Garantizar una experiencia de inicio de sesión de transparente para los usuarios mediante la configuración de su servidor DNS con un CNAME
ms.openlocfilehash: fa797b95f346d6d03bd020da146bb330c715e392
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612445"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="125fd-103">Configuración avanzada de DNS</span><span class="sxs-lookup"><span data-stu-id="125fd-103">Advanced DNS configuration</span></span>

<span data-ttu-id="125fd-p101">Para asegurarse de Bing puede siempre identificar a los usuarios dentro de la organización y firmarlos correctamente su cuenta de trabajo o escuela, configurar su servidor DNS interno o un servidor proxy para resolver desde `www.bing.com` a `ms.bing.com`. Para ello, cree una entrada DNS para `www.bing.com` a ser un CNAME para `ms.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="125fd-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="125fd-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="125fd-106">**Name**</span></span>|<span data-ttu-id="125fd-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="125fd-107">**Type**</span></span>|<span data-ttu-id="125fd-108">**Valor**</span><span class="sxs-lookup"><span data-stu-id="125fd-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="125fd-109">CNAME</span><span class="sxs-lookup"><span data-stu-id="125fd-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="125fd-p102">Uso de un CNAME en lugar de la dirección IP es preferido, ya que un CNAME seguirán funcionando si cambia la dirección IP. Después de realizar este cambio DNS, los resultados seguirán apareciendo a los usuarios como si proceden del `www.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="125fd-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="125fd-p103">Esto no requiere ninguna configuración adicional en los equipos cliente y proporciona una experiencia transparente para los usuarios. Cuando vaya a `bing.com`, aquí se sesión automáticamente en más coherente y si no pueden iniciar sesión automáticamente, se pedirá que lo haga.</span><span class="sxs-lookup"><span data-stu-id="125fd-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
