---
title: 'Lync Server 2013: メディアバイパスの計画'
description: 'Lync Server 2013: メディアバイパスの計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92a50d9d838b0f13fd6837cbfadee1c48712f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549443"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="9e840-103">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="9e840-103">Planning for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e840-104">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9e840-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9e840-105">メディア バイパスとは、信号が仲介サーバーを通過する通話について、可能な限りメディア パスから仲介サーバーを排除することです。</span><span class="sxs-lookup"><span data-stu-id="9e840-105">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="9e840-106">メディア バイパスにより、遅延、不要な変換、パケット損失の可能性、および潜在的な障害点の数を低減して、音声品質を向上できます。</span><span class="sxs-lookup"><span data-stu-id="9e840-106">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="9e840-107">バイパスされた通話のメディア処理がなくなり、仲介サーバーの負荷が軽減されるため、拡張性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="9e840-107">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="9e840-108">負荷の削減により、仲介サーバーが複数のゲートウェイを制御する機能が補完されます。</span><span class="sxs-lookup"><span data-stu-id="9e840-108">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="9e840-109">仲介サーバーのないブランチサイトが1つ以上の WAN リンクによって中央サイトに接続されている場合は、メディアのバイパスによって、ブランチサイトのクライアントから中央サイトの仲介サーバーへの直接移動を必要とせずに、そのローカルゲートウェイに直接移動できるようにすることで帯域幅の要件が減少します。</span><span class="sxs-lookup"><span data-stu-id="9e840-109">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="9e840-110">メディア処理から仲介サーバーを減らすことで、メディアバイパスがエンタープライズ Voip インフラストラクチャに必要な仲介サーバーの数を減らすこともあります。</span><span class="sxs-lookup"><span data-stu-id="9e840-110">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="9e840-111">次の図は、メディア バイパスを使用した場合と使用しない場合の、トポロジ内のメディアと信号の基本経路を示しています。</span><span class="sxs-lookup"><span data-stu-id="9e840-111">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="9e840-112">**メディア バイパスを使用した場合と使用しない場合の、メディアと信号の経路**</span><span class="sxs-lookup"><span data-stu-id="9e840-112">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="9e840-113">![音声 CAC メディアバイパス接続の強制](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "音声 CAC メディアバイパス接続の強制")</span><span class="sxs-lookup"><span data-stu-id="9e840-113">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="9e840-114">原則として、メディア バイパスを可能な限り有効にします。</span><span class="sxs-lookup"><span data-stu-id="9e840-114">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9e840-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9e840-115">In This Section</span></span>

  - [<span data-ttu-id="9e840-116">Lync Server 2013 でのメディアバイパスの概要</span><span class="sxs-lookup"><span data-stu-id="9e840-116">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="9e840-117">Lync Server 2013 のメディアバイパスモード</span><span class="sxs-lookup"><span data-stu-id="9e840-117">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="9e840-118">Lync Server 2013 でのメディアバイパスと通話受付管理</span><span class="sxs-lookup"><span data-stu-id="9e840-118">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="9e840-119">Lync Server 2013 でのメディアバイパスの技術要件</span><span class="sxs-lookup"><span data-stu-id="9e840-119">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="9e840-120">関連情報</span><span class="sxs-lookup"><span data-stu-id="9e840-120">Related Sections</span></span>

[<span data-ttu-id="9e840-121">Lync Server 2013 での高度なエンタープライズ Voip 機能の展開</span><span class="sxs-lookup"><span data-stu-id="9e840-121">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e840-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e840-122">See Also</span></span>


[<span data-ttu-id="9e840-123">Lync Server 2013 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="9e840-123">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="9e840-124">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="9e840-124">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

