---
title: 'Lync Server 2013: 会議での位置情報に基づくルーティングの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 925b71497012d7e6ed9c19042a079a7b30630c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="63b90-102">Lync Server 2013 での会議の位置情報に基づくルーティングの要件</span><span class="sxs-lookup"><span data-stu-id="63b90-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63b90-103">_**最終更新日:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="63b90-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="63b90-104">場所に基づくルーティング会議アプリケーションをインストールして構成するために必要な要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="63b90-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="63b90-105">Lync Server 2013 累積更新プログラム2は、トポロジ内のすべてのサーバーまたはプールに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b90-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63b90-106">トポロジ内の Lync サーバーまたはプールに Lync Server 2013 累積更新プログラム2以降がインストールされていない場合、Lync 会議の位置情報に基づくルーティングの適用は保証されません。</span><span class="sxs-lookup"><span data-stu-id="63b90-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="63b90-107">Lync Server 2013 の場所に基づくルーティングは、位置ベースのルーティング会議アプリケーションの前提条件です。</span><span class="sxs-lookup"><span data-stu-id="63b90-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="63b90-108">Lync Server 2013 の場所に基づくルーティングの構成の詳細については、「[場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b90-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="63b90-109">位置に基づくルーティング会議アプリケーションの要件は、Lync Server 2013 の場所に基づくルーティングの要件と同じです。</span><span class="sxs-lookup"><span data-stu-id="63b90-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="63b90-110">詳細については、「[場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b90-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="63b90-111">サポートされているサーバー</span><span class="sxs-lookup"><span data-stu-id="63b90-111">Supported Servers</span></span>

<span data-ttu-id="63b90-112">場所に基づくルーティング会議アプリケーションを使用するには、Lync Server 2013 累積更新プログラム2が、トポロジ内のすべてのフロントエンドプールおよび標準エディションのサーバーに展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b90-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="63b90-113">Lync Server 2013 累積更新プログラム2が、トポロジ内の一部の Lync サーバーにインストールされていない場合、場所に基づくルーティングの制限は、Lync 会議とコンサルティングによる通話転送に完全に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="63b90-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="63b90-114">次の表は、場所に基づくルーティングをサポートするサーバーの役割とバージョンの組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="63b90-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63b90-115">フロント エンド プールのバージョン</span><span class="sxs-lookup"><span data-stu-id="63b90-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="63b90-116">仲介サーバーのバージョン</span><span class="sxs-lookup"><span data-stu-id="63b90-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="63b90-117">サポート対象</span><span class="sxs-lookup"><span data-stu-id="63b90-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b90-118">Lync Server 2013 累積更新プログラム 2</span><span class="sxs-lookup"><span data-stu-id="63b90-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="63b90-119">Lync Server 2013 累積更新プログラム 2</span><span class="sxs-lookup"><span data-stu-id="63b90-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="63b90-120">はい</span><span class="sxs-lookup"><span data-stu-id="63b90-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b90-121">Lync Server 2013 累積更新プログラム 2</span><span class="sxs-lookup"><span data-stu-id="63b90-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="63b90-122">Lync Server 2013 累積更新プログラム 1</span><span class="sxs-lookup"><span data-stu-id="63b90-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="63b90-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="63b90-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b90-124">Lync Server 2013 累積更新プログラム 2</span><span class="sxs-lookup"><span data-stu-id="63b90-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="63b90-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="63b90-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="63b90-126">いいえ</span><span class="sxs-lookup"><span data-stu-id="63b90-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b90-127">Lync Server 2013 累積更新プログラム 2</span><span class="sxs-lookup"><span data-stu-id="63b90-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="63b90-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="63b90-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="63b90-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="63b90-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b90-130">Lync Server 2013 累積更新プログラム 1</span><span class="sxs-lookup"><span data-stu-id="63b90-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="63b90-131">任意</span><span class="sxs-lookup"><span data-stu-id="63b90-131">Any</span></span></p></td>
<td><p><span data-ttu-id="63b90-132">不可</span><span class="sxs-lookup"><span data-stu-id="63b90-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b90-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="63b90-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="63b90-134">任意</span><span class="sxs-lookup"><span data-stu-id="63b90-134">Any</span></span></p></td>
<td><p><span data-ttu-id="63b90-135">不可</span><span class="sxs-lookup"><span data-stu-id="63b90-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b90-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="63b90-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="63b90-137">任意</span><span class="sxs-lookup"><span data-stu-id="63b90-137">Any</span></span></p></td>
<td><p><span data-ttu-id="63b90-138">不可</span><span class="sxs-lookup"><span data-stu-id="63b90-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="63b90-139">サポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="63b90-139">Supported Clients</span></span>

