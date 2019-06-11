---
title: 'Lync Server 2013: 位置情報に基づくルーティングを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170ca1af77a84b655e90d5587fcd101cccf83c8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="452d8-102">Lync Server 2013 で位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="452d8-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="452d8-103">_**最終更新日:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="452d8-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="452d8-104">エンタープライズ Voip を展開し、ネットワーク領域、サイト、サブネットを定義したら、位置ベースのルーティングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="452d8-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="452d8-105">次のエンタープライズボイス要素については、位置情報に基づくルーティングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="452d8-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="452d8-106">ネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="452d8-106">Network sites</span></span>

  - <span data-ttu-id="452d8-107">トランク構成</span><span class="sxs-lookup"><span data-stu-id="452d8-107">Trunk configurations</span></span>

  - <span data-ttu-id="452d8-108">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="452d8-108">Voice policies</span></span>

  - <span data-ttu-id="452d8-109">ルーティング構成</span><span class="sxs-lookup"><span data-stu-id="452d8-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="452d8-110">ネットワークサイトへの位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="452d8-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="452d8-111">エンタープライズ Voip を展開し、ネットワークサイトを構成したら、位置ベースのルーティングを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="452d8-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="452d8-112">まず、音声ルーティングポリシーを作成して、ネットワークサイトを適切な PSTN 使用法に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="452d8-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="452d8-113">ボイスルーティングポリシーに PSTN の使用を割り当てる場合は、サイトに対するローカルの PSTN ゲートウェイを使用しているボイスルーティングに関連付けられている PSTN の使用のみを使用するようにしてください。また、位置情報に基づくルーティング制限が不要な地域にある PSTN ゲートウェイにも使用してください。Lync Server Windows PowerShell コマンド、新規-CsVoiceRoutingPolicy、または Lync Server コントロールパネルを使用して、ボイスルーティングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="452d8-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="452d8-114">詳細については、「[New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="452d8-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="452d8-115">この例では、次の表と Windows PowerShell コマンドは、このシナリオで定義された2つのボイスルーティングポリシーと関連する PSTN 使用法を示しています。</span><span class="sxs-lookup"><span data-stu-id="452d8-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="452d8-116">この表には、場所に基づくルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="452d8-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="452d8-117">ボイスルーティングポリシー1</span><span class="sxs-lookup"><span data-stu-id="452d8-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="452d8-118">ボイスルーティングポリシー2</span><span class="sxs-lookup"><span data-stu-id="452d8-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="452d8-119">ボイスポリシー ID</span><span class="sxs-lookup"><span data-stu-id="452d8-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="452d8-120">ニューデリーボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="452d8-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="452d8-121">Hyderabad ボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="452d8-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="452d8-122">PSTN の使用状況</span><span class="sxs-lookup"><span data-stu-id="452d8-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="452d8-123">ニューデリー使用量, PBX Del usage, PBX Hyd usage</span><span class="sxs-lookup"><span data-stu-id="452d8-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="452d8-124">Hyderabad usage、PBX Hyd usage、PBX Del usage</span><span class="sxs-lookup"><span data-stu-id="452d8-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="452d8-125">次に、該当するネットワークサイトの位置情報に基づくルーティングを構成し、ボイスルーティングポリシーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="452d8-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="452d8-126">Lync Server Windows PowerShell コマンドの新しい CsNetworkSite を使って、位置情報に基づくルーティングを有効にし、ルーティングの制限を適用する必要があるネットワークサイトにボイスルーティングポリシーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="452d8-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="452d8-127">この例では、次の表は、Lync Server Windows PowerShell を使用して、このシナリオで定義される2つの異なるネットワークサイト、ニューデリー、Hyderabad の位置に基づくルーティングを示しています。</span><span class="sxs-lookup"><span data-stu-id="452d8-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="452d8-128">この表には、場所に基づくルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="452d8-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="452d8-129">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="452d8-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="452d8-130">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="452d8-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="452d8-131">サイト名</span><span class="sxs-lookup"><span data-stu-id="452d8-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="452d8-132">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="452d8-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="452d8-133">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="452d8-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="452d8-134">Enablelocationrouting ルーティング</span><span class="sxs-lookup"><span data-stu-id="452d8-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="452d8-135">True</span><span class="sxs-lookup"><span data-stu-id="452d8-135">True</span></span></p></td>
