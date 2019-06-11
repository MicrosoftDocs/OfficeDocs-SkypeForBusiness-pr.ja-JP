---
title: 'Lync Server 2013: 場所に基づくルーティングの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b3a5cb2e89376a356daf54c6e5bc443ab52207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="4e704-102">Lync Server 2013 での位置情報に基づくルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="4e704-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e704-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4e704-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4e704-p101">場所に基づいたルーティングでは、国内および国際 PSTN 通話のルーティングを変更する新しいルール セットを導入して、課金回避を防止します。場所に基づいたルーティングによって、これらのルールを特定の地域、ゲートウェイ、ユーザー群のみに柔軟に適用できます。</span><span class="sxs-lookup"><span data-stu-id="4e704-p101">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass. Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="4e704-106">次のシナリオでは、位置ベースのルーティングで適用される主な種類の制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e704-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="4e704-107">出口呼び出し–位置情報に基づくルーティングでは、発信者が PSTN の電話と同じ地域に配置されている PSTN ゲートウェイからの発信通話を強制することができます。これにより、発信者は、別の地域にある PSTN ゲートウェイからの出口を、相手.</span><span class="sxs-lookup"><span data-stu-id="4e704-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="4e704-108">受信通話–位置ベースのルーティングでは、着信通話の着信が Lync ユーザーと同じ地域にない場合に、着信 PSTN 通話が Lync エンドポイントを呼び出すことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="4e704-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="4e704-109">不明な地域-場所に基づくルーティングでは、不定の場所 (インターネットから接続されているか、または不明な地域にいるリモートユーザー) との間で送受信される PSTN 通話を制限します。</span><span class="sxs-lookup"><span data-stu-id="4e704-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="4e704-110">国際地域–位置に基づくルーティングでは、ユーザーの位置情報に対するローカルゲートウェイが見つからない場合、国際 PSTN ゲートウェイを介した発信通話のルーティングが強制されます。</span><span class="sxs-lookup"><span data-stu-id="4e704-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4e704-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e704-111">See Also</span></span>


[<span data-ttu-id="4e704-112">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="4e704-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

