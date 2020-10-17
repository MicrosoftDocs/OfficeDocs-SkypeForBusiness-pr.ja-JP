---
title: 'Lync Server 2013: 会議用の Location-Based ルーティングの要件'
description: 'Lync Server 2013: 会議用の Location-Based ルーティングの要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542523"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="b02b1-103">Lync Server 2013 での会議の Location-Based ルーティングの要件</span><span class="sxs-lookup"><span data-stu-id="b02b1-103">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b02b1-104">_**トピックの最終更新日:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="b02b1-104">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="b02b1-105">Location-Based ルーティング会議アプリケーションをインストールして構成するために必要な要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b02b1-105">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="b02b1-106">Lync Server 2013 の累積的な更新プログラム2を、トポロジ内のすべてのサーバーまたはプールに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b02b1-106">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b02b1-107">トポロジ内の Lync server またはプールに Lync Server 2013 の累積的な更新プログラム2以降がインストールされていない場合、Lync 会議の Location-Based ルーティングを行うことは保証できません。</span><span class="sxs-lookup"><span data-stu-id="b02b1-107">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="b02b1-108">Lync Server 2013 Location-Based ルーティングは Location-Based ルーティング会議アプリケーションの前提条件です。</span><span class="sxs-lookup"><span data-stu-id="b02b1-108">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="b02b1-109">Lync Server 2013 Location-Based ルーティングの構成の詳細については、「 [Location-Based ルーティングを構成](lync-server-2013-configuring-location-based-routing.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b02b1-109">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="b02b1-110">Location-Based ルーティング会議アプリケーションの要件は、Lync Server 2013 Location-Based ルーティングの要件と同じです。</span><span class="sxs-lookup"><span data-stu-id="b02b1-110">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="b02b1-111">詳細については、「 [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b02b1-111">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="b02b1-112">サポートされるサーバー</span><span class="sxs-lookup"><span data-stu-id="b02b1-112">Supported Servers</span></span>

<span data-ttu-id="b02b1-113">Location-Based ルーティング会議アプリケーションでは、Lync Server 2013 の累積更新プログラム2が、トポロジ内のすべての Front-End プールおよび Standard Edition サーバーに展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b02b1-113">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="b02b1-114">トポロジ内の一部の Lync サーバーに Lync Server 2013 の累積的な更新プログラム2がインストールされていない場合は、Lync 会議と提案型の通話の転送に Location-Based ルーティングの制限を完全に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b02b1-114">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="b02b1-115">次の表は、Location-Based ルーティングをサポートするサーバーの役割とバージョンの組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="b02b1-115">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b02b1-116">Front-End プールのバージョン</span><span class="sxs-lookup"><span data-stu-id="b02b1-116">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="b02b1-117">仲介サーバーのバージョン</span><span class="sxs-lookup"><span data-stu-id="b02b1-117">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="b02b1-118">サポート</span><span class="sxs-lookup"><span data-stu-id="b02b1-118">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02b1-119">Lync Server 2013 累積更新プログラム2</span><span class="sxs-lookup"><span data-stu-id="b02b1-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="b02b1-120">Lync Server 2013 累積更新プログラム2</span><span class="sxs-lookup"><span data-stu-id="b02b1-120">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="b02b1-121">必要</span><span class="sxs-lookup"><span data-stu-id="b02b1-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b02b1-122">Lync Server 2013 累積更新プログラム2</span><span class="sxs-lookup"><span data-stu-id="b02b1-122">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="b02b1-123">Lync Server 2013 累積更新プログラム1</span><span class="sxs-lookup"><span data-stu-id="b02b1-123">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="b02b1-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="b02b1-124">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02b1-125">Lync Server 2013 累積更新プログラム2</span><span class="sxs-lookup"><span data-stu-id="b02b1-125">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="b02b1-126">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b02b1-126">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="b02b1-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="b02b1-127">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b02b1-128">Lync Server 2013 累積更新プログラム2</span><span class="sxs-lookup"><span data-stu-id="b02b1-128">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="b02b1-129">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b02b1-129">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b02b1-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="b02b1-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02b1-131">Lync Server 2013 累積更新プログラム1</span><span class="sxs-lookup"><span data-stu-id="b02b1-131">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="b02b1-132">任意</span><span class="sxs-lookup"><span data-stu-id="b02b1-132">Any</span></span></p></td>
<td><p><span data-ttu-id="b02b1-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="b02b1-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b02b1-134">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b02b1-134">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="b02b1-135">任意</span><span class="sxs-lookup"><span data-stu-id="b02b1-135">Any</span></span></p></td>
<td><p><span data-ttu-id="b02b1-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="b02b1-136">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b02b1-137">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b02b1-137">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b02b1-138">任意</span><span class="sxs-lookup"><span data-stu-id="b02b1-138">Any</span></span></p></td>
<td><p><span data-ttu-id="b02b1-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="b02b1-139">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="b02b1-140">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="b02b1-140">Supported Clients</span></span>

