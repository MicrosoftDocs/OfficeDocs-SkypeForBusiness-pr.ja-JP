---
title: 'Lync Server 2013: 場所に基づくルーティングの展開プロセス'
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
ms.openlocfilehash: 46da1be1d18477d56fa4b3046557102e8771ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f8899-102">Lync Server 2013 での場所に基づくルーティングの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="f8899-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8899-103">_**トピックの最終更新日:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="f8899-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="f8899-104">ここでは、場所に基づくルーティングの構成に関連するプロセスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8899-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="f8899-105">場所に基づくルーティングを構成する前に、エンタープライズ Voip を使用して Lync Server Enterprise Edition または Standard Edition を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8899-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="f8899-106">場所に基づくルーティングで必要なコンポーネントは、エンタープライズ Voip を展開するときに既にインストールされ、有効にされています。</span><span class="sxs-lookup"><span data-stu-id="f8899-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="f8899-107">場所に基づくルーティングの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="f8899-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8899-108">フェーズ</span><span class="sxs-lookup"><span data-stu-id="f8899-108">Phase</span></span></th>
<th><span data-ttu-id="f8899-109">手順</span><span class="sxs-lookup"><span data-stu-id="f8899-109">Steps</span></span></th>
<th><span data-ttu-id="f8899-110">必要なグループおよび役割</span><span class="sxs-lookup"><span data-stu-id="f8899-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="f8899-111">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="f8899-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8899-112">エンタープライズ Voip の展開</span><span class="sxs-lookup"><span data-stu-id="f8899-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f8899-113">トランクを構成する</span><span class="sxs-lookup"><span data-stu-id="f8899-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="f8899-114">音声ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f8899-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="f8899-115">音声ルートを定義する</span><span class="sxs-lookup"><span data-stu-id="f8899-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f8899-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="f8899-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="f8899-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8899-117">CsAdministrator</span></span><br />
<span data-ttu-id="f8899-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8899-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f8899-119">エンタープライズ Voip の展開</span><span class="sxs-lookup"><span data-stu-id="f8899-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8899-120">エンタープライズ Voip の展開を確認する</span><span class="sxs-lookup"><span data-stu-id="f8899-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8899-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="f8899-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="f8899-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8899-122">CsAdministrator</span></span><br />
<span data-ttu-id="f8899-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8899-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8899-124">ネットワーク地域、サイト、およびサブネットを構成する</span><span class="sxs-lookup"><span data-stu-id="f8899-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f8899-125">ネットワーク地域を作成する</span><span class="sxs-lookup"><span data-stu-id="f8899-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="f8899-126">ネットワークサイトを作成する</span><span class="sxs-lookup"><span data-stu-id="f8899-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="f8899-127">サブネットとネットワークサイトの関連付け</span><span class="sxs-lookup"><span data-stu-id="f8899-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f8899-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="f8899-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="f8899-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8899-129">CsAdministrator</span></span><br />
<span data-ttu-id="f8899-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8899-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f8899-131">ネットワーク領域、サイト、およびサブネットについて</span><span class="sxs-lookup"><span data-stu-id="f8899-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="f8899-132">ネットワーク領域の作成または変更</span><span class="sxs-lookup"><span data-stu-id="f8899-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="f8899-133">ネットワーク サイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="f8899-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="f8899-134">ネットワーク サイトとサブネットの関連付け</span><span class="sxs-lookup"><span data-stu-id="f8899-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8899-135">場所に基づくルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="f8899-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f8899-136">音声ルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f8899-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="f8899-137">トランクごとに個別のトランク構成を定義する</span><span class="sxs-lookup"><span data-stu-id="f8899-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="f8899-138">音声ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="f8899-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="f8899-139">場所に基づくルーティング構成を有効にする</span><span class="sxs-lookup"><span data-stu-id="f8899-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f8899-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="f8899-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="f8899-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8899-141">CsAdministrator</span></span><br />
<span data-ttu-id="f8899-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8899-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="f8899-143">サンプルの展開</span><span class="sxs-lookup"><span data-stu-id="f8899-143">Sample Deployment</span></span>

