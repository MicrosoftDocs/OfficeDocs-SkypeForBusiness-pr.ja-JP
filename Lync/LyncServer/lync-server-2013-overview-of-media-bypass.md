---
title: 'Lync Server 2013: メディアバイパスの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d5cc3106ffaabd6aee985c225f6cc13fdd5fbb6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="8f1c4-102">Lync Server 2013 でのメディアバイパスの概要</span><span class="sxs-lookup"><span data-stu-id="8f1c4-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f1c4-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8f1c4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8f1c4-104">メディアバイパスは、展開する仲介サーバーの数を最小限に抑える場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="8f1c4-105">通常、仲介サーバープールは中央サイトに展開され、ブランチサイトのゲートウェイを制御します。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="8f1c4-106">メディアバイパスを有効にすると、ブランチサイトのクライアントからの公衆交換電話網 (PSTN) 通話のメディアを、それらのサイトのゲートウェイを介して直接流すことができます。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="8f1c4-107">Lync Server 2013 の発信通話ルートとエンタープライズ音声ポリシーを適切に構成して、ブランチサイトのクライアントからの PSTN 通話を適切なゲートウェイにルーティングできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="8f1c4-108">通常、wi-fi ネットワークでは、有線ネットワークよりも多くのパケット損失が発生します。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-108">Wi-Fi networks typically experience more packet loss than wired networks.</span></span> <span data-ttu-id="8f1c4-109">このパケット損失からの回復は、通常、ゲートウェイで対応可能なものではありません。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-109">Recovery from this packet loss is not typically something that can be accommodated by gateways.</span></span> <span data-ttu-id="8f1c4-110">そのため、ワイヤレスサブネットに対してバイパスを有効にする必要があるかどうかを判断する前に、Wi-fi ネットワークの品質を評価することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-110">Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet.</span></span> <span data-ttu-id="8f1c4-111">待機時間の短縮と、パケット損失からの復旧についても考慮されています。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-111">There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well.</span></span> <span data-ttu-id="8f1c4-112">RTAudio は、仲介サーバーをバイパスしない通話で利用できるコーデックで、パケット損失を処理するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-112">RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="8f1c4-113">エンタープライズ Voip 構造が整ったら、メディアバイパスの計画は簡単です。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="8f1c4-114">ブランチサイトへの WAN リンクを含まない集中管理トポロジの場合は、微調整された制御は必要ないため、グローバルメディアバイパスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="8f1c4-115">1つまたは複数のネットワーク地域とその関連ブランチサイトで構成される分散トポロジを使用している場合は、次のことを決定します。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="8f1c4-116">仲介サーバーのピアが、メディアバイパスに必要な機能をサポートできるかどうか。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="8f1c4-117">各ネットワーク地域のどのサイトが適切に接続されているか。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="8f1c4-118">ネットワークにとって、メディアバイパスと通話受付管理のどの組み合わせが適切か。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="8f1c4-119">メディアバイパスを有効にすると、ネットワーク地域、およびその地域内の帯域幅制限のないすべてのネットワークサイトに対して、一意のバイパス ID が自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-119">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region.</span></span> <span data-ttu-id="8f1c4-120">地域内の帯域幅制限があるサイト、および帯域幅制限がある WAN リンクを介して地域に接続されたサイトには、それぞれ固有の一意のバイパス Id が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-120">Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="8f1c4-121">ユーザーが PSTN を呼び出すと、仲介サーバーはクライアントサブネットのバイパス ID とゲートウェイサブネットのバイパス ID を比較します。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="8f1c4-122">2つのバイパス Id が一致する場合、通話でメディアバイパスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="8f1c4-123">バイパス Id が一致しない場合は、通話のメディアが仲介サーバーを経由して流れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="8f1c4-124">ユーザーが PSTN から通話を受信すると、ユーザーのクライアントはそのバイパス ID を PSTN ゲートウェイのバイパス ID と比較します。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="8f1c4-125">2つのバイパス Id が一致する場合、メディアは、仲介サーバーをバイパスして、ゲートウェイからクライアントに直接送られます。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="8f1c4-126">Lync 2010 またはそれ以上のクライアントとデバイスのみが、仲介サーバーとメディアバイパスの対話をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8f1c4-127">メディアバイパスをグローバルに有効にするだけでなく、各 PSTN トランクでメディアバイパスを個別に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-127">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk.</span></span> <span data-ttu-id="8f1c4-128">バイパスがグローバルに有効になっているが、特定の PSTN トランクに対して有効になっていない場合は、その PSTN トランクを含むすべての呼び出しに対してメディアバイパスが呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-128">If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk.</span></span> <span data-ttu-id="8f1c4-129">また、メディアバイパスが<STRONG>サイトと地域の情報を使用</STRONG>するように設定されている場合は、ルーティング可能なすべてのサブネットを、それらが配置されているサイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-129">In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located.</span></span> <span data-ttu-id="8f1c4-130">バイパスが必要ないサイト内にルーティング可能なサブネットがある場合は、メディアバイパスを有効にする前に、これらのサブネットを新しいサイト内でグループ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-130">If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass.</span></span> <span data-ttu-id="8f1c4-131">これにより、unroutable サブネットに異なるバイパス ID が割り当てられるようになります。</span><span class="sxs-lookup"><span data-stu-id="8f1c4-131">Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8f1c4-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f1c4-132">See Also</span></span>


[<span data-ttu-id="8f1c4-133">Lync Server 2013 のメディアバイパスモード</span><span class="sxs-lookup"><span data-stu-id="8f1c4-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="8f1c4-134">Lync Server 2013 でのメディアバイパスと通話受付管理</span><span class="sxs-lookup"><span data-stu-id="8f1c4-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="8f1c4-135">Lync Server 2013 でのメディアバイパスの技術要件</span><span class="sxs-lookup"><span data-stu-id="8f1c4-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

