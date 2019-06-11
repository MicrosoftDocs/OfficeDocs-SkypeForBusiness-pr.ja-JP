---
title: 'Lync Server 2013: 通話転送と着信転送'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="5d70e-102">Lync Server 2013 の通話転送と着信転送</span><span class="sxs-lookup"><span data-stu-id="5d70e-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d70e-103">_**最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="5d70e-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="5d70e-104">PSTN エンドポイントが関与している場合は、位置情報に基づくルーティングによって、calle のエンドポイントの位置と、通話が転送または転送されるエンドポイント (転送/転送ターゲット) が分析されます。</span><span class="sxs-lookup"><span data-stu-id="5d70e-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="5d70e-105">位置に基づくルーティングは、両方のエンドポイントの場所に応じて、通話を転送するか転送するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5d70e-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="5d70e-106">次の表は、PSTN エンドポイントを使用した通話での Lync ユーザーのシナリオと、Lync ユーザーが別の Lync ユーザーに通話を転送するシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="5d70e-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="5d70e-107">Transferee のエンドポイントのネットワークサイトの場所に応じて、位置ベースのルーティングは、通話転送または転送のルーティングに影響します。</span><span class="sxs-lookup"><span data-stu-id="5d70e-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="5d70e-108">通話転送または着信転送の開始</span><span class="sxs-lookup"><span data-stu-id="5d70e-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d70e-109">通話転送または着信転送を開始するユーザー</span><span class="sxs-lookup"><span data-stu-id="5d70e-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="5d70e-110">ターゲット エンドポイントが、通話転送または着信転送を開始するユーザーと同じネットワーク サイトにある</span><span class="sxs-lookup"><span data-stu-id="5d70e-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="5d70e-111">ターゲット エンドポイントが、通話転送または着信転送を開始するユーザーとは別のネットワーク サイトにある</span><span class="sxs-lookup"><span data-stu-id="5d70e-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="5d70e-112">ターゲットエンドポイントが不明なネットワークサイトにあるか、または場所ベースのルーティングで有効でないネットワークサイトにある</span><span class="sxs-lookup"><span data-stu-id="5d70e-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d70e-113">Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="5d70e-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="5d70e-114">通話または着信を転送できます。</span><span class="sxs-lookup"><span data-stu-id="5d70e-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="5d70e-115">通話または着信を転送できません。</span><span class="sxs-lookup"><span data-stu-id="5d70e-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="5d70e-116">通話または着信を転送できません。</span><span class="sxs-lookup"><span data-stu-id="5d70e-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="5d70e-117">たとえば、PSTN エンドポイントでの Lync ユーザーは、同じネットワークサイト内の別の Lync ユーザーに通話を転送します。</span><span class="sxs-lookup"><span data-stu-id="5d70e-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="5d70e-118">この場合、通話の転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="5d70e-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="5d70e-119">次の表は、別の Lync ユーザーとの通話での Lync ユーザーのシナリオと、いずれかのユーザーが通話を PSTN エンドポイントに転送するシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="5d70e-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="5d70e-120">一方のユーザーが通話を PSTN エンドポイントに転送した場合に、通話の転送先ユーザーの場所によって、場所に基づくルーティングが通話にどのように影響するかを表しています。</span><span class="sxs-lookup"><span data-stu-id="5d70e-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="5d70e-121">PSTN エンドポイントへの通話転送または着信転送</span><span class="sxs-lookup"><span data-stu-id="5d70e-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d70e-122">通話/着信転送エンドポイント ターゲット</span><span class="sxs-lookup"><span data-stu-id="5d70e-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="5d70e-123">同じネットワークサイト内の Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="5d70e-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="5d70e-124">異なるネットワークサイトの Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="5d70e-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="5d70e-125">不明のネットワークサイトまたはネットワークサイト内の一方または両方の Lync ユーザーが位置情報に基づくルーティングを有効にしていない</span><span class="sxs-lookup"><span data-stu-id="5d70e-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d70e-126">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="5d70e-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="5d70e-127">転送先ユーザーのサイトの音声ルーティング ポリシーによって、通話または着信の転送が許可される</span><span class="sxs-lookup"><span data-stu-id="5d70e-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="5d70e-128">転送先ユーザーのサイトの音声ルーティング ポリシーによって、通話または着信の転送が許可される</span><span class="sxs-lookup"><span data-stu-id="5d70e-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="5d70e-129">通話または着信の転送は、転送先ユーザーの音声ポリシーによって、場所に基づくルーティングが有効になっていないトランクのみを経由して許可される</span><span class="sxs-lookup"><span data-stu-id="5d70e-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="5d70e-130">たとえば、同じネットワークサイト内の別の Lync ユーザーとの通話で Lync ユーザーが通話を PSTN エンドポイントに転送し、通話転送が許可されているとします。</span><span class="sxs-lookup"><span data-stu-id="5d70e-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5d70e-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d70e-131">See Also</span></span>


[<span data-ttu-id="5d70e-132">Lync Server 2013 の場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="5d70e-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

