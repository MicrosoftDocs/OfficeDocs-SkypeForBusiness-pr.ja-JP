---
title: Microsoft Teams でクラウド音声機能のネットワーク トポロジを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でクラウド音声機能のネットワーク設定を構成する方法について説明します。
ms.openlocfilehash: c77f1e6d31953ce529bff1fab6aa16e1d889e29f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101063"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="d07f9-103">Microsoft Teams でクラウド音声機能のネットワーク トポロジを管理する</span><span class="sxs-lookup"><span data-stu-id="d07f9-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="d07f9-104">組織で直接ルーティングまたは動的[](location-based-routing-plan.md)緊急通話用の場所に基づく[](configure-dynamic-emergency-calling.md)ルーティングを展開している場合は、Microsoft Teams のこれらのクラウド音声機能で使用するネットワーク設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07f9-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="d07f9-105">ネットワーク設定は、Teams クライアントの場所を決定するために使用され、ネットワーク領域、ネットワーク サイト、サブネット、信頼済み IP アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d07f9-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="d07f9-106">展開するクラウド音声機能に応じて、これらの設定の一部またはすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="d07f9-107">これらの用語の詳細については、「クラウド音声機能 [のネットワーク設定」を参照してください](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="d07f9-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="d07f9-108">ネットワーク設定は、Microsoft  Teams 管理センターの [ネットワーク トポロジ] ページで構成するか、Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d07f9-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="d07f9-109">Microsoft Teams 管理センターでネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="d07f9-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="d07f9-110">ネットワーク トポロジ ページの [ネットワーク サイト] タブで、ネットワーク領域、ネットワーク サイト、サブネット **を定義** します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="d07f9-111">ここでは、ネットワーク サイトを作成または変更したり、サイトをネットワーク領域に関連付け、サブネットをサイトに関連付け、場所に基づくルーティングを有効にしたり、緊急ポリシーをサイトに割り当てすることができます。</span><span class="sxs-lookup"><span data-stu-id="d07f9-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="d07f9-112">また、すべてのサイトでグローバルに使用できるネットワーク領域を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d07f9-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="d07f9-113">ネットワーク サイトを追加および構成する</span><span class="sxs-lookup"><span data-stu-id="d07f9-113">Add and configure a network site</span></span>

1. <span data-ttu-id="d07f9-114">Microsoft Teams 管理センターの左側のナビゲーションで **、Locations** Network トポロジに移動し、[ネットワーク サイト]  >  **タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="d07f9-115">[ **追加]** をクリックし、サイトの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![[ネットワーク サイトの追加] ページのスクリーンショット](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="d07f9-117">サイトをネットワーク領域に関連付ける場合は、[ネットワーク領域の追加] をクリックし、既存の地域を選択するか、[追加] をクリックして地域を追加し、[リンク] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d07f9-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="d07f9-118">サイトのLocation-Basedルーティングを有効にするには、場所に基づく **ルーティングを有効にしてください**。</span><span class="sxs-lookup"><span data-stu-id="d07f9-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="d07f9-119">緊急サービス ポリシーをサイトに割り当てるには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d07f9-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="d07f9-120">組織で通話プランを使用している場合、または展開されている電話システムダイレクトルーティングを使用している場合は、[緊急通話ポリシー] で目的のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="d07f9-121">組織が電話システムダイレクト ルーティングを展開している場合は、[緊急通話ルーティング ポリシー] で目的のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="d07f9-122">サブネットをサイトに関連付ける場合は、[ **サブネット]** の [サブネットの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d07f9-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="d07f9-123">IP のバージョン、IP アドレス、ネットワーク範囲を指定し、説明を追加して、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d07f9-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="d07f9-124">各サブネットは、特定のサイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07f9-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="d07f9-125">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d07f9-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="d07f9-126">ネットワーク サイトを変更する</span><span class="sxs-lookup"><span data-stu-id="d07f9-126">Modify a network site</span></span>

1. <span data-ttu-id="d07f9-127">Microsoft Teams 管理センターの左側のナビゲーションで **、Locations** Network トポロジに移動し、[ネットワーク サイト]  >  **タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="d07f9-128">サイト名の左側をクリックしてサイトを選択し、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d07f9-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="d07f9-129">必要な変更を行い、[保存] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="d07f9-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="d07f9-130">外部の信頼済み IP アドレスを管理する</span><span class="sxs-lookup"><span data-stu-id="d07f9-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="d07f9-131">外部の信頼済み IPアドレスは、Microsoft Teams管理センターの [ネットワーク トポロジ] ページの [信頼済み IP] タブで管理します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="d07f9-132">外部の信頼済み IP アドレスの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d07f9-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="d07f9-133">信頼できる IP アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="d07f9-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="d07f9-134">Microsoft Teams 管理センターの左側のナビゲーションで **、Locations** Network トポロジに移動し、[信頼できる  >  **IPs] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="d07f9-135">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d07f9-135">Click **New**.</span></span>
3. <span data-ttu-id="d07f9-136">[信頼 **できる IP** アドレスの追加] ウィンドウで、IP バージョン、IP アドレス、ネットワーク範囲を指定し、説明を追加して、[適用] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d07f9-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![[信頼できる IP アドレスの追加] ウィンドウのスクリーンショット](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="d07f9-138">信頼できる IP アドレスを編集する</span><span class="sxs-lookup"><span data-stu-id="d07f9-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="d07f9-139">Microsoft Teams 管理センターの左側のナビゲーションで **、Locations** Network トポロジに移動し、[信頼できる  >  **IPs] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="d07f9-140">IP アドレスの左側をクリックして選び、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d07f9-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="d07f9-141">[信頼 **できる IP アドレスの編集** ] ウィンドウで、必要な変更を行い、[適用] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d07f9-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="d07f9-142">PowerShell を使用してネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="d07f9-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="d07f9-143">このセクションの手順を完了するには、PowerShell コマンドレットに関する理解が必要です。</span><span class="sxs-lookup"><span data-stu-id="d07f9-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="d07f9-144">詳細については [、「Teams PowerShell の概要」を参照してください](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d07f9-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="d07f9-145">ネットワーク領域を定義する</span><span class="sxs-lookup"><span data-stu-id="d07f9-145">Define network regions</span></span>

 <span data-ttu-id="d07f9-146">[New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion)コマンドレットを使用して、ネットワーク領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-146">Use the [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="d07f9-147">RegionID パラメーターは地域の地理を表す論理名であり、依存関係や制限はありません。CentralSite サイト ID パラメーターは &lt; &gt; 省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d07f9-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="d07f9-148">この例では、India という名前のネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-148">In this example, we create a network region named India.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="d07f9-149">[「Set-CsTenantNetworkRegion」も参照してください](/powershell/module/skype/set-cstenantnetworkregion)。</span><span class="sxs-lookup"><span data-stu-id="d07f9-149">See also [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="d07f9-150">ネットワーク サイトを定義する</span><span class="sxs-lookup"><span data-stu-id="d07f9-150">Define network sites</span></span>

<span data-ttu-id="d07f9-151">[New-CsTenantNetworkSite コマンドレットを使用](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps)して、ネットワーク サイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-151">Use the [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="d07f9-152">各ネットワーク サイトは、ネットワーク領域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07f9-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="d07f9-153">この例では、インド地域に 2 つの新しいネットワーク サイト 、Delhi と領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="d07f9-154">次の表は、この例で定義されているネットワーク サイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="d07f9-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="d07f9-155">サイト 1</span><span class="sxs-lookup"><span data-stu-id="d07f9-155">Site 1</span></span> |<span data-ttu-id="d07f9-156">サイト 2</span><span class="sxs-lookup"><span data-stu-id="d07f9-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d07f9-157">サイト ID</span><span class="sxs-lookup"><span data-stu-id="d07f9-157">Site ID</span></span>    |    <span data-ttu-id="d07f9-158">サイト 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="d07f9-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="d07f9-159">サイト 2 (一時使用数)</span><span class="sxs-lookup"><span data-stu-id="d07f9-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="d07f9-160">地域 ID</span><span class="sxs-lookup"><span data-stu-id="d07f9-160">Region ID</span></span>  |     <span data-ttu-id="d07f9-161">地域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="d07f9-161">Region 1 (India)</span></span>    |   <span data-ttu-id="d07f9-162">地域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="d07f9-162">Region 1 (India)</span></span>      |

<span data-ttu-id="d07f9-163">[「Set-CsTenantNetworkRegion」も参照してください](/powershell/module/skype/set-cstenantnetworksite)。</span><span class="sxs-lookup"><span data-stu-id="d07f9-163">See also [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="d07f9-164">ネットワーク サブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="d07f9-164">Define network subnets</span></span>

<span data-ttu-id="d07f9-165">[New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)コマンドレットを使用して、ネットワーク サブネットを定義し、ネットワーク サイトに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="d07f9-165">Use the [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="d07f9-166">各ネットワーク サブネットは、1 つのサイトにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="d07f9-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="d07f9-167">この例では、サブネット 192.168.0.0 と Delhi ネットワーク サイトの間、およびサブネット 2001:4898:e8:25:844e:926f:85ad:dd8e と、もの間に関連付けを作成します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="d07f9-168">次の表は、この例で定義されているサブネットを示しています。</span><span class="sxs-lookup"><span data-stu-id="d07f9-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="d07f9-169">サイト 1</span><span class="sxs-lookup"><span data-stu-id="d07f9-169">Site 1</span></span> |<span data-ttu-id="d07f9-170">サイト 2</span><span class="sxs-lookup"><span data-stu-id="d07f9-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d07f9-171">サブネット ID</span><span class="sxs-lookup"><span data-stu-id="d07f9-171">Subnet ID</span></span>   |    <span data-ttu-id="d07f9-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="d07f9-172">192.168.0.0</span></span>     |  <span data-ttu-id="d07f9-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span><span class="sxs-lookup"><span data-stu-id="d07f9-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="d07f9-174">マスク</span><span class="sxs-lookup"><span data-stu-id="d07f9-174">Mask</span></span>  |     <span data-ttu-id="d07f9-175">24</span><span class="sxs-lookup"><span data-stu-id="d07f9-175">24</span></span>    |   <span data-ttu-id="d07f9-176">120</span><span class="sxs-lookup"><span data-stu-id="d07f9-176">120</span></span>      |
|<span data-ttu-id="d07f9-177">サイト ID</span><span class="sxs-lookup"><span data-stu-id="d07f9-177">Site ID</span></span>  | <span data-ttu-id="d07f9-178">サイト (Delhi)</span><span class="sxs-lookup"><span data-stu-id="d07f9-178">Site (Delhi)</span></span> | <span data-ttu-id="d07f9-179">サイト 2 (一時使用数)</span><span class="sxs-lookup"><span data-stu-id="d07f9-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="d07f9-180">複数のサブネットの場合は、次のようなスクリプトを使用して CSV ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d07f9-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="d07f9-181">この例では、CSV ファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d07f9-181">In this example, the CSV file looks something like this:</span></span>

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


<span data-ttu-id="d07f9-182">[「Set-CsTenantNetworkSubnet」も参照してください](/powershell/module/skype/set-cstenantnetworksubnet)。</span><span class="sxs-lookup"><span data-stu-id="d07f9-182">See also [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).</span></span>


### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="d07f9-183">外部サブネット (外部信頼済み IP アドレス) を定義する</span><span class="sxs-lookup"><span data-stu-id="d07f9-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="d07f9-184">[New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps)コマンドレットを使用して、外部サブネットを定義し、テナントに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="d07f9-184">Use the [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="d07f9-185">テナントに対して定義できる外部サブネットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d07f9-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="d07f9-186">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d07f9-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="d07f9-187">[「Set-CsTenantTrustedIPAddress」も参照してください](/powershell/module/skype/set-cstenanttrustedipaddress)。</span><span class="sxs-lookup"><span data-stu-id="d07f9-187">See also [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d07f9-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="d07f9-188">Related topics</span></span>

- [<span data-ttu-id="d07f9-189">Teams のクラウド音声機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="d07f9-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
