---
title: ダイレクト ルーティングの場所に基づくルーティングを有効にする
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: ダイレクトルーティングで位置情報に基づくルーティングを有効にする方法について説明します。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 48fbd1477194b7523b65ec527686b7304f0c37b2
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992022"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="5786b-103">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="5786b-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="5786b-104">この記事の手順を実行する前に、「位置[情報](location-based-routing-plan.md)に基づくルーティングのための[ネットワーク設定を構成](location-based-routing-configure-network-settings.md)する」の手順を参照していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5786b-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="5786b-105">この記事では、ダイレクトルーティングで位置情報に基づくルーティングを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5786b-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="5786b-106">電話システムのダイレクトルーティングを展開し、ネットワークのリージョン、サイト、サブネットをセットアップしたら、位置ベースのルーティングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5786b-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="5786b-107">この記事の手順を実行するには、PowerShell コマンドレットについて理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5786b-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="5786b-108">詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5786b-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="5786b-109">次の目的で、位置情報に基づくルーティングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5786b-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="5786b-110">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5786b-110">Users</span></span>
- <span data-ttu-id="5786b-111">ネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="5786b-111">Network sites</span></span>
- <span data-ttu-id="5786b-112">ゲートウェイ構成</span><span class="sxs-lookup"><span data-stu-id="5786b-112">Gateway configurations</span></span>
- <span data-ttu-id="5786b-113">通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="5786b-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="5786b-114">ユーザーの位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="5786b-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="5786b-115">PSTN の使用状況を設定するには、 [CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5786b-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="5786b-116">複数の使用の場合は、それぞれの使用をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="5786b-116">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="5786b-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5786b-117">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="5786b-118">ボイスルーティングポリシーを作成するには、 [CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ユーザーに適切な PSTN 使用法を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5786b-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="5786b-119">ボイスルーティングポリシーに PSTN 使用状況を割り当てる場合は、次のいずれかを実行してください。</span><span class="sxs-lookup"><span data-stu-id="5786b-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="5786b-120">PSTN ゲートウェイを使っているボイスルーティングに関連付けられた PSTN の使用状況をサイトに対して使用する</span><span class="sxs-lookup"><span data-stu-id="5786b-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="5786b-121">場所に基づくルーティングの制限が不要な地域内の PSTN ゲートウェイを使用するボイスルーティングに関連付けられた PSTN の使用状況を使用します。</span><span class="sxs-lookup"><span data-stu-id="5786b-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="5786b-122">この例では、2つの新しいボイスルーティングポリシーを作成し、PSTN の使用を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5786b-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="5786b-123">次の表は、この例で定義されているボイスルーティングポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="5786b-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="5786b-124">ボイスルーティングポリシー1</span><span class="sxs-lookup"><span data-stu-id="5786b-124">Voice routing policy 1</span></span>|<span data-ttu-id="5786b-125">ボイスルーティングポリシー2</span><span class="sxs-lookup"><span data-stu-id="5786b-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="5786b-126">オンラインボイスポリシー ID</span><span class="sxs-lookup"><span data-stu-id="5786b-126">Online voice policy ID</span></span>   |<span data-ttu-id="5786b-127">ニューデリーオンラインボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="5786b-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="5786b-128">Hyderabad online ボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="5786b-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="5786b-129">オンライン PSTN の使用状況</span><span class="sxs-lookup"><span data-stu-id="5786b-129">Online PSTN usages</span></span>  |<span data-ttu-id="5786b-130">長距離</span><span class="sxs-lookup"><span data-stu-id="5786b-130">Long Distance</span></span>  |<span data-ttu-id="5786b-131">長距離、ローカル、内部</span><span class="sxs-lookup"><span data-stu-id="5786b-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="5786b-132">[CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ルーティングの制限が強制されるユーザーにオンラインボイスルーティングポリシーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5786b-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="5786b-133">ネットワークサイトで位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="5786b-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="5786b-134">[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps)コマンドレットを使用して、位置情報に基づくルーティングを有効にし、ルーティングの制限を適用する必要があるネットワークサイトに音声ルーティングポリシーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5786b-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="5786b-135">この例では、ニューデリーサイトと Hyderabad サイトの位置情報に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5786b-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="5786b-136">次の表は、この例で位置情報に基づくルーティングが有効になっているサイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="5786b-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="5786b-137">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="5786b-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="5786b-138">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5786b-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="5786b-139">サイト名</span><span class="sxs-lookup"><span data-stu-id="5786b-139">Site name</span></span>    |<span data-ttu-id="5786b-140">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="5786b-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="5786b-141">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5786b-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="5786b-142">Enablelocationrouting ルーティング</span><span class="sxs-lookup"><span data-stu-id="5786b-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="5786b-143">True</span><span class="sxs-lookup"><span data-stu-id="5786b-143">True</span></span>    |<span data-ttu-id="5786b-144">True</span><span class="sxs-lookup"><span data-stu-id="5786b-144">True</span></span>    |
    |<span data-ttu-id="5786b-145">サブネット</span><span class="sxs-lookup"><span data-stu-id="5786b-145">Subnets</span></span>     |<span data-ttu-id="5786b-146">Subnet 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="5786b-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="5786b-147">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5786b-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="5786b-148">ゲートウェイで位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="5786b-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="5786b-149">[新しい-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、各ゲートウェイまたはネットワークサイトのゲートウェイ構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="5786b-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="5786b-150">複数のゲートウェイがシステム (ゲートウェイや PBX など) に関連付けられている場合は、各ゲートウェイを変更して、位置情報に基づくルーティングの制限を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5786b-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="5786b-151">この例では、ゲートウェイごとにゲートウェイ構成を1つ作成します。</span><span class="sxs-lookup"><span data-stu-id="5786b-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="5786b-152">詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5786b-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="5786b-153">[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、ルーティングの制限を適用する必要があるゲートウェイの位置情報に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5786b-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="5786b-154">PSTN への通話をルーティングする PSTN ゲートウェイへの通話をルーティングするゲートウェイへの位置情報に基づくルーティングを有効にし、ゲートウェイが配置されているネットワークサイトを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5786b-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="5786b-155">この例では、ニューデリーと Hyderabad サイトの PSTN ゲートウェイに関連付けられている各ゲートウェイの位置情報に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5786b-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="5786b-156">PSTN への通話をルーティングしないゲートウェイの位置情報に基づくルーティングを有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="5786b-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="5786b-157">ただし、その場合も、システムが配置されているネットワークサイトにゲートウェイを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="5786b-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="5786b-158">これは、このゲートウェイ経由で接続されているエンドポイントに到達するために位置情報に基づくルーティング制限が適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="5786b-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="5786b-159">この例では、Hyderabad サイトの PBX システムに関連付けられている各ゲートウェイで、位置情報に基づくルーティングが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="5786b-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="5786b-160">PSTN への通話をルーティングしないシステムに接続されたエンドポイント (たとえば、PBX など) には、位置情報に基づくルーティングが有効になっている Teams ユーザーのエンドポイントと同様の制限があります。</span><span class="sxs-lookup"><span data-stu-id="5786b-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="5786b-161">つまり、これらのユーザーは、ユーザーの場所に関係なく、Teams ユーザーとの間での通話の発信と受信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5786b-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="5786b-162">また、システムが関連付けられているネットワークサイトに関係なく、PSTN ネットワーク (たとえば、別の PBX に接続されているエンドポイント) との間で通話を送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="5786b-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="5786b-163">PSTN エンドポイントを含むすべての着信通話、発信通話、通話転送、通話転送には、位置に基づくルーティング enforcements が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5786b-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="5786b-164">これらの呼び出しでは、そのシステムにローカルとして定義されている PSTN ゲートウェイのみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5786b-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="5786b-165">次の表は、2つの異なるネットワークサイトでの4ゲートウェイのゲートウェイ構成を示しています。2つは PSTN ゲートウェイに接続され、2つは PBX システムに接続されています。</span><span class="sxs-lookup"><span data-stu-id="5786b-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="5786b-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="5786b-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="5786b-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="5786b-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="5786b-168">PstnGateway: ゲートウェイ1の DEL-GW</span><span class="sxs-lookup"><span data-stu-id="5786b-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="5786b-169">True</span><span class="sxs-lookup"><span data-stu-id="5786b-169">True</span></span>     |   <span data-ttu-id="5786b-170">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="5786b-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="5786b-171">PstnGateway: ゲートウェイ 2 HYD</span><span class="sxs-lookup"><span data-stu-id="5786b-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="5786b-172">True</span><span class="sxs-lookup"><span data-stu-id="5786b-172">True</span></span>      |      <span data-ttu-id="5786b-173">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5786b-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="5786b-174">PstnGateway: ゲートウェイ 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="5786b-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="5786b-175">False</span><span class="sxs-lookup"><span data-stu-id="5786b-175">False</span></span>     |     <span data-ttu-id="5786b-176">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="5786b-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="5786b-177">PstnGateway: ゲートウェイ 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="5786b-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="5786b-178">False</span><span class="sxs-lookup"><span data-stu-id="5786b-178">False</span></span>     |    <span data-ttu-id="5786b-179">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5786b-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="5786b-180">通話ポリシーで位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="5786b-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="5786b-181">特定のユーザーに対して位置情報に基づくルーティングを適用するには、ユーザーの音声ポリシーを設定して、PTSN の有料のバイパスを防ぐようにします。</span><span class="sxs-lookup"><span data-stu-id="5786b-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="5786b-182">PSTN の有料電話のバイパスを防止することで、位置情報に基づくルーティングを有効にするには、 [Grant-Csteam/の Grant policy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5786b-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="5786b-183">この例では、PSTN の有料電話が User1 の通話ポリシーにバイパスされるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="5786b-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

## <a name="related-topics"></a><span data-ttu-id="5786b-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="5786b-184">Related topics</span></span>

- [<span data-ttu-id="5786b-185">Teams でのクラウド音声機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="5786b-185">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
