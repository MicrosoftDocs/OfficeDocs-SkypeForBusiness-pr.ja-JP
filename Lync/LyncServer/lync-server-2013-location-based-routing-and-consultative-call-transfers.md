---
title: 'Lync Server 2013: 場所に基づくルーティングとコンサルティングによる通話転送'
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
ms.openlocfilehash: 4e433baf180b8e4abf50ec374848204bf6628eb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="7f13c-102">Lync Server 2013 での位置情報に基づくルーティングとコンサルティングによる通話転送</span><span class="sxs-lookup"><span data-stu-id="7f13c-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f13c-103">_**最終更新日:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="7f13c-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="7f13c-104">Lync 会議への位置情報に基づくルーティングを適用することに加えて、場所に基づくルーティング会議アプリケーションは、PSTN エンドポイントに送信される提案型呼び出しの転送についての位置情報に基づくルーティング制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="7f13c-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="7f13c-105">お客様による発信は、2つの当事者間で確立された通話であり、一方の当事者が新しいユーザーに通話を転送します。</span><span class="sxs-lookup"><span data-stu-id="7f13c-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="7f13c-106">たとえば、PSTN エンドポイントはユーザー A (Lync 呼び出し元) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7f13c-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="7f13c-107">ユーザー A は、PSTN ユーザーをユーザー B (Lync ユーザー) に転送する必要があることを決定します。</span><span class="sxs-lookup"><span data-stu-id="7f13c-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="7f13c-108">ユーザー A は、PSTN ユーザーとの通話を保留にし、ユーザー B を呼び出します。ユーザー B は PSTN ユーザーとの通信に同意します。</span><span class="sxs-lookup"><span data-stu-id="7f13c-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="7f13c-109">ユーザー A は、着信をユーザー B に転送します。</span><span class="sxs-lookup"><span data-stu-id="7f13c-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="7f13c-110">**取次通話転送の通話フロー**</span><span class="sxs-lookup"><span data-stu-id="7f13c-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="7f13c-111">![会議の位置情報に基づくルーティングの図](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "会議の位置情報に基づくルーティングの図")</span><span class="sxs-lookup"><span data-stu-id="7f13c-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="7f13c-112">位置情報に基づくルーティングが有効になっている場合、PSTN エンドポイント (上の図に示されているように) によって、2つのアクティブな通話、PSTN ユーザー A と Lync ユーザー A との間の通話、および Lync ユーザー A と Lync ユーザー B 間の通話が1つ作成されます。次の動作は、場所に基づくルーティング会議アプリケーションによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="7f13c-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="7f13c-113">PSTN 通話をルーティングする SIP トランクが、Lync ユーザー B (つまり転送先) があるネットワークサイトへの PSTN 通話を再ルーティングすることを許可されている場合は、通話転送が許可されます。それ以外の場合は、コンサルティング着信の転送がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="7f13c-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="7f13c-114">この承認は、転送された当事者が、PSTN エンドポイントへのアクティブな通話をルーティングしている SIP トランクと同じネットワークサイトに配置されている場所に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="7f13c-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="7f13c-115">着信 PSTN 通話をルーティングしている SIP トランクが、転送されたパーティ (Lync ユーザー B) が存在するか、または送信されたパーティが不明なネットワークサイトにある場合は、PSTN への提案型コール転送エンドポイント (つまり、着信転送ターゲット) はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="7f13c-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="7f13c-116">次の表では、位置情報に基づくルーティングの制限が、提案型の通話転送についての位置情報に基づくルーティング会議アプリケーションによってどのように適用されるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="7f13c-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="7f13c-117">PBX エンドポイントはネットワーク サイトに直接関連付けられませんが、PBX の接続先の SIP トランクにネットワーク サイトが割り当てられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f13c-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="7f13c-118">したがって、PBX エンドポイントがネットワーク サイトに間接的に関連付けられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f13c-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f13c-119">通話転送を受ける側のネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="7f13c-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="7f13c-120">通話転送ターゲットのネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="7f13c-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="7f13c-121">動作</span><span class="sxs-lookup"><span data-stu-id="7f13c-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f13c-122">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7f13c-123">同じネットワークサイト内の Lync ユーザー (例: サイト 1)</span><span class="sxs-lookup"><span data-stu-id="7f13c-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7f13c-124">取次転送が許可される</span><span class="sxs-lookup"><span data-stu-id="7f13c-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f13c-125">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7f13c-126">異なるネットワークサイトの Lync ユーザー (例: サイト 2)</span><span class="sxs-lookup"><span data-stu-id="7f13c-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7f13c-127">取次転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="7f13c-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f13c-128">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7f13c-129">不明なネットワークサイトの Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="7f13c-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="7f13c-130">取次転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="7f13c-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f13c-131">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7f13c-132">フェデレーションされた Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="7f13c-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="7f13c-133">取次転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="7f13c-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f13c-134">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7f13c-135">同じサイト (サイト 1) 内の PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7f13c-136">取次転送が許可される</span><span class="sxs-lookup"><span data-stu-id="7f13c-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f13c-137">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7f13c-138">別のサイト (サイト 2) 内の PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7f13c-139">取次転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="7f13c-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f13c-140">同じサイト (サイト 1) 内の PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7f13c-141">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7f13c-142">取次転送が許可される</span><span class="sxs-lookup"><span data-stu-id="7f13c-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f13c-143">別のサイト (サイト 2) 内の PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7f13c-144">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7f13c-145">取次転送が許可されない</span><span class="sxs-lookup"><span data-stu-id="7f13c-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f13c-146">任意のサイト内の PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7f13c-147">同じネットワークサイト内の Lync ユーザー (例: サイト 1)</span><span class="sxs-lookup"><span data-stu-id="7f13c-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="7f13c-148">取次転送が許可される</span><span class="sxs-lookup"><span data-stu-id="7f13c-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f13c-149">任意のサイト内の PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7f13c-150">異なるネットワークサイトの Lync ユーザー (例: サイト 2)</span><span class="sxs-lookup"><span data-stu-id="7f13c-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="7f13c-151">取次転送が許可される</span><span class="sxs-lookup"><span data-stu-id="7f13c-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f13c-152">任意のサイト内の PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7f13c-153">不明なネットワークサイトの Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="7f13c-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="7f13c-154">取次転送が許可される</span><span class="sxs-lookup"><span data-stu-id="7f13c-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f13c-155">任意のサイト内の PBX エンドポイント</span><span class="sxs-lookup"><span data-stu-id="7f13c-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="7f13c-156">フェデレーションされた Lync ユーザー</span><span class="sxs-lookup"><span data-stu-id="7f13c-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="7f13c-157">取次転送が許可される</span><span class="sxs-lookup"><span data-stu-id="7f13c-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

