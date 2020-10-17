---
title: 'Lync Server 2013: 着信呼び出し'
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
ms.openlocfilehash: 05147e469ce120663992e5ae7b8a3ee59acaf78c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526614"
---
# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="2d196-102">Lync Server 2013 の着信呼び出し</span><span class="sxs-lookup"><span data-stu-id="2d196-102">Incoming calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d196-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="2d196-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="2d196-104">Location-Based ルーティングが有効になっているユーザーへの着信通話のルーティングは、ユーザーのエンドポイントの場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2d196-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="2d196-105">着信呼び出しのルーティングには、次のような影響があります。</span><span class="sxs-lookup"><span data-stu-id="2d196-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="2d196-106">ユーザーが Location-Based ルーティングが有効なネットワークサイトにあるエンドポイントへの着信呼び出しを行い、エンドポイントが PSTN ゲートウェイと同じネットワークサイトにある場合、通話はルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="2d196-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="2d196-107">ユーザーが Location-Based ルーティングが有効なネットワークサイトにあるエンドポイントへの着信呼び出しを行い、そのエンドポイントが PSTN ゲートウェイとは別のネットワークサイトにある場合、通話はルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="2d196-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="2d196-108">着信呼び出しが行われている PSTN ゲートウェイと同じネットワークサイト内にエンドポイントが存在しない場合、着信呼び出しは直接ユーザーのボイスメールにルーティングされ、不在着信通知が呼び出し元に送信されます。</span><span class="sxs-lookup"><span data-stu-id="2d196-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="2d196-109">Location-Based ルーティングが有効になっているユーザーの着信転送設定は引き続き強制されますが、転送される呼び出しは、ユーザーの Location-Based ルーティング制限の対象となります。</span><span class="sxs-lookup"><span data-stu-id="2d196-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="2d196-110">次の表は、呼び出し先のエンドポイントの場所に応じて、Location-Based ルーティングが着信呼び出しのルーティングにどのように影響するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="2d196-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="2d196-111">PSTN ゲートウェイのネットワークサイトは Location-Based ルーティングに対して有効になっており、Location-Based ルーティングでは、同じネットワークサイト内のエンドポイントへの PSTN 通話のルーティングのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="2d196-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="2d196-112">PSTN からの着信通話を受信する呼び出し先</span><span class="sxs-lookup"><span data-stu-id="2d196-112">Callee receiving an inbound call from the PSTN</span></span>

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
<th><span data-ttu-id="2d196-113">PSTN ゲートウェイと同じネットワークサイトにある呼び出し先のエンドポイント</span><span class="sxs-lookup"><span data-stu-id="2d196-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="2d196-114">呼び出し先のエンドポイントが PSTN ゲートウェイと同じネットワークサイトにありません</span><span class="sxs-lookup"><span data-stu-id="2d196-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="2d196-115">呼び出し先のエンドポイントが不明なネットワークサイトにあるか、Location-Based ルーティングに対して有効になっていません</span><span class="sxs-lookup"><span data-stu-id="2d196-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d196-116">着信 PSTN 通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="2d196-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="2d196-117">着信呼び出しは、呼び出し先のエンドポイントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="2d196-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="2d196-118">着信呼び出しが、呼び出し先のエンドポイントにルーティングされない</span><span class="sxs-lookup"><span data-stu-id="2d196-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="2d196-119">着信呼び出しが、呼び出し先のエンドポイントにルーティングされない</span><span class="sxs-lookup"><span data-stu-id="2d196-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="2d196-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d196-120">See Also</span></span>


[<span data-ttu-id="2d196-121">Lync Server 2013 での Location-Based ルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="2d196-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

