---
title: 'Lync Server 2013: 場所に基づくルーティングの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 108dd35c7f184c974a317f68901c94bc81e9e403
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="38232-102">Lync Server 2013 の場所に基づくルーティングの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="38232-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38232-103">_**最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="38232-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="38232-104">このトピックでは、位置情報に基づくルーティングの構成に関連するプロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="38232-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="38232-105">位置情報に基づくルーティングを構成する前に、Lync Server Enterprise Edition または Standard Edition をエンタープライズ Voip に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38232-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="38232-106">エンタープライズ Voip を展開すると、位置情報に基づくルーティングに必要なコンポーネントが既にインストールされ、有効になります。</span><span class="sxs-lookup"><span data-stu-id="38232-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="38232-107">位置情報に基づくルーティングの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="38232-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38232-108">段階</span><span class="sxs-lookup"><span data-stu-id="38232-108">Phase</span></span></th>
<th><span data-ttu-id="38232-109">ステップ</span><span class="sxs-lookup"><span data-stu-id="38232-109">Steps</span></span></th>
<th><span data-ttu-id="38232-110">必要なグループおよび役割</span><span class="sxs-lookup"><span data-stu-id="38232-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="38232-111">「展開」のドキュメント</span><span class="sxs-lookup"><span data-stu-id="38232-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38232-112">エンタープライズ VoIP の展開</span><span class="sxs-lookup"><span data-stu-id="38232-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="38232-113">Trunks を構成する</span><span class="sxs-lookup"><span data-stu-id="38232-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="38232-114">音声ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="38232-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="38232-115">ボイスルートの定義</span><span class="sxs-lookup"><span data-stu-id="38232-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="38232-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="38232-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="38232-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="38232-117">CsAdministrator</span></span><br />
<span data-ttu-id="38232-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="38232-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="38232-119">エンタープライズボイスの展開</span><span class="sxs-lookup"><span data-stu-id="38232-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38232-120">エンタープライズ Voip の展開を確認する</span><span class="sxs-lookup"><span data-stu-id="38232-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38232-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="38232-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="38232-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="38232-122">CsAdministrator</span></span><br />
<span data-ttu-id="38232-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="38232-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38232-124">ネットワークのリージョン、サイト、サブネットを構成する</span><span class="sxs-lookup"><span data-stu-id="38232-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="38232-125">ネットワークの領域を作成する</span><span class="sxs-lookup"><span data-stu-id="38232-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="38232-126">ネットワークサイトを作成する</span><span class="sxs-lookup"><span data-stu-id="38232-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="38232-127">サブネットとネットワークサイトを関連付ける</span><span class="sxs-lookup"><span data-stu-id="38232-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="38232-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="38232-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="38232-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="38232-129">CsAdministrator</span></span><br />
<span data-ttu-id="38232-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="38232-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="38232-131">ネットワークの領域、サイト、サブネットについて</span><span class="sxs-lookup"><span data-stu-id="38232-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="38232-132">ネットワーク領域を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="38232-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="38232-133">ネットワークサイトを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="38232-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="38232-134">サブネットとネットワークサイトを関連付ける</span><span class="sxs-lookup"><span data-stu-id="38232-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38232-135">位置に基づくルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="38232-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="38232-136">ボイスルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="38232-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="38232-137">トランクごとに個別のトランク構成を定義する</span><span class="sxs-lookup"><span data-stu-id="38232-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="38232-138">ボイスポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="38232-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="38232-139">位置に基づくルーティング構成を有効にする</span><span class="sxs-lookup"><span data-stu-id="38232-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="38232-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="38232-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="38232-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="38232-141">CsAdministrator</span></span><br />
<span data-ttu-id="38232-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="38232-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="38232-143">展開の例</span><span class="sxs-lookup"><span data-stu-id="38232-143">Sample Deployment</span></span>

<span data-ttu-id="38232-144">次の展開は、位置情報に基づくルーティングによって有効になるメカニズムの詳細を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="38232-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="38232-145">![4784 e1bd2230-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "4784 e1bd2230-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="38232-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="38232-146">着信 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="38232-146">Incoming PSTN calls</span></span>

