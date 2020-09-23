---
title: エッジ サーバーの NAT IP を追加する
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
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: パブリック IP アドレスは、ネットワーク アドレス変換 (NAT) で使用される IP アドレスです。 この IP アドレスがパブリック ルーティング可能であることが必要です。 これは、このウィザードの [機能の選択] ページで [NAT を使用してこのエッジ プールの外部 IP アドレスを変換する] オプションを選択したためです。
ms.openlocfilehash: 12749d3bcaec2478481fc1a4bc5597fb9693c5c4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216548"
---
# <a name="add-edge-server-nat-ip"></a>エッジ サーバーの NAT IP を追加する

パブリック IP アドレスは、ネットワーク アドレス変換 (NAT) で使用される IP アドレスです。この IP アドレスがパブリック ルーティング可能であることが必要です。これは、このウィザードの [**機能の選択**] ページで [**NAT を使用してこのエッジ プールの外部 IP アドレスを変換する**] オプションを選択したためです。

> [!NOTE]
> ネットワーク アドレス変換 (NAT) により、プライベート ネットワーク (たとえば 192.168.0.0 の範囲など) 上のクライアントやサーバーは、パブリック インターネット ネットワーク経由でリモート ネットワーク上のシステムと通信することができます。NAT は、外部インターフェイスの 1 つのパブリック IP アドレスを使用して、その 1 つのパブリック IP アドレスに内部 IP アドレスを関連付けることで機能します。NAT マッピングが内部アドレスを外部パブリック IP アドレスにマップします。リモート システムがソースのパブリック アドレスのみ認識します。リモート システムがソースに応答すると、ソースが NAT マップを参照し、応答を返す必要がある内部 IP アドレスを判断します。

最初のトポロジの展開時やその後に、外部ユーザー アクセスのサポートを追加できます。 既存のトポロジにエッジ サーバーを追加する方法の詳細については、「エッジ サーバーの展開」のドキュメントの「[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)」を参照してください。