<td><p><span data-ttu-id="452d8-136">True</span><span class="sxs-lookup"><span data-stu-id="452d8-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="452d8-137">ボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="452d8-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="452d8-138">ニューデリーボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="452d8-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="452d8-139">Hyderabad ボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="452d8-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="452d8-140">サブネット</span><span class="sxs-lookup"><span data-stu-id="452d8-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="452d8-141">Subnet 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="452d8-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="452d8-142">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="452d8-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="452d8-143">Trunks への位置に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="452d8-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="452d8-144">位置情報に基づくルーティングでトランク構成を有効にするには、各トランクまたは各ネットワークサイトのトランク構成を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="452d8-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="452d8-145">Lync Server Windows PowerShell コマンドの New-Set-cstrunkconfiguration を使用して、トランク構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="452d8-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="452d8-146">特定のシステム (ゲートウェイまたは PBX など) に複数の trunks が関連付けられている場合は、各トランク構成を変更して、位置ベースのルーティング制限を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="452d8-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="452d8-147">詳細については、「 [New-set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="452d8-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="452d8-148">この例では、次の Windows PowerShell コマンドを使用して、このシナリオで定義されている展開の各トランクに対してトランク構成を1つ作成しています。</span><span class="sxs-lookup"><span data-stu-id="452d8-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="452d8-149">トランク構成がトランクごとに構成されると、Lync Server Windows PowerShell コマンドである Set-cstrunkconfiguration を使用して、ルーティングの制限を適用する必要がある trunks への位置情報に基づくルーティングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="452d8-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="452d8-150">PSTN への通話をルーティングする PSTN ゲートウェイへの通話をルーティングし、ゲートウェイが配置されているネットワークサイトを関連付ける trunks に、位置情報に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="452d8-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="452d8-151">詳細については、「 [New-set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="452d8-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="452d8-152">この例では、ニューデリーと Hyderabad の PSTN ゲートウェイに関連付けられている各トランクで位置情報に基づくルーティングが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="452d8-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="452d8-153">PSTN への通話をルーティングしない trunks の位置情報に基づくルーティングを有効にしないでください。ただし、このトランク経由で接続されているエンドポイントに対応する PSTN 通話には、場所に基づくルーティング制限が適用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="452d8-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="452d8-154">この例では、ニューデリーと Hyderabad の PBX システムに関連付けられている各トランクの位置情報に基づくルーティングが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="452d8-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="452d8-155">PSTN (つまり PBX) への通話をルーティングしないシステムに接続されているエンドポイントは、場所に基づくルーティングが有効になっているユーザーの Lync エンドポイントと同様の制限があります。</span><span class="sxs-lookup"><span data-stu-id="452d8-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="452d8-156">これは、ユーザーの場所に関係なく、ユーザーが Lync ユーザーとの間で通話を発信および受信できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="452d8-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="452d8-157">また、システムが関連付けられているネットワークサイトに関係なく、PSTN ネットワーク (つまり、別の PBX に接続されているエンドポイント) との間で着信を転送することができます。</span><span class="sxs-lookup"><span data-stu-id="452d8-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="452d8-158">PSTN エンドポイントを含むすべての着信通話、発信通話、通話転送、通話転送には、位置ベースのルーティング enforcements が適用されます。</span><span class="sxs-lookup"><span data-stu-id="452d8-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="452d8-159">このような呼び出しでは、そのようなシステムのローカルとして定義されている PSTN ゲートウェイのみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="452d8-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="452d8-160">次の表は、2つの異なるネットワークサイトでの4つの trunks のトランク構成を示しています。2つは PSTN ゲートウェイに接続され、2つは PBX システムに接続されています。</span><span class="sxs-lookup"><span data-stu-id="452d8-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="452d8-161">名前</span><span class="sxs-lookup"><span data-stu-id="452d8-161">Name</span></span></th>
<th><span data-ttu-id="452d8-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="452d8-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="452d8-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="452d8-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="452d8-164">PstnGateway: トランク1の DEL-GW</span><span class="sxs-lookup"><span data-stu-id="452d8-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="452d8-165">True</span><span class="sxs-lookup"><span data-stu-id="452d8-165">True</span></span></p></td>
<td><p><span data-ttu-id="452d8-166">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="452d8-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="452d8-167">PstnGateway: トランク 2 HYD</span><span class="sxs-lookup"><span data-stu-id="452d8-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="452d8-168">True</span><span class="sxs-lookup"><span data-stu-id="452d8-168">True</span></span></p></td>
<td><p><span data-ttu-id="452d8-169">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="452d8-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="452d8-170">PstnGateway: トランク 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="452d8-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="452d8-171">False</span><span class="sxs-lookup"><span data-stu-id="452d8-171">False</span></span></p></td>
<td><p><span data-ttu-id="452d8-172">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="452d8-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="452d8-173">PstnGateway: トランク 4 HYD</span><span class="sxs-lookup"><span data-stu-id="452d8-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="452d8-174">False</span><span class="sxs-lookup"><span data-stu-id="452d8-174">False</span></span></p></td>
<td><p><span data-ttu-id="452d8-175">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="452d8-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="452d8-176">ボイスポリシーへの位置に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="452d8-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="452d8-177">特定のユーザーに対して位置情報に基づくルーティングを適用するには、これらのユーザーの音声ポリシーを構成して、PSTN の有料通話を回避します。</span><span class="sxs-lookup"><span data-stu-id="452d8-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="452d8-178">Lync Server Windows PowerShell コマンドの CsVoicePolicy を使用して、新しい音声ポリシーを作成するか、既存のポリシーを使用する場合は CsVoicePolicy を使って、PSTN の有料電話のバイパスを防ぐことで位置情報に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="452d8-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="452d8-179">詳細については、「 [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="452d8-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="452d8-180">この例では、次の表と Windows PowerShell コマンドを使用して、このシナリオで定義された、ニューデリーと Hyderabad のボイスポリシーに PSTN 有料電話のバイパスを防ぐことを示します。</span><span class="sxs-lookup"><span data-stu-id="452d8-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="452d8-181">この表には、場所に基づくルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="452d8-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="452d8-182">ボイスポリシー1</span><span class="sxs-lookup"><span data-stu-id="452d8-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="452d8-183">ボイスポリシー2</span><span class="sxs-lookup"><span data-stu-id="452d8-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="452d8-184">ボイスポリシー ID</span><span class="sxs-lookup"><span data-stu-id="452d8-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="452d8-185">ニューデリーのボイスポリシー</span><span class="sxs-lookup"><span data-stu-id="452d8-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="452d8-186">Hyderabad ボイスポリシー</span><span class="sxs-lookup"><span data-stu-id="452d8-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="452d8-187">PSTN の使用状況</span><span class="sxs-lookup"><span data-stu-id="452d8-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="452d8-188">ニューデリー使用量, PBX Del usage, PBX Hyd usage</span><span class="sxs-lookup"><span data-stu-id="452d8-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="452d8-189">Hyderabad usage、PBX Hyd usage、PBX Del usage</span><span class="sxs-lookup"><span data-stu-id="452d8-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="452d8-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="452d8-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="452d8-191">True</span><span class="sxs-lookup"><span data-stu-id="452d8-191">True</span></span></p></td>
<td><p><span data-ttu-id="452d8-192">True</span><span class="sxs-lookup"><span data-stu-id="452d8-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="452d8-193">ルーティング構成で位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="452d8-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="452d8-194">最後に、ルーティング構成への位置に基づくルーティングをグローバルに有効にします。</span><span class="sxs-lookup"><span data-stu-id="452d8-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="452d8-195">Lync Server Windows PowerShell コマンドである [新しい-CsRoutingConfiguration] を使って、位置情報に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="452d8-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="452d8-196">詳細については、「 [CsRoutingConfiguration を設定](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="452d8-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="452d8-197">位置情報に基づくルーティングはグローバル構成を使用して有効にする必要がありますが、適用されるルールのセットは、このドキュメントで指定されているように構成されているサイト、ユーザー、および trunks に対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="452d8-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="452d8-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="452d8-198">See Also</span></span>


[<span data-ttu-id="452d8-199">Lync Server 2013 の場所に基づくルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="452d8-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

