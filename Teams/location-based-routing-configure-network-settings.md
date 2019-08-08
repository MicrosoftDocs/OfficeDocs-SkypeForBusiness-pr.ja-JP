---
title: 場所に基づくルーティングのネットワーク設定を構成する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: ダイレクトルーティングの位置情報に基づくルーティング用に、ネットワークの領域、サイト、サブネットを作成してセットアップする方法について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f6f6f1e74cc50b37ade03e97106d2befe36a6dd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245108"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="ee949-103">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="ee949-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="ee949-104">まだインストールしていない場合は、「[位置情報に基づくルーティングを計画](location-based-routing-plan.md)する」を参照して、場所に基づくルーティングのネットワーク設定を構成する前に実行する必要があるその他の手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ee949-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="ee949-105">この記事では、場所に基づくルーティングのネットワーク設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee949-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="ee949-106">組織で電話システムの直接ルーティングを展開した後、次の手順では、ネットワーク領域、ネットワークサイト、ネットワークサブネットを作成してセットアップします。</span><span class="sxs-lookup"><span data-stu-id="ee949-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="ee949-107">この記事の手順を実行するには、PowerShell コマンドレットについて理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee949-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="ee949-108">詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee949-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="ee949-109">ネットワーク領域を定義する</span><span class="sxs-lookup"><span data-stu-id="ee949-109">Define network regions</span></span>
 <span data-ttu-id="ee949-110">ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。</span><span class="sxs-lookup"><span data-stu-id="ee949-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ee949-111">ネットワーク領域を定義するには、 [CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee949-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="ee949-112">RegionID パラメーターは、領域の地理を表す論理名であり、依存関係または制限がないため、CentralSite &lt;site ID&gt;パラメーターは省略可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ee949-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="ee949-113">この例では、インドという名前のネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="ee949-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="ee949-114">ネットワークサイトを定義する</span><span class="sxs-lookup"><span data-stu-id="ee949-114">Define network sites</span></span>

<span data-ttu-id="ee949-115">ネットワークサイトを定義するには、 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee949-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="ee949-116">この例では、インド地域に2つの新しいネットワークサイト、ニューデリーと Hyderabad を作成します。</span><span class="sxs-lookup"><span data-stu-id="ee949-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="ee949-117">次の表は、この例で定義されているネットワークサイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee949-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="ee949-118">サイト1</span><span class="sxs-lookup"><span data-stu-id="ee949-118">Site 1</span></span> |<span data-ttu-id="ee949-119">サイト2</span><span class="sxs-lookup"><span data-stu-id="ee949-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ee949-120">サイト ID</span><span class="sxs-lookup"><span data-stu-id="ee949-120">Site ID</span></span>    |    <span data-ttu-id="ee949-121">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="ee949-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="ee949-122">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ee949-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="ee949-123">地域 ID</span><span class="sxs-lookup"><span data-stu-id="ee949-123">Region ID</span></span>  |     <span data-ttu-id="ee949-124">地域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="ee949-124">Region 1 (India)</span></span>    |   <span data-ttu-id="ee949-125">地域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="ee949-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="ee949-126">ネットワークサブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="ee949-126">Define network subnets</span></span>

<span data-ttu-id="ee949-127">ネットワークサブネットを定義してネットワークサイトに関連付けるには、 [CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee949-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="ee949-128">各内部サブネットは、1つのサイトにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ee949-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="ee949-129">この例では、サブネット192.168.0.0 と、ニューデリーネットワークサイトと subnet 2001: 4898: 844e: 926f: 85ad: dd8e と Hyderabad ネットワークサイト間の関連付けを作成します。</span><span class="sxs-lookup"><span data-stu-id="ee949-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="ee949-130">次の表は、この例で定義されているサブネットを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee949-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="ee949-131">サイト1</span><span class="sxs-lookup"><span data-stu-id="ee949-131">Site 1</span></span> |<span data-ttu-id="ee949-132">サイト2</span><span class="sxs-lookup"><span data-stu-id="ee949-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ee949-133">サブネット ID</span><span class="sxs-lookup"><span data-stu-id="ee949-133">Subnet ID</span></span>   |    <span data-ttu-id="ee949-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="ee949-134">192.168.0.0</span></span>     |  <span data-ttu-id="ee949-135">2001: 4898: e8:25: 844e: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="ee949-135">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="ee949-136">Mask</span><span class="sxs-lookup"><span data-stu-id="ee949-136">Mask</span></span>  |     <span data-ttu-id="ee949-137">24</span><span class="sxs-lookup"><span data-stu-id="ee949-137">24</span></span>    |   <span data-ttu-id="ee949-138">120</span><span class="sxs-lookup"><span data-stu-id="ee949-138">120</span></span>      |
|<span data-ttu-id="ee949-139">サイト ID</span><span class="sxs-lookup"><span data-stu-id="ee949-139">Site ID</span></span>  | <span data-ttu-id="ee949-140">サイト (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="ee949-140">Site (Delhi)</span></span> | <span data-ttu-id="ee949-141">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ee949-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="ee949-142">複数のサブネットの場合は、次のようなスクリプトを使用して CSV ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ee949-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="ee949-143">この例では、CSV ファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ee949-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="ee949-144">外部サブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="ee949-144">Define external subnets</span></span>
<span data-ttu-id="ee949-145">[CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps)コマンドレットを使用して外部サブネットを定義し、それをテナントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ee949-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="ee949-146">1つのテナントに対して無制限の数のサブネットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ee949-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="ee949-147">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ee949-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="ee949-148">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ee949-148">Next steps</span></span>
<span data-ttu-id="ee949-149">「[ダイレクトルーティングで位置情報に基づくルーティングを有効](location-based-routing-enable.md)にする」に進みます。</span><span class="sxs-lookup"><span data-stu-id="ee949-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="ee949-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ee949-150">Related topics</span></span>
- [<span data-ttu-id="ee949-151">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="ee949-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="ee949-152">場所に基づくルーティングの用語集</span><span class="sxs-lookup"><span data-stu-id="ee949-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
