---
title: 'Lync Server 2013: メディアバイパスモード'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fe8133b5becc15d1ecbebfffe0e1314da97682a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="607ca-102">Lync Server 2013 のメディアバイパスモード</span><span class="sxs-lookup"><span data-stu-id="607ca-102">Media bypass modes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="607ca-103">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="607ca-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="607ca-p101">メディア バイパスには、グローバル レベルの構成と個々の PSTN トランクごとの構成が必要です。 メディア バイパスをグローバルで有効にする場合は、 [**常にバイパスする**] と [**サイトおよび地域情報の使用**] の 2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="607ca-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="607ca-p102">[**常にバイパスする**] では、その名のとおり、すべての PSTN 通話に対してバイパスが試みられます。 [**常にバイパスする**] は、通話受付管理を有効にする必要がない展開で使用されます。また、メディア バイパスを試行するタイミングに関する詳細な構成情報を指定する必要がない展開でも使用されます。 また、[**常にバイパスする**] は、クライアントと PSTN ゲートウェイ間に十分な接続がある場合にも使用されます。 この構成では、すべてのサブネットが、システムが計算する 1 つのバイパス ID だけにマップされます。</span><span class="sxs-lookup"><span data-stu-id="607ca-p102">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="607ca-p103">[**サイトおよび地域情報の使用**] では、バイパスの決定にサイトや地域の構成に関連付けられたバイパス ID が使用されます。 ほとんどの一般的なトポロジでは、この構成によりバイパス構成が柔軟になります。この構成では、バイパス発生のタイミングについて詳細なコントロールが可能であり、通話受付管理 (CAC) との対話もサポートされるからです。システムは、以下で説明するようにバイパス ID を自動で割り当てることで、タスクを容易にしようとします。</span><span class="sxs-lookup"><span data-stu-id="607ca-p103">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="607ca-113">システムは、各地域に一意のバイパス ID を自動で 1 つ割り当てます。</span><span class="sxs-lookup"><span data-stu-id="607ca-113">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="607ca-114">帯域幅制限のない WAN リンクを経由して地域に接続されるサイトはすべて、地域と同じバイパス ID を継承します。</span><span class="sxs-lookup"><span data-stu-id="607ca-114">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="607ca-115">帯域幅の制限のある WAN リンク経由で地域に関連付けられるサイトには、地域とは別のバイパス ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="607ca-115">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="607ca-116">各サイトに関連付けられるサブネットは、そのサイトのバイパス ID を継承します。</span><span class="sxs-lookup"><span data-stu-id="607ca-116">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="607ca-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="607ca-117">See Also</span></span>


[<span data-ttu-id="607ca-118">Lync Server 2013 でのメディアバイパスの概要</span><span class="sxs-lookup"><span data-stu-id="607ca-118">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="607ca-119">Lync Server 2013 でのメディアバイパスと通話受付管理</span><span class="sxs-lookup"><span data-stu-id="607ca-119">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="607ca-120">Lync Server 2013 でのメディアバイパスの技術要件</span><span class="sxs-lookup"><span data-stu-id="607ca-120">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

