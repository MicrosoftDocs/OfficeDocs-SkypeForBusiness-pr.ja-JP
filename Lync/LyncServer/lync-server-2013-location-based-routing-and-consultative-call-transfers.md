---
title: 'Lync Server 2013: ルーティングとコンサルティング呼び出しの転送を Location-Based'
description: 'Lync Server 2013: ルーティングとコンサルティング呼び出しの転送を Location-Based します。'
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
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567673"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="18910-103">Lync Server 2013 でのルーティングおよびコンサルティング呼び出しの転送の Location-Based</span><span class="sxs-lookup"><span data-stu-id="18910-103">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18910-104">_**トピックの最終更新日:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="18910-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="18910-105">Location-Based が Lync 会議にルーティングされるようにすることに加えて、Location-Based ルーティング会議アプリケーションは、PSTN エンドポイントに出てくるコンサルティング呼び出し転送に対して Location-Based ルーティング制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="18910-105">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="18910-106">コンサルティング着信転送とは、当事者の一方が新しいユーザーに通話を転送する2つの当事者間で確立された通話のことです。</span><span class="sxs-lookup"><span data-stu-id="18910-106">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="18910-107">たとえば、PSTN エンドポイントはユーザー A (Lync 呼び出し先) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="18910-107">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="18910-108">ユーザー A は、PSTN ユーザーが user B (Lync user) に転送される必要があることを決定します。</span><span class="sxs-lookup"><span data-stu-id="18910-108">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="18910-109">ユーザー A は、PSTN ユーザーに通話を保留し、ユーザー B を呼び出します。ユーザー B は、PSTN ユーザーに連絡することに同意します。</span><span class="sxs-lookup"><span data-stu-id="18910-109">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="18910-110">ユーザー A が通話を保留にして、ユーザー B に転送します。</span><span class="sxs-lookup"><span data-stu-id="18910-110">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="18910-111">**コンサルティング呼び出し転送の通話フロー**</span><span class="sxs-lookup"><span data-stu-id="18910-111">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="18910-112">![会議図の場所に基づくルーティング](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "会議図の場所に基づくルーティング")</span><span class="sxs-lookup"><span data-stu-id="18910-112">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="18910-113">Location-Based ルーティングが有効になっているユーザーが PSTN エンドポイントのコンサルティング呼び出し転送を開始すると (前の図に示すように)、これに Location-Based より、2つのアクティブな通話、PSTN ユーザーと Lync ユーザー A の間の通話、および Lync ユーザー A と Lync ユーザー B 間の他の呼び出しが行われます</span><span class="sxs-lookup"><span data-stu-id="18910-113">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="18910-114">PSTN 通話をルーティングする SIP トランクが、Lync ユーザー B (つまり転送先) が配置されているネットワークサイトへの PSTN 通話の再ルーティングを承認されている場合は、呼び出し転送が許可されます。それ以外の場合は、コンサルティング呼び出しの転送がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="18910-114">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="18910-115">この認証は、PSTN エンドポイントへのアクティブな通話をルーティングしている SIP トランクと同じネットワークサイトにある、転送先のパーティの場所に基づいて実行されます。</span><span class="sxs-lookup"><span data-stu-id="18910-115">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="18910-116">着信 PSTN 通話をルーティングする SIP トランクが、転送先 (Lync ユーザー B) がある、または転送先が不明なネットワークサイトにあるネットワークサイトへの呼び出しをルーティングすることを許可されていない場合は、PSTN エンドポイントへのコンサルティング呼び出し転送 (つまり、通話転送ターゲット) はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="18910-116">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="18910-117">次の表では、Location-Based ルーティングの制限が、提案型の通話の転送に対して Location-Based ルーティング会議アプリケーションによって適用される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="18910-117">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="18910-118">PBX エンドポイントはネットワークサイトに直接関連付けられていませんが、PBX に接続されている SIP トランクにはネットワークサイトを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="18910-118">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="18910-119">そのため、PBX エンドポイントは、ネットワークサイトに間接的に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="18910-119">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18910-120">着信転送された相手のネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="18910-120">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="18910-121">着信転送ターゲットのネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="18910-121">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="18910-122">動作</span><span class="sxs-lookup"><span data-stu-id="18910-122">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18910-123">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-123">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="18910-124">同じネットワークサイト内の Lync ユーザー (つまり、サイト 1)</span><span class="sxs-lookup"><span data-stu-id="18910-124">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="18910-125">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="18910-125">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18910-126">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="18910-127">異なるネットワークサイトにある Lync ユーザー (サイト 2)</span><span class="sxs-lookup"><span data-stu-id="18910-127">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="18910-128">提案転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="18910-128">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18910-129">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-129">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="18910-130">不明なネットワークサイトの Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="18910-130">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="18910-131">提案転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="18910-131">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18910-132">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-132">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="18910-133">フェデレーション Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="18910-133">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="18910-134">提案転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="18910-134">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18910-135">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-135">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="18910-136">同じサイト内の PBX エンドポイント (つまりサイト 1)</span><span class="sxs-lookup"><span data-stu-id="18910-136">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="18910-137">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="18910-137">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18910-138">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-138">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="18910-139">別のサイトの PBX エンドポイント (つまりサイト 2)</span><span class="sxs-lookup"><span data-stu-id="18910-139">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="18910-140">提案転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="18910-140">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18910-141">同じサイト内の PBX エンドポイント (つまりサイト 1)</span><span class="sxs-lookup"><span data-stu-id="18910-141">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="18910-142">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-142">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="18910-143">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="18910-143">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18910-144">別のサイトの PBX エンドポイント (つまりサイト 2)</span><span class="sxs-lookup"><span data-stu-id="18910-144">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="18910-145">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-145">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="18910-146">提案転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="18910-146">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18910-147">任意のサイトの PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-147">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="18910-148">同じネットワークサイト内の Lync ユーザー (つまり、サイト 1)</span><span class="sxs-lookup"><span data-stu-id="18910-148">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="18910-149">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="18910-149">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18910-150">任意のサイトの PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-150">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="18910-151">異なるネットワークサイトにある Lync ユーザー (サイト 2)</span><span class="sxs-lookup"><span data-stu-id="18910-151">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="18910-152">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="18910-152">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18910-153">任意のサイトの PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-153">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="18910-154">不明なネットワークサイトの Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="18910-154">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="18910-155">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="18910-155">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18910-156">任意のサイトの PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="18910-156">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="18910-157">フェデレーション Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="18910-157">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="18910-158">提案転送が許可されます。</span><span class="sxs-lookup"><span data-stu-id="18910-158">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

