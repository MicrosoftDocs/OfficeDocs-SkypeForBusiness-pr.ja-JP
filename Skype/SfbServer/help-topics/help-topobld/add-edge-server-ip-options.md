---
title: エッジ サーバー IP 追加オプション
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 では、エッジサーバーとエッジプールの各インターフェイスに対して IPv4 アドレスと IPv6 アドレスを構成できます。 これを行うには、次の操作を行います。
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219792"
---
# <a name="add-edge-server-ip-options"></a>エッジ サーバー IP 追加オプション
 
Microsoft Lync Server 2013 では、エッジサーバーとエッジプールの各インターフェイスに対して IPv4 アドレスと IPv6 アドレスを構成できます。 これを行うには、次の操作を行います。
  
- **[内部インターフェイスで ipv4 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。
    
- **[内部インターフェイスで Ipv6 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv6 アドレスを適用する場合は、このチェックボックスをオンにします。
    
- **[外部インターフェイスで ipv4 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。
    
- **[外部インターフェイスで Ipv6 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv6 アドレスを適用する場合は、このチェックボックスをオンにします。
    
また、外部 IP アドレスにネットワークアドレス変換アドレスを使用するようにエッジサーバーまたはエッジプールを構成することもできます。 これを行うには、[**このエッジ プールの外部 IP アドレスは NAT を使用して変換されます**] チェック ボックスをオンにします。
  
NAT のサポート。ロード バランサー機器を使用している場合、ネットワーク アドレス変換 (NAT) はサポートされないため、ロード バランサー機器を使用するエッジ サーバー プールを展開している場合は、NAT オプションを選択しないでください。
  