<span data-ttu-id="38232-147">管理者は、場所に基づくルーティングのために "サイト1ゲートウェイ" への通話をルーティングするように定義されたトランクを有効にし、"サイト1ゲートウェイ" をサイト1に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="38232-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="38232-148">有効にすると、"サイト1ゲートウェイ" 経由でルーティングされた通話は、サイト1にあるユーザーにのみルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="38232-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="38232-149">サイト2などのサイト内のユーザーに送信される "サイト1ゲートウェイ" トランク経由でルーティングされたすべての通話は、PSTN の有料電話のバイパスを防ぐためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="38232-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="38232-150">"サイト1ゲートウェイ" 経由でのすべての着信 PSTN 通話は、サイト1にあるエンドポイントにのみルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="38232-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="38232-151">たとえば、"Lync user 1" がサイト2に転送されると、"サイト1ゲートウェイ" を経由するすべての着信 PSTN 通話は、サイト2にある "Lync user 1" エンドポイントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="38232-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="38232-152">"Lync user 1" は、ユーザーの位置情報を特定できない不明のネットワークサイトに移動する場合に、同じルーティングルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="38232-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="38232-153">次の表は、このコンテキストでの "Lync user 1" のユーザーエクスペリエンスをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="38232-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="38232-154">ネットワークサイト1にある Lync ユーザー1エンドポイント</span><span class="sxs-lookup"><span data-stu-id="38232-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="38232-155">ネットワークサイト2にある Lync ユーザー1エンドポイント</span><span class="sxs-lookup"><span data-stu-id="38232-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="38232-156">不明のネットワークサイトにある Lync ユーザー1エンドポイント</span><span class="sxs-lookup"><span data-stu-id="38232-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38232-157">Lync ユーザー1への着信 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="38232-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="38232-158">通話はこの場所のエンドポイントにルーティングされます</span><span class="sxs-lookup"><span data-stu-id="38232-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="38232-159">通話はこの場所のエンドポイントにはルーティングされません</span><span class="sxs-lookup"><span data-stu-id="38232-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="38232-160">通話はこの場所のエンドポイントにはルーティングされません</span><span class="sxs-lookup"><span data-stu-id="38232-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="38232-161">発信 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="38232-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="38232-162">音声ルートは、ユーザーに直接割り当てられている音声ポリシーと、ネットワークサイトに割り当てられているボイスルーティングポリシーの両方で参照されます。</span><span class="sxs-lookup"><span data-stu-id="38232-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="38232-163">どちらのポリシーにもルートへの参照が含まれており、異なる方法で通話をルーティングするために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="38232-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="38232-164">たとえば、管理者は、特定のユーザーのボイスポリシーで "サイト2ゲートウェイ" を使ってすべての発信通話のルートを定義しながら、ネットワークサイト1のすべてのユーザーに対してボイスルーティングポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="38232-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="38232-165">これらのユーザーはネットワークサイト1に配置されていますが、発信通話は "サイト1ゲートウェイ" を介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="38232-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="38232-166">場所に基づくルーティング用に構成されたネットワークサイトにユーザーがいる場合、ネットワークサイトのボイスルーティングポリシーのルートは、ユーザーのボイスポリシールートを上書きします。</span><span class="sxs-lookup"><span data-stu-id="38232-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="38232-167">この規則は、別のサイトに一時的に移動するユーザーに特に便利です。</span><span class="sxs-lookup"><span data-stu-id="38232-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="38232-168">この例では、ユーザーは自分の位置に対してローカルなゲートウェイを常に使用します。"Lync user 3" を "サイト 2" に配置している場合、すべての送信通話は "サイト2ゲートウェイ" 経由でルーティングされますが、サイト1に移動すると、サイト1のユーザーが送信したすべての発信通話は、"サイト1ゲートウェイ" 経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="38232-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="38232-169">次の表は、Lync ユーザー1が次のネットワークサイトから発信通話を発信した場合のユーザーエクスペリエンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="38232-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="38232-170">ネットワークサイト1</span><span class="sxs-lookup"><span data-stu-id="38232-170">Network site 1</span></span></th>
<th><span data-ttu-id="38232-171">ネットワークサイト2</span><span class="sxs-lookup"><span data-stu-id="38232-171">Network site 2</span></span></th>
<th><span data-ttu-id="38232-172">不明のネットワークサイト、または場所に基づくルーティングでは無効</span><span class="sxs-lookup"><span data-stu-id="38232-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38232-173">発信の承認</span><span class="sxs-lookup"><span data-stu-id="38232-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="38232-174">Lync ユーザー1のボイスポリシー</span><span class="sxs-lookup"><span data-stu-id="38232-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="38232-175">Lync ユーザー1のボイスポリシー</span><span class="sxs-lookup"><span data-stu-id="38232-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="38232-176">Lync ユーザー1のボイスポリシー</span><span class="sxs-lookup"><span data-stu-id="38232-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38232-177">発信通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="38232-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="38232-178">サイト1ボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="38232-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="38232-179">サイト2ボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="38232-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="38232-180">ユーザーのボイスポリシーと、位置情報に基づくルーティングで有効になっていないシステムのみ</span><span class="sxs-lookup"><span data-stu-id="38232-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="38232-181">着信の転送と転送</span><span class="sxs-lookup"><span data-stu-id="38232-181">Call transfers and forwards</span></span>

