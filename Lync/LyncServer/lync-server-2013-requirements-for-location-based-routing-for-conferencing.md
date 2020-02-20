---
title: 'Lync Server 2013: 会議の場所に基づくルーティングの要件'
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
ms.openlocfilehash: 4ce41a338f3185f6f051da3df41e91c6b287af20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="c4d93-102">Lync Server 2013 での会議の場所に基づくルーティングの要件</span><span class="sxs-lookup"><span data-stu-id="c4d93-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4d93-103">_**トピックの最終更新日:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="c4d93-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="c4d93-104">場所に基づくルーティング会議アプリケーションをインストールして構成するために必要な要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c4d93-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="c4d93-105">Lync Server 2013 の累積的な更新プログラム2を、トポロジ内のすべてのサーバーまたはプールに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d93-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4d93-106">トポロジ内の Lync server またはプールに Lync Server 2013 の累積的な更新プログラム2以降がインストールされていない場合、Lync 会議の場所に基づくルーティングの適用は保証できません。</span><span class="sxs-lookup"><span data-stu-id="c4d93-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="c4d93-107">Lync Server 2013 の場所に基づくルーティングは、場所に基づくルーティング会議アプリケーションの前提条件です。</span><span class="sxs-lookup"><span data-stu-id="c4d93-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="c4d93-108">Lync Server 2013 の場所に基づくルーティングの構成の詳細については、「[場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d93-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="c4d93-109">場所に基づくルーティング会議アプリケーションの要件は、Lync Server 2013 の場所に基づくルーティングの要件と同じです。</span><span class="sxs-lookup"><span data-stu-id="c4d93-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="c4d93-110">詳細については、「[場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d93-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="c4d93-111">サポートされるサーバー</span><span class="sxs-lookup"><span data-stu-id="c4d93-111">Supported Servers</span></span>

<span data-ttu-id="c4d93-112">場所に基づくルーティング会議アプリケーションを使用するには、Lync Server 2013 の累積的な更新プログラム2が、トポロジ内のすべてのフロントエンドプールおよび Standard Edition サーバーに展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d93-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="c4d93-113">Lync Server 2013 の累積的な更新プログラム2が、トポロジ内の一部の Lync サーバーにインストールされていない場合は、Lync 会議とコンサルティング呼び出しの転送に対して、場所に基づくルーティング制限を完全に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4d93-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="c4d93-114">次の表は、場所に基づくルーティングをサポートするサーバーの役割とバージョンの組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4d93-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4d93-115">フロントエンドプールのバージョン</span><span class="sxs-lookup"><span data-stu-id="c4d93-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="c4d93-116">仲介サーバーのバージョン</span><span class="sxs-lookup"><span data-stu-id="c4d93-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="c4d93-117">サポート済み</span><span class="sxs-lookup"><span data-stu-id="c4d93-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4d93-118">Lync Server 2013 累積更新プログラム2</span><span class="sxs-lookup"><span data-stu-id="c4d93-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="c4d93-119">Lync Server 2013 累積更新プログラム2</span><span class="sxs-lookup"><span data-stu-id="c4d93-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="c4d93-120">はい</span><span class="sxs-lookup"><span data-stu-id="c4d93-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4d93-121">Lync Server 2013 累積更新プログラム2</span><span class="sxs-lookup"><span data-stu-id="c4d93-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="c4d93-122">Lync Server 2013 累積更新プログラム1</span><span class="sxs-lookup"><span data-stu-id="c4d93-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="c4d93-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="c4d93-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4d93-124">Lync Server 2013 累積更新プログラム2</span><span class="sxs-lookup"><span data-stu-id="c4d93-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="c4d93-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c4d93-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="c4d93-126">いいえ</span><span class="sxs-lookup"><span data-stu-id="c4d93-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4d93-127">Lync Server 2013 累積更新プログラム2</span><span class="sxs-lookup"><span data-stu-id="c4d93-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="c4d93-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c4d93-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="c4d93-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="c4d93-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4d93-130">Lync Server 2013 累積更新プログラム1</span><span class="sxs-lookup"><span data-stu-id="c4d93-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="c4d93-131">任意</span><span class="sxs-lookup"><span data-stu-id="c4d93-131">Any</span></span></p></td>
<td><p><span data-ttu-id="c4d93-132">いいえ</span><span class="sxs-lookup"><span data-stu-id="c4d93-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4d93-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c4d93-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="c4d93-134">任意</span><span class="sxs-lookup"><span data-stu-id="c4d93-134">Any</span></span></p></td>
<td><p><span data-ttu-id="c4d93-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="c4d93-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4d93-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c4d93-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="c4d93-137">任意</span><span class="sxs-lookup"><span data-stu-id="c4d93-137">Any</span></span></p></td>
<td><p><span data-ttu-id="c4d93-138">いいえ</span><span class="sxs-lookup"><span data-stu-id="c4d93-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="c4d93-139">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="c4d93-139">Supported Clients</span></span>

<span data-ttu-id="c4d93-140">Lync 会議の場所に基づくルーティングをサポートする Lync クライアントは、Lync Server 2013 の場所に基づくルーティングをサポートするクライアントと同じです。</span><span class="sxs-lookup"><span data-stu-id="c4d93-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="c4d93-141">詳細については、「[クライアントとサーバーのサポート](lync-server-2013-client-and-server-support-for-location-based-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d93-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="c4d93-142">コンサルティング呼び出しの転送に関する仲介サーバーの要件</span><span class="sxs-lookup"><span data-stu-id="c4d93-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="c4d93-143">場所に基づくルーティング会議アプリケーションは、スタンドアロンの仲介サーバーを展開する必要があります。これには、提案型の通話の転送に対して、場所に基づくルーティングの制限を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d93-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="c4d93-144">提案型呼び出しの転送の場所ベースのルーティングを適用するには、場所に基づくルーティングが必要なネットワーク地域で、仲介サーバーが1つの仲介サーバーピア (PBX、SIP ゲートウェイなど) にのみ関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d93-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="c4d93-145">別の仲介サーバーピアが同じネットワーク地域に展開されている場合は、仲介サーバーのピアを別の仲介サーバーに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d93-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="c4d93-146">この要件は、次のように詳細に説明されています。</span><span class="sxs-lookup"><span data-stu-id="c4d93-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="c4d93-147">複数の仲介サーバーピアごとに1台の仲介サーバー複数の SIP トランクを使用して構成されている仲介サーバーを使用して、コンサルティングによる転送が仲介サーバーのピアにルーティングされる場合 (Pbx およびゲートウェイ)、提案一部の SIP トランクでコンサルティング呼び出し転送が許可されていても、他の SIP トランク経由では許可されていない場合、通話転送は PSTN の有料電話を回避するためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c4d93-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="c4d93-148">たとえば、PSTN ゲートウェイ仲介サーバーのピアと PBX 仲介サーバーのピアを1つの仲介サーバーでサービスしている場合は、次の動作が確認されます。</span><span class="sxs-lookup"><span data-stu-id="c4d93-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="c4d93-149">特定のサイト (サイト 1) からの Lync ユーザーが、提案転送を介して別のサイト (つまり、サイト 2) から Lync ユーザーに通話を転送しようとすると、その通話は PSTN の有料サービスを回避することを許可されません。</span><span class="sxs-lookup"><span data-stu-id="c4d93-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="c4d93-150">特定のサイトの Lync ユーザー (サイト 1) が、別のサイト (サイト 1) 内の PBX エンドポイントとの通話を、提案転送を介して別のサイトの Lync ユーザーに転送しようとすると、その通話は PSTN tol の可能性がある場合でも許可されません。l バイパス。</span><span class="sxs-lookup"><span data-stu-id="c4d93-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="c4d93-151">仲介サーバーピアごとに別々の仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="c4d93-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="c4d93-152">コンサルティング転送が仲介サーバーピアを対象にしている場合は、仲介サーバーによって提供される単一の仲介サーバーピアに対して、コンサルティング転送が評価されます。</span><span class="sxs-lookup"><span data-stu-id="c4d93-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="c4d93-153">この通話は、サイト内の他のすべての Mediations いるサーバーピアが個別の仲介サーバーによって処理されている場合でも、PSTN の有料通話で発生する可能性に基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="c4d93-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="c4d93-154">たとえば、PSTN ゲートウェイ仲介サーバーのピアと PBX 仲介サーバーのピアをサービスしている個別の仲介サーバーの場合、次の動作が確認されます。</span><span class="sxs-lookup"><span data-stu-id="c4d93-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="c4d93-155">特定のサイト (サイト 1) からの Lync ユーザーが、提案転送を介して別のサイト (つまり、サイト 2) から Lync ユーザーに通話を転送しようとすると、その通話は PSTN の有料サービスを回避することを許可されません。</span><span class="sxs-lookup"><span data-stu-id="c4d93-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="c4d93-156">特定のサイトの Lync ユーザー (サイト 1) が、別のサイト (サイト 1) の PBX ユーザーに対して、提案転送を介して別のサイトの (サイト 2) の通話を転送しようとすると、その通話は許可されますが、PSTN の有料電話のバイパスでは発生しません。留守番.</span><span class="sxs-lookup"><span data-stu-id="c4d93-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="c4d93-157">場所に基づくルーティング会議アプリケーションでサポートされていない機能</span><span class="sxs-lookup"><span data-stu-id="c4d93-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="c4d93-158">次の機能は、場所に基づくルーティング会議アプリケーションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c4d93-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="c4d93-159">ダイヤルイン会議。</span><span class="sxs-lookup"><span data-stu-id="c4d93-159">Dial-in conferencing.</span></span> <span data-ttu-id="c4d93-160">ダイヤルイン会議に対して、場所に基づくルーティングを強制することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4d93-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="c4d93-161">会議開催者が場所に基づくルーティングを有効にした Lync ユーザーであっても、特定の会議に対するダイヤルイン要求は、場所に基づいたルーティングによって制限されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c4d93-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="c4d93-162">場所に基づくルーティング制限を適用する必要がある地域では、会議アクセス番号をプロビジョニングしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c4d93-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

