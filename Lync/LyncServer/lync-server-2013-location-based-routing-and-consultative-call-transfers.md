---
title: 'Lync Server 2013: ルーティングとコンサルティング呼び出しの転送を Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513814"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="60327-102">Lync Server 2013 でのルーティングおよびコンサルティング呼び出しの転送の Location-Based</span><span class="sxs-lookup"><span data-stu-id="60327-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60327-103">_**トピックの最終更新日:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="60327-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="60327-104">Location-Based が Lync 会議にルーティングされるようにすることに加えて、Location-Based ルーティング会議アプリケーションは、PSTN エンドポイントに出てくるコンサルティング呼び出し転送に対して Location-Based ルーティング制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="60327-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="60327-105">コンサルティング着信転送とは、当事者の一方が新しいユーザーに通話を転送する2つの当事者間で確立された通話のことです。</span><span class="sxs-lookup"><span data-stu-id="60327-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="60327-106">たとえば、PSTN エンドポイントはユーザー A (Lync 呼び出し先) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="60327-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="60327-107">ユーザー A は、PSTN ユーザーが user B (Lync user) に転送される必要があることを決定します。</span><span class="sxs-lookup"><span data-stu-id="60327-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="60327-108">ユーザー A は、PSTN ユーザーに通話を保留し、ユーザー B を呼び出します。ユーザー B は、PSTN ユーザーに連絡することに同意します。</span><span class="sxs-lookup"><span data-stu-id="60327-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="60327-109">ユーザー A が通話を保留にして、ユーザー B に転送します。</span><span class="sxs-lookup"><span data-stu-id="60327-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="60327-110">**コンサルティング呼び出し転送の通話フロー**</span><span class="sxs-lookup"><span data-stu-id="60327-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="60327-111">![会議図の場所に基づくルーティング](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "会議図の場所に基づくルーティング")</span><span class="sxs-lookup"><span data-stu-id="60327-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="60327-112">Location-Based ルーティングが有効になっているユーザーが PSTN エンドポイントのコンサルティング呼び出し転送を開始すると (前の図に示すように)、これに Location-Based より、2つのアクティブな通話、PSTN ユーザーと Lync ユーザー A の間の通話、および Lync ユーザー A と Lync ユーザー B 間の他の呼び出しが行われます</span><span class="sxs-lookup"><span data-stu-id="60327-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="60327-113">PSTN 通話をルーティングする SIP トランクが、Lync ユーザー B (つまり転送先) が配置されているネットワークサイトへの PSTN 通話の再ルーティングを承認されている場合は、呼び出し転送が許可されます。それ以外の場合は、コンサルティング呼び出しの転送がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="60327-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="60327-114">この認証は、PSTN エンドポイントへのアクティブな通話をルーティングしている SIP トランクと同じネットワークサイトにある、転送先のパーティの場所に基づいて実行されます。</span><span class="sxs-lookup"><span data-stu-id="60327-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="60327-115">着信 PSTN 通話をルーティングする SIP トランクが、転送先 (Lync ユーザー B) がある、または転送先が不明なネットワークサイトにあるネットワークサイトへの呼び出しをルーティングすることを許可されていない場合は、PSTN エンドポイントへのコンサルティング呼び出し転送 (つまり、通話転送ターゲット) はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="60327-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="60327-116">次の表では、Location-Based ルーティングの制限が、提案型の通話の転送に対して Location-Based ルーティング会議アプリケーションによって適用される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="60327-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="60327-117">PBX エンドポイントはネットワークサイトに直接関連付けられていませんが、PBX に接続されている SIP トランクにはネットワークサイトを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="60327-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="60327-118">そのため、PBX エンドポイントは、ネットワークサイトに間接的に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="60327-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60327-119">着信転送された相手のネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="60327-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="60327-120">着信転送ターゲットのネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="60327-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="60327-121">動作</span><span class="sxs-lookup"><span data-stu-id="60327-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60327-122">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="60327-123">同じネットワークサイト内の Lync ユーザー (つまり、サイト 1)</span><span class="sxs-lookup"><span data-stu-id="60327-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="60327-124">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="60327-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60327-125">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="60327-126">異なるネットワークサイトにある Lync ユーザー (サイト 2)</span><span class="sxs-lookup"><span data-stu-id="60327-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="60327-127">提案転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="60327-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60327-128">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="60327-129">不明なネットワークサイトの Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="60327-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="60327-130">提案転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="60327-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60327-131">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="60327-132">フェデレーション Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="60327-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="60327-133">提案転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="60327-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60327-134">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="60327-135">同じサイト内の PBX エンドポイント (つまりサイト 1)</span><span class="sxs-lookup"><span data-stu-id="60327-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="60327-136">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="60327-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60327-137">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="60327-138">別のサイトの PBX エンドポイント (つまりサイト 2)</span><span class="sxs-lookup"><span data-stu-id="60327-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="60327-139">提案転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="60327-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60327-140">同じサイト内の PBX エンドポイント (つまりサイト 1)</span><span class="sxs-lookup"><span data-stu-id="60327-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="60327-141">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="60327-142">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="60327-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60327-143">別のサイトの PBX エンドポイント (つまりサイト 2)</span><span class="sxs-lookup"><span data-stu-id="60327-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="60327-144">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="60327-145">提案転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="60327-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60327-146">任意のサイトの PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="60327-147">同じネットワークサイト内の Lync ユーザー (つまり、サイト 1)</span><span class="sxs-lookup"><span data-stu-id="60327-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="60327-148">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="60327-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60327-149">任意のサイトの PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="60327-150">異なるネットワークサイトにある Lync ユーザー (サイト 2)</span><span class="sxs-lookup"><span data-stu-id="60327-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="60327-151">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="60327-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60327-152">任意のサイトの PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="60327-153">不明なネットワークサイトの Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="60327-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="60327-154">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="60327-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60327-155">任意のサイトの PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="60327-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="60327-156">フェデレーション Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="60327-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="60327-157">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="60327-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

