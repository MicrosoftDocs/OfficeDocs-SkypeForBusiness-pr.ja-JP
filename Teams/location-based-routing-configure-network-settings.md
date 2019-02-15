---
title: 場所ベースのルーティングのネットワーク設定を構成します。
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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b818b10a333fbb7cf50cf4e49d521aa224e2d17
ms.sourcegitcommit: b53d99d06178c26297d1349ff82d05f706dfb479
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "30050765"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="cff2f-103">場所ベースのルーティングのネットワーク設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="cff2f-104">まだためには、他の手順を確認するのには[Plan Location-Based が直接ルーティングのルーティング](location-based-routing-plan.md)を読み取る場合は、場所ベースのルーティングのネットワーク設定を展開する前に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cff2f-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you deploy network settings for Location-Based Routing.</span></span>

<span data-ttu-id="cff2f-105">この資料では、場所ベースのルーティングのネットワーク設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="cff2f-106">組織の電話システムの直接のルーティングを展開した後次の手順は、ネットワーク地域、ネットワーク サイト、およびネットワーク サブネットを作成して設定します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="cff2f-107">この資料の手順を完了するには、PowerShell コマンドレットをある程度必要があります。</span><span class="sxs-lookup"><span data-stu-id="cff2f-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="cff2f-108">詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cff2f-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="cff2f-109">ネットワークの領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-109">Define network regions</span></span>
 <span data-ttu-id="cff2f-110">ネットワークの領域は、複数の地理的な分野にわたって、ネットワークのさまざまな部分を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="cff2f-111">使用して、``New-CsTenantNetworkRegion``ネットワークの領域を定義する PowerShell コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="cff2f-111">Use the ``New-CsTenantNetworkRegion`` PowerShell cmdlet to define network regions.</span></span> <span data-ttu-id="cff2f-112">注意して、``RegionID``パラメーターは、論理名を地域の地理的な位置を表し、依存関係または制約を持たないと、``CentralSite <site ID>``パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cff2f-112">Note that the ``RegionID`` parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the ``CentralSite <site ID>`` parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="cff2f-113">この例では、インドをという名前のネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="cff2f-114">ネットワークのサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-114">Define network sites</span></span>

<span data-ttu-id="cff2f-115">使用して、``New-CsTenantNetworkSite``ネットワーク サイトを定義するための PowerShell コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="cff2f-115">Use the ``New-CsTenantNetworkSite`` PowerShell cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="cff2f-116">この例では、2 つの新しいネットワーク サイト、デリーおよび Hyderabad、インドの領域に作成します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="cff2f-117">次の表は、次の使用例で定義されているネットワークのサイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="cff2f-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="cff2f-118">サイト 1</span><span class="sxs-lookup"><span data-stu-id="cff2f-118">Site 1</span></span> |<span data-ttu-id="cff2f-119">サイト 2</span><span class="sxs-lookup"><span data-stu-id="cff2f-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="cff2f-120">サイト ID</span><span class="sxs-lookup"><span data-stu-id="cff2f-120">Site ID</span></span>    |    <span data-ttu-id="cff2f-121">サイト 1 (デリー)</span><span class="sxs-lookup"><span data-stu-id="cff2f-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="cff2f-122">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="cff2f-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="cff2f-123">地域 ID</span><span class="sxs-lookup"><span data-stu-id="cff2f-123">Region ID</span></span>  |     <span data-ttu-id="cff2f-124">領域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="cff2f-124">Region 1 (India)</span></span>    |   <span data-ttu-id="cff2f-125">領域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="cff2f-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="cff2f-126">ネットワークのサブネットを定義します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-126">Define network subnets</span></span>

<span data-ttu-id="cff2f-127">使用して、``New-CsTenantNetworkSubnet``コマンドレットには、ネットワークのサブネットを定義し、ネットワーク サイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="cff2f-127">Use the ``New-CsTenantNetworkSubnet`` cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="cff2f-128">各内部のサブネットは、1 つのサイトに関連付けられているのみできます。</span><span class="sxs-lookup"><span data-stu-id="cff2f-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="cff2f-129">この例では、サブネット 192.168.0.0 とサイト間で、デリー ネットワークとサブネット 192.168.1.0 と Hyderabad のネットワーク サイトとの間の関連付けを作成します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="cff2f-130">次の表は、次の使用例で定義されているサブネットを示しています。</span><span class="sxs-lookup"><span data-stu-id="cff2f-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="cff2f-131">サイト 1</span><span class="sxs-lookup"><span data-stu-id="cff2f-131">Site 1</span></span> |<span data-ttu-id="cff2f-132">サイト 2</span><span class="sxs-lookup"><span data-stu-id="cff2f-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="cff2f-133">サブネット ID</span><span class="sxs-lookup"><span data-stu-id="cff2f-133">Subnet ID</span></span>   |    <span data-ttu-id="cff2f-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="cff2f-134">192.168.0.0</span></span>     |  <span data-ttu-id="cff2f-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="cff2f-135">192.168.1.0</span></span>     |
|<span data-ttu-id="cff2f-136">マスク</span><span class="sxs-lookup"><span data-stu-id="cff2f-136">Mask</span></span>  |     <span data-ttu-id="cff2f-137">24</span><span class="sxs-lookup"><span data-stu-id="cff2f-137">24</span></span>    |   <span data-ttu-id="cff2f-138">24</span><span class="sxs-lookup"><span data-stu-id="cff2f-138">24</span></span>      |
|<span data-ttu-id="cff2f-139">サイト ID</span><span class="sxs-lookup"><span data-stu-id="cff2f-139">Site ID</span></span>  | <span data-ttu-id="cff2f-140">サイト (デリー)</span><span class="sxs-lookup"><span data-stu-id="cff2f-140">Site (Delhi)</span></span> | <span data-ttu-id="cff2f-141">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="cff2f-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="cff2f-142">複数のサブネットに次のようなスクリプトを使用して CSV ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="cff2f-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="cff2f-143">この例では、CSV ファイル次のようにします。</span><span class="sxs-lookup"><span data-stu-id="cff2f-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="cff2f-144">外部サブネットを定義します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-144">Define external subnets</span></span>
<span data-ttu-id="cff2f-145">使用して、``New-CsTenantTrustedIPAddress``コマンドレットには、外部のサブネットを定義し、テナントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cff2f-145">Use the ``New-CsTenantTrustedIPAddress`` cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="cff2f-146">テナントの無制限の数のサブネットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="cff2f-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="cff2f-147">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="cff2f-148">次のステップ</span><span class="sxs-lookup"><span data-stu-id="cff2f-148">Next steps</span></span>
<span data-ttu-id="cff2f-149">[直接ルーティングのための場所ベースのルーティングを有効にするの](location-based-routing-enable.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="cff2f-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cff2f-150">Related topics</span></span>
- [<span data-ttu-id="cff2f-151">直接ルーティングのための場所ベースのルーティングを計画します。</span><span class="sxs-lookup"><span data-stu-id="cff2f-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="cff2f-152">場所ベースのルーティングの用語</span><span class="sxs-lookup"><span data-stu-id="cff2f-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
