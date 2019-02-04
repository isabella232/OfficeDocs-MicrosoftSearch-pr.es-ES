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
description: Garantice una experiencia de inicio de sesión sin problemas para los usuarios mediante la configuración del servidor DNS con CNAME
ms.openlocfilehash: fa797b95f346d6d03bd020da146bb330c715e392
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612445"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="c9d4b-103">Configuración avanzada de DNS</span><span class="sxs-lookup"><span data-stu-id="c9d4b-103">Advanced DNS configuration</span></span>

<span data-ttu-id="c9d4b-p101">Para asegurarse de que Bing pueda identificar siempre a los usuarios de su organización e iniciar sesión correctamente en su cuenta profesional o educativa, configure su servidor DNS interno o el servidor proxy para resolverse de `www.bing.com` a `ms.bing.com`. Para ello, cree una entrada DNS para que `www.bing.com` sea un CNAME para `ms.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="c9d4b-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="c9d4b-106">**Name**</span><span class="sxs-lookup"><span data-stu-id="c9d4b-106">**Name**</span></span>|<span data-ttu-id="c9d4b-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="c9d4b-107">**Type**</span></span>|<span data-ttu-id="c9d4b-108">**Value**</span><span class="sxs-lookup"><span data-stu-id="c9d4b-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="c9d4b-109">CNAME</span><span class="sxs-lookup"><span data-stu-id="c9d4b-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="c9d4b-p102">Es preferible usar un CNAME en lugar de la dirección IP ya que un CNAME seguirá funcionando si cambia la dirección IP. Después de realizar este cambio de DNS, los resultados seguirán apareciendo como si procediesen de `www.bing.com` para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c9d4b-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="c9d4b-p103">Esto no requiere ninguna configuración adicional en los equipos de los clientes y proporciona una experiencia óptima para sus usuarios. Cuando vayan a `bing.com`, se iniciará sesión automáticamente de forma más coherente y si no se puede iniciar su sesión automáticamente, se les pedirá que lo hagan.</span><span class="sxs-lookup"><span data-stu-id="c9d4b-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
