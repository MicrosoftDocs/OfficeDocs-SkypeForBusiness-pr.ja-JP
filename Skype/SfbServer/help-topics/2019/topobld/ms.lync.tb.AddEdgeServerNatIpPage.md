---
title: エッジ サーバーの NAT の IP を追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: パブリック IP アドレスは、ネットワーク アドレス変換 (NAT) によって使用される IP アドレスです。 IP アドレスをパブリック ルーティング可能にする必要があります。 この辺のプールは、このウィザードの [機能の選択] ページ上の NAT オプションで変換の外部 IP アドレスを選択するために必要です。
ms.openlocfilehash: ee4a2d12d44e17c3219395174451f00db7674e76
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21059291"
---
# <a name="add-edge-server-nat-ip"></a>エッジ サーバーの NAT の IP を追加します。
 
パブリック IP アドレスは、ネットワーク アドレス変換 (NAT) によって使用される IP アドレスです。 IP アドレスをパブリック ルーティング可能にする必要があります。 このウィザードの [**機能の選択**] ページで、**このエッジ プールの外部 IP アドレスが NAT によって変換**オプションを選択しているために必要です。
  
> [!NOTE]
> ネットワーク アドレス変換 (NAT) により、クライアント、またはプライベート ネットワーク上のサーバー (たとえば、192.168.0.0 範囲) インターネットのパブリック ネットワーク経由でリモート ネットワーク上のシステムと通信するために。 NAT は、外部インターフェイスの 1 つのパブリック IP アドレスを使用して 1 つのパブリック IP アドレスと内部 IP アドレスを関連付けることによって動作します。 NAT マッピングでは、内部アドレスを外部のパブリック IP アドレスにマップします。 リモート システムには、元のパブリック アドレスのみが表示されます。 ソースをリモート システムが応答し、ソースへの応答を返す必要がどのような内部 IP アドレスを決定するのには NAT マップを参照しています。 
  
最初のトポロジの展開時やその後に、外部ユーザー アクセスのサポートを追加できます。 既存のトポロジにエッジ サーバーを追加する方法の詳細は、エッジ サーバーの展開に関するドキュメントの「[エッジ トポロジ定義](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)を参照してください。
  

