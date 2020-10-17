---
title: 'Lync Server 2013: Location-Based ルーティングの展開プロセス'
description: 'Lync Server 2013: Location-Based ルーティングの展開プロセス。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c321d9b0eada6e9501b2ded69120feae36be171
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551063"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="87a96-103">Lync Server 2013 での Location-Based ルーティングの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="87a96-103">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87a96-104">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="87a96-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="87a96-105">ここでは、Location-Based ルーティングの構成に関連するプロセスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="87a96-105">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="87a96-106">Location-Based ルーティングを構成する前に、エンタープライズ Voip を使用して Lync Server Enterprise Edition または Standard Edition を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87a96-106">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="87a96-107">Location-Based ルーティングで必要なコンポーネントは、エンタープライズ Voip を展開するときに既にインストールされ、有効にされています。</span><span class="sxs-lookup"><span data-stu-id="87a96-107">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="87a96-108">Location-Based ルーティングの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="87a96-108">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87a96-109">フェーズ</span><span class="sxs-lookup"><span data-stu-id="87a96-109">Phase</span></span></th>
<th><span data-ttu-id="87a96-110">手順</span><span class="sxs-lookup"><span data-stu-id="87a96-110">Steps</span></span></th>
<th><span data-ttu-id="87a96-111">必要なグループおよび役割</span><span class="sxs-lookup"><span data-stu-id="87a96-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="87a96-112">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="87a96-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87a96-113">エンタープライズ VoIP の展開</span><span class="sxs-lookup"><span data-stu-id="87a96-113">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="87a96-114">トランクを構成する</span><span class="sxs-lookup"><span data-stu-id="87a96-114">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="87a96-115">音声ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="87a96-115">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="87a96-116">音声ルートを定義する</span><span class="sxs-lookup"><span data-stu-id="87a96-116">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87a96-117">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="87a96-117">CSVoiceAdmins</span></span><br />
<span data-ttu-id="87a96-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="87a96-118">CsAdministrator</span></span><br />
<span data-ttu-id="87a96-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="87a96-119">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="87a96-120">エンタープライズ Voip の展開</span><span class="sxs-lookup"><span data-stu-id="87a96-120">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87a96-121">エンタープライズ Voip の展開を確認する</span><span class="sxs-lookup"><span data-stu-id="87a96-121">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87a96-122">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="87a96-122">CSVoiceAdmins</span></span><br />
<span data-ttu-id="87a96-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="87a96-123">CsAdministrator</span></span><br />
<span data-ttu-id="87a96-124">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="87a96-124">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87a96-125">ネットワーク地域、サイト、およびサブネットを構成する</span><span class="sxs-lookup"><span data-stu-id="87a96-125">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="87a96-126">ネットワーク地域を作成する</span><span class="sxs-lookup"><span data-stu-id="87a96-126">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="87a96-127">ネットワークサイトを作成する</span><span class="sxs-lookup"><span data-stu-id="87a96-127">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="87a96-128">サブネットとネットワークサイトの関連付け</span><span class="sxs-lookup"><span data-stu-id="87a96-128">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87a96-129">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="87a96-129">CSVoiceAdmins</span></span><br />
<span data-ttu-id="87a96-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="87a96-130">CsAdministrator</span></span><br />
<span data-ttu-id="87a96-131">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="87a96-131">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="87a96-132">ネットワーク領域、サイト、およびサブネットについて</span><span class="sxs-lookup"><span data-stu-id="87a96-132">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="87a96-133">ネットワーク領域の作成または変更</span><span class="sxs-lookup"><span data-stu-id="87a96-133">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="87a96-134">ネットワーク サイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="87a96-134">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="87a96-135">ネットワーク サイトとサブネットの関連付け</span><span class="sxs-lookup"><span data-stu-id="87a96-135">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87a96-136">Location-Based ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="87a96-136">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="87a96-137">音声ルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="87a96-137">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="87a96-138">トランクごとに個別のトランク構成を定義する</span><span class="sxs-lookup"><span data-stu-id="87a96-138">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="87a96-139">音声ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="87a96-139">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="87a96-140">Location-Based ルーティング構成を有効にする</span><span class="sxs-lookup"><span data-stu-id="87a96-140">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87a96-141">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="87a96-141">CSVoiceAdmins</span></span><br />
<span data-ttu-id="87a96-142">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="87a96-142">CsAdministrator</span></span><br />
<span data-ttu-id="87a96-143">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="87a96-143">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="87a96-144">サンプルの展開</span><span class="sxs-lookup"><span data-stu-id="87a96-144">Sample Deployment</span></span>

