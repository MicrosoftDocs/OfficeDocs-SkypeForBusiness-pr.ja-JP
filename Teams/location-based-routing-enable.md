---
title: ダイレクト ルーティングの場所に基づくルーティングを有効にする
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: ダイレクトルーティングで位置情報に基づくルーティングを有効にする方法について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68b239d00e67d942f80a259facb87c80ddf2a55
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245255"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="c388d-103">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="c388d-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="c388d-104">この記事の手順を実行する前に、「位置[情報](location-based-routing-plan.md)に基づくルーティングのための[ネットワーク設定を構成](location-based-routing-configure-network-settings.md)する」の手順を参照していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c388d-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="c388d-105">この記事では、ダイレクトルーティングで位置情報に基づくルーティングを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c388d-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="c388d-106">電話システムのダイレクトルーティングを展開し、ネットワークのリージョン、サイト、サブネットをセットアップしたら、位置ベースのルーティングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c388d-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="c388d-107">この記事の手順を実行するには、PowerShell コマンドレットについて理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c388d-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="c388d-108">詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c388d-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="c388d-109">次の目的で、位置情報に基づくルーティングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c388d-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="c388d-110">ユーザー</span><span class="sxs-lookup"><span data-stu-id="c388d-110">Users</span></span>
- <span data-ttu-id="c388d-111">ネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="c388d-111">Network sites</span></span>
- <span data-ttu-id="c388d-112">ゲートウェイ構成</span><span class="sxs-lookup"><span data-stu-id="c388d-112">Gateway configurations</span></span>
- <span data-ttu-id="c388d-113">通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="c388d-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="c388d-114">ユーザーの位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="c388d-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="c388d-115">PSTN の使用状況を設定するには、 [CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c388d-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="c388d-116">複数の使用の場合は、それぞれの使用をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c388d-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="c388d-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c388d-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="c388d-118">ボイスルーティングポリシーを作成するには、 [CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ユーザーに適切な PSTN 使用法を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c388d-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="c388d-119">ボイスルーティングポリシーに PSTN 使用状況を割り当てる場合は、次のいずれかを実行してください。</span><span class="sxs-lookup"><span data-stu-id="c388d-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="c388d-120">PSTN ゲートウェイを使っているボイスルーティングに関連付けられた PSTN の使用状況をサイトに対して使用する</span><span class="sxs-lookup"><span data-stu-id="c388d-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="c388d-121">場所に基づくルーティングの制限が不要な地域内の PSTN ゲートウェイを使用するボイスルーティングに関連付けられた PSTN の使用状況を使用します。</span><span class="sxs-lookup"><span data-stu-id="c388d-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="c388d-122">この例では、2つの新しいボイスルーティングポリシーを作成し、PSTN の使用を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c388d-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="c388d-123">次の表は、この例で定義されているボイスルーティングポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="c388d-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="c388d-124">ボイスルーティングポリシー1</span><span class="sxs-lookup"><span data-stu-id="c388d-124">Voice routing policy 1</span></span>|<span data-ttu-id="c388d-125">ボイスルーティングポリシー2</span><span class="sxs-lookup"><span data-stu-id="c388d-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="c388d-126">オンラインボイスポリシー ID</span><span class="sxs-lookup"><span data-stu-id="c388d-126">Online voice policy ID</span></span>   |<span data-ttu-id="c388d-127">ニューデリーオンラインボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="c388d-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="c388d-128">Hyderabad online ボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="c388d-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="c388d-129">オンライン PSTN の使用状況</span><span class="sxs-lookup"><span data-stu-id="c388d-129">Online PSTN usages</span></span>  |<span data-ttu-id="c388d-130">長距離</span><span class="sxs-lookup"><span data-stu-id="c388d-130">Long Distance</span></span>  |<span data-ttu-id="c388d-131">長距離、ローカル、内部</span><span class="sxs-lookup"><span data-stu-id="c388d-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="c388d-132">[CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ルーティングの制限が強制されるユーザーにオンラインボイスルーティングポリシーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c388d-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="c388d-133">ネットワークサイトで位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="c388d-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="c388d-134">[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps)コマンドレットを使用して、位置情報に基づくルーティングを有効にし、ルーティングの制限を適用する必要があるネットワークサイトに音声ルーティングポリシーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c388d-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="c388d-135">この例では、ニューデリーサイトと Hyderabad サイトの位置情報に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c388d-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="c388d-136">次の表は、この例で位置情報に基づくルーティングが有効になっているサイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="c388d-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="c388d-137">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="c388d-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="c388d-138">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c388d-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="c388d-139">サイト名</span><span class="sxs-lookup"><span data-stu-id="c388d-139">Site name</span></span>    |<span data-ttu-id="c388d-140">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="c388d-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="c388d-141">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c388d-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="c388d-142">Enablelocationrouting ルーティング</span><span class="sxs-lookup"><span data-stu-id="c388d-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="c388d-143">True</span><span class="sxs-lookup"><span data-stu-id="c388d-143">True</span></span>    |<span data-ttu-id="c388d-144">True</span><span class="sxs-lookup"><span data-stu-id="c388d-144">True</span></span>    |
    |<span data-ttu-id="c388d-145">サブネット</span><span class="sxs-lookup"><span data-stu-id="c388d-145">Subnets</span></span>     |<span data-ttu-id="c388d-146">Subnet 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="c388d-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="c388d-147">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c388d-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="c388d-148">ゲートウェイで位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="c388d-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="c388d-149">[新しい-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、各ゲートウェイまたはネットワークサイトのゲートウェイ構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="c388d-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="c388d-150">複数のゲートウェイがシステム (ゲートウェイや PBX など) に関連付けられている場合は、各ゲートウェイを変更して、位置情報に基づくルーティングの制限を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c388d-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="c388d-151">この例では、ゲートウェイごとにゲートウェイ構成を1つ作成します。</span><span class="sxs-lookup"><span data-stu-id="c388d-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="c388d-152">詳細については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c388d-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="c388d-153">[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、ルーティングの制限を適用する必要があるゲートウェイの位置情報に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c388d-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="c388d-154">PSTN への通話をルーティングする PSTN ゲートウェイへの通話をルーティングするゲートウェイへの位置情報に基づくルーティングを有効にし、ゲートウェイが配置されているネットワークサイトを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c388d-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="c388d-155">この例では、ニューデリーと Hyderabad サイトの PSTN ゲートウェイに関連付けられている各ゲートウェイの位置情報に基づくルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c388d-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="c388d-156">PSTN への通話をルーティングしないゲートウェイの位置情報に基づくルーティングを有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="c388d-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="c388d-157">ただし、その場合も、システムが配置されているネットワークサイトにゲートウェイを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="c388d-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="c388d-158">これは、このゲートウェイ経由で接続されているエンドポイントに到達するために位置情報に基づくルーティング制限が適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="c388d-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="c388d-159">この例では、Hyderabad サイトの PBX システムに関連付けられている各ゲートウェイで、位置情報に基づくルーティングが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="c388d-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="c388d-160">PSTN への通話をルーティングしないシステムに接続されたエンドポイント (たとえば、PBX など) には、位置情報に基づくルーティングが有効になっている Teams ユーザーのエンドポイントと同様の制限があります。</span><span class="sxs-lookup"><span data-stu-id="c388d-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="c388d-161">つまり、これらのユーザーは、ユーザーの場所に関係なく、Teams ユーザーとの間での通話の発信と受信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c388d-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="c388d-162">また、システムが関連付けられているネットワークサイトに関係なく、PSTN ネットワーク (たとえば、別の PBX に接続されているエンドポイント) との間で通話を送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="c388d-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="c388d-163">PSTN エンドポイントを含むすべての着信通話、発信通話、通話転送、通話転送には、位置に基づくルーティング enforcements が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c388d-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="c388d-164">これらの呼び出しでは、そのシステムにローカルとして定義されている PSTN ゲートウェイのみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c388d-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="c388d-165">次の表は、2つの異なるネットワークサイトでの4ゲートウェイのゲートウェイ構成を示しています。2つは PSTN ゲートウェイに接続され、2つは PBX システムに接続されています。</span><span class="sxs-lookup"><span data-stu-id="c388d-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="c388d-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="c388d-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="c388d-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="c388d-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="c388d-168">PstnGateway: ゲートウェイ1の DEL-GW</span><span class="sxs-lookup"><span data-stu-id="c388d-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="c388d-169">True</span><span class="sxs-lookup"><span data-stu-id="c388d-169">True</span></span>     |   <span data-ttu-id="c388d-170">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="c388d-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="c388d-171">PstnGateway: ゲートウェイ 2 HYD</span><span class="sxs-lookup"><span data-stu-id="c388d-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="c388d-172">True</span><span class="sxs-lookup"><span data-stu-id="c388d-172">True</span></span>      |      <span data-ttu-id="c388d-173">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c388d-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="c388d-174">PstnGateway: ゲートウェイ 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="c388d-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="c388d-175">False</span><span class="sxs-lookup"><span data-stu-id="c388d-175">False</span></span>     |     <span data-ttu-id="c388d-176">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="c388d-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="c388d-177">PstnGateway: ゲートウェイ 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="c388d-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="c388d-178">False</span><span class="sxs-lookup"><span data-stu-id="c388d-178">False</span></span>     |    <span data-ttu-id="c388d-179">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c388d-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="c388d-180">通話ポリシーで位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="c388d-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="c388d-181">特定のユーザーに対して位置情報に基づくルーティングを適用するには、ユーザーの音声ポリシーを設定して、PTSN の有料のバイパスを防ぐようにします。</span><span class="sxs-lookup"><span data-stu-id="c388d-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="c388d-182">PSTN の有料電話のバイパスを防止することで、位置情報に基づくルーティングを有効にするには、 [Grant-Csteam/の Grant policy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c388d-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="c388d-183">この例では、PSTN の有料電話が User1 の通話ポリシーにバイパスされるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="c388d-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="c388d-184">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c388d-184">Related topics</span></span>
- [<span data-ttu-id="c388d-185">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="c388d-185">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="c388d-186">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="c388d-186">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="c388d-187">場所に基づくルーティングの用語集</span><span class="sxs-lookup"><span data-stu-id="c388d-187">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
