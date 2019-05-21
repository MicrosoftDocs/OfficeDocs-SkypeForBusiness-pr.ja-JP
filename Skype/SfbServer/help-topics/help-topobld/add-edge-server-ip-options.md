---
title: エッジ サーバー IP 追加オプション
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 では、エッジサーバーとエッジプールの各インターフェイスに対して IPv4 アドレスと IPv6 アドレスを構成することができます。 この操作を行うには、次の操作を行います。
ms.openlocfilehash: de0b0e0c050721a4fb54a450db89e34f65ea7f7f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293974"
---
# <a name="add-edge-server-ip-options"></a>エッジ サーバー IP 追加オプション
 
Microsoft Lync Server 2013 では、エッジサーバーとエッジプールの各インターフェイスに対して IPv4 アドレスと IPv6 アドレスを構成することができます。 この操作を行うには、次の操作を行います。
  
- **[内部インターフェイスで Ipv4 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。
    
- **[内部インターフェイスで Ipv6 を有効**にする]: ipv6 アドレスをエッジサーバーまたはエッジプールの内部インターフェイスに適用する場合は、このチェックボックスをオンにします。
    
- **[外部インターフェイスで Ipv4 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。
    
- **[外部インターフェイスで Ipv6 を有効**にする]: ipv6 アドレスをエッジサーバーまたはエッジプールの外部インターフェイスに適用する場合は、このチェックボックスをオンにします。
    
また、外部 IP アドレスにネットワークアドレス変換アドレスを使用するようにエッジサーバーまたはエッジプールを構成することもできます。 この操作を行うには、チェックボックスをオンにします。**このエッジプールの外部 IP アドレスは NAT によって変換され**ます。
  
NAT サポート。 ハードウェア負荷分散を使用している場合、ネットワークアドレス変換 (NAT) はサポートされていません。そのため、ハードウェア負荷分散でエッジサーバープールを展開している場合は、[NAT] オプションを選択しないでください。
  

