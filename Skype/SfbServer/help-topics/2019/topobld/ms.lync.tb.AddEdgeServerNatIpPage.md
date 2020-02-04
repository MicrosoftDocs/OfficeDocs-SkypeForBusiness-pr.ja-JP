---
title: エッジ サーバーの NAT IP の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: '[パブリック IP アドレス] は、ネットワークアドレス変換 (NAT) で使用される IP アドレスです。 IP アドレスは、パブリックルーティング可能である必要があります。 このエッジプールの外部 IP アドレスは、このウィザードの [機能の選択] ページの [NAT オプションで変換されます] オプションを選択したためです。'
ms.openlocfilehash: f06d9b61d5ffad29d24e143cf3afbbc4501a67d4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689416"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="ff4ca-105">エッジ サーバーの NAT IP の追加</span><span class="sxs-lookup"><span data-stu-id="ff4ca-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="ff4ca-106">[パブリック IP アドレス] は、ネットワークアドレス変換 (NAT) で使用される IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="ff4ca-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="ff4ca-107">IP アドレスは、パブリックルーティング可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff4ca-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="ff4ca-108">この**エッジプールの外部 IP アドレス**は、このウィザードの **[機能の選択**] ページの [NAT オプションで変換されます] オプションを選択したためです。</span><span class="sxs-lookup"><span data-stu-id="ff4ca-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="ff4ca-109">ネットワークアドレス変換 (NAT) を使用すると、プライベートネットワーク上のクライアントまたはサーバー (192.168.0.0 など) を使って、リモートネットワーク上のシステムとの通信をパブリックインターネットネットワーク経由で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ff4ca-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="ff4ca-110">NAT は、外部インターフェイスで単一のパブリック IP アドレスを使って、内部の IP アドレスを1つのパブリック IP アドレスに関連付けることによって動作します。</span><span class="sxs-lookup"><span data-stu-id="ff4ca-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="ff4ca-111">NAT マッピングは、内部アドレスを外部のパブリック IP アドレスにマップします。</span><span class="sxs-lookup"><span data-stu-id="ff4ca-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="ff4ca-112">リモートシステムには、ソースのパブリックアドレスのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff4ca-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="ff4ca-113">リモートシステムはソースに応答し、ソースは NAT マップを参照して、応答を返す必要がある内部 IP アドレスを特定します。</span><span class="sxs-lookup"><span data-stu-id="ff4ca-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="ff4ca-p104">最初のトポロジの展開時やその後に、外部ユーザー アクセスのサポートを追加できます。既存のトポロジにエッジ サーバーを追加する方法の詳細については、「エッジ サーバーの展開」のドキュメントの「[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff4ca-p104">You can add support for external user access when you deploy your initial topology or afterward. For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


