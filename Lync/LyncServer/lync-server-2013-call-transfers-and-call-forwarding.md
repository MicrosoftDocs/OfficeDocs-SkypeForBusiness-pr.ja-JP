---
title: 'Lync Server 2013: 通話転送と着信転送'
description: 'Lync Server 2013: 通話転送と着信転送。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565253"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="e2cd3-103">Lync Server 2013 での通話転送と着信の転送</span><span class="sxs-lookup"><span data-stu-id="e2cd3-103">Call transfers and call forwarding in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2cd3-104">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="e2cd3-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="e2cd3-105">PSTN エンドポイントが関係している場合、Location-Based ルーティングによって、calle のエンドポイントの場所と、呼び出しが転送または転送されるエンドポイント (移行先と転送先) が分析されます。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-105">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="e2cd3-106">Location-Based ルーティングは、両方のエンドポイントの場所に応じて、通話を転送するか転送するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-106">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="e2cd3-107">次の表は、PSTN エンドポイントを使用した通話での Lync ユーザーのシナリオと、Lync ユーザーが別の Lync ユーザーに通話を転送する例を示しています。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-107">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="e2cd3-108">通話のエンドポイントのネットワークサイトの場所に応じて、Location-Based ルーティングは、通話の転送または転送のルーティングに影響します。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-108">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="e2cd3-109">着信転送または転送の開始</span><span class="sxs-lookup"><span data-stu-id="e2cd3-109">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2cd3-110">着信転送/転送を開始するユーザー</span><span class="sxs-lookup"><span data-stu-id="e2cd3-110">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="e2cd3-111">ターゲットエンドポイントが、着信転送または転送を開始したユーザーと同じネットワークサイトにある</span><span class="sxs-lookup"><span data-stu-id="e2cd3-111">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="e2cd3-112">転送先エンドポイントが別のネットワークサイトにある場合に、着信転送または着信転送を開始します。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-112">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="e2cd3-113">ターゲットエンドポイントが不明なネットワークサイトにあるか、または Location-Based ルーティングで有効になっていないネットワークサイトにあります</span><span class="sxs-lookup"><span data-stu-id="e2cd3-113">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2cd3-114">Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="e2cd3-114">Lync user</span></span></p></td>
<td><p><span data-ttu-id="e2cd3-115">着信/転送が許可されている</span><span class="sxs-lookup"><span data-stu-id="e2cd3-115">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="e2cd3-116">着信/転送は許可されていません</span><span class="sxs-lookup"><span data-stu-id="e2cd3-116">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="e2cd3-117">着信/転送は許可されていません</span><span class="sxs-lookup"><span data-stu-id="e2cd3-117">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="e2cd3-118">たとえば、PSTN エンドポイントを使用する Lync ユーザーは、同じネットワークサイトにある別の Lync ユーザーに通話を転送します。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-118">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="e2cd3-119">この場合は、通話の転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-119">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="e2cd3-120">次の表は、別の Lync ユーザーとの通話での Lync ユーザーのシナリオと、その通話を PSTN エンドポイントに転送するユーザーの1人を示しています。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-120">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="e2cd3-121">呼び出しが転送されるユーザーの場所に応じて、Location-Based ルーティングが通話に与える影響についての詳細を表に示します。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-121">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="e2cd3-122">PSTN エンドポイントへの着信転送または転送</span><span class="sxs-lookup"><span data-stu-id="e2cd3-122">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2cd3-123">着信転送/転送エンドポイントのターゲット</span><span class="sxs-lookup"><span data-stu-id="e2cd3-123">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="e2cd3-124">同じネットワークサイト内の Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="e2cd3-124">Lync users in same network site</span></span></th>
<th><span data-ttu-id="e2cd3-125">異なるネットワークサイトにある Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="e2cd3-125">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="e2cd3-126">不明なネットワークサイトまたはネットワークサイト内の1つまたは両方の Lync ユーザーが、Location-Based ルーティングに対して有効になっていません</span><span class="sxs-lookup"><span data-stu-id="e2cd3-126">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2cd3-127">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="e2cd3-127">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="e2cd3-128">転送されたユーザーのサイトの音声ルーティングポリシーによって許可される通話転送または転送</span><span class="sxs-lookup"><span data-stu-id="e2cd3-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="e2cd3-129">転送されたユーザーのサイトの音声ルーティングポリシーによって許可される通話転送または転送</span><span class="sxs-lookup"><span data-stu-id="e2cd3-129">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="e2cd3-130">転送されたユーザーの音声ポリシーによって許可される通話転送または転送は、Location-Based ルーティングに対してトランクが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-130">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="e2cd3-131">たとえば、同じネットワークサイトにある別の Lync ユーザーとの通話で Lync ユーザーが通話を転送すると、通話転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="e2cd3-131">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e2cd3-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2cd3-132">See Also</span></span>


[<span data-ttu-id="e2cd3-133">Lync Server 2013 での Location-Based ルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="e2cd3-133">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

