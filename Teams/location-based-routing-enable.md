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
description: 直接ルーティングのための場所ベースのルーティングを有効にする方法を説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68b239d00e67d942f80a259facb87c80ddf2a55
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886033"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="65fa1-103">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="65fa1-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="65fa1-104">この資料の手順を実行する前に、 [Plan Location-Based を直接ルーティングのルーティング](location-based-routing-plan.md)を参照し、[場所ベースのルーティング用のネットワーク設定の構成](location-based-routing-configure-network-settings.md)手順を完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65fa1-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="65fa1-105">この資料では、直接ルーティングするための場所ベースのルーティングを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="65fa1-106">電話システムの直接のルーティングを展開し、ネットワーク領域、サイト、およびサブネットを設定すると、場所ベースのルーティングを有効にする準備ができています。</span><span class="sxs-lookup"><span data-stu-id="65fa1-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="65fa1-107">この資料の手順を完了するには、PowerShell コマンドレットをある程度必要があります。</span><span class="sxs-lookup"><span data-stu-id="65fa1-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="65fa1-108">詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65fa1-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="65fa1-109">次の場所ベースのルーティングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65fa1-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="65fa1-110">ユーザー</span><span class="sxs-lookup"><span data-stu-id="65fa1-110">Users</span></span>
- <span data-ttu-id="65fa1-111">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="65fa1-111">Network sites</span></span>
- <span data-ttu-id="65fa1-112">ゲートウェイの構成</span><span class="sxs-lookup"><span data-stu-id="65fa1-112">Gateway configurations</span></span>
- <span data-ttu-id="65fa1-113">ポリシーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="65fa1-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="65fa1-114">ユーザーの場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65fa1-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="65fa1-115">[セット CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)コマンドレットを使用すると、PSTN の使用法を設定できます。</span><span class="sxs-lookup"><span data-stu-id="65fa1-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="65fa1-116">複数の使用状況を毎回使用をカンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="65fa1-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="65fa1-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="65fa1-118">ユーザーを関連付ける適切な PSTN 使用法の音声ルーティング ポリシーを作成するのにには、[新規 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="65fa1-119">音声ルーティング ポリシーに PSTN 使用法を割り当てると、次のいずれかの操作を行うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="65fa1-120">サイトをローカルの PSTN ゲートウェイを使用してボイス ルートに関連付けられている PSTN 使用法を使用します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="65fa1-121">場所ベースのルーティングの制限が不要の領域内にある PSTN ゲートウェイを使用してボイス ルートに関連付けられている PSTN 使用法を使用します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="65fa1-122">この例は、2 つの新しい音声ルーティング ポリシーを作成し、PSTN の使用法に割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="65fa1-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="65fa1-123">次の表は、次の使用例で定義されている音声ルーティング ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="65fa1-124">音声ルーティング ポリシー 1</span><span class="sxs-lookup"><span data-stu-id="65fa1-124">Voice routing policy 1</span></span>|<span data-ttu-id="65fa1-125">音声ルーティング ポリシー 2</span><span class="sxs-lookup"><span data-stu-id="65fa1-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="65fa1-126">オンラインでのボイス ポリシー ID</span><span class="sxs-lookup"><span data-stu-id="65fa1-126">Online voice policy ID</span></span>   |<span data-ttu-id="65fa1-127">デリー オンライン音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="65fa1-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="65fa1-128">Hyderabad のオンラインの音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="65fa1-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="65fa1-129">オンラインの PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="65fa1-129">Online PSTN usages</span></span>  |<span data-ttu-id="65fa1-130">市外通話</span><span class="sxs-lookup"><span data-stu-id="65fa1-130">Long Distance</span></span>  |<span data-ttu-id="65fa1-131">長い距離、ローカルな内部</span><span class="sxs-lookup"><span data-stu-id="65fa1-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="65fa1-132">[許可 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、オンライン音声ルーティング ポリシーの適用するルーティングの制限を必要とするユーザーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="65fa1-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="65fa1-133">ネットワークのサイトの場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65fa1-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="65fa1-134">場所ベースのルーティングを有効にして、ルーティングの制限を適用する必要があるネットワーク サイトの音声ルーティング ポリシーを関連付けるには、[セット CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="65fa1-135">この例では、Delhi サイトおよび Hyderabad のサイトの場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65fa1-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="65fa1-136">次の表は、この例では、場所ベースのルーティングを有効になっているサイトを示します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="65fa1-137">サイト 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="65fa1-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="65fa1-138">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="65fa1-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="65fa1-139">サイト名</span><span class="sxs-lookup"><span data-stu-id="65fa1-139">Site name</span></span>    |<span data-ttu-id="65fa1-140">サイト 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="65fa1-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="65fa1-141">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="65fa1-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="65fa1-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="65fa1-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="65fa1-143">True</span><span class="sxs-lookup"><span data-stu-id="65fa1-143">True</span></span>    |<span data-ttu-id="65fa1-144">True</span><span class="sxs-lookup"><span data-stu-id="65fa1-144">True</span></span>    |
    |<span data-ttu-id="65fa1-145">サブネット</span><span class="sxs-lookup"><span data-stu-id="65fa1-145">Subnets</span></span>     |<span data-ttu-id="65fa1-146">サブネット 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="65fa1-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="65fa1-147">サブネット 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="65fa1-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="65fa1-148">ゲートウェイの場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65fa1-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="65fa1-149">[新規 CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps)コマンドレットを使用すると、ゲートウェイ、またはネットワークの各サイトのゲートウェイの構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="65fa1-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="65fa1-150">複数のゲートウェイ (たとえば、ゲートウェイまたは PBX) システムに関連付けられている場合は、場所ベースのルーティングの制限を有効にするには、各ゲートウェイを変更します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="65fa1-151">この例では、各ゲートウェイの 1 つのゲートウェイの構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="65fa1-152">詳細については、[直接ルーティングの構成](direct-routing-configure.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65fa1-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="65fa1-153">[セット CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、ルーティングの制限を適用する必要がある、ゲートウェイの場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65fa1-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="65fa1-154">呼び出しをルーティングするゲートウェイに場所ベースのルーティングを有効にする PSTN ゲートウェイが PSTN への呼び出しをルーティングし、ゲートウェイが配置されているネットワーク サイトに関連付けることにします。</span><span class="sxs-lookup"><span data-stu-id="65fa1-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="65fa1-155">この例では、デリーおよび Hyderabad のサイトでの PSTN ゲートウェイに関連付けられているゲートウェイごとに場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65fa1-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="65fa1-156">PSTN への呼び出しをルーティングしないゲートウェイの場所ベースのルーティングを有効にしません。</span><span class="sxs-lookup"><span data-stu-id="65fa1-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="65fa1-157">ただし、まだ、システムが配置されているネットワーク サイトへのゲートウェイを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="65fa1-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="65fa1-158">これは、場所ベースのルーティングの制限は、このゲートウェイ経由で接続されているエンドポイントに到達する PSTN の呼び出しに適用する必要があるためにです。</span><span class="sxs-lookup"><span data-stu-id="65fa1-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="65fa1-159">この例では、場所ベースのルーティングは、デリーおよび Hyderabad のサイト内の PBX システムに関連付けられている各ゲートウェイを有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="65fa1-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="65fa1-160">(PBX など) の PSTN への呼び出しをルーティングしないシステムに接続されているエンドポイントでは、場所ベースのルーティングが有効なチームのユーザーのエンドポイントとして、同様の制限があります。</span><span class="sxs-lookup"><span data-stu-id="65fa1-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="65fa1-161">これは、これらのユーザーが配置し、ユーザーの場所に関係なくチームのユーザーとの間の呼び出しを受信することを意味します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="65fa1-162">したりすることがどのシステムと関連付けられているネットワーク サイト (たとえば、別の PBX に接続されているエンドポイント) PSTN ネットワークへの呼び出しをルーティングしないその他のシステムとの間の呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="65fa1-163">着信、発信、転送、PSTN エンドポイントに関連する呼び出しの転送は、場所ベースのルーティングを制限するまで対象となります。</span><span class="sxs-lookup"><span data-stu-id="65fa1-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="65fa1-164">これらの呼び出しは、このようなシステムにローカルに定義されている PSTN ゲートウェイのみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="65fa1-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="65fa1-165">次の表は、2 つの別のネットワークのサイトに 4 つのゲートウェイのゲートウェイの構成を示します。 PBX システムに接続されている 2 つの 2 つの PSTN ゲートウェイを接続します。</span><span class="sxs-lookup"><span data-stu-id="65fa1-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="65fa1-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="65fa1-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="65fa1-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="65fa1-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="65fa1-168">PstnGateway:Gateway 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="65fa1-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="65fa1-169">True</span><span class="sxs-lookup"><span data-stu-id="65fa1-169">True</span></span>     |   <span data-ttu-id="65fa1-170">サイト 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="65fa1-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="65fa1-171">PstnGateway:Gateway 2 HYD の GW</span><span class="sxs-lookup"><span data-stu-id="65fa1-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="65fa1-172">True</span><span class="sxs-lookup"><span data-stu-id="65fa1-172">True</span></span>      |      <span data-ttu-id="65fa1-173">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="65fa1-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="65fa1-174">DEL-PBX の PstnGateway:Gateway 3</span><span class="sxs-lookup"><span data-stu-id="65fa1-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="65fa1-175">False</span><span class="sxs-lookup"><span data-stu-id="65fa1-175">False</span></span>     |     <span data-ttu-id="65fa1-176">サイト 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="65fa1-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="65fa1-177">PstnGateway:Gateway 4 HYD の PBX</span><span class="sxs-lookup"><span data-stu-id="65fa1-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="65fa1-178">False</span><span class="sxs-lookup"><span data-stu-id="65fa1-178">False</span></span>     |    <span data-ttu-id="65fa1-179">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="65fa1-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="65fa1-180">ポリシーを呼び出すための場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65fa1-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="65fa1-181">特定のユーザーの場所ベースのルーティングを適用するには、PTSN の有料電話を防ぐために、ユーザーの音声ポリシーを設定をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="65fa1-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="65fa1-182">[許可 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps)コマンドレットを使用して、場所ベースの PSTN 電話使用しないようにすることでルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65fa1-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="65fa1-183">この例では、User1 に PSTN 有料のバイパス ポリシーを呼び出すことを防ぐことです。</span><span class="sxs-lookup"><span data-stu-id="65fa1-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="65fa1-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="65fa1-184">Related topics</span></span>
- [<span data-ttu-id="65fa1-185">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="65fa1-185">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="65fa1-186">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="65fa1-186">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="65fa1-187">場所に基づくルーティングの用語集</span><span class="sxs-lookup"><span data-stu-id="65fa1-187">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
