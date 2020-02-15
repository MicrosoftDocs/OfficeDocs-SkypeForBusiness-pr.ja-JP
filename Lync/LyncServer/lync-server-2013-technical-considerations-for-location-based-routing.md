---
title: 'Lync Server 2013: 場所に基づくルーティングに関する技術的な考慮事項'
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
ms.openlocfilehash: fcdebdccd0584d31b27120709212be674e8d3c2a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="70212-102">Lync Server 2013 での場所に基づくルーティングに関する技術的考慮事項</span><span class="sxs-lookup"><span data-stu-id="70212-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70212-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="70212-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="70212-104">場所に基づくルーティングを計画するときは、次のシナリオに対する影響を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70212-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="70212-105">障害復旧</span><span class="sxs-lookup"><span data-stu-id="70212-105">Disaster Recovery</span></span>

<span data-ttu-id="70212-106">プライマリプールからバックアッププールへのフェールオーバーに加えて、プライマリプールへの通常の操作の復元時には、場所に基づくルーティングは障害発生時および回復手順中に常に適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="70212-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="70212-107">存続可能ブランチ アプライアンス</span><span class="sxs-lookup"><span data-stu-id="70212-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="70212-108">場所に基づくルーティングを構成すると、存続可能ブランチアプライアンスに関連付けられているゲートウェイの展開計画に影響します。</span><span class="sxs-lookup"><span data-stu-id="70212-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="70212-109">SBA に関連付けられているゲートウェイは、存続可能ブランチアプライアンスと同じネットワークサイトに配置する必要があります。そうしないと、存続可能 Branch アプライアンスに所属するユーザーは、場所に基づくルーティングが構成されている場合に、送信呼び出しを行うことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="70212-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="70212-110">存続可能ブランチアプライアンスと中央サイトとの間の WAN 接続がダウンすると、場所に基づくルーティング制限が適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="70212-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70212-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="70212-111">See Also</span></span>


[<span data-ttu-id="70212-112">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="70212-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

