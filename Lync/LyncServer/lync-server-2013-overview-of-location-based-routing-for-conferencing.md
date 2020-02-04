---
title: 'Lync Server 2013: 会議での位置情報に基づくルーティングの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adb103d1f2314e033d9ef0958dd05a7648012bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f5c37-102">Lync Server 2013 での会議の位置情報に基づくルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="f5c37-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5c37-103">_**最終更新日:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="f5c37-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="f5c37-104">場所に基づくルーティング会議アプリケーションは、PSTN の有料電話のバイパスを防止するメカニズムを Lync 会議に提供します。</span><span class="sxs-lookup"><span data-stu-id="f5c37-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="f5c37-105">アプリケーションは、参加している Lync ユーザーの場所に基づいて、アクティブな会議を監視し、位置情報に基づくルーティング制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="f5c37-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="f5c37-106">次の条件が満たされている場合、位置情報に基づくルーティング会議アプリケーションによって、Lync 会議で位置情報に基づくルーティングが適用されるかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="f5c37-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="f5c37-107">会議の開催者の位置情報に基づくルーティングが有効になっている。</span><span class="sxs-lookup"><span data-stu-id="f5c37-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="f5c37-108">位置情報に基づくルーティング制限は、場所に基づくルーティングが有効になっているユーザーによって開催された会議にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c37-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f5c37-109">少なくとも 1 人の会議参加者が PSTN エンドポイントである。</span><span class="sxs-lookup"><span data-stu-id="f5c37-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="f5c37-110">位置情報に基づくルーティングの制限は、PSTN エンドポイントが含まれている会議にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c37-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="f5c37-111">会議と PSTN の橋渡しに使用される PSTN ゲートウェイがあるネットワーク サイトが、開催者と参加者の接続元のネットワーク サイトでもある。</span><span class="sxs-lookup"><span data-stu-id="f5c37-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="f5c37-112">場所に基づくルーティング会議アプリケーションは、異なるネットワークサイトから同じ電話会議への Lync ユーザーと PSTN エンドポイントの参加を防止します。</span><span class="sxs-lookup"><span data-stu-id="f5c37-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="f5c37-113">会議の開催者が位置情報に基づくルーティングを有効にしている場合、会議アプリケーションでは次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c37-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="f5c37-114">Lync 会議に参加できるエンドポイントは、既に会議に参加しているエンドポイントによって異なります。この制限は、参加したエンドポイントの退出と新しいエンドポイントが会議に参加すると調整されます。</span><span class="sxs-lookup"><span data-stu-id="f5c37-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="f5c37-115">開催者と参加者が同じネットワークサイトから Lync 会議に参加している場合、PSTN エンドポイント、同じネットワークサイトからの別の参加者、別のネットワークサイトからの別の参加者、または不明なネットワークサイトからの参加者は、次のように許可されています。追加.</span><span class="sxs-lookup"><span data-stu-id="f5c37-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="f5c37-116">開催者と参加者が別のネットワーク サイトや不明なネットワーク サイトから会議に参加している場合、場所に基づくルーティングが有効な SIP トランクから PSTN 通話が入ると、PSTN エンドポイントは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="f5c37-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f5c37-117">開催者と参加者が同じネットワークサイトから会議に参加していて、参加者が PSTN から同じ会議に参加している場合は、別のネットワークサイトの Lync エンドポイントで会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5c37-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="f5c37-118">これらの会議の場所に基づくルーティングの制限について、次の表で概要を示します。</span><span class="sxs-lookup"><span data-stu-id="f5c37-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5c37-119">任意の時点の会議のユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="f5c37-120">会議に参加できるユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="f5c37-121">会議に参加できないユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c37-122">1つのネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="f5c37-123">同じネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="f5c37-124">別のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="f5c37-125">不明のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="f5c37-126">フェデレーションされた Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="f5c37-127">PSTN エンドポイントから参加しているユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="f5c37-128">なし</span><span class="sxs-lookup"><span data-stu-id="f5c37-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c37-129">不明のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="f5c37-130">任意のサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="f5c37-131">不明なサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="f5c37-132">フェデレーションされた Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="f5c37-133">PSTN エンドポイント経由で参加しているユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c37-134">異なるネットワークサイトの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="f5c37-135">任意のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="f5c37-136">不明のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="f5c37-137">フェデレーションされた Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="f5c37-138">PSTN エンドポイント経由で参加しているユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c37-139">1つのネットワークサイトの Lync VoIP クライアントユーザーと PSTN エンドポイントからの参加ユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="f5c37-140">同じネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="f5c37-141">別のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="f5c37-142">不明のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="f5c37-143">フェデレーションされた Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="f5c37-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f5c37-144">次に、場所に基づくルーティング会議アプリケーションのその他の特徴を示します。</span><span class="sxs-lookup"><span data-stu-id="f5c37-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="f5c37-145">場所に基づくルーティングの制限により、ユーザーが会議に参加することを許可されていない場合は、会議へのユーザー呼び出しは拒否され、その通話が完了していないか終了したことが Lync クライアントに報告されます。</span><span class="sxs-lookup"><span data-stu-id="f5c37-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="f5c37-146">場所に基づくルーティング enforcements を使って会議に参加する PSTN エンドポイントは、その状態に関係なく、場所に基づくルーティングが有効になっていないトランク経由で参加している場合は、その状態に関係なく、会議への参加に制限されません。</span><span class="sxs-lookup"><span data-stu-id="f5c37-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f5c37-147">PSTN への出口がない SIP トランク経由で Mediptserver に接続された PBX システムは、SIP トランクが定義されている同じネットワークサイトにある Lync ユーザーと同じ enforcements を持つことになります。</span><span class="sxs-lookup"><span data-stu-id="f5c37-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="f5c37-148">たとえば、PSTN エンドポイントは、PBX ユーザーと Lync ユーザーが同じネットワークサイトにある場合に、そのユーザーとの会議に参加することができます。そうしないと、PBX ユーザーが Lync ユーザーとは別のネットワークサイトにいる場合、PSTN エンドポイントは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="f5c37-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

