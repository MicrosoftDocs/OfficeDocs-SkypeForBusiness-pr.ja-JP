---
title: ダイレクト ルーティングの場所に基づくルーティングを有効にする
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: ユーザー、ネットワーク Location-Basedゲートウェイの構成、通話ポリシーに対して有効にする方法など、直接ルーティングのルーティングを有効にする方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d43d650384dd538ff481ac9625c15b9a9f420d95
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120578"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="eaadb-103">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="eaadb-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="eaadb-104">この記事の手順を実行する前に、「ダイレクト ルーティングの計画 [Location-Based](location-based-routing-plan.md) ルーティング」を参照し、「Location-Based ルーティングのネットワーク設定を構成する」の手順 [を完了](location-based-routing-configure-network-settings.md)してください。</span><span class="sxs-lookup"><span data-stu-id="eaadb-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="eaadb-105">この記事では、直接ルーティングの自動ルーティングLocation-Basedする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="eaadb-106">電話システム ダイレクト ルーティングを展開し、ネットワーク領域、サイト、サブネットを設定した後、ネットワーク ルーティングを有効Location-Basedできます。</span><span class="sxs-lookup"><span data-stu-id="eaadb-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="eaadb-107">この記事の手順を完了するには、PowerShell コマンドレットに関する理解が必要です。</span><span class="sxs-lookup"><span data-stu-id="eaadb-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="eaadb-108">詳細については [、「Teams PowerShell の概要」を参照してください](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="eaadb-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="eaadb-109">次の場合、Location-Basedルーティングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaadb-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="eaadb-110">ユーザー</span><span class="sxs-lookup"><span data-stu-id="eaadb-110">Users</span></span>
- <span data-ttu-id="eaadb-111">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="eaadb-111">Network sites</span></span>
- <span data-ttu-id="eaadb-112">ゲートウェイの構成</span><span class="sxs-lookup"><span data-stu-id="eaadb-112">Gateway configurations</span></span>
- <span data-ttu-id="eaadb-113">通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="eaadb-113">Calling policies</span></span>

