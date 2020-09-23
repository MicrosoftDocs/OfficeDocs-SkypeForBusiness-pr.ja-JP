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
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="043ae-105">エッジ サーバーの NAT IP を追加する</span><span class="sxs-lookup"><span data-stu-id="043ae-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="043ae-p102">パブリック IP アドレスは、ネットワーク アドレス変換 (NAT) で使用される IP アドレスです。この IP アドレスがパブリック ルーティング可能であることが必要です。これは、このウィザードの [**機能の選択**] ページで [**NAT を使用してこのエッジ プールの外部 IP アドレスを変換する**] オプションを選択したためです。</span><span class="sxs-lookup"><span data-stu-id="043ae-p102">The public IP address is the IP address that is used by network address translation (NAT). The IP address must be publicly routable. This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="043ae-p103">ネットワーク アドレス変換 (NAT) により、プライベート ネットワーク (たとえば 192.168.0.0 の範囲など) 上のクライアントやサーバーは、パブリック インターネット ネットワーク経由でリモート ネットワーク上のシステムと通信することができます。NAT は、外部インターフェイスの 1 つのパブリック IP アドレスを使用して、その 1 つのパブリック IP アドレスに内部 IP アドレスを関連付けることで機能します。NAT マッピングが内部アドレスを外部パブリック IP アドレスにマップします。リモート システムがソースのパブリック アドレスのみ認識します。リモート システムがソースに応答すると、ソースが NAT マップを参照し、応答を返す必要がある内部 IP アドレスを判断します。</span><span class="sxs-lookup"><span data-stu-id="043ae-p103">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks. NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address. NAT mapping maps an internal address to the external public IP address. The remote system sees only the public address of the source. The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="043ae-114">最初のトポロジの展開時やその後に、外部ユーザー アクセスのサポートを追加できます。</span><span class="sxs-lookup"><span data-stu-id="043ae-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="043ae-115">既存のトポロジにエッジ サーバーを追加する方法の詳細については、「エッジ サーバーの展開」のドキュメントの「[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="043ae-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


