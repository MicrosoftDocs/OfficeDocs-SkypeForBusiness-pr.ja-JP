---
title: 'Lync Server 2013: 着信通話'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e70e5a489cbfa581c666374e6535b898727e1fdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="f6ead-102">Lync Server 2013 着信通話</span><span class="sxs-lookup"><span data-stu-id="f6ead-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6ead-103">_**最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="f6ead-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="f6ead-104">場所に基づくルーティングが有効になっているユーザーに対する着信のルーティングは、ユーザーのエンドポイントの場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f6ead-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="f6ead-105">着信通話のルーティングは、次のように影響されます。</span><span class="sxs-lookup"><span data-stu-id="f6ead-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="f6ead-106">ユーザーが位置情報に基づくルーティングが有効になっているネットワークサイト内のエンドポイントに対して着信した場合、そのエンドポイントが PSTN ゲートウェイと同じネットワークサイト内にある場合は、通話がルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f6ead-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="f6ead-107">ユーザーが位置情報に基づくルーティングが有効になっているネットワークサイトにあるエンドポイントへの着信通話を使用していて、そのエンドポイントが PSTN ゲートウェイとは異なるネットワークサイトにある場合、通話はルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="f6ead-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="f6ead-108">着信通話の発信元の PSTN ゲートウェイと同じネットワーク サイトにエンドポイントがない場合、着信通話はユーザーのボイスメールに直接ルーティングされ、不在着信通知が呼び出し先に送信されます。</span><span class="sxs-lookup"><span data-stu-id="f6ead-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="f6ead-109">位置情報に基づくルーティングが有効になっているユーザーの着信の転送設定は引き続き適用されますが、転送された通話には、ユーザーの位置情報に基づくルーティングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f6ead-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="f6ead-110">次の表は、位置情報に基づくルーティングが、呼び出し元のエンドポイントの場所に応じて着信呼び出しのルーティングにどのように影響するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="f6ead-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="f6ead-111">PSTN ゲートウェイのネットワークサイトが位置情報に基づくルーティングに対応しており、位置情報に基づくルーティングでは、同じネットワークサイト内のエンドポイントへの PSTN 通話のルーティングのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="f6ead-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="f6ead-112">呼び出し先が PSTN から着信通話を受信する</span><span class="sxs-lookup"><span data-stu-id="f6ead-112">Callee receiving an inbound call from the PSTN</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f6ead-113">呼び出し先のエンドポイントが PSTN ゲートウェイと同じネットワーク サイトにある</span><span class="sxs-lookup"><span data-stu-id="f6ead-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="f6ead-114">呼び出し先のエンドポイントが PSTN ゲートウェイと同じネットワーク サイトにない</span><span class="sxs-lookup"><span data-stu-id="f6ead-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="f6ead-115">呼び出し先のエンドポイントが不明なネットワーク サイトにある、または場所に基づくルーティングが有効になっていない</span><span class="sxs-lookup"><span data-stu-id="f6ead-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6ead-116">着信 PSTN 通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="f6ead-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="f6ead-117">着信通話は呼び出し先のエンドポイントにルーティングされる</span><span class="sxs-lookup"><span data-stu-id="f6ead-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="f6ead-118">着信通話は呼び出し先のエンドポイントにルーティングされない</span><span class="sxs-lookup"><span data-stu-id="f6ead-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="f6ead-119">着信通話は呼び出し先のエンドポイントにルーティングされない</span><span class="sxs-lookup"><span data-stu-id="f6ead-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="f6ead-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6ead-120">See Also</span></span>


[<span data-ttu-id="f6ead-121">Lync Server 2013 の場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="f6ead-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

