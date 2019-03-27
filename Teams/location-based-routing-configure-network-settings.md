---
title: 場所に基づくルーティングのネットワーク設定を構成する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 作成し、直接ルーティングの場所ベースのルーティング ネットワーク領域、サイト、およびサブネットを設定する方法について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60af1c90cd1dbd7855da7686950ffd135d1da5dc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876769"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="ddac5-103">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="ddac5-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="ddac5-104">まだためには、他の手順を確認するのには[Plan Location-Based が直接ルーティングのルーティング](location-based-routing-plan.md)を読み取る場合は、場所ベースのルーティングのネットワーク設定を構成する前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddac5-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="ddac5-105">この資料では、場所ベースのルーティングのネットワーク設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="ddac5-106">組織の電話システムの直接のルーティングを展開した後次の手順は、ネットワーク地域、ネットワーク サイト、およびネットワーク サブネットを作成して設定します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="ddac5-107">この資料の手順を完了するには、PowerShell コマンドレットをある程度必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddac5-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="ddac5-108">詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddac5-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="ddac5-109">ネットワークの領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-109">Define network regions</span></span>
 <span data-ttu-id="ddac5-110">ネットワークの領域は、複数の地理的な分野にわたって、ネットワークのさまざまな部分を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ddac5-111">[新規 CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps)コマンドレットを使用して、ネットワークの領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="ddac5-112">RegionID パラメーターは、論理名を地域の地理的な場所を表しに依存しないか、制限と、CentralSite&lt;サイトの ID&gt;パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ddac5-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="ddac5-113">この例では、インドをという名前のネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="ddac5-114">ネットワークのサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-114">Define network sites</span></span>

<span data-ttu-id="ddac5-115">[新規 CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps)コマンドレットを使用すると、ネットワークのサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="ddac5-116">この例では、2 つの新しいネットワーク サイト、デリーおよび Hyderabad、インドの領域に作成します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="ddac5-117">次の表は、次の使用例で定義されているネットワークのサイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="ddac5-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="ddac5-118">サイト 1</span><span class="sxs-lookup"><span data-stu-id="ddac5-118">Site 1</span></span> |<span data-ttu-id="ddac5-119">サイト 2</span><span class="sxs-lookup"><span data-stu-id="ddac5-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ddac5-120">サイト ID</span><span class="sxs-lookup"><span data-stu-id="ddac5-120">Site ID</span></span>    |    <span data-ttu-id="ddac5-121">サイト 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="ddac5-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="ddac5-122">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ddac5-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="ddac5-123">地域 ID</span><span class="sxs-lookup"><span data-stu-id="ddac5-123">Region ID</span></span>  |     <span data-ttu-id="ddac5-124">領域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="ddac5-124">Region 1 (India)</span></span>    |   <span data-ttu-id="ddac5-125">領域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="ddac5-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="ddac5-126">ネットワークのサブネットを定義します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-126">Define network subnets</span></span>

<span data-ttu-id="ddac5-127">ネットワークのサブネットを定義し、ネットワーク サイトに関連付けるには、[新しい CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="ddac5-128">各内部のサブネットは、1 つのサイトに関連付けられているのみできます。</span><span class="sxs-lookup"><span data-stu-id="ddac5-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="ddac5-129">この例では、サブネット 192.168.0.0 とサイト間で、デリー ネットワークとサブネット 192.168.1.0 と Hyderabad のネットワーク サイトとの間の関連付けを作成します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="ddac5-130">次の表は、次の使用例で定義されているサブネットを示しています。</span><span class="sxs-lookup"><span data-stu-id="ddac5-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="ddac5-131">サイト 1</span><span class="sxs-lookup"><span data-stu-id="ddac5-131">Site 1</span></span> |<span data-ttu-id="ddac5-132">サイト 2</span><span class="sxs-lookup"><span data-stu-id="ddac5-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ddac5-133">サブネット ID</span><span class="sxs-lookup"><span data-stu-id="ddac5-133">Subnet ID</span></span>   |    <span data-ttu-id="ddac5-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="ddac5-134">192.168.0.0</span></span>     |  <span data-ttu-id="ddac5-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="ddac5-135">192.168.1.0</span></span>     |
|<span data-ttu-id="ddac5-136">マスク</span><span class="sxs-lookup"><span data-stu-id="ddac5-136">Mask</span></span>  |     <span data-ttu-id="ddac5-137">24</span><span class="sxs-lookup"><span data-stu-id="ddac5-137">24</span></span>    |   <span data-ttu-id="ddac5-138">24</span><span class="sxs-lookup"><span data-stu-id="ddac5-138">24</span></span>      |
|<span data-ttu-id="ddac5-139">サイト ID</span><span class="sxs-lookup"><span data-stu-id="ddac5-139">Site ID</span></span>  | <span data-ttu-id="ddac5-140">サイト (デリー)</span><span class="sxs-lookup"><span data-stu-id="ddac5-140">Site (Delhi)</span></span> | <span data-ttu-id="ddac5-141">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ddac5-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="ddac5-142">複数のサブネットに次のようなスクリプトを使用して CSV ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ddac5-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="ddac5-143">この例では、CSV ファイル次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ddac5-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="ddac5-144">外部サブネットを定義します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-144">Define external subnets</span></span>
<span data-ttu-id="ddac5-145">外部サブネットを定義し、テナントに割り当てるには、[新規 CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="ddac5-146">テナントの無制限の数のサブネットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ddac5-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="ddac5-147">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="ddac5-148">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ddac5-148">Next steps</span></span>
<span data-ttu-id="ddac5-149">[直接ルーティングのための場所ベースのルーティングを有効にするの](location-based-routing-enable.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="ddac5-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="ddac5-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="ddac5-150">Related topics</span></span>
- [<span data-ttu-id="ddac5-151">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="ddac5-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="ddac5-152">場所に基づくルーティングの用語集</span><span class="sxs-lookup"><span data-stu-id="ddac5-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
