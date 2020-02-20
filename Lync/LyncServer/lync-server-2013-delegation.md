---
title: 'Lync Server 2013: 委任'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 360223733f003c30d63ef0145fa04c51503d510d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="2754d-102">Lync Server 2013 での委任</span><span class="sxs-lookup"><span data-stu-id="2754d-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2754d-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="2754d-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="2754d-104">Lync の委任機能は、次の方法で場所に基づくルーティングによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="2754d-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="2754d-105">場所に基づくルーティングを有効にした代理人が上司に代わって呼び出しを行う場合は、代理人の音声ポリシーを使用して通話を承認し、代理人のサイトの音声ルーティングポリシーを使用して通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="2754d-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="2754d-106">マネージャーへの PSTN 通話の着信の場合、通話の転送と同時呼び出しの場合と同じ規則が、「通話の転送と転送と同時呼び出し」のトピックで説明しているとおりに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2754d-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="2754d-107">代理人が PSTN エンドポイントを同時呼び出しターゲットとして設定している場合、マネージャーへの着信呼び出しでは、着信トランクに関連付けられているサイトの音声ルーティングポリシーを使用して、代理人の PSTN エンドポイントに通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="2754d-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="2754d-108">委任では、管理者とその関連付けられた代理人を、通常同じネットワークサイトに配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2754d-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2754d-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="2754d-109">See Also</span></span>


[<span data-ttu-id="2754d-110">Lync Server 2013 での場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="2754d-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

