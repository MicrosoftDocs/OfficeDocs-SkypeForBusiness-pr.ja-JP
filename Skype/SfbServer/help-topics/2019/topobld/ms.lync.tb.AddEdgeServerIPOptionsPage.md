---
title: エッジ サーバー IP 追加オプション
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server では、エッジ サーバーとエッジ プールのインターフェイスごとに IPv4 アドレスと IPv6 アドレスを構成できます。 これを行うには、次の操作を行います。
ms.openlocfilehash: f940e0480c51b1a2541386401a71f0d7d9818566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801077"
---
# <a name="add-edge-server-ip-options"></a>エッジ サーバー IP のオプション
 
Skype for Business Server では、エッジ サーバーとエッジ プールのインターフェイスごとに IPv4 アドレスと IPv6 アドレスを構成できます。 これを行うには、次の操作を行います。
  
- **内部インターフェイスで IPv4** を有効にする : エッジ サーバーまたはエッジ プールの内部インターフェイスに IPv4 アドレスを適用する場合は、このチェック ボックスをオンにします。
    
- **内部インターフェイスで IPv6** を有効にする : エッジ サーバーまたはエッジ プールの内部インターフェイスに IPv6 アドレスを適用する場合は、このチェック ボックスをオンにします。
    
- **外部インターフェイスで IPv4** を有効にする : エッジ サーバーまたはエッジ プールの外部インターフェイスに IPv4 アドレスを適用する場合は、このチェック ボックスをオンにします。
    
- **外部インターフェイスで IPv6** を有効にする : エッジ サーバーまたはエッジ プールの外部インターフェイスに IPv6 アドレスを適用する場合は、このチェック ボックスをオンにします。
    
外部 IP アドレスにネットワーク アドレス変換アドレスを使用するエッジ サーバーまたはエッジ プールを構成することもできます。 これを行うには、[**このエッジ プールの外部 IP アドレスは NAT を使用して変換されます**] チェック ボックスをオンにします。
  
NAT のサポート。ロード バランサー機器を使用している場合、ネットワーク アドレス変換 (NAT) はサポートされないため、ロード バランサー機器を使用するエッジ サーバー プールを展開している場合は、NAT オプションを選択しないでください。
  

