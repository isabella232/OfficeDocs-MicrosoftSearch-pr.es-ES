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
ms.openlocfilehash: 05562bd9379af395ee305ffebdddbf7bfcd1e835
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727901"
---
# <a name="advanced-dns-configuration"></a>Configuración avanzada de DNS


Para asegurarse de que Bing pueda identificar siempre a los usuarios de su organización e iniciar sesión correctamente en su cuenta profesional o educativa, configure su servidor DNS interno o el servidor proxy para resolverse de `www.bing.com` a `ms.bing.com`. Para ello, cree una entrada DNS para que `www.bing.com` sea un CNAME para `ms.bing.com`.
  
****

|**Name**|**Type**|**Value**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
Es preferible usar un CNAME en lugar de la dirección IP ya que un CNAME seguirá funcionando si cambia la dirección IP. Después de realizar este cambio de DNS, los resultados seguirán apareciendo como si procediesen de `www.bing.com` para los usuarios. 
  
Esto no requiere ninguna configuración adicional en los equipos de los clientes y proporciona una experiencia óptima para sus usuarios. Cuando vayan a `bing.com`, se iniciará sesión automáticamente de forma más coherente y si no se puede iniciar su sesión automáticamente, se les pedirá que lo hagan.