<span data-ttu-id="63b90-140">Lync 会議の位置情報に基づくルーティングをサポートする Lync クライアントは、Lync Server 2013 の場所に基づくルーティングをサポートしているクライアントと同じです。</span><span class="sxs-lookup"><span data-stu-id="63b90-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="63b90-141">詳細については、「[場所に基づくルーティングのクライアントとサーバーのサポート](lync-server-2013-client-and-server-support-for-location-based-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b90-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="63b90-142">提案型通話転送の仲介サーバー要件</span><span class="sxs-lookup"><span data-stu-id="63b90-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="63b90-143">位置情報に基づくルーティング会議アプリケーションでは、提案型の通話転送についての位置情報に基づくルーティング制限を適用するために、スタンドアロンの仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b90-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="63b90-144">提案型の通話転送の位置情報に基づくルーティングを適用するには、位置情報に基づくルーティングが必要なネットワーク領域で、仲介サーバーが1つの仲介サーバーピア (PBX、SIP ゲートウェイなど) と関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b90-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="63b90-145">追加の仲介サーバーピアが同じネットワーク領域に展開されている場合、仲介サーバーピアは、別の仲介サーバーと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b90-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="63b90-146">この要件は、次のように詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="63b90-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="63b90-147">複数の仲介サーバーピアに対して1つの仲介サーバーを使用して、複数の SIP trunks で構成されている仲介サーバーを経由して仲介サーバーピアにルーティングされる場合 (Pbx とゲートウェイ)、コンサルティング一部の SIP trunks で提案型通話転送が許可されていても、他の SIP trunks では許可されていない場合は、着信転送がブロックされています。</span><span class="sxs-lookup"><span data-stu-id="63b90-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="63b90-148">たとえば、PSTN ゲートウェイ仲介サーバーピアと PBX 仲介サーバーピアをサービスしている単一の仲介サーバーの場合、次の動作が監視されます。</span><span class="sxs-lookup"><span data-stu-id="63b90-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="63b90-149">特定のサイトの Lync ユーザー (つまり、サイト 1) から別のサイト (つまり、サイト 2) の Lync ユーザーに対して、提案型転送を使用して通話を転送しようとすると、PSTN の有料通話を防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="63b90-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="63b90-150">特定のサイトの Lync ユーザー (サイト 1) と、別のサイト (サイト 1) の PBX エンドポイントを使用して、別のサイト (サイト 2) との通話を発信しようとしたときに、tol の可能性がある場合でも、通話は許可されません。l バイパス。</span><span class="sxs-lookup"><span data-stu-id="63b90-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="63b90-151">仲介サーバーピアごとに個別の仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="63b90-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="63b90-152">提案型転送が仲介サーバーピアを対象としている場合は、仲介サーバーによって処理される単一の仲介サーバーピアに対して、コンサルティング転送が評価されます。</span><span class="sxs-lookup"><span data-stu-id="63b90-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="63b90-153">この通話は、サイト内の他のすべての Mediations サーバーピアが、個別の仲介サーバーによってサービスされている場合でも、PSTN の有料電話による通話は許可されません。</span><span class="sxs-lookup"><span data-stu-id="63b90-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="63b90-154">たとえば、PSTN ゲートウェイ仲介サーバーピアと PBX 仲介サーバーピアをサービスしている別個の仲介サーバーがある場合は、次の動作が監視されます。</span><span class="sxs-lookup"><span data-stu-id="63b90-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="63b90-155">特定のサイトの Lync ユーザー (つまり、サイト 1) から別のサイト (つまり、サイト 2) の Lync ユーザーに対して、提案型転送を使用して通話を転送しようとすると、PSTN の有料通話を防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="63b90-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="63b90-156">指定したサイトの Lync ユーザー (サイト 1) と、別のサイト (サイト 1) の PBX エンドポイントを使用して、別のサイト (サイト 2) との通話を提案転送によって転送しようとすると、PSTN 通話の可能性があるため、通話が許可されません。あげる.</span><span class="sxs-lookup"><span data-stu-id="63b90-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="63b90-157">場所に基づくルーティング会議アプリケーションでサポートされていない機能</span><span class="sxs-lookup"><span data-stu-id="63b90-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="63b90-158">場所に基づくルーティング会議アプリケーションでは、次の機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63b90-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="63b90-159">ダイヤルイン会議。</span><span class="sxs-lookup"><span data-stu-id="63b90-159">Dial-in conferencing.</span></span> <span data-ttu-id="63b90-160">位置情報に基づくルーティングは、ダイヤルイン会議には適用できません。</span><span class="sxs-lookup"><span data-stu-id="63b90-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="63b90-161">会議開催者が位置情報に基づくルーティングを有効にしている Lync ユーザーであっても、特定の会議へのダイヤルイン要求は、位置情報に基づくルーティングで制限されません。</span><span class="sxs-lookup"><span data-stu-id="63b90-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="63b90-162">場所に基づくルーティング制限を適用する必要がある地域では、会議アクセス番号をプロビジョニングしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63b90-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