<span data-ttu-id="38232-182">通話が転送または転送されると、通話のルーティングが位置情報に基づくルーティングの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="38232-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="38232-183">次の表は、Lync ユーザー1が、別の Lync ユーザーに PSTN 通話を転送または転送する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="38232-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38232-184">着信転送または転送を開始するユーザー</span><span class="sxs-lookup"><span data-stu-id="38232-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="38232-185">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="38232-185">Lync user 2</span></span></th>
<th><span data-ttu-id="38232-186">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="38232-186">Lync user 4</span></span></th>
<th><span data-ttu-id="38232-187">ネットワークサイトの Lync ユーザーが位置情報に基づくルーティングを有効にしていない</span><span class="sxs-lookup"><span data-stu-id="38232-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38232-188">Lync ユーザー1</span><span class="sxs-lookup"><span data-stu-id="38232-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="38232-189">通話または着信を転送できます。</span><span class="sxs-lookup"><span data-stu-id="38232-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="38232-190">通話または着信を転送できません。</span><span class="sxs-lookup"><span data-stu-id="38232-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="38232-191">通話または着信を転送できません。</span><span class="sxs-lookup"><span data-stu-id="38232-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="38232-192">次の表は、場所に基づくルーティングが、転送される Lync ユーザー (Lync ユーザー2、Lync ユーザー4など) の場所に基づいて通話が PSTN エンドポイントにどのようにルーティングされるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="38232-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38232-193">通話が転送または転送されるエンドポイント</span><span class="sxs-lookup"><span data-stu-id="38232-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="38232-194">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="38232-194">Lync user 2</span></span></th>
<th><span data-ttu-id="38232-195">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="38232-195">Lync user 4</span></span></th>
<th><span data-ttu-id="38232-196">ネットワークサイトの Lync ユーザーが位置情報に基づくルーティングを有効にしていない</span><span class="sxs-lookup"><span data-stu-id="38232-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38232-197">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="38232-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="38232-198">着信の転送または転送は、サイト1のゲートウェイ経由でサイト1のボイスルーティングポリシーと出口を経由してルーティングされます</span><span class="sxs-lookup"><span data-stu-id="38232-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="38232-199">着信の転送または転送は、サイト2ゲートウェイ経由でサイト2のボイスルーティングポリシーと出口を経由してルーティングされる</span><span class="sxs-lookup"><span data-stu-id="38232-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="38232-200">着信の転送または転送は、Lync ユーザーの音声ポリシーを通じてルーティングされ、位置情報に基づくルーティングのためにゲートウェイ経由で送信が有効になっていない (使用可能な場合)</span><span class="sxs-lookup"><span data-stu-id="38232-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="38232-201">同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="38232-201">Simultaneous ringing</span></span>

<span data-ttu-id="38232-202">サンプルトポロジで位置情報に基づくルーティングを構成すると、次の操作が強制されます。</span><span class="sxs-lookup"><span data-stu-id="38232-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="38232-203">次の表は、場所に基づくルーティングで、さまざまな Lync ユーザー (Lync ユーザー2、Lync ユーザー4など) の同時呼び出しを許可するかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="38232-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38232-204">着信 PSTN 通話ターゲット</span><span class="sxs-lookup"><span data-stu-id="38232-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="38232-205">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="38232-205">Lync user 2</span></span></th>
<th><span data-ttu-id="38232-206">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="38232-206">Lync user 4</span></span></th>
<th><span data-ttu-id="38232-207">ネットワークサイトの Lync ユーザーが位置情報に基づくルーティングを有効にしていない</span><span class="sxs-lookup"><span data-stu-id="38232-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38232-208">Lync ユーザー1</span><span class="sxs-lookup"><span data-stu-id="38232-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="38232-209">同時呼び出しが許可されている</span><span class="sxs-lookup"><span data-stu-id="38232-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="38232-210">同時呼び出しが許可されていない</span><span class="sxs-lookup"><span data-stu-id="38232-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="38232-211">同時呼び出しが許可されていない</span><span class="sxs-lookup"><span data-stu-id="38232-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="38232-212">次の表は、場所ベースのルーティングで、異なる Lync ユーザーから PSTN エンドポイントへの同時呼び出しを許可するかどうか (Lync ユーザー2、Lync ユーザー4など) を示しています。</span><span class="sxs-lookup"><span data-stu-id="38232-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38232-213">同時呼び出しのターゲット ユーザー</span><span class="sxs-lookup"><span data-stu-id="38232-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="38232-214">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="38232-214">Lync user 2</span></span></th>
<th><span data-ttu-id="38232-215">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="38232-215">Lync user 4</span></span></th>
<th><span data-ttu-id="38232-216">ネットワークサイトの Lync ユーザーが位置情報に基づくルーティングを有効にしていない</span><span class="sxs-lookup"><span data-stu-id="38232-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38232-217">Lync ユーザー1携帯電話 (PSTN エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="38232-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="38232-218">ネットワークサイト1のボイスルーティングポリシーと出口によるルーティング (サイト1ゲートウェイ経由)</span><span class="sxs-lookup"><span data-stu-id="38232-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="38232-219">サイト2ゲートウェイ経由でのネットワークサイト2のボイスルーティングポリシーと出口による通話</span><span class="sxs-lookup"><span data-stu-id="38232-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="38232-220">発信者の音声ポリシーを通してルーティングし、位置情報に基づくルーティングのために PSTN ゲートウェイ経由で着信する</span><span class="sxs-lookup"><span data-stu-id="38232-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38232-221">関連項目</span><span class="sxs-lookup"><span data-stu-id="38232-221">See Also</span></span>


[<span data-ttu-id="38232-222">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="38232-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

