---
title: 'Lync Server 2013: 場所に基づくルーティングの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bc7320ffd8bb4d12483a882b588205d26e7e164
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f80bb-102">Lync Server 2013 での場所に基づくルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="f80bb-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f80bb-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f80bb-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f80bb-104">場所に基づくルーティングでは、国内および国際間の PSTN 通話のルーティングを変更して、有料のバイパスを防止する新しいルールのセットが導入されています。</span><span class="sxs-lookup"><span data-stu-id="f80bb-104">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="f80bb-105">場所に基づくルーティングは、これらのルールを特定の地域、特定のゲートウェイ、または特定のユーザーのセットに限定するための柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="f80bb-105">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="f80bb-106">次のシナリオでは、場所に基づいたルーティングによって実行される主な種類の制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="f80bb-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="f80bb-107">出口呼び出し–場所に基づいたルーティングでは、発信者が PSTN の通話を禁止しているのと同じ地域に配置されている pstn ゲートウェイからの発信呼び出しを強制できます。これにより、別の地域にある PSTN ゲートウェイからの呼び出しが、コール.</span><span class="sxs-lookup"><span data-stu-id="f80bb-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="f80bb-108">受信呼び出し–場所に基づくルーティングは、着信呼び出しをルーティングする PSTN ゲートウェイが Lync ユーザーと同じ地域にない場合に、Lync エンドポイントを着信させないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f80bb-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="f80bb-109">不明な地域–場所に基づいたルーティングでは、不定の場所にあるユーザーとの間で送受信される PSTN 通話を制限します (つまり、リモートユーザーがインターネットから接続するか、または不明な地域に配置されます)。</span><span class="sxs-lookup"><span data-stu-id="f80bb-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="f80bb-110">国際的な地域–場所に基づいたルーティングによって、ユーザーの場所にローカルのゲートウェイが見つからない場合は、国際 PSTN ゲートウェイを経由した発信呼び出しのルーティングが強制されます。</span><span class="sxs-lookup"><span data-stu-id="f80bb-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f80bb-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f80bb-111">See Also</span></span>


[<span data-ttu-id="f80bb-112">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="f80bb-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

