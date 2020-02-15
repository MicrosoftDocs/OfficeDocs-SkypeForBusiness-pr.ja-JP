---
title: 'Lync Server 2013: メディアバイパスの計画'
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
ms.openlocfilehash: 0bb4d495637cd78e430e975e9831421906bfbf6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="4ea0f-102">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="4ea0f-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ea0f-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4ea0f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4ea0f-104">メディア バイパスとは、信号が仲介サーバーを通過する通話について、可能な限りメディア パスから仲介サーバーを排除することです。</span><span class="sxs-lookup"><span data-stu-id="4ea0f-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="4ea0f-105">メディア バイパスにより、遅延、不要な変換、パケット損失の可能性、および潜在的な障害点の数を低減して、音声品質を向上できます。</span><span class="sxs-lookup"><span data-stu-id="4ea0f-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="4ea0f-106">バイパスされた通話のメディア処理がなくなり、仲介サーバーの負荷が軽減されるため、拡張性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="4ea0f-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="4ea0f-107">負荷の削減により、仲介サーバーが複数のゲートウェイを制御する機能が補完されます。</span><span class="sxs-lookup"><span data-stu-id="4ea0f-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="4ea0f-108">仲介サーバーのないブランチサイトが、帯域幅が制限された1つまたは複数の WAN リンクによって中央サイトに接続されている場合、メディアバイパスにより、ブランチサイトのクライアントからのメディアをローカルゲートウェイに直接流すことができるため、帯域幅の要件が減少します。最初に、WAN リンクを中央サイトの仲介サーバーに転送し、バックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ea0f-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="4ea0f-109">メディア処理から仲介サーバーを減らすことで、メディアバイパスがエンタープライズ Voip インフラストラクチャに必要な仲介サーバーの数を減らすこともあります。</span><span class="sxs-lookup"><span data-stu-id="4ea0f-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="4ea0f-110">次の図は、メディア バイパスを使用した場合と使用しない場合の、トポロジ内のメディアと信号の基本経路を示しています。</span><span class="sxs-lookup"><span data-stu-id="4ea0f-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="4ea0f-111">**メディア バイパスを使用した場合と使用しない場合の、メディアと信号の経路**</span><span class="sxs-lookup"><span data-stu-id="4ea0f-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="4ea0f-112">![音声 CAC メディアバイパス接続の強制](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "音声 CAC メディアバイパス接続の強制")</span><span class="sxs-lookup"><span data-stu-id="4ea0f-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="4ea0f-113">原則として、メディア バイパスを可能な限り有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ea0f-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4ea0f-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4ea0f-114">In This Section</span></span>

  - [<span data-ttu-id="4ea0f-115">Lync Server 2013 でのメディアバイパスの概要</span><span class="sxs-lookup"><span data-stu-id="4ea0f-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="4ea0f-116">Lync Server 2013 のメディアバイパスモード</span><span class="sxs-lookup"><span data-stu-id="4ea0f-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="4ea0f-117">Lync Server 2013 でのメディアバイパスと通話受付管理</span><span class="sxs-lookup"><span data-stu-id="4ea0f-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="4ea0f-118">Lync Server 2013 でのメディアバイパスの技術要件</span><span class="sxs-lookup"><span data-stu-id="4ea0f-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="4ea0f-119">関連情報</span><span class="sxs-lookup"><span data-stu-id="4ea0f-119">Related Sections</span></span>

[<span data-ttu-id="4ea0f-120">Lync Server 2013 での高度なエンタープライズ Voip 機能の展開</span><span class="sxs-lookup"><span data-stu-id="4ea0f-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ea0f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ea0f-121">See Also</span></span>


[<span data-ttu-id="4ea0f-122">Lync Server 2013 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="4ea0f-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="4ea0f-123">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="4ea0f-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

