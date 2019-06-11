---
title: 'Lync Server 2013: 委任'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82be0bdc382440cc8a4307dc0ba981f31c5a9313
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="555f4-102">Lync Server 2013 の委任</span><span class="sxs-lookup"><span data-stu-id="555f4-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="555f4-103">_**最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="555f4-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="555f4-104">Lync の委任機能は、次のような方法で位置情報に基づくルーティングによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="555f4-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="555f4-105">位置情報に基づくルーティングを有効にした代理人が管理者の代わりに通話を発信する場合、代理人のボイスポリシーを使って通話を承認し、代理人のサイトボイスルーティングポリシーを使って通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="555f4-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="555f4-106">マネージャーへの着信 PSTN 通話については、通話の転送または同時呼び出しに適用されるのと同じルールが適用されます (着信の転送と通話の転送および同時呼び出しのトピックを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="555f4-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="555f4-107">代理人がマネージャーへの着信通話に対して PSTN エンドポイントを同時呼び出しターゲットとして設定すると、代理人の PSTN エンドポイントへの通話のルーティングに、受信トランクに関連付けられたサイトの音声ルーティング ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="555f4-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="555f4-108">委任に関して、通常はマネージャーとその関連付けられた代理人を同じネットワーク サイトに配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="555f4-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="555f4-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="555f4-109">See Also</span></span>


[<span data-ttu-id="555f4-110">Lync Server 2013 の場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="555f4-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

