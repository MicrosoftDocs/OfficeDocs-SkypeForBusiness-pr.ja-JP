---
title: 'Lync Server 2013: メディア バイパスと仲介サーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524c0f2556eec339b6698f156966ea95538dbaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="4dce1-102">Lync Server 2013 のメディア バイパスと仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="4dce1-102">Media bypass and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dce1-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4dce1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4dce1-104">メディアのバイパスは、管理者がユーザーのエンドポイントと公衆交換電話網 (PSTN) ゲートウェイの間で直接流れるようにするための Lync Server の機能です。</span><span class="sxs-lookup"><span data-stu-id="4dce1-104">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="4dce1-105">メディアのバイパスでは、待ち時間の削減、不必要な翻訳、パケット損失の可能性、および潜在的な障害ポイントの数によって通話品質が向上します。</span><span class="sxs-lookup"><span data-stu-id="4dce1-105">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="4dce1-106">仲介サーバーを使用していないリモートサイトが1つ以上の WAN リンクによって中央サイトに接続されていて、帯域幅が制限されている場合、メディアのバイパスにより、リモートサイトのクライアントからのメディアをローカルゲートウェイに直接流れるようにすることによって、帯域幅の要件を軽減します。まず、WAN リンクを中央サイトの仲介サーバーに移動して、戻る必要があります。このメディア処理の削減は、複数のゲートウェイを制御するための仲介サーバーの機能にも補います。</span><span class="sxs-lookup"><span data-stu-id="4dce1-106">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="4dce1-p102">メディア バイパスと通話受付管理 (CAC) を同時に使用することはできません。 通話にメディア バイパスを使用している場合、その通話に対して CAC は実行されません。 通話に関連するリンクについて、帯域幅に制約のあるリンクがないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="4dce1-p102">Media bypass and call admission control (CAC) are mutually exclusive. If media bypass is employed for a call, CAC is not performed for that call. The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4dce1-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4dce1-110">See Also</span></span>


[<span data-ttu-id="4dce1-111">Lync Server 2013 の通話受付管理と仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="4dce1-111">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="4dce1-112">Lync Server 2013 でのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="4dce1-112">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

