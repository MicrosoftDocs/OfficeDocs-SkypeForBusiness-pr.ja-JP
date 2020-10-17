---
title: 'Lync Server 2013: 会議の Location-Based ルーティングの概要'
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
ms.openlocfilehash: 9dd3508221babdd9c503e21d5662a1bbe60d4ce0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520954"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="8a566-102">Lync Server 2013 での会議の Location-Based ルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="8a566-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a566-103">_**トピックの最終更新日:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="8a566-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="8a566-104">Location-Based ルーティング会議アプリケーションは、PSTN 通話のバイパスを防止するメカニズムを Lync 会議に提供します。</span><span class="sxs-lookup"><span data-stu-id="8a566-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="8a566-105">アプリケーションはアクティブな会議を監視し、参加している Lync ユーザーの場所に基づいて Location-Based ルーティング制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="8a566-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="8a566-106">Location-Based ルーティング会議アプリケーションは、次の条件が満たされた場合に Lync 会議に対して Location-Based ルーティングを適用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8a566-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="8a566-107">Location-Based ルーティングに対して会議の開催者が有効になります。</span><span class="sxs-lookup"><span data-stu-id="8a566-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="8a566-108">Location-Based ルーティング制限は、Location-Based ルーティングが有効になっているユーザーによって開催される電話会議にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a566-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="8a566-109">少なくとも1つの会議参加者が PSTN エンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="8a566-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="8a566-110">Location-Based ルーティング制限は、PSTN エンドポイントを含む電話会議に対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a566-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="8a566-111">PSTN に電話会議をブリッジするために使用される PSTN ゲートウェイが配置されているネットワークサイト、および開催者と参加者が接続しているネットワークサイトがあります。</span><span class="sxs-lookup"><span data-stu-id="8a566-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="8a566-112">Location-Based ルーティング会議アプリケーションによって、Lync ユーザーと PSTN エンドポイントが異なるネットワークサイトから同じ電話会議に参加することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="8a566-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="8a566-113">会議の開催者が Location-Based ルーティングに対して有効になっている場合、会議アプリケーションは次の制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="8a566-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="8a566-114">Lync 会議に参加できるエンドポイントは、既に会議に参加しているエンドポイントに依存します。この制限は、参加したエンドポイントの退室と新しいエンドポイントが会議に参加したときに調整されます。</span><span class="sxs-lookup"><span data-stu-id="8a566-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="8a566-115">開催者と参加者が、同じネットワークサイトから Lync 会議に参加している場合、PSTN エンドポイント、同じネットワークサイトの別の参加者、別のネットワークサイトからの別の参加者、または不明なネットワークサイトからの参加者が参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8a566-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="8a566-116">開催者と参加者が、異なるまたは不明なネットワークサイトから会議に参加している場合は、pstn エンドポイントは Location-Based ルーティングに対して SIP トランクからの ingresses によって有効になっていると、会議に参加することができません。</span><span class="sxs-lookup"><span data-stu-id="8a566-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="8a566-117">開催者と参加者が全員同じネットワークサイトから参加していて、PSTN から同じ会議に参加している参加者がいる場合、別のネットワークサイトの Lync エンドポイントは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="8a566-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="8a566-118">これらの会議 Location-Based ルーティング制限を次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="8a566-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a566-119">任意の時点での会議のユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="8a566-120">会議への参加が許可されたユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="8a566-121">ユーザーが会議に参加することは許可されていません</span><span class="sxs-lookup"><span data-stu-id="8a566-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a566-122">単一のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="8a566-123">同じネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="8a566-124">別のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="8a566-125">不明なネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="8a566-126">フェデレーション Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="8a566-127">PSTN エンドポイントから参加しているユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="8a566-128">なし</span><span class="sxs-lookup"><span data-stu-id="8a566-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a566-129">不明なネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="8a566-130">任意のサイトの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="8a566-131">不明なサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="8a566-132">フェデレーション Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="8a566-133">PSTN エンドポイント経由で参加するユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a566-134">異なるネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="8a566-135">任意のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="8a566-136">不明なネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="8a566-137">フェデレーション Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="8a566-138">PSTN エンドポイント経由で参加するユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a566-139">単一のネットワークサイトからの Lync VoIP クライアントユーザーと PSTN エンドポイントから参加しているユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="8a566-140">同じネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="8a566-141">別のネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="8a566-142">不明なネットワークサイトからの Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="8a566-143">フェデレーション Lync VoIP クライアントユーザー</span><span class="sxs-lookup"><span data-stu-id="8a566-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8a566-144">Location-Based ルーティング会議アプリケーションのその他の特徴は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8a566-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="8a566-145">ユーザーが Location-Based ルーティング制限を使用して電話会議に参加することを許可されていない場合、会議へのユーザー呼び出しは拒否され、その通話が完了していないか、または終了したことが Lync クライアントから報告されます。</span><span class="sxs-lookup"><span data-stu-id="8a566-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="8a566-146">Location-Based ルーティング強制を使用して電話会議に参加する PSTN エンドポイントは、そのエンドポイントが Location-Based ルーティングに対して有効になっていないトランクを介して参加した場合、その状態にかかわらず、会議への参加を制限されません。</span><span class="sxs-lookup"><span data-stu-id="8a566-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="8a566-147">PSTN への呼び出しを出口しない SIP トランクを介して Mediadditionalserver に接続されている PBX システムは、SIP トランクが定義されているのと同じネットワークサイトにある Lync ユーザーと同じ強制を持つことになります。</span><span class="sxs-lookup"><span data-stu-id="8a566-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="8a566-148">たとえば、PSTN エンドポイントは、PBX ユーザーと Lync ユーザーが同じネットワークサイトに配置されている場合に、そのユーザーとの電話会議に参加できます。そうしないと、PBX ユーザーが Lync ユーザーとは別のネットワークサイトにある場合、PSTN エンドポイントは会議への参加を許可されません。</span><span class="sxs-lookup"><span data-stu-id="8a566-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