<span data-ttu-id="87a96-145">Location-Based ルーティングによって有効になるメカニズムについては、次の展開を使用して説明します。</span><span class="sxs-lookup"><span data-stu-id="87a96-145">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="87a96-146">![e1bd2230-44 da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44 da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="87a96-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="87a96-147">着信 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="87a96-147">Incoming PSTN calls</span></span>

<span data-ttu-id="87a96-148">管理者は、Location-Based ルーティングのために "サイト1ゲートウェイ" への呼び出しをルーティングするように定義されたトランクを有効にし、"サイト1ゲートウェイ" をサイト1に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="87a96-148">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="87a96-149">有効にした場合、"Site 1 Gateway" を経由してルーティングされる通話は、サイト1にあるユーザーにのみルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="87a96-149">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="87a96-150">サイト2などの「サイト1ゲートウェイ」トランクを介してルーティングされたすべての通話は、PSTN の有料電話を回避するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="87a96-150">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="87a96-151">"サイト1ゲートウェイ" 経由のすべての着信 PSTN 通話は、サイト1にあるエンドポイントへのルーティングのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="87a96-151">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="87a96-152">たとえば、"Lync user 1" がサイト2に転送されると、"サイト1ゲートウェイ" 経由のすべての着信 PSTN 通話は、サイト2にある "Lync user 1" エンドポイントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="87a96-152">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="87a96-153">"Lync user 1" が、ユーザーの場所を特定できない不明なネットワークサイトに移動する場合は、同じルーティングルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="87a96-153">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="87a96-154">次の表では、このコンテキストでの "Lync user 1" のユーザー環境の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="87a96-154">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="87a96-155">ネットワークサイト1にある Lync ユーザー1エンドポイント</span><span class="sxs-lookup"><span data-stu-id="87a96-155">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="87a96-156">ネットワークサイト2にある Lync ユーザー1エンドポイント</span><span class="sxs-lookup"><span data-stu-id="87a96-156">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="87a96-157">不明なネットワークサイトにある Lync ユーザー1エンドポイント</span><span class="sxs-lookup"><span data-stu-id="87a96-157">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87a96-158">Lync ユーザー1への PSTN 通話の着信</span><span class="sxs-lookup"><span data-stu-id="87a96-158">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="87a96-159">呼び出しは、この場所のエンドポイントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="87a96-159">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="87a96-160">呼び出しは、この場所のエンドポイントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="87a96-160">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="87a96-161">呼び出しは、この場所のエンドポイントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="87a96-161">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="87a96-162">PSTN 通話の発信</span><span class="sxs-lookup"><span data-stu-id="87a96-162">Outgoing PSTN calls</span></span>

<span data-ttu-id="87a96-163">音声ルートは、ユーザーに直接割り当てられた音声ポリシーと、ネットワークサイトに割り当てられた音声ルーティングポリシーの両方で参照されます。</span><span class="sxs-lookup"><span data-stu-id="87a96-163">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="87a96-164">両方のポリシーには、呼び出しを異なる方法でルーティングするために使用できるルートへの参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="87a96-164">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="87a96-165">たとえば、一部のユーザーの音声ポリシーでは、"site 2 Gateway" を経由してすべての発信呼び出しに対してルートを定義する一方で、ネットワークサイト1に配置されているすべてのユーザーに対して音声ルーティングポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="87a96-165">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="87a96-166">これらのユーザーはネットワークサイト1に配置されていますが、それらの発信通話は "サイト1ゲートウェイ" を経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="87a96-166">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="87a96-167">ユーザーが Location-Based ルーティング用に構成されたネットワークサイトに配置されている場合、ネットワークサイトの音声ルーティングポリシールートはユーザーの音声ポリシールートを上書きします。</span><span class="sxs-lookup"><span data-stu-id="87a96-167">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="87a96-168">このルールは、別のサイトに一時的に移動するユーザーに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="87a96-168">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="87a96-169">この特定のケースでは、ユーザーは自分の場所に対してローカルなゲートウェイを常に使用します。"Lync user 3" が "Site 2" に配置されている場合は、自分のすべての発信通話が "サイト2ゲートウェイ" 経由でルーティングされますが、サイト1に移動すると、サイト1のユーザーの発信通話はすべて "サイト1ゲートウェイ" を経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="87a96-169">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="87a96-170">次の表は、Lync ユーザー1が次のネットワークサイトから発信呼び出しを行うユーザーの利便性を示しています。</span><span class="sxs-lookup"><span data-stu-id="87a96-170">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="87a96-171">ネットワークサイト1</span><span class="sxs-lookup"><span data-stu-id="87a96-171">Network site 1</span></span></th>
<th><span data-ttu-id="87a96-172">ネットワークサイト2</span><span class="sxs-lookup"><span data-stu-id="87a96-172">Network site 2</span></span></th>
<th><span data-ttu-id="87a96-173">不明なネットワークサイト、または Location-Based ルーティングに対して有効になっていない</span><span class="sxs-lookup"><span data-stu-id="87a96-173">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87a96-174">発信呼び出しの承認</span><span class="sxs-lookup"><span data-stu-id="87a96-174">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="87a96-175">Lync ユーザー1音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="87a96-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="87a96-176">Lync ユーザー1音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="87a96-176">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="87a96-177">Lync ユーザー1音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="87a96-177">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87a96-178">発信通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="87a96-178">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="87a96-179">サイト1音声ルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="87a96-179">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="87a96-180">サイト2音声ルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="87a96-180">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="87a96-181">ユーザーの音声ポリシーおよび Location-Based ルーティングが有効になっていないシステムのみ</span><span class="sxs-lookup"><span data-stu-id="87a96-181">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="87a96-182">着信の転送と転送</span><span class="sxs-lookup"><span data-stu-id="87a96-182">Call transfers and forwards</span></span>

<span data-ttu-id="87a96-183">呼び出しが転送または転送される場合、呼び出しのルーティングは Location-Based ルーティングによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="87a96-183">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="87a96-184">次の表は、Lync ユーザー1が別の Lync ユーザーに PSTN 通話を転送または転送することを示しています。</span><span class="sxs-lookup"><span data-stu-id="87a96-184">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87a96-185">着信転送または転送を開始するユーザー</span><span class="sxs-lookup"><span data-stu-id="87a96-185">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="87a96-186">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="87a96-186">Lync user 2</span></span></th>
<th><span data-ttu-id="87a96-187">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="87a96-187">Lync user 4</span></span></th>
<th><span data-ttu-id="87a96-188">ネットワークサイトの Lync ユーザーが Location-Based ルーティングに対して有効になっていない</span><span class="sxs-lookup"><span data-stu-id="87a96-188">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87a96-189">Lync ユーザー1</span><span class="sxs-lookup"><span data-stu-id="87a96-189">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="87a96-190">着信/転送が許可されている</span><span class="sxs-lookup"><span data-stu-id="87a96-190">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="87a96-191">着信/転送は許可されていません</span><span class="sxs-lookup"><span data-stu-id="87a96-191">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="87a96-192">着信/転送は許可されていません</span><span class="sxs-lookup"><span data-stu-id="87a96-192">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="87a96-193">次の表は、転送される Lync ユーザーの場所 (Lync ユーザー2、Lync user 4 など) に基づいて、Location-Based ルーティングが PSTN エンドポイントにどのようにルーティングされるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="87a96-193">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87a96-194">通話が転送または転送されるエンドポイント</span><span class="sxs-lookup"><span data-stu-id="87a96-194">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="87a96-195">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="87a96-195">Lync user 2</span></span></th>
<th><span data-ttu-id="87a96-196">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="87a96-196">Lync user 4</span></span></th>
<th><span data-ttu-id="87a96-197">ネットワークサイトの Lync ユーザーが Location-Based ルーティングに対して有効になっていない</span><span class="sxs-lookup"><span data-stu-id="87a96-197">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87a96-198">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="87a96-198">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="87a96-199">着信転送または転送は、サイト1ゲートウェイ経由でのサイト1音声ルーティングポリシーおよび出口を経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="87a96-199">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="87a96-200">着信転送または転送は、サイト2の音声ルーティングポリシーおよび出口を介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="87a96-200">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="87a96-201">通話の転送または転送は、Lync ユーザーの音声ポリシーを経由してルーティングされ、場所に基づくルーティングが有効になっていないゲートウェイ経由の出口</span><span class="sxs-lookup"><span data-stu-id="87a96-201">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="87a96-202">同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="87a96-202">Simultaneous ringing</span></span>

<span data-ttu-id="87a96-203">サンプルトポロジで場所ベースのルーティングを構成すると、次の操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="87a96-203">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="87a96-204">次の表は Location-Based ルーティングが異なる Lync ユーザー (Lync ユーザー2、Lync ユーザー4など) に対して同時呼び出しを許可するかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="87a96-204">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87a96-205">着信 PSTN 通話のターゲット</span><span class="sxs-lookup"><span data-stu-id="87a96-205">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="87a96-206">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="87a96-206">Lync user 2</span></span></th>
<th><span data-ttu-id="87a96-207">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="87a96-207">Lync user 4</span></span></th>
<th><span data-ttu-id="87a96-208">ネットワークサイトの Lync ユーザーが Location-Based ルーティングに対して有効になっていない</span><span class="sxs-lookup"><span data-stu-id="87a96-208">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87a96-209">Lync ユーザー1</span><span class="sxs-lookup"><span data-stu-id="87a96-209">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="87a96-210">同時呼び出しを許可する</span><span class="sxs-lookup"><span data-stu-id="87a96-210">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="87a96-211">同時呼び出しは許可されていません</span><span class="sxs-lookup"><span data-stu-id="87a96-211">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="87a96-212">同時呼び出しは許可されていません</span><span class="sxs-lookup"><span data-stu-id="87a96-212">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="87a96-213">次の表に、Location-Based ルーティングで、異なる Lync ユーザー (Lync ユーザー2、Lync user 4 など) から PSTN エンドポイントへの同時呼び出しを許可するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="87a96-213">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87a96-214">同時呼び出しのターゲット</span><span class="sxs-lookup"><span data-stu-id="87a96-214">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="87a96-215">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="87a96-215">Lync user 2</span></span></th>
<th><span data-ttu-id="87a96-216">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="87a96-216">Lync user 4</span></span></th>
<th><span data-ttu-id="87a96-217">ネットワークサイトの Lync ユーザーが Location-Based ルーティングに対して有効になっていない</span><span class="sxs-lookup"><span data-stu-id="87a96-217">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87a96-218">Lync ユーザー1携帯電話 (PSTN エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="87a96-218">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="87a96-219">通話は、ネットワークサイト1の音声ルーティングポリシーと、サイト1ゲートウェイ経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="87a96-219">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="87a96-220">通話は、ネットワークサイト2の音声ルーティングポリシーと、サイト2ゲートウェイ経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="87a96-220">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="87a96-221">発信者の音声ポリシーを経由してルーティングし、PSTN ゲートウェイを経由してルーティングする通話は Location-Based ルーティングに対して有効ではない</span><span class="sxs-lookup"><span data-stu-id="87a96-221">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="87a96-222">関連項目</span><span class="sxs-lookup"><span data-stu-id="87a96-222">See Also</span></span>


[<span data-ttu-id="87a96-223">Lync Server 2013 での Location-Based ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="87a96-223">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

