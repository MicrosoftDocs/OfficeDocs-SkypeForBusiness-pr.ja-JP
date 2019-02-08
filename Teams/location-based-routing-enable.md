---
title: 直接ルーティングのための場所ベースのルーティングを有効にします。
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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8437eba299cb42415d224017ca7d0e888fffa684
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "29771009"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="a54c8-103">直接ルーティングのための場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a54c8-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="a54c8-104">この資料の手順を実行する前に、 [Plan Location-Based を直接ルーティングのルーティング](location-based-routing-plan.md)を参照し、[場所ベースのルーティング用のネットワーク設定の構成](location-based-routing-configure-network-settings.md)手順を完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a54c8-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="a54c8-105">この資料では、直接ルーティングするための場所ベースのルーティングを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="a54c8-106">電話システムの直接のルーティングを展開し、ネットワーク領域、サイト、およびサブネットを設定すると、場所ベースのルーティングを有効にする準備ができています。</span><span class="sxs-lookup"><span data-stu-id="a54c8-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="a54c8-107">この資料の手順を完了するには、PowerShell コマンドレットをある程度必要があります。</span><span class="sxs-lookup"><span data-stu-id="a54c8-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="a54c8-108">詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a54c8-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="a54c8-109">次の場所ベースのルーティングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a54c8-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="a54c8-110">ユーザー</span><span class="sxs-lookup"><span data-stu-id="a54c8-110">Users</span></span>
- <span data-ttu-id="a54c8-111">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="a54c8-111">Network sites</span></span>
- <span data-ttu-id="a54c8-112">ゲートウェイの構成</span><span class="sxs-lookup"><span data-stu-id="a54c8-112">Gateway configurations</span></span>
- <span data-ttu-id="a54c8-113">ポリシーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="a54c8-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="a54c8-114">ユーザーの場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a54c8-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="a54c8-115">使用して、``Set-CsOnlinePstnUsages``コマンドレットは PSTN の使用法を設定します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-115">Use the ``Set-CsOnlinePstnUsages`` cmdlet to set PSTN usages.</span></span> <span data-ttu-id="a54c8-116">複数の使用状況を毎回使用をカンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="a54c8-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="a54c8-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="a54c8-118">使用して、``New-CsOnlineVoiceRoutingPolicy``にユーザーを関連付ける適切な PSTN 使用法の音声ルーティング ポリシーを作成するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="a54c8-118">Use the ``New-CsOnlineVoiceRoutingPolicy`` cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="a54c8-119">音声ルーティング ポリシーに PSTN 使用法を割り当てると、次のいずれかの操作を行うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="a54c8-120">サイトをローカルの PSTN ゲートウェイを使用してボイス ルートに関連付けられている PSTN 使用法を使用します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="a54c8-121">場所ベースのルーティングの制限が不要の領域内にある PSTN ゲートウェイを使用してボイス ルートに関連付けられている PSTN 使用法を使用します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="a54c8-122">この例は、2 つの新しい音声ルーティング ポリシーを作成し、PSTN の使用法に割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="a54c8-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="a54c8-123">次の表は、次の使用例で定義されている音声ルーティング ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="a54c8-124">音声ルーティング ポリシー 1</span><span class="sxs-lookup"><span data-stu-id="a54c8-124">Voice routing policy 1</span></span>|<span data-ttu-id="a54c8-125">音声ルーティング ポリシー 2</span><span class="sxs-lookup"><span data-stu-id="a54c8-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="a54c8-126">ボイス ポリシー ID</span><span class="sxs-lookup"><span data-stu-id="a54c8-126">Voice policy ID</span></span>   |<span data-ttu-id="a54c8-127">デリー音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="a54c8-127">Delhi voice routing policy</span></span>   |<span data-ttu-id="a54c8-128">Hyderabad の音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="a54c8-128">Hyderabad voice routing policy</span></span>    |
    |<span data-ttu-id="a54c8-129">オンラインの PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="a54c8-129">Online PSTN usages</span></span>  |<span data-ttu-id="a54c8-130">市外通話</span><span class="sxs-lookup"><span data-stu-id="a54c8-130">Long Distance</span></span>  |<span data-ttu-id="a54c8-131">長い距離、ローカルな内部</span><span class="sxs-lookup"><span data-stu-id="a54c8-131">Long Distance, Local, Internal</span></span>  |

    <span data-ttu-id="a54c8-132">詳細については、[新規 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a54c8-132">For more information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>
3. <span data-ttu-id="a54c8-133">使用して、``Grant-CsOnlineVoiceRoutingPolicy``オンラインに関連付けるには、コマンドレットの音声ルーティング ポリシーを適用するルーティングの制限を必要とするユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a54c8-133">Use the ``Grant-CsOnlineVoiceRoutingPolicy`` cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="a54c8-134">ネットワークのサイトの場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a54c8-134">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="a54c8-135">使用して、``Set-CsTenantNetworkSite``コマンドレットには、場所ベースのルーティングを有効にして、関連付けの音声ルーティング ポリシー、ルーティングの制限を適用する必要があるネットワーク サイトです。</span><span class="sxs-lookup"><span data-stu-id="a54c8-135">Use the ``Set-CsTenantNetworkSite`` cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -OnlineVoiceRoutingPolicy <voice routing policy ID> 
    ```

    <span data-ttu-id="a54c8-136">この例では、Delhi サイトおよび Hyderabad のサイトの場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a54c8-136">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "DelhiVoiceRoutingPolicy" 
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "HyderabadVoiceRoutingPolicy" 
    ```
    <span data-ttu-id="a54c8-137">次の表は、この例では、場所ベースのルーティングを有効になっているサイトを示します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-137">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="a54c8-138">サイト 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="a54c8-138">Site 1 (Delhi)</span></span>  |<span data-ttu-id="a54c8-139">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a54c8-139">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="a54c8-140">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="a54c8-140">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="a54c8-141">True</span><span class="sxs-lookup"><span data-stu-id="a54c8-141">True</span></span>    |<span data-ttu-id="a54c8-142">True</span><span class="sxs-lookup"><span data-stu-id="a54c8-142">True</span></span>    |
    |<span data-ttu-id="a54c8-143">音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="a54c8-143">Voice routing policy</span></span>    | <span data-ttu-id="a54c8-144">デリー音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="a54c8-144">Delhi voice routing policy</span></span>       |<span data-ttu-id="a54c8-145">Hyderabad の音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="a54c8-145">Hyderabad voice routing policy</span></span>    |
    |<span data-ttu-id="a54c8-146">サブネット</span><span class="sxs-lookup"><span data-stu-id="a54c8-146">Subnets</span></span>     |<span data-ttu-id="a54c8-147">サブネット 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="a54c8-147">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="a54c8-148">サブネット 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a54c8-148">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="a54c8-149">ゲートウェイの場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a54c8-149">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="a54c8-150">使用して、``New-CsOnlinePstnGateway``ゲートウェイ、またはネットワークの各サイトのゲートウェイの構成を作成するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="a54c8-150">Use the ``New-CsOnlinePstnGateway`` cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="a54c8-151">複数のゲートウェイ (たとえば、ゲートウェイまたは PBX) システムに関連付けられている場合は、場所ベースのルーティングの制限を有効にするには、各ゲートウェイを変更します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-151">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="a54c8-152">この例では、各ゲートウェイの 1 つのゲートウェイの構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-152">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="a54c8-153">詳細については、[直接ルーティングの構成](direct-routing-configure.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a54c8-153">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="a54c8-154">使用して、 ``Set-CSOnlinePSTNGateway`` 、ルーティングの制限を適用する必要があるゲートウェイの場所ベースのルーティングを有効にするコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="a54c8-154">Use the ``Set-CSOnlinePSTNGateway`` cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="a54c8-155">呼び出しをルーティングするゲートウェイに場所ベースのルーティングを有効にする PSTN ゲートウェイが PSTN への呼び出しをルーティングし、ゲートウェイが配置されているネットワーク サイトに関連付けることにします。</span><span class="sxs-lookup"><span data-stu-id="a54c8-155">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="a54c8-156">この例では、デリーおよび Hyderabad のサイトでの PSTN ゲートウェイに関連付けられているゲートウェイごとに場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a54c8-156">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="a54c8-157">PSTN への呼び出しをルーティングしないゲートウェイの場所ベースのルーティングを有効にしません。</span><span class="sxs-lookup"><span data-stu-id="a54c8-157">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="a54c8-158">ただし、まだ、システムが配置されているネットワーク サイトへのゲートウェイを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a54c8-158">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="a54c8-159">これは、場所ベースのルーティングの制限は、このゲートウェイ経由で接続されているエンドポイントに到達する PSTN の呼び出しに適用する必要があるためにです。</span><span class="sxs-lookup"><span data-stu-id="a54c8-159">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="a54c8-160">この例では、場所ベースのルーティングは、デリーおよび Hyderabad のサイト内の PBX システムに関連付けられている各ゲートウェイを有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="a54c8-160">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="a54c8-161">(PBX など) の PSTN への呼び出しをルーティングしないシステムに接続されているエンドポイントでは、場所ベースのルーティングが有効なチームのユーザーのエンドポイントとして、同様の制限があります。</span><span class="sxs-lookup"><span data-stu-id="a54c8-161">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="a54c8-162">これは、これらのユーザーが配置し、ユーザーの場所に関係なくチームのユーザーとの間の呼び出しを受信することを意味します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-162">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="a54c8-163">したりすることがどのシステムと関連付けられているネットワーク サイト (たとえば、別の PBX に接続されているエンドポイント) PSTN ネットワークへの呼び出しをルーティングしないその他のシステムとの間の呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-163">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="a54c8-164">着信、発信、転送、PSTN エンドポイントに関連する呼び出しの転送は、場所ベースのルーティングを制限するまで対象となります。</span><span class="sxs-lookup"><span data-stu-id="a54c8-164">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="a54c8-165">これらの呼び出しは、このようなシステムにローカルに定義されている PSTN ゲートウェイのみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="a54c8-165">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="a54c8-166">次の表は、2 つの別のネットワークのサイトに 4 つのゲートウェイのゲートウェイの構成を示します。 PBX システムに接続されている 2 つの 2 つの PSTN ゲートウェイを接続します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-166">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="a54c8-167">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="a54c8-167">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="a54c8-168">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="a54c8-168">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="a54c8-169">PstnGateway:Gateway 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="a54c8-169">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="a54c8-170">True</span><span class="sxs-lookup"><span data-stu-id="a54c8-170">True</span></span>     |   <span data-ttu-id="a54c8-171">サイト 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="a54c8-171">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="a54c8-172">PstnGateway:Gateway 2 HYD の GW</span><span class="sxs-lookup"><span data-stu-id="a54c8-172">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="a54c8-173">True</span><span class="sxs-lookup"><span data-stu-id="a54c8-173">True</span></span>      |      <span data-ttu-id="a54c8-174">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a54c8-174">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="a54c8-175">DEL-PBX の PstnGateway:Gateway 3</span><span class="sxs-lookup"><span data-stu-id="a54c8-175">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="a54c8-176">True</span><span class="sxs-lookup"><span data-stu-id="a54c8-176">True</span></span>     |     <span data-ttu-id="a54c8-177">サイト 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="a54c8-177">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="a54c8-178">PstnGateway:Gateway 4 HYD の PBX</span><span class="sxs-lookup"><span data-stu-id="a54c8-178">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="a54c8-179">True</span><span class="sxs-lookup"><span data-stu-id="a54c8-179">True</span></span>     |    <span data-ttu-id="a54c8-180">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a54c8-180">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="a54c8-181">ポリシーを呼び出すための場所ベースのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a54c8-181">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="a54c8-182">特定のユーザーの場所ベースのルーティングを適用するには、PTSN の有料電話を防ぐために、ユーザーの音声ポリシーを設定をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="a54c8-182">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="a54c8-183">使用、``Grant-TeamsCallingPolicy``の場所ベースの PSTN 通話を防止することでルーティングを有効にするコマンドレットをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="a54c8-183">Use the ``Grant-TeamsCallingPolicy`` cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-TeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="a54c8-184">この例では、User1 に PSTN 有料のバイパス ポリシーを呼び出すことを防ぐことです。</span><span class="sxs-lookup"><span data-stu-id="a54c8-184">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-TeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="a54c8-185">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a54c8-185">Related topics</span></span>
- [<span data-ttu-id="a54c8-186">直接ルーティングのための場所ベースのルーティングを計画します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-186">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="a54c8-187">場所ベースのルーティングのネットワーク設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a54c8-187">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="a54c8-188">場所ベースのルーティングの用語</span><span class="sxs-lookup"><span data-stu-id="a54c8-188">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
