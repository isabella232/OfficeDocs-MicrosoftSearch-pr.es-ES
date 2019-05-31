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
ROBOTS: NoIndex
description: Garantice una experiencia de inicio de sesión sin problemas para los usuarios mediante la configuración del servidor DNS con CNAME
ms.openlocfilehash: 6a291165df33f8acc99d247104e8e88cd35c3a0e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591363"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="29536-103">Configuración avanzada de DNS</span><span class="sxs-lookup"><span data-stu-id="29536-103">Advanced DNS configuration</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29536-104">Este artículo se aplica al portal de administración de Microsoft Search (Búsqueda de Microsoft) en Bing</span><span class="sxs-lookup"><span data-stu-id="29536-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="29536-105">Estamos moviendo el portal al Centro de administración de Microsoft 365 y después se eliminará.</span><span class="sxs-lookup"><span data-stu-id="29536-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="29536-106">Se recomienda utilizar el Centro de administración de Microsoft 365 para empezar.</span><span class="sxs-lookup"><span data-stu-id="29536-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="29536-107">[Introducción a Microsoft Search (Búsqueda de Microsoft)](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="29536-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="29536-p102">Para asegurarse de que Bing pueda identificar siempre a los usuarios de su organización e iniciar sesión correctamente en su cuenta profesional o educativa, configure su servidor DNS interno o el servidor proxy para resolverse de `www.bing.com` a `ms.bing.com`. Para ello, cree una entrada DNS para que `www.bing.com` sea un CNAME para `ms.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="29536-p102">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="29536-110">**Name**</span><span class="sxs-lookup"><span data-stu-id="29536-110">**Name**</span></span>|<span data-ttu-id="29536-111">**Type**</span><span class="sxs-lookup"><span data-stu-id="29536-111">**Type**</span></span>|<span data-ttu-id="29536-112">**Value**</span><span class="sxs-lookup"><span data-stu-id="29536-112">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="29536-113">CNAME</span><span class="sxs-lookup"><span data-stu-id="29536-113">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="29536-p103">Es preferible usar un CNAME en lugar de la dirección IP ya que un CNAME seguirá funcionando si cambia la dirección IP. Después de realizar este cambio de DNS, los resultados seguirán apareciendo como si procediesen de `www.bing.com` para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="29536-p103">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="29536-p104">Esto no requiere ninguna configuración adicional en los equipos de los clientes y proporciona una experiencia óptima para sus usuarios. Cuando vayan a `bing.com`, se iniciará sesión automáticamente de forma más coherente y si no se puede iniciar su sesión automáticamente, se les pedirá que lo hagan.</span><span class="sxs-lookup"><span data-stu-id="29536-p104">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
