---
title: 'Lync Server 2013: 場所に基づくルーティングを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f36d28ca41bb12aa98bab5add471e102ed282b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="3ddb4-102">Lync Server 2013 での場所に基づくルーティングの有効化</span><span class="sxs-lookup"><span data-stu-id="3ddb4-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ddb4-103">_**トピックの最終更新日:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="3ddb4-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="3ddb4-104">エンタープライズ Voip を展開し、ネットワーク地域、サイト、およびサブネットを定義すると、場所に基づくルーティングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="3ddb4-105">次のエンタープライズ Voip 要素に対して、場所に基づくルーティングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="3ddb4-106">ネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="3ddb4-106">Network sites</span></span>

  - <span data-ttu-id="3ddb4-107">トランク構成</span><span class="sxs-lookup"><span data-stu-id="3ddb4-107">Trunk configurations</span></span>

  - <span data-ttu-id="3ddb4-108">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ddb4-108">Voice policies</span></span>

  - <span data-ttu-id="3ddb4-109">ルーティング構成</span><span class="sxs-lookup"><span data-stu-id="3ddb4-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="3ddb4-110">ネットワークサイトへの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="3ddb4-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="3ddb4-111">エンタープライズ Voip を展開し、ネットワークサイトを構成したら、場所に基づくルーティングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="3ddb4-112">最初に、音声ルーティングポリシーを作成して、ネットワークサイトを適切な PSTN 使用法に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="3ddb4-113">音声ルーティングポリシーに PSTN 使用法を割り当てる場合は、サイトのローカルにある PSTN ゲートウェイ、または場所に基づくルーティング制限が不要な地域内の PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用法のみを使用してください。音声ルーティングポリシーを作成するには、Lync Server の Windows PowerShell コマンド、Grant-csvoiceroutingpolicy、または Lync Server コントロールパネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="3ddb4-114">詳細については、「 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="3ddb4-115">この例では、次の表および Windows PowerShell コマンドは、このシナリオで定義されている2つの音声ルーティングポリシーと、それらに関連付けられた PSTN 使用法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="3ddb4-116">説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="3ddb4-117">音声ルーティングポリシー1</span><span class="sxs-lookup"><span data-stu-id="3ddb4-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="3ddb4-118">音声ルーティングポリシー2</span><span class="sxs-lookup"><span data-stu-id="3ddb4-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ddb4-119">音声ポリシー ID</span><span class="sxs-lookup"><span data-stu-id="3ddb4-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-120">ニューデリー音声ルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="3ddb4-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-121">Hyderabad 音声ルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="3ddb4-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ddb4-122">PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="3ddb4-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-123">ニューデリー使用法、PBX Del usage、PBX Hyd usage</span><span class="sxs-lookup"><span data-stu-id="3ddb4-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-124">Hyderabad usage、PBX Hyd usage、PBX Del usage</span><span class="sxs-lookup"><span data-stu-id="3ddb4-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="3ddb4-125">次に、該当するネットワークサイトの場所に基づくルーティングを構成し、音声ルーティングポリシーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="3ddb4-126">Lync Server Windows PowerShell コマンドの New-CsNetworkSite を使用して、場所に基づくルーティングを有効にし、ルーティングの制限を適用する必要があるネットワークサイトに音声ルーティングポリシーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="3ddb4-127">この例では、次の表に、Lync Server Windows PowerShell を使用して、このシナリオで定義されている2つの異なるネットワークサイト、ニューデリー、Hyderabad の場所に基づくルーティングを示します。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="3ddb4-128">説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="3ddb4-129">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="3ddb4-130">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ddb4-131">Site Name</span><span class="sxs-lookup"><span data-stu-id="3ddb4-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-132">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-133">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ddb4-134">Enablelocationのルーティング</span><span class="sxs-lookup"><span data-stu-id="3ddb4-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-135">True</span><span class="sxs-lookup"><span data-stu-id="3ddb4-135">True</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-136">True</span><span class="sxs-lookup"><span data-stu-id="3ddb4-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ddb4-137">音声ルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="3ddb4-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-138">ニューデリー音声ルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="3ddb4-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-139">Hyderabad 音声ルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="3ddb4-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ddb4-140">サブネット</span><span class="sxs-lookup"><span data-stu-id="3ddb4-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-141">サブネット 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-142">サブネット 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="3ddb4-143">トランクへの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="3ddb4-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="3ddb4-144">場所に基づくルーティングに対してトランク構成を有効にするには、トランクまたはネットワークサイトごとにトランク構成を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="3ddb4-145">Lync Server Windows PowerShell コマンド Get-cstrunkconfiguration を使用して、トランク構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="3ddb4-146">特定のシステム (ゲートウェイまたは PBX) に複数のトランクが関連付けられている場合は、場所に基づいたルーティング制限を有効にするために、各トランク構成を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="3ddb4-147">詳細については、「 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="3ddb4-148">この例では、次の Windows PowerShell コマンドは、このシナリオで定義された展開内の各トランクに対して1つのトランク構成を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="3ddb4-149">トランクごとにトランク構成を構成したら、Lync Server Windows PowerShell コマンド Get-cstrunkconfiguration を使用して、ルーティング制限を強制する必要があるトランクへの場所ベースのルーティングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="3ddb4-150">PSTN への通話をルーティングする PSTN ゲートウェイへの通話をルーティングするトランクへの場所ベースのルーティングを有効にし、ゲートウェイが配置されているネットワークサイトを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="3ddb4-151">詳細については、「 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="3ddb4-152">この例では、Hyderabad の PSTN ゲートウェイに関連付けられている各トランクに対して、場所に基づくルーティングが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="3ddb4-153">PSTN に通話をルーティングしないトランクの場所に基づくルーティングを有効にしないでください。ただし、このトランクを介して接続されたエンドポイントに到着する PSTN 通話には、場所に基づいたルーティング制限として、システムが配置されているネットワークサイトにトランクを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="3ddb4-154">この例では、Hyderabad の PBX システムに関連付けられている各トランクに対して、場所に基づくルーティングが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="3ddb4-155">PSTN (つまり PBX) への通話をルーティングしないシステムに接続されているエンドポイントは、場所に基づくルーティングが有効になっているユーザーの Lync エンドポイントと同様の制限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="3ddb4-156">これは、ユーザーの場所に関係なく、Lync ユーザーとの間で通話を発信および受信できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="3ddb4-157">また、システムが関連付けられているネットワークサイトに関係なく、PSTN ネットワークへの通話のルーティングを行わない他のシステム (つまり、別の PBX に接続されているエンドポイント) との間で受信通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="3ddb4-158">PSTN エンドポイントを使用した着信呼び出し、発信通話、着信転送、および通話転送は、場所に基づいたルーティング強制の対象となります。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="3ddb4-159">このような呼び出しでは、そのようなシステムのローカルとして定義されている PSTN ゲートウェイのみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="3ddb4-160">次の表は、2つの異なるネットワークサイトにある4つのトランクのトランク構成を示しています。2つは PSTN ゲートウェイに接続され、2台は PBX システムに接続されています。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ddb4-161">名前</span><span class="sxs-lookup"><span data-stu-id="3ddb4-161">Name</span></span></th>
