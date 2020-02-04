---
title: 'Lync Server 2013: メディア バイパスの計画'
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
ms.openlocfilehash: 97b28559ea58439d370042d54ab7ef58943bc594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="2082d-102">Lync Server 2013 でのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="2082d-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2082d-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2082d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2082d-104">メディアバイパスは、可能な限りメディアパスから仲介サーバーを削除します。これは、シグナルが仲介サーバーを通過する呼び出しに対して可能です。</span><span class="sxs-lookup"><span data-stu-id="2082d-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="2082d-105">メディア バイパスにより、遅延、不要な変換、パケット損失の可能性、および潜在的な障害点の数を低減して、音声品質を向上できます。</span><span class="sxs-lookup"><span data-stu-id="2082d-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="2082d-106">回避された通話のメディア処理を排除することで、仲介サーバーにかかる負荷が減るため、スケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="2082d-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="2082d-107">この負荷の削減は、複数のゲートウェイを制御する仲介サーバーの機能を補完します。</span><span class="sxs-lookup"><span data-stu-id="2082d-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="2082d-108">仲介サーバーのないブランチサイトが1つまたは複数の WAN リンクによって中央サイトに接続されていて、帯域幅が制限されている場合、メディアのバイパスによって、ブランチサイトのクライアントからのメディアをローカルゲートウェイに直接流し込むことができます。まず、WAN リンクを中央サイトの仲介サーバーに移動して、戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="2082d-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="2082d-109">メディアの処理から仲介サーバーを削減することで、エンタープライズ Voip インフラストラクチャで必要な仲介サーバーの数を減らすこともできます。</span><span class="sxs-lookup"><span data-stu-id="2082d-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="2082d-110">次の図は、メディア バイパスを使用した場合と使用しない場合の、トポロジ内のメディアと信号の基本経路を示しています。</span><span class="sxs-lookup"><span data-stu-id="2082d-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="2082d-111">**メディア バイパスを使用した場合と使用しない場合の、メディアと信号の経路**</span><span class="sxs-lookup"><span data-stu-id="2082d-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="2082d-112">![音声 CAC メディア バイパス接続の適用](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "音声 CAC メディア バイパス接続の適用")</span><span class="sxs-lookup"><span data-stu-id="2082d-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="2082d-113">原則として、メディア バイパスを可能な限り有効にします。</span><span class="sxs-lookup"><span data-stu-id="2082d-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2082d-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="2082d-114">In This Section</span></span>

  - [<span data-ttu-id="2082d-115">Lync Server 2013 でのメディアのバイパスの概要</span><span class="sxs-lookup"><span data-stu-id="2082d-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="2082d-116">Lync Server 2013 のメディア バイパス モード</span><span class="sxs-lookup"><span data-stu-id="2082d-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="2082d-117">Lync Server 2013 でのメディア バイパスと通話受付管理</span><span class="sxs-lookup"><span data-stu-id="2082d-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="2082d-118">Lync Server 2013 メディア バイパスの技術要件</span><span class="sxs-lookup"><span data-stu-id="2082d-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="2082d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="2082d-119">Related Sections</span></span>

[<span data-ttu-id="2082d-120">Lync Server 2013 での高度なエンタープライズ Voip 機能の展開</span><span class="sxs-lookup"><span data-stu-id="2082d-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2082d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="2082d-121">See Also</span></span>


[<span data-ttu-id="2082d-122">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2082d-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="2082d-123">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="2082d-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

