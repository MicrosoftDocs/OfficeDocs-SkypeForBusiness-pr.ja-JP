---
title: 'Lync Server 2013: Location-Based ルーティングに関する技術的な考慮事項'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80364f35ffaf361353815988bcae12f29bca019c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536184"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="d0c7a-102">Lync Server 2013 での Location-Based ルーティングに関する技術的考慮事項</span><span class="sxs-lookup"><span data-stu-id="d0c7a-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0c7a-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="d0c7a-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="d0c7a-104">Location-Based ルーティングを計画するときは、次のシナリオに対する影響を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0c7a-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="d0c7a-105">障害回復</span><span class="sxs-lookup"><span data-stu-id="d0c7a-105">Disaster Recovery</span></span>

<span data-ttu-id="d0c7a-106">プライマリプールからバックアッププールへのフェールオーバーに加えて、プライマリプールへの通常の操作の復元時には、Location-Based ルーティングは障害発生時および回復手順中に常に適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="d0c7a-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="d0c7a-107">存続可能ブランチ アプライアンス</span><span class="sxs-lookup"><span data-stu-id="d0c7a-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="d0c7a-108">Location-Based ルーティングを構成すると、存続可能 Branch アプライアンスに関連付けられているゲートウェイを展開する場所の計画に影響します。</span><span class="sxs-lookup"><span data-stu-id="d0c7a-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="d0c7a-109">SBA に関連付けられているゲートウェイは、存続可能ブランチアプライアンスと同じネットワークサイトに配置する必要があります。そうしないと、存続可能ブランチアプライアンスに所属するユーザーは Location-Based ルーティングが構成されている場合に、送信呼び出しをすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0c7a-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="d0c7a-110">存続可能ブランチアプライアンスと中央サイトとの間の WAN 接続がダウンすると、Location-Based ルーティング制限が適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="d0c7a-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0c7a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0c7a-111">See Also</span></span>


[<span data-ttu-id="d0c7a-112">Lync Server 2013 での Location-Based ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="d0c7a-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

