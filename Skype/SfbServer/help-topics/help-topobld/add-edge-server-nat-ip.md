---
title: エッジ サーバーの NAT IP の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: '[パブリック IP アドレス] は、ネットワークアドレス変換 (NAT) で使用される IP アドレスです。 IP アドレスは、パブリックルーティング可能である必要があります。 このエッジプールの外部 IP アドレスは、このウィザードの [機能の選択] ページの [NAT オプションで変換されます] オプションを選択したためです。'
ms.openlocfilehash: f2e5a00b4e7c91f2343b9c917f6249d2ecee8930
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698402"
---
# <a name="add-edge-server-nat-ip"></a>エッジ サーバーの NAT IP の追加

[パブリック IP アドレス] は、ネットワークアドレス変換 (NAT) で使用される IP アドレスです。 IP アドレスは、パブリックルーティング可能である必要があります。 この**エッジプールの外部 IP アドレス**は、このウィザードの **[機能の選択**] ページの [NAT オプションで変換されます] オプションを選択したためです。

> [!NOTE]
> ネットワークアドレス変換 (NAT) を使用すると、プライベートネットワーク上のクライアントまたはサーバー (192.168.0.0 など) を使って、リモートネットワーク上のシステムとの通信をパブリックインターネットネットワーク経由で行うことができます。 NAT は、外部インターフェイスで単一のパブリック IP アドレスを使って、内部の IP アドレスを1つのパブリック IP アドレスに関連付けることによって動作します。 NAT マッピングは、内部アドレスを外部のパブリック IP アドレスにマップします。 リモートシステムには、ソースのパブリックアドレスのみが表示されます。 リモートシステムはソースに応答し、ソースは NAT マップを参照して、応答を返す必要がある内部 IP アドレスを特定します。

最初のトポロジの展開時やその後に、外部ユーザー アクセスのサポートを追加できます。既存のトポロジにエッジ サーバーを追加する方法の詳細については、「エッジ サーバーの展開」のドキュメントの「[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)」を参照してください。