<th><span data-ttu-id="3ddb4-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="3ddb4-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="3ddb4-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="3ddb4-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ddb4-164">PstnGateway: トランク 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="3ddb4-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-165">はい</span><span class="sxs-lookup"><span data-stu-id="3ddb4-165">True</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-166">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ddb4-167">PstnGateway: トランク 2 HYD</span><span class="sxs-lookup"><span data-stu-id="3ddb4-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-168">はい</span><span class="sxs-lookup"><span data-stu-id="3ddb4-168">True</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-169">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ddb4-170">PstnGateway: トランク 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="3ddb4-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-171">False</span><span class="sxs-lookup"><span data-stu-id="3ddb4-171">False</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-172">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ddb4-173">PstnGateway: トランク 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="3ddb4-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-174">False</span><span class="sxs-lookup"><span data-stu-id="3ddb4-174">False</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-175">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3ddb4-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="3ddb4-176">音声ポリシーへの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="3ddb4-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="3ddb4-177">特定のユーザーに対する場所ベースのルーティングを強制するには、そのユーザーの音声ポリシーを構成して PSTN の有料電話をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="3ddb4-178">Lync Server Windows PowerShell コマンド Set-csvoicepolicy を使用して、新しい音声ポリシーを作成するか、既存のポリシーを使用している場合は Set-csvoicepolicy を使用して、PSTN の有料電話のバイパスを防ぐことで、場所に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="3ddb4-179">詳細については、「 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="3ddb4-180">この例では、次の表および Windows PowerShell コマンドを使用して、このシナリオで定義されている、ニューデリーおよび Hyderabad の音声ポリシーに対する PSTN 通話のバイパスの防止を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="3ddb4-181">説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="3ddb4-182">音声ポリシー1</span><span class="sxs-lookup"><span data-stu-id="3ddb4-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="3ddb4-183">音声ポリシー2</span><span class="sxs-lookup"><span data-stu-id="3ddb4-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ddb4-184">音声ポリシー ID</span><span class="sxs-lookup"><span data-stu-id="3ddb4-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-185">ニューデリー音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ddb4-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-186">Hyderabad 音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ddb4-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ddb4-187">PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="3ddb4-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-188">ニューデリー使用法、PBX Del usage、PBX Hyd usage</span><span class="sxs-lookup"><span data-stu-id="3ddb4-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-189">Hyderabad usage、PBX Hyd usage、PBX Del usage</span><span class="sxs-lookup"><span data-stu-id="3ddb4-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ddb4-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="3ddb4-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-191">True</span><span class="sxs-lookup"><span data-stu-id="3ddb4-191">True</span></span></p></td>
<td><p><span data-ttu-id="3ddb4-192">True</span><span class="sxs-lookup"><span data-stu-id="3ddb4-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="3ddb4-193">ルーティング構成での場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="3ddb4-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="3ddb4-194">最後に、ルーティング構成への場所ベースのルーティングをグローバルに有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="3ddb4-195">Lync Server Windows PowerShell コマンドの [新規-CsRoutingConfiguration] を使用して、場所に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="3ddb4-196">詳細については、「 [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3ddb4-197">場所に基づくルーティングはグローバル構成を使用して有効にする必要がありますが、適用されるルールのセットは、このドキュメントで指定されたとおりに構成されているサイト、ユーザー、およびトランクに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ddb4-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ddb4-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ddb4-198">See Also</span></span>


[<span data-ttu-id="3ddb4-199">Lync Server 2013 での場所に基づくルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="3ddb4-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