<span data-ttu-id="b02b1-141">Lync 会議の Location-Based ルーティングをサポートする Lync クライアントは、Lync Server 2013 Location-Based ルーティングをサポートするクライアントと同じです。</span><span class="sxs-lookup"><span data-stu-id="b02b1-141">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="b02b1-142">詳細については、 [Location-Based ルーティングのクライアントとサーバーのサポート](lync-server-2013-client-and-server-support-for-location-based-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b02b1-142">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="b02b1-143">コンサルティング呼び出しの転送に関する仲介サーバーの要件</span><span class="sxs-lookup"><span data-stu-id="b02b1-143">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="b02b1-144">Location-Based ルーティング会議アプリケーションは、スタンドアロンの仲介サーバーを展開する必要があります。これには、提案型呼び出しの転送に関する Location-Based ルーティングの制限を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b02b1-144">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="b02b1-145">コンサルティング呼び出し転送の Location-Based ルーティングを強制するには、仲介サーバーが、Location-Based ルーティングが必要なネットワーク地域で、1つの仲介サーバーピア (PBX、SIP ゲートウェイなど) にのみ関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b02b1-145">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="b02b1-146">別の仲介サーバーピアが同じネットワーク地域に展開されている場合は、仲介サーバーのピアを別の仲介サーバーに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b02b1-146">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="b02b1-147">この要件は、次のように詳細に説明されています。</span><span class="sxs-lookup"><span data-stu-id="b02b1-147">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="b02b1-148">複数の仲介サーバーピアごとに1つの仲介サーバー。複数の SIP トランクで構成されている仲介サーバー (Pbx およびゲートウェイ) に対して、コンサルティング呼び出し転送が仲介サーバーのピアにルーティングされる場合、一部の SIP トランクでコンサルティング呼び出しの転送が許可されているが、他の SIP トランクでは許可されていない場合は、</span><span class="sxs-lookup"><span data-stu-id="b02b1-148">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="b02b1-149">たとえば、PSTN ゲートウェイ仲介サーバーのピアと PBX 仲介サーバーのピアを1つの仲介サーバーでサービスしている場合は、次の動作が確認されます。</span><span class="sxs-lookup"><span data-stu-id="b02b1-149">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="b02b1-150">特定のサイト (サイト 1) からの Lync ユーザーが、提案転送を介して別のサイト (つまり、サイト 2) から Lync ユーザーに通話を転送しようとすると、その通話は PSTN の有料サービスを回避することを許可されません。</span><span class="sxs-lookup"><span data-stu-id="b02b1-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="b02b1-151">特定のサイトの Lync ユーザー (サイト 1) が、別のサイト (サイト 1) 内の PBX エンドポイントとの通話を、提案転送を介して別のサイト (つまり、サイト 2) から Lync ユーザーに転送しようとすると、PSTN の有料の通話が行われない場合でも通話が許可されません。</span><span class="sxs-lookup"><span data-stu-id="b02b1-151">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="b02b1-152">仲介サーバーピアごとに別々の仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="b02b1-152">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="b02b1-153">コンサルティング転送が仲介サーバーピアを対象にしている場合は、仲介サーバーによって提供される単一の仲介サーバーピアに対して、コンサルティング転送が評価されます。</span><span class="sxs-lookup"><span data-stu-id="b02b1-153">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="b02b1-154">この通話は、サイト内の他のすべての Mediations いるサーバーピアが個別の仲介サーバーによって処理されている場合でも、PSTN の有料通話で発生する可能性に基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="b02b1-154">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="b02b1-155">たとえば、PSTN ゲートウェイ仲介サーバーのピアと PBX 仲介サーバーのピアをサービスしている個別の仲介サーバーの場合、次の動作が確認されます。</span><span class="sxs-lookup"><span data-stu-id="b02b1-155">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="b02b1-156">特定のサイト (サイト 1) からの Lync ユーザーが、提案転送を介して別のサイト (つまり、サイト 2) から Lync ユーザーに通話を転送しようとすると、その通話は PSTN の有料サービスを回避することを許可されません。</span><span class="sxs-lookup"><span data-stu-id="b02b1-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="b02b1-157">特定のサイトの Lync ユーザー (サイト 1) が、別のサイト (サイト 1) の PBX ユーザーに対して、提案転送を介して別のサイト (つまり、サイト 2) からの通話を転送しようとすると、その通話は PSTN の有料の通話がバイパスされる可能性があるため許可されます。</span><span class="sxs-lookup"><span data-stu-id="b02b1-157">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="b02b1-158">Location-Based ルーティング会議アプリケーションでサポートされていない機能</span><span class="sxs-lookup"><span data-stu-id="b02b1-158">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="b02b1-159">Location-Based ルーティング会議アプリケーションでは、次の機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b02b1-159">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="b02b1-160">ダイヤルイン会議。</span><span class="sxs-lookup"><span data-stu-id="b02b1-160">Dial-in conferencing.</span></span> <span data-ttu-id="b02b1-161">ダイヤルイン会議に Location-Based ルーティングを強制することはできません。</span><span class="sxs-lookup"><span data-stu-id="b02b1-161">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="b02b1-162">会議開催者が Location-Based ルーティングを有効にしている Lync ユーザーであっても、特定の会議に対するダイヤルイン要求は Location-Based ルーティングによって制限されません。</span><span class="sxs-lookup"><span data-stu-id="b02b1-162">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="b02b1-163">Location-Based ルーティング制限を適用する必要がある地域では、会議アクセス番号をプロビジョニングしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b02b1-163">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

