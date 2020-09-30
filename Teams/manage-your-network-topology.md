---
title: Microsoft Teams でクラウド音声機能のネットワークトポロジを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でクラウド音声機能のネットワーク設定を構成する方法について説明します。
ms.openlocfilehash: 21d47b5b2fae0b22ea585168acdce4a5e25af2ea
ms.sourcegitcommit: 7631af666ae439cc85f1dae8955653a67170cf20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304581"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="758cc-103">Microsoft Teams でクラウド音声機能のネットワークトポロジを管理する</span><span class="sxs-lookup"><span data-stu-id="758cc-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="758cc-104">組織で、ダイレクトルーティングまたは[動的な緊急通話](configure-dynamic-emergency-calling.md)[のための位置情報に基づくルーティング](location-based-routing-plan.md)を展開している場合は、Microsoft Teams でこれらのクラウド音声機能を使用するためのネットワーク設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="758cc-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="758cc-105">[ネットワーク設定] は、Teams クライアントの場所を決定するために使用され、ネットワークの領域、ネットワークサイト、サブネット、および信頼された IP アドレスを含みます。</span><span class="sxs-lookup"><span data-stu-id="758cc-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="758cc-106">展開しているクラウドの音声機能と機能に応じて、これらの設定の一部またはすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="758cc-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="758cc-107">これらの用語の詳細については、「 [クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="758cc-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="758cc-108">ネットワーク設定は、Microsoft Teams 管理センターの [ **ネットワークトポロジ** ] ページ、または Windows PowerShell を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="758cc-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="758cc-109">Microsoft Teams 管理センターでネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="758cc-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="758cc-110">ネットワーク**トポロジ**ページの [**ネットワークサイト**] タブで、ネットワーク領域、ネットワークサイト、サブネットを定義します。</span><span class="sxs-lookup"><span data-stu-id="758cc-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="758cc-111">ここでは、ネットワークサイトを作成または変更し、ネットワーク領域にサイトを関連付け、サブネットをサイトに関連付け、場所に基づくルーティングを有効にして、サイトに緊急ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="758cc-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="758cc-112">また、すべてのサイトでグローバルに使用できるネットワーク領域を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="758cc-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="758cc-113">ネットワークサイトを追加および構成する</span><span class="sxs-lookup"><span data-stu-id="758cc-113">Add and configure a network site</span></span>

