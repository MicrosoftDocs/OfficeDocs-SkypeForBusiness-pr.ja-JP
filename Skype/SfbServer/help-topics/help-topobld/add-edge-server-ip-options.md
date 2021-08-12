---
title: エッジ サーバー IP 追加オプション
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Microsoft Lync Server 2013 では、エッジ サーバーとエッジ プールのインターフェイスごとに IPv4 アドレスと IPv6 アドレスを構成できます。 これを行うには、次の操作を行います。
ms.openlocfilehash: 713c5030b0ca39555c57bb5ae0d36f873701c54181b46cb845d75012b3a81b65
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284867"
---
# <a name="add-edge-server-ip-options"></a>エッジ サーバー IP のオプション
 
Microsoft Lync Server 2013 では、エッジ サーバーとエッジ プールのインターフェイスごとに IPv4 アドレスと IPv6 アドレスを構成できます。 これを行うには、次の操作を行います。
  
- **内部インターフェイスで IPv4 を** 有効にする: エッジ サーバーまたはエッジ プールの内部インターフェイスに IPv4 アドレスを適用する場合は、チェック ボックスをオンにします。
    
- **内部インターフェイスで IPv6** を有効にする: エッジ サーバーまたはエッジ プールの内部インターフェイスに IPv6 アドレスを適用する場合は、チェック ボックスをオンにします。
    
- **外部インターフェイスで IPv4 を** 有効にする: エッジ サーバーまたはエッジ プールの外部インターフェイスに IPv4 アドレスを適用する場合は、チェック ボックスをオンにします。
    
- **外部インターフェイスで IPv6** を有効にする: エッジ サーバーまたはエッジ プールの外部インターフェイスに IPv6 アドレスを適用する場合は、チェック ボックスをオンにします。
    
外部 IP アドレスにネットワーク アドレス変換アドレスを使用するエッジ サーバーまたはエッジ プールを構成することもできます。 これを行うには、[**このエッジ プールの外部 IP アドレスは NAT を使用して変換されます**] チェック ボックスをオンにします。
  
NAT のサポート。ロード バランサー機器を使用している場合、ネットワーク アドレス変換 (NAT) はサポートされないため、ロード バランサー機器を使用するエッジ サーバー プールを展開している場合は、NAT オプションを選択しないでください。
  

