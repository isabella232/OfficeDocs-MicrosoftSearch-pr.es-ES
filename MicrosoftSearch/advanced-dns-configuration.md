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
# <a name="advanced-dns-configuration"></a>Configuración avanzada de DNS

Para asegurarse de Bing puede siempre identificar a los usuarios dentro de la organización y firmarlos correctamente su cuenta de trabajo o escuela, configurar su servidor DNS interno o un servidor proxy para resolver desde `www.bing.com` a `ms.bing.com`. Para ello, cree una entrada DNS para `www.bing.com` a ser un CNAME para `ms.bing.com`.
  
****

|**Nombre**|**Tipo**|**Valor**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
Uso de un CNAME en lugar de la dirección IP es preferido, ya que un CNAME seguirán funcionando si cambia la dirección IP. Después de realizar este cambio DNS, los resultados seguirán apareciendo a los usuarios como si proceden del `www.bing.com`. 
  
Esto no requiere ninguna configuración adicional en los equipos cliente y proporciona una experiencia transparente para los usuarios. Cuando vaya a `bing.com`, aquí se sesión automáticamente en más coherente y si no pueden iniciar sesión automáticamente, se pedirá que lo haga.