1. <span data-ttu-id="758cc-114">Microsoft Teams 管理センターの左のナビゲーションで、[**場所**のネットワークトポロジ] に移動し、[  >  **Network topology\*\*\*\*ネットワークサイト**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="758cc-115">[ **追加**] をクリックして、サイトの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="758cc-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![[ネットワークサイトの追加] ページのスクリーンショット](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="758cc-117">ネットワーク領域にサイトを関連付けるには、[ **ネットワーク領域の追加**] をクリックし、既存の地域を選択するか、[ **追加** ] をクリックして地域を追加し、[ **リンク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="758cc-118">サイトの位置情報に基づくルーティングを有効にするには、 **場所に基づくルーティング**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="758cc-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="758cc-119">サイトに緊急サービスポリシーを割り当てるには、次のいずれか、または両方の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="758cc-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="758cc-120">組織で通話プランまたは展開された電話システムのダイレクトルーティングを使用している場合は、[ **緊急通話ポリシー**] で、目的のポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="758cc-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="758cc-121">組織で電話システムのダイレクトルーティングを展開している場合は、[ **緊急着信ルーティングポリシー**] で、目的のポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="758cc-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="758cc-122">サブネットをサイトに関連付けるには、[ **サブ**ネット] で [ **サブネットの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="758cc-123">IP のバージョン、IP アドレス、ネットワークの範囲を指定し、説明を追加して、[ **適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="758cc-124">各サブネットは、特定のサイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="758cc-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="758cc-125">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="758cc-126">ネットワークサイトを変更する</span><span class="sxs-lookup"><span data-stu-id="758cc-126">Modify a network site</span></span>

1. <span data-ttu-id="758cc-127">Microsoft Teams 管理センターの左のナビゲーションで、[**場所**のネットワークトポロジ] に移動し、[  >  **Network topology\*\*\*\*ネットワークサイト**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="758cc-128">サイト名の左側をクリックして、サイトを選択し、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="758cc-129">必要な変更を加えて、[保存] をクリックし **ます。**</span><span class="sxs-lookup"><span data-stu-id="758cc-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="758cc-130">外部の信頼できる IP アドレスを管理する</span><span class="sxs-lookup"><span data-stu-id="758cc-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="758cc-131">外部の信頼できる IP アドレスは、Microsoft Teams 管理センターの**ネットワークトポロジ**ページの [**信頼済み**ip] タブで管理します。</span><span class="sxs-lookup"><span data-stu-id="758cc-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="758cc-132">外部の信頼済み IP アドレスは無制限に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="758cc-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="758cc-133">信頼できる IP アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="758cc-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="758cc-134">Microsoft Teams 管理センターの左のナビゲーションで、[**場所**のネットワークトポロジ] に移動し、[  >  **Network topology\*\*\*\*信頼さ**れている ip] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="758cc-135">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-135">Click **New**.</span></span>
3. <span data-ttu-id="758cc-136">[ **信頼できる ip アドレスの追加** ] ウィンドウで、ip のバージョン、ip アドレス、ネットワークの範囲を指定し、説明を追加して、[ **適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![[信頼できる IP アドレスの追加] ウィンドウのスクリーンショット](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="758cc-138">信頼できる IP アドレスを編集する</span><span class="sxs-lookup"><span data-stu-id="758cc-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="758cc-139">Microsoft Teams 管理センターの左のナビゲーションで、[**場所**のネットワークトポロジ] に移動し、[  >  **Network topology\*\*\*\*信頼さ**れている ip] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="758cc-140">[IP アドレス] の左側をクリックして選び、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="758cc-141">[ **信頼できる IP アドレスの編集** ] ウィンドウで、必要な変更を行い、[ **適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="758cc-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="758cc-142">PowerShell を使用してネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="758cc-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="758cc-143">このセクションの手順を実行するには、PowerShell コマンドレットについて理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="758cc-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="758cc-144">詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="758cc-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="758cc-145">ネットワーク領域を定義する</span><span class="sxs-lookup"><span data-stu-id="758cc-145">Define network regions</span></span>

 <span data-ttu-id="758cc-146">ネットワーク領域を定義するには、 [CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="758cc-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="758cc-147">RegionID パラメーターは、領域の地理を表す論理名であり、依存関係または制限がないため、CentralSite &lt; SITE ID &gt; パラメーターは省略可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="758cc-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="758cc-148">この例では、インドという名前のネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="758cc-148">In this example, we create a network region named India.</span></span>
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="758cc-149">「 [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="758cc-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="758cc-150">ネットワークサイトを定義する</span><span class="sxs-lookup"><span data-stu-id="758cc-150">Define network sites</span></span>

<span data-ttu-id="758cc-151">ネットワークサイトを定義するには、 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="758cc-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="758cc-152">各ネットワークサイトは、ネットワーク領域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="758cc-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="758cc-153">この例では、インド地域に2つの新しいネットワークサイト、ニューデリーと Hyderabad を作成します。</span><span class="sxs-lookup"><span data-stu-id="758cc-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="758cc-154">次の表は、この例で定義されているネットワークサイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="758cc-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="758cc-155">サイト1</span><span class="sxs-lookup"><span data-stu-id="758cc-155">Site 1</span></span> |<span data-ttu-id="758cc-156">サイト2</span><span class="sxs-lookup"><span data-stu-id="758cc-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="758cc-157">サイト ID</span><span class="sxs-lookup"><span data-stu-id="758cc-157">Site ID</span></span>    |    <span data-ttu-id="758cc-158">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="758cc-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="758cc-159">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="758cc-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="758cc-160">地域 ID</span><span class="sxs-lookup"><span data-stu-id="758cc-160">Region ID</span></span>  |     <span data-ttu-id="758cc-161">地域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="758cc-161">Region 1 (India)</span></span>    |   <span data-ttu-id="758cc-162">地域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="758cc-162">Region 1 (India)</span></span>      |

<span data-ttu-id="758cc-163">「 [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="758cc-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="758cc-164">ネットワークサブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="758cc-164">Define network subnets</span></span>

<span data-ttu-id="758cc-165">ネットワークサブネットを定義してネットワークサイトに関連付けるには、 [CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="758cc-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="758cc-166">各ネットワークサブネットは、1つのサイトにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="758cc-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="758cc-167">この例では、サブネット192.168.0.0 と、ニューデリーネットワークサイトと subnet 2001: 4898: 844e: 926f: 85ad: dd8e と Hyderabad ネットワークサイト間の関連付けを作成します。</span><span class="sxs-lookup"><span data-stu-id="758cc-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="758cc-168">次の表は、この例で定義されているサブネットを示しています。</span><span class="sxs-lookup"><span data-stu-id="758cc-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="758cc-169">サイト1</span><span class="sxs-lookup"><span data-stu-id="758cc-169">Site 1</span></span> |<span data-ttu-id="758cc-170">サイト2</span><span class="sxs-lookup"><span data-stu-id="758cc-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="758cc-171">サブネット ID</span><span class="sxs-lookup"><span data-stu-id="758cc-171">Subnet ID</span></span>   |    <span data-ttu-id="758cc-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="758cc-172">192.168.0.0</span></span>     |  <span data-ttu-id="758cc-173">2001: 4898: e8:25: 844e: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="758cc-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="758cc-174">Mask</span><span class="sxs-lookup"><span data-stu-id="758cc-174">Mask</span></span>  |     <span data-ttu-id="758cc-175">24</span><span class="sxs-lookup"><span data-stu-id="758cc-175">24</span></span>    |   <span data-ttu-id="758cc-176">120</span><span class="sxs-lookup"><span data-stu-id="758cc-176">120</span></span>      |
|<span data-ttu-id="758cc-177">サイト ID</span><span class="sxs-lookup"><span data-stu-id="758cc-177">Site ID</span></span>  | <span data-ttu-id="758cc-178">サイト (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="758cc-178">Site (Delhi)</span></span> | <span data-ttu-id="758cc-179">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="758cc-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="758cc-180">複数のサブネットの場合は、次のようなスクリプトを使用して CSV ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="758cc-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="758cc-181">この例では、CSV ファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="758cc-181">In this example, the CSV file looks something like this:</span></span> 

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="758cc-182">「 [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="758cc-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="758cc-183">外部のサブネット (外部の信頼できる IP アドレス) を定義する</span><span class="sxs-lookup"><span data-stu-id="758cc-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="758cc-184">[CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps)コマンドレットを使用して外部サブネットを定義し、それをテナントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="758cc-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="758cc-185">テナントに対して無制限の数の外部サブネットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="758cc-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="758cc-186">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="758cc-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="758cc-187">「 [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="758cc-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="758cc-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="758cc-188">Related topics</span></span>

- [<span data-ttu-id="758cc-189">Teams でのクラウド音声機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="758cc-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
