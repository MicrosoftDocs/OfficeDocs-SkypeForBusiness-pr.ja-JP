---
title: 'Lync Server 2013: 場所に基づくルーティングに関する技術的考慮事項'
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
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="bffb4-102">場所に基づくルーティングに関する Lync Server 2013 の技術的考慮事項</span><span class="sxs-lookup"><span data-stu-id="bffb4-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bffb4-103">_**最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="bffb4-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="bffb4-104">位置ベースのルーティングを計画する場合、次のシナリオに対する影響を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bffb4-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="bffb4-105">障害復旧</span><span class="sxs-lookup"><span data-stu-id="bffb4-105">Disaster Recovery</span></span>

<span data-ttu-id="bffb4-106">プライマリプールからバックアッププールへのフェールオーバー、および通常の操作をプライマリプールに復元するときに、場所に基づくルーティングは、障害発生時と回復時に常に適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="bffb4-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="bffb4-107">存続可能ブランチ アプライアンス</span><span class="sxs-lookup"><span data-stu-id="bffb4-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="bffb4-108">場所に基づくルーティングを構成すると、Survivable Branch アプライアンスに関連付けられているゲートウェイを展開する際の計画に影響します。</span><span class="sxs-lookup"><span data-stu-id="bffb4-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="bffb4-109">SBA に関連付けられているゲートウェイは、Survivable Branch Appliance と同じネットワークサイトにある必要があります。そうしないと、Survivable Branch アプライアンスをホームにしているユーザーは、位置情報に基づくルーティングが構成されている場合に、発信通話を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="bffb4-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="bffb4-110">Survivable Branch Appliance とセントラルサイト間の WAN 接続がダウンしている場合、位置ベースのルーティング制限は適用されます。</span><span class="sxs-lookup"><span data-stu-id="bffb4-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bffb4-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="bffb4-111">See Also</span></span>


[<span data-ttu-id="bffb4-112">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="bffb4-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

