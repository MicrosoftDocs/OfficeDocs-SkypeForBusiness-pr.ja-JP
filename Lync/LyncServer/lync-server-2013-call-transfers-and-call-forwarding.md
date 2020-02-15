---
title: 'Lync Server 2013: 通話転送と着信転送'
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
ms.openlocfilehash: 46b16ad2faac58a5999b803c75d02e01da0da2dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="4e7cf-102">Lync Server 2013 での通話転送と着信の転送</span><span class="sxs-lookup"><span data-stu-id="4e7cf-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e7cf-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="4e7cf-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="4e7cf-104">PSTN エンドポイントが関係している場合は、場所に基づくルーティングによって、calle のエンドポイントの場所と、呼び出しが転送または転送されるエンドポイント (移行先および転送先) が分析されます。</span><span class="sxs-lookup"><span data-stu-id="4e7cf-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="4e7cf-105">場所に基づくルーティングは、両方のエンドポイントの場所に応じて、通話を転送または転送するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="4e7cf-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="4e7cf-106">次の表は、PSTN エンドポイントを使用した通話での Lync ユーザーのシナリオと、Lync ユーザーが別の Lync ユーザーに通話を転送する例を示しています。</span><span class="sxs-lookup"><span data-stu-id="4e7cf-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="4e7cf-107">通話のエンドポイントのネットワークサイトの場所に応じて、場所に基づくルーティングは、呼び出し転送または転送のルーティングに影響します。</span><span class="sxs-lookup"><span data-stu-id="4e7cf-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="4e7cf-108">着信転送または転送の開始</span><span class="sxs-lookup"><span data-stu-id="4e7cf-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e7cf-109">着信転送/転送を開始するユーザー</span><span class="sxs-lookup"><span data-stu-id="4e7cf-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="4e7cf-110">ターゲットエンドポイントが、着信転送または転送を開始したユーザーと同じネットワークサイトにある</span><span class="sxs-lookup"><span data-stu-id="4e7cf-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="4e7cf-111">転送先エンドポイントが別のネットワークサイトにある場合に、着信転送または着信転送を開始します。</span><span class="sxs-lookup"><span data-stu-id="4e7cf-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="4e7cf-112">ターゲットエンドポイントが不明なネットワークサイトにあるか、または場所に基づくルーティングが有効になっていないネットワークサイトにある</span><span class="sxs-lookup"><span data-stu-id="4e7cf-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e7cf-113">Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="4e7cf-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="4e7cf-114">着信/転送が許可されている</span><span class="sxs-lookup"><span data-stu-id="4e7cf-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="4e7cf-115">着信/転送は許可されていません</span><span class="sxs-lookup"><span data-stu-id="4e7cf-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="4e7cf-116">着信/転送は許可されていません</span><span class="sxs-lookup"><span data-stu-id="4e7cf-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="4e7cf-117">たとえば、PSTN エンドポイントを使用する Lync ユーザーは、同じネットワークサイトにある別の Lync ユーザーに通話を転送します。</span><span class="sxs-lookup"><span data-stu-id="4e7cf-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="4e7cf-118">この場合は、通話の転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="4e7cf-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="4e7cf-119">次の表は、別の Lync ユーザーとの通話での Lync ユーザーのシナリオと、その通話を PSTN エンドポイントに転送するユーザーの1人を示しています。</span><span class="sxs-lookup"><span data-stu-id="4e7cf-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="4e7cf-120">呼び出しが転送されるユーザーの場所に応じて、場所に基づくルーティングが通話にどのような影響を与えるかについて、表で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="4e7cf-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="4e7cf-121">PSTN エンドポイントへの着信転送または転送</span><span class="sxs-lookup"><span data-stu-id="4e7cf-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e7cf-122">着信転送/転送エンドポイントのターゲット</span><span class="sxs-lookup"><span data-stu-id="4e7cf-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="4e7cf-123">同じネットワークサイト内の Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="4e7cf-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="4e7cf-124">異なるネットワークサイトにある Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="4e7cf-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="4e7cf-125">不明なネットワークサイトまたはネットワークサイト内の1つまたは両方の Lync ユーザーが、場所に基づいたルーティングを有効にしていません</span><span class="sxs-lookup"><span data-stu-id="4e7cf-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e7cf-126">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="4e7cf-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="4e7cf-127">転送されたユーザーのサイトの音声ルーティングポリシーによって許可される通話転送または転送</span><span class="sxs-lookup"><span data-stu-id="4e7cf-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="4e7cf-128">転送されたユーザーのサイトの音声ルーティングポリシーによって許可される通話転送または転送</span><span class="sxs-lookup"><span data-stu-id="4e7cf-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="4e7cf-129">転送されたユーザーの音声ポリシーによって許可される通話転送または転送は、場所に基づいたルーティングでトランクが有効になっていません</span><span class="sxs-lookup"><span data-stu-id="4e7cf-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="4e7cf-130">たとえば、同じネットワークサイトにある別の Lync ユーザーとの通話で Lync ユーザーが通話を転送すると、通話転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="4e7cf-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4e7cf-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e7cf-131">See Also</span></span>


[<span data-ttu-id="4e7cf-132">Lync Server 2013 での場所に基づくルーティングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="4e7cf-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

