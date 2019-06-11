---
title: 'Lync Server 2013: メディアのバイパスの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04bc9dfa250bc399f10a56ef58f78462044f5cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="0f220-102">Lync Server 2013 でのメディアのバイパスの概要</span><span class="sxs-lookup"><span data-stu-id="0f220-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f220-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0f220-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0f220-104">メディアのバイパスは、展開されている仲介サーバーの数を最小化する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="0f220-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="0f220-105">通常、仲介サーバープールはセントラルサイトに展開され、ブランチサイトでのゲートウェイを制御します。</span><span class="sxs-lookup"><span data-stu-id="0f220-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="0f220-106">メディア バイパスを有効にすると、ブランチ サイトのクライアントからの公衆交換電話網 (PSTN) 通話のメディアが、そのブランチ サイトのゲートウェイを直接通過することができます。</span><span class="sxs-lookup"><span data-stu-id="0f220-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="0f220-107">支社サイトのクライアントからの PSTN 通話が適切なゲートウェイにルーティングされるように、Lync Server 2013 の発信通話ルーティングとエンタープライズボイスポリシーを適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f220-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="0f220-p102">Wi-Fi ネットワークでは、一般に、有線ネットワークに比べ、パケット損失の数が多くなります。このパケット損失からの復元は、通常、ゲートウェイが対応できるようなものではありません。このため、無線サブネットに対してバイパスを有効にするかどうかを決定する際は、その前に、Wi-Fi ネットワークの品質を評価することをお勧めします。また、遅延を減らそうとすればパケット損失からの復元が困難になり、パケット損失からの復元を重視すれば遅延が増えます。この 2 つの要素の妥協点も検討してください。RTAudio は、仲介サーバーをバイパスしない通話で使用できるコーデックです。パケット損失の処理には、この RTAudio が適しています。</span><span class="sxs-lookup"><span data-stu-id="0f220-p102">Wi-Fi networks typically experience more packet loss than wired networks. Recovery from this packet loss is not typically something that can be accommodated by gateways. Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet. There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well. RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="0f220-113">エンタープライズ Voip 構造が整ったら、メディアのバイパス計画を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0f220-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="0f220-114">ブランチ サイトへの WAN リンクを含まない集中管理トポロジの場合は、細かい制御は必要ないため、グローバル メディア バイパスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f220-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="0f220-115">1 つまたは複数のネットワーク地域とその地域と連携するブランチ サイトで構成される分散トポロジの場合は、次の点を判断してください。</span><span class="sxs-lookup"><span data-stu-id="0f220-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="0f220-116">仲介サーバーのピアが、メディア バイパスで必要な処理能力をサポートできるかどうか。</span><span class="sxs-lookup"><span data-stu-id="0f220-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="0f220-117">各ネットワーク地域の中のどのサイトの接続状況が良好か。</span><span class="sxs-lookup"><span data-stu-id="0f220-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="0f220-118">ネットワークにとって、メディア バイパスと通話受付管理のどの組み合わせが適切か。</span><span class="sxs-lookup"><span data-stu-id="0f220-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="0f220-p103">メディア バイパスを有効にすると、ネットワーク地域およびその地域内の帯域幅制限のないすべてのネットワーク サイトに対して、一意のバイパス ID が自動で生成されます。地域内の帯域幅制限があるサイトや帯域幅制限がある WAN リンク経由で地域に接続されているサイトには、それぞれ、一意の専用バイパス ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0f220-p103">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region. Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="0f220-121">ユーザーが PSTN に通話を発信すると、仲介サーバーはクライアントサブネットのバイパス ID とゲートウェイサブネットのバイパス ID を比較します。</span><span class="sxs-lookup"><span data-stu-id="0f220-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="0f220-122">2 つのバイパス ID が一致すると、その通話にはメディア バイパスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f220-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="0f220-123">バイパス Id が一致しない場合、通話のメディアは仲介サーバー経由で流れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f220-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="0f220-124">ユーザーが PSTN からの通話を受信すると、ユーザーのクライアントがそのバイパス ID を PSTN ゲートウェイのバイパス ID と比較します。</span><span class="sxs-lookup"><span data-stu-id="0f220-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="0f220-125">この2つの Id が一致している場合、メディアは、仲介サーバーを経由せずにゲートウェイからクライアントに直接送られます。</span><span class="sxs-lookup"><span data-stu-id="0f220-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="0f220-126">Lync 2010 以上のクライアントとデバイスでのみ、仲介サーバーとの対話式操作をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0f220-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f220-p106">メディア バイパスをグローバルで有効にすることに加え、PSTN トランクごとに個別に有効にする必要もあります。バイパスがグローバルでは有効になっているが、特定の PSTN トランクに対しては有効になっていない場合、その PSTN トランクが関わる通話に対してはメディア バイパスは起動されません。また、メディア バイパスが [<STRONG>サイトおよび地域情報の使用</STRONG>] に設定されている場合は、ルーティング可能なすべてのサブネットをそのサブネットが配置されているサイトに関連付ける必要があります。バイパスが必要ないサイト内部にルーティング可能なサブネットがある場合、新しいサイトを作りこれらのサブネットをその中にまとめてから、メディア バイパスを有効にしてください。そうすることで、ルーティングが不可能なサブネットに別のバイパス ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0f220-p106">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk. If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk. In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located. If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass. Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f220-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f220-132">See Also</span></span>


[<span data-ttu-id="0f220-133">Lync Server 2013 のメディア バイパス モード</span><span class="sxs-lookup"><span data-stu-id="0f220-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="0f220-134">Lync Server 2013 でのメディア バイパスと通話受付管理</span><span class="sxs-lookup"><span data-stu-id="0f220-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="0f220-135">Lync Server 2013 メディア バイパスの技術要件</span><span class="sxs-lookup"><span data-stu-id="0f220-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