<span data-ttu-id="eaadb-114">Microsoft チーム管理 [センターまたは](#using-the-microsoft-teams-admin-center) [PowerShel](#using-powershell)l を使用して、ルーティングLocation-Basedできます。</span><span class="sxs-lookup"><span data-stu-id="eaadb-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="eaadb-115">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="eaadb-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="eaadb-116">ユーザーのLocation-Basedルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="eaadb-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="eaadb-117">音声ルーティング ポリシーを作成し、PSTN 使用状況をポリシーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="eaadb-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="eaadb-118">PSTN 使用状況をポリシーに割り当てる場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eaadb-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="eaadb-119">サイトにローカルな PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用状況を使用します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="eaadb-120">ルーティングの制限が不要な地域にある PSTN ゲートウェイを使用する音声ルートLocation-Based PSTN 使用状況を使用します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="eaadb-121">ルーティング制限を適用する必要があるユーザーに音声ルーティング ポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="eaadb-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="eaadb-122">音声ルーティング ポリシーを作成してユーザーに割り当てる方法の詳細については [、「Microsoft Teams](manage-voice-routing-policies.md)で音声ルーティング ポリシーを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaadb-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="eaadb-123">ネットワーク Location-Basedルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="eaadb-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="eaadb-124">ルーティングLocation-Based適用する必要があるサイトのルーティングを有効にする。</span><span class="sxs-lookup"><span data-stu-id="eaadb-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="eaadb-125">これを行うには、Microsoft Teams 管理センターの左側のナビゲーションで、[場所ネットワーク トポロジ] に移動し、ネットワーク サイトを選択し、[編集] をクリックして、[場所に基づくルーティング] をオン  >  **に** します。 </span><span class="sxs-lookup"><span data-stu-id="eaadb-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="eaadb-126">詳細については、「ネットワーク トポロジ [を管理する」を参照してください](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="eaadb-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="eaadb-127">ゲートウェイLocation-Basedルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="eaadb-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="eaadb-128">通話Location-Based PSTN にルーティングする PSTN ゲートウェイに通話をルーティングするゲートウェイへのルーティングを有効にし、ゲートウェイがあるネットワーク サイトを関連付ける。</span><span class="sxs-lookup"><span data-stu-id="eaadb-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="eaadb-129">左側のナビゲーションで、[**音声ダイレクト** ルーティング]  >  **に移動** し **、[SPC] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="eaadb-130">SBC を選択し、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="eaadb-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="eaadb-131">[ **場所に基づくルーティングとメディアの最適化**] で、[場所に基づく **ルーティングを有効にする] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="eaadb-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="eaadb-132">ゲートウェイ サイト ID を指定し、バイパス モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="eaadb-133">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eaadb-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="eaadb-134">通話Location-Basedルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="eaadb-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="eaadb-135">特定のLocation-Basedルーティングを適用するには、PSTN 有料バイパスを防止するためにユーザーの通話ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="eaadb-136">これを行うには、通話 **ポリシーの** [有料バイパスを防止する] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="eaadb-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="eaadb-137">詳細については [、Teams の通話ポリシーを参照してください](teams-calling-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="eaadb-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="eaadb-138">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="eaadb-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="eaadb-139">ユーザーのLocation-Basedルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="eaadb-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="eaadb-140">PSTN 使用状況 [を設定するには、Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-140">Use the [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="eaadb-141">複数の使用法の場合は、各使用法をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="eaadb-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="eaadb-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="eaadb-143">[New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して音声ルーティング ポリシーを作成し、ユーザーを適切な PSTN 使用状況に関連付ける。</span><span class="sxs-lookup"><span data-stu-id="eaadb-143">Use the [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="eaadb-144">PSTN 使用状況を音声ルーティング ポリシーに割り当てる場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eaadb-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="eaadb-145">サイトにローカルな PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用状況を使用する</span><span class="sxs-lookup"><span data-stu-id="eaadb-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="eaadb-146">ルーティングの制限が不要な地域にある PSTN ゲートウェイを使用する音声ルートLocation-Based PSTN 使用状況を使用します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="eaadb-147">この例では、2 つの新しい音声ルーティング ポリシーを作成し、PSTN 使用状況を割り当てにします。</span><span class="sxs-lookup"><span data-stu-id="eaadb-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="eaadb-148">次の表は、この例で定義されている音声ルーティング ポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="eaadb-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="eaadb-149">音声ルーティング ポリシー 1</span><span class="sxs-lookup"><span data-stu-id="eaadb-149">Voice routing policy 1</span></span>|<span data-ttu-id="eaadb-150">音声ルーティング ポリシー 2</span><span class="sxs-lookup"><span data-stu-id="eaadb-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="eaadb-151">オンライン音声ポリシー ID</span><span class="sxs-lookup"><span data-stu-id="eaadb-151">Online voice policy ID</span></span>   |<span data-ttu-id="eaadb-152">Delhi オンライン音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="eaadb-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="eaadb-153">インターネット音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="eaadb-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="eaadb-154">オンライン PSTN 使用状況</span><span class="sxs-lookup"><span data-stu-id="eaadb-154">Online PSTN usages</span></span>  |<span data-ttu-id="eaadb-155">長距離</span><span class="sxs-lookup"><span data-stu-id="eaadb-155">Long Distance</span></span>  |<span data-ttu-id="eaadb-156">長距離、ローカル、内部</span><span class="sxs-lookup"><span data-stu-id="eaadb-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="eaadb-157">[Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ルーティング制限を適用する必要があるユーザーにオンライン音声ルーティング ポリシーを関連付ける。</span><span class="sxs-lookup"><span data-stu-id="eaadb-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="eaadb-158">ネットワーク Location-Basedルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="eaadb-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="eaadb-159">[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps)コマンドレットを使用して、Location-Based ルーティングを有効にし、ルーティング制限を適用する必要があるネットワーク サイトに音声ルーティング ポリシーを関連付ける。</span><span class="sxs-lookup"><span data-stu-id="eaadb-159">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="eaadb-160">この例では、Delhi サイトとLocation-Basedサイトのルーティングを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="eaadb-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="eaadb-161">次の表は、この例の Location-Based有効になっているサイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="eaadb-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="eaadb-162">サイト 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="eaadb-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="eaadb-163">サイト 2 (一時使用数)</span><span class="sxs-lookup"><span data-stu-id="eaadb-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="eaadb-164">サイト名</span><span class="sxs-lookup"><span data-stu-id="eaadb-164">Site name</span></span>    |<span data-ttu-id="eaadb-165">サイト 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="eaadb-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="eaadb-166">サイト 2 (一時使用数)</span><span class="sxs-lookup"><span data-stu-id="eaadb-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="eaadb-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="eaadb-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="eaadb-168">True</span><span class="sxs-lookup"><span data-stu-id="eaadb-168">True</span></span>    |<span data-ttu-id="eaadb-169">True</span><span class="sxs-lookup"><span data-stu-id="eaadb-169">True</span></span>    |
    |<span data-ttu-id="eaadb-170">サブネット</span><span class="sxs-lookup"><span data-stu-id="eaadb-170">Subnets</span></span>     |<span data-ttu-id="eaadb-171">サブネット 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="eaadb-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="eaadb-172">サブネット 2 (一時使用数)</span><span class="sxs-lookup"><span data-stu-id="eaadb-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="eaadb-173">ゲートウェイLocation-Basedルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="eaadb-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="eaadb-174">[New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、ゲートウェイまたはネットワーク サイトごとにゲートウェイ構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-174">Use the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="eaadb-175">複数のゲートウェイがシステム (ゲートウェイや PBX など) に関連付けられている場合は、各ゲートウェイを変更して、ルーティングLocation-Based有効にします。</span><span class="sxs-lookup"><span data-stu-id="eaadb-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="eaadb-176">この例では、ゲートウェイごとに 1 つのゲートウェイ構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="eaadb-177">詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaadb-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="eaadb-178">[Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、ルーティングLocation-Based適用する必要があるゲートウェイのルーティングを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="eaadb-178">Use the [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="eaadb-179">通話Location-Based PSTN にルーティングする PSTN ゲートウェイに通話をルーティングするゲートウェイへのルーティングを有効にし、ゲートウェイがあるネットワーク サイトを関連付ける。</span><span class="sxs-lookup"><span data-stu-id="eaadb-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="eaadb-180">この例では、delhi サイトLocation-Based Pstn ゲートウェイに関連付けられている各ゲートウェイのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="eaadb-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="eaadb-181">PSTN に通話をLocation-Basedゲートウェイのルーティングを有効にしません。</span><span class="sxs-lookup"><span data-stu-id="eaadb-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="eaadb-182">ただし、システムが存在するネットワーク サイトにゲートウェイを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaadb-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="eaadb-183">これは、このLocation-Based経由して接続されるエンドポイントに到達する PSTN 通話には、ルーティング制限を適用する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="eaadb-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="eaadb-184">この例では、Location-Basedサイトの PBX システムに関連付けられている各ゲートウェイで、ルーティングが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="eaadb-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="eaadb-185">通話Location-Basedルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="eaadb-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="eaadb-186">特定のLocation-Basedルーティングを適用するには、PTSN 有料バイパスを防止するためにユーザーの音声ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="eaadb-187">[GRANT-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps)コマンドレットを使用して、PSTN 有料Location-Basedによるルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="eaadb-187">Use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="eaadb-188">この例では、User1 の通話ポリシーへの PSTN 有料バイパスを防止します。</span><span class="sxs-lookup"><span data-stu-id="eaadb-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="eaadb-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaadb-189">Related topics</span></span>

- [<span data-ttu-id="eaadb-190">Teams のクラウド音声機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="eaadb-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)