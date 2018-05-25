---
title: エッジ サーバーの NAT の IP を追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: パブリック IP アドレスは、ネットワーク アドレス変換 (NAT) によって使用される IP アドレスです。 IP アドレスをパブリック ルーティング可能にする必要があります。 この辺のプールは、このウィザードの [機能の選択] ページ上の NAT オプションで変換の外部 IP アドレスを選択するために必要です。
ms.openlocfilehash: 4bfbcb7d8859dc928c78c8e32b21604ef473317b
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="463a8-105">エッジ サーバーの NAT の IP を追加します。</span><span class="sxs-lookup"><span data-stu-id="463a8-105">Add Edge Server NAT IP</span></span>
 
<span data-ttu-id="463a8-106">パブリック IP アドレスは、ネットワーク アドレス変換 (NAT) によって使用される IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="463a8-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="463a8-107">IP アドレスをパブリック ルーティング可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="463a8-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="463a8-108">このウィザードの [**機能の選択**] ページで、**このエッジ プールの外部 IP アドレスが NAT によって変換**オプションを選択しているために必要です。</span><span class="sxs-lookup"><span data-stu-id="463a8-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>
  
> [!NOTE]
> <span data-ttu-id="463a8-109">ネットワーク アドレス変換 (NAT) により、クライアント、またはプライベート ネットワーク上のサーバー (たとえば、192.168.0.0 範囲) インターネットのパブリック ネットワーク経由でリモート ネットワーク上のシステムと通信するために。</span><span class="sxs-lookup"><span data-stu-id="463a8-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="463a8-110">NAT は、外部インターフェイスの 1 つのパブリック IP アドレスを使用して 1 つのパブリック IP アドレスと内部 IP アドレスを関連付けることによって動作します。</span><span class="sxs-lookup"><span data-stu-id="463a8-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="463a8-111">NAT マッピングでは、内部アドレスを外部のパブリック IP アドレスにマップします。</span><span class="sxs-lookup"><span data-stu-id="463a8-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="463a8-112">リモート システムには、元のパブリック アドレスのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="463a8-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="463a8-113">ソースをリモート システムが応答し、ソースへの応答を返す必要がどのような内部 IP アドレスを決定するのには NAT マップを参照しています。</span><span class="sxs-lookup"><span data-stu-id="463a8-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span> 
  
<span data-ttu-id="463a8-114">最初のトポロジの展開時やその後に、外部ユーザー アクセスのサポートを追加できます。</span><span class="sxs-lookup"><span data-stu-id="463a8-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="463a8-115">既存のトポロジにエッジ サーバーを追加する方法の詳細は、エッジ サーバーの展開に関するドキュメントの「[エッジ トポロジ定義](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463a8-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>
  