<span data-ttu-id="f8899-144">次の展開は、場所に基づくルーティングによって有効になるメカニズムについて説明するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8899-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="f8899-145">![e1bd2230-44 da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44 da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="f8899-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="f8899-146">着信 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="f8899-146">Incoming PSTN calls</span></span>

<span data-ttu-id="f8899-147">管理者は、場所に基づいたルーティングのための "サイト1ゲートウェイ" への呼び出しをルーティングするように定義されたトランクを有効にして、"サイト1ゲートウェイ" をサイト1に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="f8899-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="f8899-148">有効にした場合、"Site 1 Gateway" を経由してルーティングされる通話は、サイト1にあるユーザーにのみルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f8899-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="f8899-149">サイト2などの「サイト1ゲートウェイ」トランクを介してルーティングされたすべての通話は、PSTN の有料電話を回避するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f8899-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="f8899-150">"サイト1ゲートウェイ" 経由のすべての着信 PSTN 通話は、サイト1にあるエンドポイントへのルーティングのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="f8899-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="f8899-151">たとえば、"Lync user 1" がサイト2に転送されると、"サイト1ゲートウェイ" 経由のすべての着信 PSTN 通話は、サイト2にある "Lync user 1" エンドポイントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="f8899-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="f8899-152">"Lync user 1" が、ユーザーの場所を特定できない不明なネットワークサイトに移動する場合は、同じルーティングルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f8899-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="f8899-153">次の表では、このコンテキストでの "Lync user 1" のユーザー環境の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="f8899-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="f8899-154">ネットワークサイト1にある Lync ユーザー1エンドポイント</span><span class="sxs-lookup"><span data-stu-id="f8899-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="f8899-155">ネットワークサイト2にある Lync ユーザー1エンドポイント</span><span class="sxs-lookup"><span data-stu-id="f8899-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="f8899-156">不明なネットワークサイトにある Lync ユーザー1エンドポイント</span><span class="sxs-lookup"><span data-stu-id="f8899-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8899-157">Lync ユーザー1への PSTN 通話の着信</span><span class="sxs-lookup"><span data-stu-id="f8899-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="f8899-158">呼び出しは、この場所のエンドポイントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f8899-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="f8899-159">呼び出しは、この場所のエンドポイントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="f8899-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="f8899-160">呼び出しは、この場所のエンドポイントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="f8899-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="f8899-161">PSTN 通話の発信</span><span class="sxs-lookup"><span data-stu-id="f8899-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="f8899-162">音声ルートは、ユーザーに直接割り当てられた音声ポリシーと、ネットワークサイトに割り当てられた音声ルーティングポリシーの両方で参照されます。</span><span class="sxs-lookup"><span data-stu-id="f8899-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="f8899-163">両方のポリシーには、呼び出しを異なる方法でルーティングするために使用できるルートへの参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f8899-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="f8899-164">たとえば、一部のユーザーの音声ポリシーでは、"site 2 Gateway" を経由してすべての発信呼び出しに対してルートを定義する一方で、ネットワークサイト1に配置されているすべてのユーザーに対して音声ルーティングポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f8899-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="f8899-165">これらのユーザーはネットワークサイト1に配置されていますが、それらの発信通話は "サイト1ゲートウェイ" を経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f8899-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="f8899-166">場所に基づくルーティング用に構成されたネットワークサイトにユーザーがいる場合、ネットワークサイトの音声ルーティングポリシールートはユーザーの音声ポリシールートを上書きします。</span><span class="sxs-lookup"><span data-stu-id="f8899-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="f8899-167">このルールは、別のサイトに一時的に移動するユーザーに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f8899-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="f8899-168">この特定のケースでは、ユーザーは自分の場所に対してローカルなゲートウェイを常に使用します。"Lync user 3" が "Site 2" に配置されている場合は、自分のすべての発信通話が "サイト2ゲートウェイ" 経由でルーティングされますが、サイト1に移動すると、サイト1のユーザーの発信通話はすべて "サイト1ゲートウェイ" を経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f8899-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="f8899-169">次の表は、Lync ユーザー1が次のネットワークサイトから発信呼び出しを行うユーザーの利便性を示しています。</span><span class="sxs-lookup"><span data-stu-id="f8899-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="f8899-170">ネットワークサイト1</span><span class="sxs-lookup"><span data-stu-id="f8899-170">Network site 1</span></span></th>
<th><span data-ttu-id="f8899-171">ネットワークサイト2</span><span class="sxs-lookup"><span data-stu-id="f8899-171">Network site 2</span></span></th>
<th><span data-ttu-id="f8899-172">不明なネットワークサイト、または場所に基づくルーティングが有効になっていない</span><span class="sxs-lookup"><span data-stu-id="f8899-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8899-173">発信呼び出しの承認</span><span class="sxs-lookup"><span data-stu-id="f8899-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="f8899-174">Lync ユーザー1音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="f8899-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="f8899-175">Lync ユーザー1音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="f8899-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="f8899-176">Lync ユーザー1音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="f8899-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8899-177">発信通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="f8899-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="f8899-178">サイト1音声ルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="f8899-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f8899-179">サイト2音声ルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="f8899-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f8899-180">ユーザーの音声ポリシーと、場所に基づくルーティングが有効になっていないシステムのみ</span><span class="sxs-lookup"><span data-stu-id="f8899-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="f8899-181">着信の転送と転送</span><span class="sxs-lookup"><span data-stu-id="f8899-181">Call transfers and forwards</span></span>

<span data-ttu-id="f8899-182">通話が転送または転送される場合、通話のルーティングは場所に基づくルーティングによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="f8899-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="f8899-183">次の表は、Lync ユーザー1が別の Lync ユーザーに PSTN 通話を転送または転送することを示しています。</span><span class="sxs-lookup"><span data-stu-id="f8899-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8899-184">着信転送または転送を開始するユーザー</span><span class="sxs-lookup"><span data-stu-id="f8899-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="f8899-185">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="f8899-185">Lync user 2</span></span></th>
<th><span data-ttu-id="f8899-186">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="f8899-186">Lync user 4</span></span></th>
<th><span data-ttu-id="f8899-187">ネットワークサイトの Lync ユーザーの場所に基づくルーティングが有効になっていません</span><span class="sxs-lookup"><span data-stu-id="f8899-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8899-188">Lync ユーザー1</span><span class="sxs-lookup"><span data-stu-id="f8899-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="f8899-189">着信/転送が許可されている</span><span class="sxs-lookup"><span data-stu-id="f8899-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="f8899-190">着信/転送は許可されていません</span><span class="sxs-lookup"><span data-stu-id="f8899-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="f8899-191">着信/転送は許可されていません</span><span class="sxs-lookup"><span data-stu-id="f8899-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="f8899-192">次の表は、転送される Lync ユーザーの場所 (Lync ユーザー2、Lync user 4 など) に基づいて、場所に基づくルーティングが PSTN エンドポイントにどのようにルーティングされるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="f8899-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8899-193">通話が転送または転送されるエンドポイント</span><span class="sxs-lookup"><span data-stu-id="f8899-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="f8899-194">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="f8899-194">Lync user 2</span></span></th>
<th><span data-ttu-id="f8899-195">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="f8899-195">Lync user 4</span></span></th>
<th><span data-ttu-id="f8899-196">ネットワークサイトの Lync ユーザーの場所に基づくルーティングが有効になっていません</span><span class="sxs-lookup"><span data-stu-id="f8899-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8899-197">PSTN エンドポイント</span><span class="sxs-lookup"><span data-stu-id="f8899-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="f8899-198">着信転送または転送は、サイト1ゲートウェイ経由でのサイト1音声ルーティングポリシーおよび出口を経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f8899-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="f8899-199">着信転送または転送は、サイト2の音声ルーティングポリシーおよび出口を介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f8899-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="f8899-200">通話の転送または転送は、Lync ユーザーの音声ポリシーを経由してルーティングされ、場所に基づくルーティングが有効になっていないゲートウェイ経由の出口</span><span class="sxs-lookup"><span data-stu-id="f8899-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="f8899-201">同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="f8899-201">Simultaneous ringing</span></span>

<span data-ttu-id="f8899-202">サンプルトポロジで場所ベースのルーティングを構成すると、次の操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f8899-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="f8899-203">次の表は、場所に基づくルーティングが、異なる Lync ユーザー (Lync ユーザー2、Lync ユーザー4など) に対して同時呼び出しを許可するかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="f8899-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8899-204">着信 PSTN 通話のターゲット</span><span class="sxs-lookup"><span data-stu-id="f8899-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="f8899-205">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="f8899-205">Lync user 2</span></span></th>
<th><span data-ttu-id="f8899-206">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="f8899-206">Lync user 4</span></span></th>
<th><span data-ttu-id="f8899-207">ネットワークサイトの Lync ユーザーの場所に基づくルーティングが有効になっていません</span><span class="sxs-lookup"><span data-stu-id="f8899-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8899-208">Lync ユーザー1</span><span class="sxs-lookup"><span data-stu-id="f8899-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="f8899-209">同時呼び出しを許可する</span><span class="sxs-lookup"><span data-stu-id="f8899-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="f8899-210">同時呼び出しは許可されていません</span><span class="sxs-lookup"><span data-stu-id="f8899-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="f8899-211">同時呼び出しは許可されていません</span><span class="sxs-lookup"><span data-stu-id="f8899-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="f8899-212">次の表に、場所に基づくルーティングで、異なる Lync ユーザー (Lync ユーザー2、Lync user 4 など) からの PSTN エンドポイントへの同時呼び出しを許可するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f8899-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8899-213">同時呼び出しのターゲット</span><span class="sxs-lookup"><span data-stu-id="f8899-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="f8899-214">Lync ユーザー2</span><span class="sxs-lookup"><span data-stu-id="f8899-214">Lync user 2</span></span></th>
<th><span data-ttu-id="f8899-215">Lync ユーザー4</span><span class="sxs-lookup"><span data-stu-id="f8899-215">Lync user 4</span></span></th>
<th><span data-ttu-id="f8899-216">ネットワークサイトの Lync ユーザーの場所に基づくルーティングが有効になっていません</span><span class="sxs-lookup"><span data-stu-id="f8899-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8899-217">Lync ユーザー1携帯電話 (PSTN エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="f8899-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="f8899-218">通話は、ネットワークサイト1の音声ルーティングポリシーと、サイト1ゲートウェイ経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="f8899-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="f8899-219">通話は、ネットワークサイト2の音声ルーティングポリシーと、サイト2ゲートウェイ経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="f8899-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="f8899-220">発信者の音声ポリシーを通じてルーティングされ、場所に基づいたルーティングに対して PSTN ゲートウェイ経由で出口を通過する通話</span><span class="sxs-lookup"><span data-stu-id="f8899-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8899-221">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8899-221">See Also</span></span>


[<span data-ttu-id="f8899-222">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="f8899-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

