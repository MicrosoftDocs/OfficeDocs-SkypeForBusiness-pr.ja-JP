---
title: ダイレクトルーティングのローカルメディア最適化
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接ルーティング用のローカルメディア最適化を構成する
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53f9156b6ab6d33223c9b1d3e11a604ba0c1c31
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121607"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="79778-103">直接ルーティング用のローカルメディア最適化を構成する</span><span class="sxs-lookup"><span data-stu-id="79778-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="79778-104">ローカルメディア最適化の構成は、場所に基づくルーティングや動的な緊急通話など、他のクラウド音声機能に共通するネットワーク設定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="79778-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="79778-105">ネットワーク領域、ネットワークサイト、ネットワークサブネット、および信頼された IP アドレスの詳細については、「[クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79778-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="79778-106">ローカルメディア最適化を構成する前に、「[直接ルーティング用のローカルメディアの最適化](direct-routing-media-optimization.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="79778-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="79778-107">ローカルメディア最適化を構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="79778-108">Teams 管理センターまたは PowerShell を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="79778-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="79778-109">詳細については、「[ネットワークトポロジを管理する](manage-your-network-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79778-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="79778-110">ユーザーと SBC サイトを構成します (この記事で説明します)。</span><span class="sxs-lookup"><span data-stu-id="79778-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="79778-111">(SBC ベンダー仕様に従って) ローカルメディア最適化用に SBCs を構成します。</span><span class="sxs-lookup"><span data-stu-id="79778-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="79778-112">次の図は、この記事の例で使用されているネットワークセットアップを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="79778-113">![例のネットワークセットアップを示す図](media/direct-routing-media-op-9.png "ネットワークセットアップ例")</span><span class="sxs-lookup"><span data-stu-id="79778-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="79778-114">ユーザーと SBC サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="79778-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="79778-115">ユーザーと SBC サイトを構成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="79778-116">[外部の信頼できる IP アドレスを管理](#manage-external-trusted-ip-addresses)する。</span><span class="sxs-lookup"><span data-stu-id="79778-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="79778-117">ネットワークの領域、ネットワークサイト、ネットワークサブネットを構成して、[ネットワークトポロジを定義](#define-the-network-topology)します。</span><span class="sxs-lookup"><span data-stu-id="79778-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="79778-118">関連するモードとプロキシの SBC 値を使って、サイトに SBC (s) を割り当てることで[、仮想ネットワークトポロジを定義](#define-the-virtual-network-topology)します。</span><span class="sxs-lookup"><span data-stu-id="79778-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="79778-119">SBC ベンダー仕様に従って、ローカルメディア最適化用に SBC を構成する</span><span class="sxs-lookup"><span data-stu-id="79778-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="79778-120">この記事では、Microsoft コンポーネントの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="79778-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="79778-121">SBC 構成の詳細については、SBC ベンダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79778-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="79778-122">ローカルメディア最適化は、次の SBC ベンダーによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79778-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="79778-123">仕入先</span><span class="sxs-lookup"><span data-stu-id="79778-123">Vendor</span></span> | <span data-ttu-id="79778-124">Product</span><span class="sxs-lookup"><span data-stu-id="79778-124">Product</span></span> |    <span data-ttu-id="79778-125">ソフトウェアのバージョン</span><span class="sxs-lookup"><span data-stu-id="79778-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="79778-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="79778-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="79778-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="79778-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="79778-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="79778-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="79778-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="79778-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="79778-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="79778-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="79778-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="79778-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="79778-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="79778-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="79778-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="79778-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="79778-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="79778-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="79778-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="79778-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="79778-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="79778-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="79778-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="79778-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="79778-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="79778-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="79778-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="79778-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="79778-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="79778-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="79778-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="79778-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="79778-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="79778-142">7.20A.256</span></span> |
| [<span data-ttu-id="79778-143">リボンの SBC コア</span><span class="sxs-lookup"><span data-stu-id="79778-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="79778-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="79778-144">SBC 5110</span></span>         | <span data-ttu-id="79778-145">8.2</span><span class="sxs-lookup"><span data-stu-id="79778-145">8.2</span></span>  |
|            |  <span data-ttu-id="79778-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="79778-146">SBC 5210</span></span>         | <span data-ttu-id="79778-147">8.2</span><span class="sxs-lookup"><span data-stu-id="79778-147">8.2</span></span>  |
|            |  <span data-ttu-id="79778-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="79778-148">SBC 5400</span></span>         | <span data-ttu-id="79778-149">8.2</span><span class="sxs-lookup"><span data-stu-id="79778-149">8.2</span></span>  |
|            |  <span data-ttu-id="79778-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="79778-150">SBC 7000</span></span>         | <span data-ttu-id="79778-151">8.2</span><span class="sxs-lookup"><span data-stu-id="79778-151">8.2</span></span>  |
|            |  <span data-ttu-id="79778-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="79778-152">SBC SWe</span></span>          | <span data-ttu-id="79778-153">8.2</span><span class="sxs-lookup"><span data-stu-id="79778-153">8.2</span></span>  |
| [<span data-ttu-id="79778-154">リボンの SBC エッジ</span><span class="sxs-lookup"><span data-stu-id="79778-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="79778-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="79778-155">SBC SWe Lite</span></span> | <span data-ttu-id="79778-156">8.1.5 (ビルド 239)</span><span class="sxs-lookup"><span data-stu-id="79778-156">8.1.5 (build 239)</span></span> |
| [<span data-ttu-id="79778-157">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="79778-157">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="79778-158">anynode</span><span class="sxs-lookup"><span data-stu-id="79778-158">anynode</span></span>          | <span data-ttu-id="79778-159">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="79778-159">4.0.1+</span></span> |
| [<span data-ttu-id="79778-160">Oracle</span><span class="sxs-lookup"><span data-stu-id="79778-160">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="79778-161">AP 1100</span><span class="sxs-lookup"><span data-stu-id="79778-161">AP 1100</span></span> | <span data-ttu-id="79778-162">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="79778-162">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="79778-163">AP 3900</span><span class="sxs-lookup"><span data-stu-id="79778-163">AP 3900</span></span> | <span data-ttu-id="79778-164">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="79778-164">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="79778-165">AP 4600</span><span class="sxs-lookup"><span data-stu-id="79778-165">AP 4600</span></span> | <span data-ttu-id="79778-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="79778-166">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="79778-167">AP 6300</span><span class="sxs-lookup"><span data-stu-id="79778-167">AP 6300</span></span> | <span data-ttu-id="79778-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="79778-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="79778-169">AP 6350</span><span class="sxs-lookup"><span data-stu-id="79778-169">AP 6350</span></span> | <span data-ttu-id="79778-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="79778-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="79778-171">VME</span><span class="sxs-lookup"><span data-stu-id="79778-171">VME</span></span>     | <span data-ttu-id="79778-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="79778-172">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="79778-173">外部の信頼できる IP アドレスを管理する</span><span class="sxs-lookup"><span data-stu-id="79778-173">Manage external trusted IP addresses</span></span>

<span data-ttu-id="79778-174">外部の信頼できる Ip は、エンタープライズネットワークのインターネット外部 Ip です。</span><span class="sxs-lookup"><span data-stu-id="79778-174">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="79778-175">これらの IP アドレスは、microsoft Teams クライアントが Microsoft 365 に接続したときに使用される IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="79778-175">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="79778-176">ユーザーがローカルメディア最適化を使用しているサイトごとに、これらの外部 Ip を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-176">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="79778-177">各サイトのパブリック IP アドレスを追加するには、CsTenantTrustedIPAddress コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="79778-177">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="79778-178">1つのテナントに対して無制限の数の信頼できる IP アドレスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="79778-178">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="79778-179">Microsoft 365 によって表示される外部 Ip が IPv4 アドレスと IPv6 アドレスの両方である場合は、両方の種類の IP アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-179">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="79778-180">IPv4 の場合は、マスク32を使用します。</span><span class="sxs-lookup"><span data-stu-id="79778-180">For IPv4, use mask 32.</span></span> <span data-ttu-id="79778-181">IPv6 の場合は、マスク128を使用します。</span><span class="sxs-lookup"><span data-stu-id="79778-181">For IPv6, use mask 128.</span></span> <span data-ttu-id="79778-182">コマンドレットで異なる MaskBits を指定することで、個々の外部 IP アドレスと外部 IP サブネットの両方を追加できます。</span><span class="sxs-lookup"><span data-stu-id="79778-182">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="79778-183">信頼された IP アドレスを追加する例。</span><span class="sxs-lookup"><span data-stu-id="79778-183">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="79778-184">ネットワークトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="79778-184">Define the network topology</span></span>

<span data-ttu-id="79778-185">このセクションでは、ネットワークトポロジのネットワーク領域、ネットワークサイト、ネットワークサブネットを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="79778-185">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="79778-186">すべてのパラメーターは大文字と小文字を区別するため、セットアップ時に使用したのと同じケースを確実に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-186">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="79778-187">(たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は、別のサイトとして扱われます)。</span><span class="sxs-lookup"><span data-stu-id="79778-187">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="79778-188">ネットワーク領域を定義する</span><span class="sxs-lookup"><span data-stu-id="79778-188">Define network regions</span></span>

<span data-ttu-id="79778-189">ネットワーク領域を定義するには、CsTenantNetworkRegion コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="79778-189">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="79778-190">RegionID パラメーターは、地域の地理を表す論理名であり、依存関係または制限がありません。</span><span class="sxs-lookup"><span data-stu-id="79778-190">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="79778-191">CentralSite <site ID> パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="79778-191">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="79778-192">次の例では、APAC という名前のネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="79778-192">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="79778-193">ネットワークサイトを定義する</span><span class="sxs-lookup"><span data-stu-id="79778-193">Define network sites</span></span>

<span data-ttu-id="79778-194">ネットワークサイトを定義するには、CsTenantNetworkSite コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="79778-194">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="79778-195">各ネットワークサイトは、ネットワーク領域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-195">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="79778-196">次の例では、APAC 地域で3つの新しいネットワークサイト、ベトナム、インドネシア、シンガポールを作成します。</span><span class="sxs-lookup"><span data-stu-id="79778-196">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="79778-197">ネットワークサブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="79778-197">Define network subnets</span></span>

<span data-ttu-id="79778-198">ネットワークサブネットを定義してネットワークサイトに関連付けるには、CsTenantNetworkSubnet コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="79778-198">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="79778-199">各ネットワークサブネットは、1つのサイトにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="79778-199">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="79778-200">次の例では、3つのネットワークサブネットを定義し、それをベトナム、インドネシア、シンガポールという3つのネットワークサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="79778-200">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="79778-201">仮想ネットワークトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="79778-201">Define the virtual network topology</span></span> 

<span data-ttu-id="79778-202">まず、テナント管理者は、CsOnlinePSTNGateway コマンドレットを使用して、関連する SBC ごとに新しい SBC 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="79778-202">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="79778-203">テナント管理者は、CsOnlinePSTNGateway コマンドレットを使用して、PSTN ゲートウェイオブジェクトのネットワークサイトを指定することで、仮想ネットワークトポロジを定義します。</span><span class="sxs-lookup"><span data-stu-id="79778-203">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="79778-204">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="79778-204">Note the following:</span></span> 
   - <span data-ttu-id="79778-205">顧客が1つの SBC を使用している場合は、-ProxySBC パラメーターは必須 $null または SBC FQDN 値 (集中型 trunks シナリオを持つ集中型 SBC) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-205">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="79778-206">ローカルメディアの最適化をサポートするには、-MediaBypass ・・・・・バイのパラメーターが $true に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-206">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="79778-207">SBC に-BypassMode パラメーターが設定されていない場合、X ミリ秒のヘッダーは送信されません。</span><span class="sxs-lookup"><span data-stu-id="79778-207">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="79778-208">すべてのパラメーターは大文字と小文字を区別するため、セットアップ時に使用したのと同じケースを確実に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-208">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="79778-209">(たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は、別のサイトとして扱われます)。</span><span class="sxs-lookup"><span data-stu-id="79778-209">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="79778-210">次の例では、APAC 領域の2つの SBCs をネットワークサイトに追加します。これは、モードが常にバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="79778-210">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="79778-211">注: ローカルメディア最適化と位置情報に基づくルーティング (LBR) を同時に構成するときに中断のない操作を行うには、GatewaySiteLbrEnabled パラメーターを各下流の SBC の $true に設定して、下位の SBCs を LBR に対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-211">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="79778-212">(この設定はプロキシ SBC には必須ではありません)。</span><span class="sxs-lookup"><span data-stu-id="79778-212">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="79778-213">上記の情報に基づいて、次の表に示すように、直接ルーティングを行うと、SIP の招待に対しては3つの専用 SIP ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="79778-213">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="79778-214">BypassMode が定義されている場合に、招待と再招待の際に直接ルーティングで導入された X-MS ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="79778-214">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="79778-215">ヘッダー名</span><span class="sxs-lookup"><span data-stu-id="79778-215">Header name</span></span> | <span data-ttu-id="79778-216">Values</span><span class="sxs-lookup"><span data-stu-id="79778-216">Values</span></span> | <span data-ttu-id="79778-217">注釈</span><span class="sxs-lookup"><span data-stu-id="79778-217">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="79778-218">エックス--UserLocation</span><span class="sxs-lookup"><span data-stu-id="79778-218">X-MS-UserLocation</span></span> | <span data-ttu-id="79778-219">内部/外部</span><span class="sxs-lookup"><span data-stu-id="79778-219">internal/external</span></span> | <span data-ttu-id="79778-220">ユーザーが内部と外部のどちらであるかを示します</span><span class="sxs-lookup"><span data-stu-id="79778-220">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="79778-221">要求-URI 招待 sip: + 84439263000@VNsbc.contoso.com SIP/2.0</span><span class="sxs-lookup"><span data-stu-id="79778-221">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="79778-222">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="79778-222">SBC FQDN</span></span> | <span data-ttu-id="79778-223">SBC が直接ルーティングに直接接続されていない場合でも、通話の対象となる FQDN</span><span class="sxs-lookup"><span data-stu-id="79778-223">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="79778-224">MediaPath</span><span class="sxs-lookup"><span data-stu-id="79778-224">X-MS-MediaPath</span></span> | <span data-ttu-id="79778-225">例: proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-225">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="79778-226">ユーザーとターゲットの間のメディアパスに使用する SBCs の順序です。</span><span class="sxs-lookup"><span data-stu-id="79778-226">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="79778-227">最後の SBC は常に最終です</span><span class="sxs-lookup"><span data-stu-id="79778-227">The final SBC is always last</span></span> |
| <span data-ttu-id="79778-228">-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="79778-228">X-MS-UserSite</span></span> | <span data-ttu-id="79778-229">usersiteID</span><span class="sxs-lookup"><span data-stu-id="79778-229">usersiteID</span></span> | <span data-ttu-id="79778-230">テナント管理者によって定義された文字列</span><span class="sxs-lookup"><span data-stu-id="79778-230">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="79778-231">コールフロー</span><span class="sxs-lookup"><span data-stu-id="79778-231">Call flows</span></span> 

<span data-ttu-id="79778-232">次に、2つのモードのコールフローを示します。</span><span class="sxs-lookup"><span data-stu-id="79778-232">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="79778-233">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="79778-233">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="79778-234">ローカルユーザーのみ</span><span class="sxs-lookup"><span data-stu-id="79778-234">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="79778-235">常にバイパスモード</span><span class="sxs-lookup"><span data-stu-id="79778-235">Always Bypass mode</span></span>

<span data-ttu-id="79778-236">[常にバイパス] モードは、構成するのに最も簡単なオプションです。</span><span class="sxs-lookup"><span data-stu-id="79778-236">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="79778-237">テナント管理者は、すべてのユーザーに対して1つのサイトを構成することができます。すべてのサイトからすべての SBCs に到達可能である場合は、SBCs になります。</span><span class="sxs-lookup"><span data-stu-id="79778-237">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="79778-238">次のシナリオでは、この例では常にバイパスモードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79778-238">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="79778-239">発信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="79778-239">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="79778-240">着信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="79778-240">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="79778-241">発信通話とユーザーは外部です</span><span class="sxs-lookup"><span data-stu-id="79778-241">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="79778-242">着信通話とユーザーは外部</span><span class="sxs-lookup"><span data-stu-id="79778-242">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="79778-243">次の表は、例で使用される FQDN と IP アドレスを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-243">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="79778-244">FQDN</span><span class="sxs-lookup"><span data-stu-id="79778-244">FQDN</span></span> | <span data-ttu-id="79778-245">SBC 外部 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="79778-245">SBC external IP address</span></span> | <span data-ttu-id="79778-246">SBC 内部 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="79778-246">SBC internal IP Address</span></span> | <span data-ttu-id="79778-247">内部サブネット</span><span class="sxs-lookup"><span data-stu-id="79778-247">Internal subnet</span></span> | <span data-ttu-id="79778-248">場所</span><span class="sxs-lookup"><span data-stu-id="79778-248">Location</span></span> | <span data-ttu-id="79778-249">外部 NAT (信頼できる IP)</span><span class="sxs-lookup"><span data-stu-id="79778-249">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="79778-250">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-250">VNsbc.contoso.com</span></span> | <span data-ttu-id="79778-251">なし</span><span class="sxs-lookup"><span data-stu-id="79778-251">None</span></span> | <span data-ttu-id="79778-252">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="79778-252">192.168.1.5</span></span> | <span data-ttu-id="79778-253">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="79778-253">192.168.1.0/24</span></span> | <span data-ttu-id="79778-254">ベトナム</span><span class="sxs-lookup"><span data-stu-id="79778-254">Vietnam</span></span> | <span data-ttu-id="79778-255">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="79778-255">172.16.240.110</span></span> |
| <span data-ttu-id="79778-256">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-256">IDsbc.contoso.com</span></span> | <span data-ttu-id="79778-257">なし</span><span class="sxs-lookup"><span data-stu-id="79778-257">None</span></span> | <span data-ttu-id="79778-258">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="79778-258">192.168.2.5</span></span> | <span data-ttu-id="79778-259">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="79778-259">192.168.2.0/24</span></span> | <span data-ttu-id="79778-260">インドネシア</span><span class="sxs-lookup"><span data-stu-id="79778-260">Indonesia</span></span> | <span data-ttu-id="79778-261">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="79778-261">172.16.240.120</span></span> |
| <span data-ttu-id="79778-262">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-262">proxysbc.contoso.com</span></span> | <span data-ttu-id="79778-263">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="79778-263">172.16.240.133</span></span> | <span data-ttu-id="79778-264">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="79778-264">192.168.3.5</span></span> | <span data-ttu-id="79778-265">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="79778-265">192.168.3.0/24</span></span> | <span data-ttu-id="79778-266">シンガポール</span><span class="sxs-lookup"><span data-stu-id="79778-266">Singapore</span></span> | <span data-ttu-id="79778-267">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="79778-267">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="79778-268">発信通話とユーザーは、常にバイパスの SBC と同じ場所にあります</span><span class="sxs-lookup"><span data-stu-id="79778-268">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="79778-269">モード</span><span class="sxs-lookup"><span data-stu-id="79778-269">Mode</span></span> |    <span data-ttu-id="79778-270">ユーザー</span><span class="sxs-lookup"><span data-stu-id="79778-270">User</span></span> |  <span data-ttu-id="79778-271">場所</span><span class="sxs-lookup"><span data-stu-id="79778-271">Location</span></span> |  <span data-ttu-id="79778-272">通話の方向</span><span class="sxs-lookup"><span data-stu-id="79778-272">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="79778-273">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="79778-273">AlwaysBypass</span></span> |    <span data-ttu-id="79778-274">内部</span><span class="sxs-lookup"><span data-stu-id="79778-274">Internal</span></span> |  <span data-ttu-id="79778-275">SBC と同じサイト</span><span class="sxs-lookup"><span data-stu-id="79778-275">The same site as SBC</span></span> |  <span data-ttu-id="79778-276">発信</span><span class="sxs-lookup"><span data-stu-id="79778-276">Outbound</span></span> |

<span data-ttu-id="79778-277">次の表は、エンドユーザーの構成とアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-277">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="79778-278">ユーザーの物理的な場所</span><span class="sxs-lookup"><span data-stu-id="79778-278">User physical location</span></span>| <span data-ttu-id="79778-279">ユーザーが電話番号を発信または受信した場合</span><span class="sxs-lookup"><span data-stu-id="79778-279">User makes or receives a call to/from number</span></span> | <span data-ttu-id="79778-280">ユーザの電話番号</span><span class="sxs-lookup"><span data-stu-id="79778-280">User phone number</span></span>  | <span data-ttu-id="79778-281">オンラインボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="79778-281">Online Voice Routing Policy</span></span> | <span data-ttu-id="79778-282">SBC 用に構成されたモード</span><span class="sxs-lookup"><span data-stu-id="79778-282">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="79778-283">ベトナム</span><span class="sxs-lookup"><span data-stu-id="79778-283">Vietnam</span></span> | <span data-ttu-id="79778-284">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="79778-284">+84 4 3926 3000</span></span> | <span data-ttu-id="79778-285">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="79778-285">+84 4 5555 5555</span></span>   | <span data-ttu-id="79778-286">優先度 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-286">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="79778-287">優先度 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-287">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="79778-288">VNsbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="79778-288">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="79778-289">proxysbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="79778-289">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="79778-290">次の図は、常にバイパスモードを使用した発信通話の SIP のはしごと、SBC と同じ場所にいるユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-290">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="79778-291">![発信通話を示す図](media/direct-routing-media-op-10.png "発信通話")</span><span class="sxs-lookup"><span data-stu-id="79778-291">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="79778-292">次の表は、直接ルーティングによって送信された X-MS ヘッダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-292">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="79778-293">パラメーター</span><span class="sxs-lookup"><span data-stu-id="79778-293">Parameter</span></span> | <span data-ttu-id="79778-294">説明</span><span class="sxs-lookup"><span data-stu-id="79778-294">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="79778-295">招待 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-295">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="79778-296">オンラインボイスルーティングポリシーで定義された SBC のターゲット FQDN は、要求 URI で送信されます。</span><span class="sxs-lookup"><span data-stu-id="79778-296">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="79778-297">X--UserLocation: internal</span><span class="sxs-lookup"><span data-stu-id="79778-297">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="79778-298">このフィールドは、ユーザーが企業ネットワーク内に配置されていることを示しています</span><span class="sxs-lookup"><span data-stu-id="79778-298">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="79778-299">MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-299">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="79778-300">クライアントがターゲット SBC にどの SBC を通過する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="79778-300">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="79778-301">この例では、常にバイパスしているため、クライアントはヘッダーで唯一の名前として送信されるターゲット名です。</span><span class="sxs-lookup"><span data-stu-id="79778-301">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="79778-302">----UserSite: ベトナム</span><span class="sxs-lookup"><span data-stu-id="79778-302">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="79778-303">ユーザーが配置されているサイトで示されているフィールド。</span><span class="sxs-lookup"><span data-stu-id="79778-303">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="79778-304">着信通話とユーザーは、常にバイパスの SBC と同じ場所にあります</span><span class="sxs-lookup"><span data-stu-id="79778-304">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="79778-305">モード</span><span class="sxs-lookup"><span data-stu-id="79778-305">Mode</span></span> |    <span data-ttu-id="79778-306">ユーザー</span><span class="sxs-lookup"><span data-stu-id="79778-306">User</span></span> |  <span data-ttu-id="79778-307">場所</span><span class="sxs-lookup"><span data-stu-id="79778-307">Location</span></span> |  <span data-ttu-id="79778-308">通話の方向</span><span class="sxs-lookup"><span data-stu-id="79778-308">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="79778-309">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="79778-309">AlwaysBypass</span></span> |    <span data-ttu-id="79778-310">内部</span><span class="sxs-lookup"><span data-stu-id="79778-310">Internal</span></span> | <span data-ttu-id="79778-311">SBC と同じサイト</span><span class="sxs-lookup"><span data-stu-id="79778-311">The same site as SBC</span></span> | <span data-ttu-id="79778-312">トラフィック</span><span class="sxs-lookup"><span data-stu-id="79778-312">Inbound</span></span> |


<span data-ttu-id="79778-313">着信通話では、ユーザーの場所が不明であり、SBC はユーザーがどこにいるかを推測する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79778-313">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="79778-314">推測が正しくない場合は、再招待が必要になります。</span><span class="sxs-lookup"><span data-stu-id="79778-314">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="79778-315">この例では、ユーザーが内部であることを前提としています。メディアは直接流れることができ、それ以上の操作は必要ありません (再招待)。</span><span class="sxs-lookup"><span data-stu-id="79778-315">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="79778-316">ダイレクトルーティングサービスに接続された SBC は、レコードルーティングと連絡先フィールドを提供して、送信元の SBC の位置情報を報告します。</span><span class="sxs-lookup"><span data-stu-id="79778-316">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="79778-317">これらのフィールドに基づいて、メディアパスはダイレクトルーティングによって計算されます。</span><span class="sxs-lookup"><span data-stu-id="79778-317">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="79778-318">注: ユーザーが複数のエンドポイントを持つことができる場合、183のサポートはできません。</span><span class="sxs-lookup"><span data-stu-id="79778-318">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="79778-319">この場合、直接ルーティングでは常に180呼び出しが使用されます。</span><span class="sxs-lookup"><span data-stu-id="79778-319">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="79778-320">次の図は、Always バイパスモードの着信呼び出しでの SIP のはしごを示しています。ユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="79778-320">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="79778-322">発信通話とユーザーは外部であり、常にバイパスする</span><span class="sxs-lookup"><span data-stu-id="79778-322">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="79778-323">モード</span><span class="sxs-lookup"><span data-stu-id="79778-323">Mode</span></span> |    <span data-ttu-id="79778-324">ユーザー</span><span class="sxs-lookup"><span data-stu-id="79778-324">User</span></span> |  <span data-ttu-id="79778-325">サイト</span><span class="sxs-lookup"><span data-stu-id="79778-325">Site</span></span> |  <span data-ttu-id="79778-326">通話の方向</span><span class="sxs-lookup"><span data-stu-id="79778-326">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="79778-327">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="79778-327">AlwaysBypass</span></span> |  <span data-ttu-id="79778-328">外部</span><span class="sxs-lookup"><span data-stu-id="79778-328">External</span></span> |  <span data-ttu-id="79778-329">該当なし</span><span class="sxs-lookup"><span data-stu-id="79778-329">N/A</span></span> | <span data-ttu-id="79778-330">発信</span><span class="sxs-lookup"><span data-stu-id="79778-330">Outbound</span></span> |


<span data-ttu-id="79778-331">次の図は、常にバイパスモードの発信通話に関する SIP のはしごを示しています。ユーザーは外部であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-331">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-12.png)

<span data-ttu-id="79778-333">次の表は、ダイレクトルーティングサービスによって送信された X ミリ秒のヘッダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-333">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="79778-334">パラメーター</span><span class="sxs-lookup"><span data-stu-id="79778-334">Parameter</span></span> |   <span data-ttu-id="79778-335">説明</span><span class="sxs-lookup"><span data-stu-id="79778-335">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="79778-336">招待 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-336">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="79778-337">オンラインボイスルーティングポリシーで定義された SBC のターゲット FQDN は、要求 URI で送信されます。</span><span class="sxs-lookup"><span data-stu-id="79778-337">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="79778-338">X--UserLocation: external</span><span class="sxs-lookup"><span data-stu-id="79778-338">X-MS-UserLocation: external</span></span> | <span data-ttu-id="79778-339">このフィールドは、ユーザーが企業ネットワークの外部にあることを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-339">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="79778-340">MediaPath: proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="79778-341">クライアントがターゲット SBC にどの SBC を通過する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="79778-341">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="79778-342">この例では、常にバイパスしており、クライアントは外部です。</span><span class="sxs-lookup"><span data-stu-id="79778-342">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="79778-343">着信通話とユーザーは外部であり、常にバイパスする</span><span class="sxs-lookup"><span data-stu-id="79778-343">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="79778-344">モード</span><span class="sxs-lookup"><span data-stu-id="79778-344">Mode</span></span> | <span data-ttu-id="79778-345">ユーザー</span><span class="sxs-lookup"><span data-stu-id="79778-345">User</span></span> | <span data-ttu-id="79778-346">サイト</span><span class="sxs-lookup"><span data-stu-id="79778-346">Site</span></span> |  <span data-ttu-id="79778-347">通話の方向</span><span class="sxs-lookup"><span data-stu-id="79778-347">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="79778-348">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="79778-348">AlwaysBypass</span></span> |  <span data-ttu-id="79778-349">外部</span><span class="sxs-lookup"><span data-stu-id="79778-349">External</span></span> |  <span data-ttu-id="79778-350">該当なし</span><span class="sxs-lookup"><span data-stu-id="79778-350">N/A</span></span> |   <span data-ttu-id="79778-351">トラフィック</span><span class="sxs-lookup"><span data-stu-id="79778-351">Inbound</span></span> |

<span data-ttu-id="79778-352">着信通話の場合、直接ルーティングに接続された SBC は、ユーザーの場所が外部である場合は、再招待を送信する必要があります (既定では、ローカルメディア候補は常に提供されています)。</span><span class="sxs-lookup"><span data-stu-id="79778-352">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="79778-353">X-MediaPath は、指定されたレコードルートと SBC ユーザーに基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="79778-353">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="79778-354">次の図は、常にバイパスモードの着信呼び出しに対する SIP のはしごを示しています。また、ユーザーは外部であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-354">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="79778-356">ローカルユーザーモードに対してのみ</span><span class="sxs-lookup"><span data-stu-id="79778-356">Only for local users mode</span></span>

<span data-ttu-id="79778-357">ターゲット SBC のローカルメディア候補は、ユーザーが SBC と同じ場所にいる場合にのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="79778-357">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="79778-358">それ以外の場合、メディアはプロキシ SBC の内部または外部 IP 経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="79778-358">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="79778-359">次のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="79778-359">The following scenarios are described:</span></span>

- [<span data-ttu-id="79778-360">発信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="79778-360">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="79778-361">着信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="79778-361">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="79778-362">ユーザーは SBC と同じ場所にありませんが、企業ネットワーク内にある</span><span class="sxs-lookup"><span data-stu-id="79778-362">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="79778-363">着信通話とユーザーは内部にありますが、SBC と同じ場所にありません。</span><span class="sxs-lookup"><span data-stu-id="79778-363">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="79778-364">次の表は、エンドユーザーによる構成とアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-364">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="79778-365">ユーザーの物理的な場所</span><span class="sxs-lookup"><span data-stu-id="79778-365">User physical location</span></span> |  <span data-ttu-id="79778-366">ユーザーが電話番号を発信または受信した場合</span><span class="sxs-lookup"><span data-stu-id="79778-366">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="79778-367">ユーザの電話番号</span><span class="sxs-lookup"><span data-stu-id="79778-367">User phone number</span></span> | <span data-ttu-id="79778-368">オンラインボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="79778-368">Online Voice Routing Policy</span></span> |   <span data-ttu-id="79778-369">SBC 用に構成されたモード</span><span class="sxs-lookup"><span data-stu-id="79778-369">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="79778-370">ベトナム</span><span class="sxs-lookup"><span data-stu-id="79778-370">Vietnam</span></span> | <span data-ttu-id="79778-371">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="79778-371">+84 4 3926  3000</span></span> |  <span data-ttu-id="79778-372">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="79778-372">+84 4 5555 5555</span></span> | <span data-ttu-id="79778-373">優先度 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-373">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="79778-374">優先度 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79778-374">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="79778-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="79778-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="79778-376">発信通話とユーザーは、ローカルユーザーに対してのみ、SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="79778-376">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="79778-377">モード</span><span class="sxs-lookup"><span data-stu-id="79778-377">Mode</span></span> | <span data-ttu-id="79778-378">ユーザー</span><span class="sxs-lookup"><span data-stu-id="79778-378">User</span></span> | <span data-ttu-id="79778-379">サイト</span><span class="sxs-lookup"><span data-stu-id="79778-379">Site</span></span> | <span data-ttu-id="79778-380">通話の方向</span><span class="sxs-lookup"><span data-stu-id="79778-380">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="79778-381">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="79778-381">OnlyForLocalUsers</span></span> |   <span data-ttu-id="79778-382">内部</span><span class="sxs-lookup"><span data-stu-id="79778-382">Internal</span></span> |<span data-ttu-id="79778-383">SBC と同じ</span><span class="sxs-lookup"><span data-stu-id="79778-383">Same as SBC</span></span>   | <span data-ttu-id="79778-384">発信</span><span class="sxs-lookup"><span data-stu-id="79778-384">Outbound</span></span> |

<span data-ttu-id="79778-385">次の図は、OnlyForLocalUsers モードを使った発信通話と、ユーザーが SBC と同じ場所にいることを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-385">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="79778-386">これは、[ユーザーが SBC と同じ場所にいるとき](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)の、[送信中の通話と同じフローを示します。</span><span class="sxs-lookup"><span data-stu-id="79778-386">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="79778-388">着信通話とユーザーは、ローカルユーザーに対してのみ、SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="79778-388">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="79778-389">モード</span><span class="sxs-lookup"><span data-stu-id="79778-389">Mode</span></span> | <span data-ttu-id="79778-390">ユーザー</span><span class="sxs-lookup"><span data-stu-id="79778-390">User</span></span> | <span data-ttu-id="79778-391">サイト</span><span class="sxs-lookup"><span data-stu-id="79778-391">Site</span></span> | <span data-ttu-id="79778-392">通話の方向</span><span class="sxs-lookup"><span data-stu-id="79778-392">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="79778-393">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="79778-393">OnlyForLocalUsers</span></span> |   <span data-ttu-id="79778-394">内部</span><span class="sxs-lookup"><span data-stu-id="79778-394">Internal</span></span> | <span data-ttu-id="79778-395">SBC と同じ</span><span class="sxs-lookup"><span data-stu-id="79778-395">Same as SBC</span></span> | <span data-ttu-id="79778-396">トラフィック</span><span class="sxs-lookup"><span data-stu-id="79778-396">Inbound</span></span> |

<span data-ttu-id="79778-397">次の図は、OnlyForLocalUsers モードを使った着信通話と、ユーザーが SBC と同じ場所にいることを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-397">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="79778-398">これは、[ユーザーが SBC と同じ場所にいるときに、着信通話](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)に表示されるフローと同じです。</span><span class="sxs-lookup"><span data-stu-id="79778-398">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="79778-400">ユーザーは SBC と同じ場所にありませんが、社内ネットワーク内にあるのはローカルユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="79778-400">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="79778-401">モード</span><span class="sxs-lookup"><span data-stu-id="79778-401">Mode</span></span> | <span data-ttu-id="79778-402">ユーザー</span><span class="sxs-lookup"><span data-stu-id="79778-402">User</span></span> | <span data-ttu-id="79778-403">サイト</span><span class="sxs-lookup"><span data-stu-id="79778-403">Site</span></span> |<span data-ttu-id="79778-404">通話の方向</span><span class="sxs-lookup"><span data-stu-id="79778-404">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="79778-405">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="79778-405">OnlyForLocalUsers</span></span>  | <span data-ttu-id="79778-406">内部</span><span class="sxs-lookup"><span data-stu-id="79778-406">Internal</span></span> |   <span data-ttu-id="79778-407">SBC と異なる</span><span class="sxs-lookup"><span data-stu-id="79778-407">Different from SBC</span></span> | <span data-ttu-id="79778-408">発信</span><span class="sxs-lookup"><span data-stu-id="79778-408">Outbound</span></span> |

<span data-ttu-id="79778-409">直接ルーティングでは、SBC で構成されたユーザーとモードの報告された場所に基づいて、X-MediaPath が計算されます。</span><span class="sxs-lookup"><span data-stu-id="79778-409">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="79778-410">次の図は、OnlyForLocalUsers モードを使った発信通話と、SBC と同じ場所にない内部ユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-410">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="79778-412">着信通話とユーザーは内部ですが、ローカルユーザーのみを含む SBC と同じ場所にありません。</span><span class="sxs-lookup"><span data-stu-id="79778-412">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="79778-413">モード</span><span class="sxs-lookup"><span data-stu-id="79778-413">Mode</span></span> |    <span data-ttu-id="79778-414">ユーザー</span><span class="sxs-lookup"><span data-stu-id="79778-414">User</span></span> |  <span data-ttu-id="79778-415">サイト</span><span class="sxs-lookup"><span data-stu-id="79778-415">Site</span></span> |  <span data-ttu-id="79778-416">通話の方向</span><span class="sxs-lookup"><span data-stu-id="79778-416">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="79778-417">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="79778-417">OnlyForLocalUsers</span></span> | <span data-ttu-id="79778-418">内部</span><span class="sxs-lookup"><span data-stu-id="79778-418">Internal</span></span> |    <span data-ttu-id="79778-419">SBC と異なる</span><span class="sxs-lookup"><span data-stu-id="79778-419">Different from SBC</span></span> |    <span data-ttu-id="79778-420">トラフィック</span><span class="sxs-lookup"><span data-stu-id="79778-420">Inbound</span></span> |

<span data-ttu-id="79778-421">次の図は、OnlyForLocalUsers モードの着信呼び出しと、SBC と同じ場所にない内部ユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="79778-421">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-17.png)









