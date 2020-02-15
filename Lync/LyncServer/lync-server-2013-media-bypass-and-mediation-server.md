---
title: 'Lync Server 2013: メディアバイパスと仲介サーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 426499da4659548d90ed2160c23a905565edddd6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="e3d30-102">Lync Server 2013 のメディアバイパスと仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="e3d30-102">Media bypass and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3d30-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e3d30-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e3d30-104">メディアバイパスは、管理者が、仲介サーバーをトラバースせずに、ユーザーエンドポイントと公衆交換電話網 (PSTN) ゲートウェイの間で直接フローするように通話ルーティングを構成できるようにする Lync Server の機能です。</span><span class="sxs-lookup"><span data-stu-id="e3d30-104">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="e3d30-105">Media バイパス待機時間の短縮、不要な変換、パケット損失の可能性、および潜在的な障害点の数を減らすことで、通話の品質が向上します。</span><span class="sxs-lookup"><span data-stu-id="e3d30-105">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="e3d30-106">仲介サーバーを使用しないリモートサイトが1つまたは複数の WAN リンクによって中央サイトに接続されていて、帯域幅が制限されている場合、メディアバイパスにより、リモートサイトのクライアントからのメディアをローカルゲートウェイに直接流すことができるため、帯域幅の要件が減少します。最初に、WAN リンクを中央サイトの仲介サーバーに転送し、バックアップする必要があります。また、メディア処理が減少することで、仲介サーバーが複数のゲートウェイを制御する機能が補完されます。</span><span class="sxs-lookup"><span data-stu-id="e3d30-106">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="e3d30-p102">メディア バイパスと通話受付管理 (CAC) を同時に使用することはできません。 通話にメディア バイパスを使用している場合、その通話に対して CAC は実行されません。 通話に関連するリンクについて、帯域幅に制約のあるリンクがないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e3d30-p102">Media bypass and call admission control (CAC) are mutually exclusive. If media bypass is employed for a call, CAC is not performed for that call. The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e3d30-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3d30-110">See Also</span></span>


[<span data-ttu-id="e3d30-111">Lync Server 2013 での通話受付管理と仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="e3d30-111">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="e3d30-112">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="e3d30-112">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

