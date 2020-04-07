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
ms.openlocfilehash: 3097f97a856dc4e947281847c65669c23c73a408
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2020
ms.locfileid: "43158107"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="03e3f-103">直接ルーティング用のローカルメディア最適化を構成する</span><span class="sxs-lookup"><span data-stu-id="03e3f-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="03e3f-104">ローカルメディア最適化の構成は、場所に基づくルーティングや動的な緊急通話など、他のクラウド音声機能に共通するネットワーク設定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="03e3f-105">ネットワーク領域、ネットワークサイト、ネットワークサブネット、および信頼された IP アドレスの詳細については、「[クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03e3f-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="03e3f-106">ローカルメディア最適化を構成する前に、「[直接ルーティング用のローカルメディアの最適化](direct-routing-media-optimization.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="03e3f-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="03e3f-107">ローカルメディア最適化を構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="03e3f-108">Teams 管理センターまたは PowerShell を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="03e3f-109">詳細については、「[ネットワークトポロジを管理する](manage-your-network-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03e3f-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="03e3f-110">ユーザーと SBC サイトを構成します (この記事で説明します)。</span><span class="sxs-lookup"><span data-stu-id="03e3f-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="03e3f-111">(SBC ベンダー仕様に従って) ローカルメディア最適化用に SBCs を構成します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="03e3f-112">次の図は、この記事の例で使用されているネットワークセットアップを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="03e3f-113">![例のネットワークセットアップを示す図](media/direct-routing-media-op-9.png "ネットワークセットアップ例")</span><span class="sxs-lookup"><span data-stu-id="03e3f-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="03e3f-114">ユーザーと SBC サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="03e3f-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="03e3f-115">ユーザーと SBC サイトを構成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="03e3f-116">[外部の信頼できる IP アドレスを管理](#manage-external-trusted-ip-addresses)する。</span><span class="sxs-lookup"><span data-stu-id="03e3f-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="03e3f-117">ネットワークの領域、ネットワークサイト、ネットワークサブネットを構成して、[ネットワークトポロジを定義](#define-the-network-topology)します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="03e3f-118">関連するモードとプロキシの SBC 値を使って、サイトに SBC (s) を割り当てることで[、仮想ネットワークトポロジを定義](#define-the-virtual-network-topology)します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="03e3f-119">SBC ベンダー仕様に従って、ローカルメディア最適化用に SBC を構成する</span><span class="sxs-lookup"><span data-stu-id="03e3f-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="03e3f-120">この記事では、Microsoft コンポーネントの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="03e3f-121">SBC 構成の詳細については、SBC ベンダーの documenation を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03e3f-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="03e3f-122">ローカルメディア最適化は、次の SBC ベンダーによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="03e3f-123">仕入先</span><span class="sxs-lookup"><span data-stu-id="03e3f-123">Vendor</span></span> | <span data-ttu-id="03e3f-124">Product</span><span class="sxs-lookup"><span data-stu-id="03e3f-124">Product</span></span> |    <span data-ttu-id="03e3f-125">ソフトウェアのバージョン</span><span class="sxs-lookup"><span data-stu-id="03e3f-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="03e3f-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="03e3f-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="03e3f-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="03e3f-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="03e3f-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="03e3f-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="03e3f-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="03e3f-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="03e3f-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="03e3f-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="03e3f-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="03e3f-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="03e3f-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="03e3f-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="03e3f-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="03e3f-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="03e3f-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="03e3f-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="03e3f-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="03e3f-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="03e3f-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="03e3f-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="03e3f-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="03e3f-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="03e3f-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="03e3f-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="03e3f-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="03e3f-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="03e3f-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="03e3f-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="03e3f-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="03e3f-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="03e3f-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="03e3f-142">7.20A.256</span></span> |
| [<span data-ttu-id="03e3f-143">リボンの SBC コア</span><span class="sxs-lookup"><span data-stu-id="03e3f-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="03e3f-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="03e3f-144">SBC 5110</span></span>         | <span data-ttu-id="03e3f-145">8.2</span><span class="sxs-lookup"><span data-stu-id="03e3f-145">8.2</span></span>  |
|            |  <span data-ttu-id="03e3f-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="03e3f-146">SBC 5210</span></span>         | <span data-ttu-id="03e3f-147">8.2</span><span class="sxs-lookup"><span data-stu-id="03e3f-147">8.2</span></span>  |
|            |  <span data-ttu-id="03e3f-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="03e3f-148">SBC 5400</span></span>         | <span data-ttu-id="03e3f-149">8.2</span><span class="sxs-lookup"><span data-stu-id="03e3f-149">8.2</span></span>  |
|            |  <span data-ttu-id="03e3f-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="03e3f-150">SBC 7000</span></span>         | <span data-ttu-id="03e3f-151">8.2</span><span class="sxs-lookup"><span data-stu-id="03e3f-151">8.2</span></span>  |
|            |  <span data-ttu-id="03e3f-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="03e3f-152">SBC SWe</span></span>          | <span data-ttu-id="03e3f-153">8.2</span><span class="sxs-lookup"><span data-stu-id="03e3f-153">8.2</span></span>  |
| [<span data-ttu-id="03e3f-154">リボンの SBC エッジ</span><span class="sxs-lookup"><span data-stu-id="03e3f-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  <span data-ttu-id="03e3f-155">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="03e3f-155">SBC 1000</span></span>         | <span data-ttu-id="03e3f-156">8.1.1、ビルド527</span><span class="sxs-lookup"><span data-stu-id="03e3f-156">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="03e3f-157">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="03e3f-157">SBC 2000</span></span>         | <span data-ttu-id="03e3f-158">8.1.1、ビルド527</span><span class="sxs-lookup"><span data-stu-id="03e3f-158">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="03e3f-159">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="03e3f-159">SBC SWe Lite</span></span>     | <span data-ttu-id="03e3f-160">8.1.0、ビルド222</span><span class="sxs-lookup"><span data-stu-id="03e3f-160">8.1.0, build 222</span></span> |
| [<span data-ttu-id="03e3f-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="03e3f-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="03e3f-162">anynode</span><span class="sxs-lookup"><span data-stu-id="03e3f-162">anynode</span></span>          | <span data-ttu-id="03e3f-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="03e3f-163">4.0.1+</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="03e3f-164">外部の信頼できる IP アドレスを管理する</span><span class="sxs-lookup"><span data-stu-id="03e3f-164">Manage external trusted IP addresses</span></span>

<span data-ttu-id="03e3f-165">外部の信頼できる Ip は、エンタープライズネットワークのインターネット外部 Ip です。</span><span class="sxs-lookup"><span data-stu-id="03e3f-165">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="03e3f-166">これらの IP アドレスは、microsoft Teams クライアントが Microsoft 365 に接続したときに使用される IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="03e3f-166">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="03e3f-167">ユーザーがローカルメディア最適化を使用しているサイトごとに、これらの外部 Ip を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-167">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="03e3f-168">各サイトのパブリック IP アドレスを追加するには、CsTenantTrustedIPAddress コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-168">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="03e3f-169">1つのテナントに対して無制限の数の信頼できる IP アドレスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-169">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="03e3f-170">Microsoft 365 によって表示される外部 Ip が IPv4 アドレスと IPv6 アドレスの両方である場合は、両方の種類の IP アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-170">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="03e3f-171">IPv4 の場合は、マスク32を使用します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-171">For IPv4, use mask 32.</span></span> <span data-ttu-id="03e3f-172">IPv6 の場合は、マスク128を使用します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-172">For IPv6, use mask 128.</span></span> <span data-ttu-id="03e3f-173">コマンドレットで異なる MaskBits を指定することで、個々の外部 IP アドレスと外部 IP サブネットの両方を追加できます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-173">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="03e3f-174">信頼された IP アドレスを追加する例。</span><span class="sxs-lookup"><span data-stu-id="03e3f-174">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="03e3f-175">ネットワークトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="03e3f-175">Define the network topology</span></span>

<span data-ttu-id="03e3f-176">このセクションでは、ネットワークトポロジのネットワーク領域、ネットワークサイト、ネットワークサブネットを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-176">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="03e3f-177">すべてのパラメーターは大文字と小文字を区別するため、セットアップ時に使用したのと同じケースを確実に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-177">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="03e3f-178">(たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は、別のサイトとして扱われます)。</span><span class="sxs-lookup"><span data-stu-id="03e3f-178">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="03e3f-179">ネットワーク領域を定義する</span><span class="sxs-lookup"><span data-stu-id="03e3f-179">Define network regions</span></span>

<span data-ttu-id="03e3f-180">ネットワーク領域を定義するには、CsTenantNetworkRegion コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-180">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="03e3f-181">RegionID パラメーターは、地域の地理を表す論理名であり、依存関係または制限がありません。</span><span class="sxs-lookup"><span data-stu-id="03e3f-181">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="03e3f-182">CentralSite <site ID>パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="03e3f-182">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="03e3f-183">次の例では、APAC という名前のネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-183">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="03e3f-184">ネットワークサイトを定義する</span><span class="sxs-lookup"><span data-stu-id="03e3f-184">Define network sites</span></span>

<span data-ttu-id="03e3f-185">ネットワークサイトを定義するには、CsTenantNetworkSite コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-185">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="03e3f-186">各ネットワークサイトは、ネットワーク領域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-186">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="03e3f-187">次の例では、APAC 地域で3つの新しいネットワークサイト、ベトナム、インドネシア、シンガポールを作成します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-187">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="03e3f-188">ネットワークサブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="03e3f-188">Define network subnets</span></span>

<span data-ttu-id="03e3f-189">ネットワークサブネットを定義してネットワークサイトに関連付けるには、CsTenantNetworkSubnet コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-189">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="03e3f-190">各ネットワークサブネットは、1つのサイトにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-190">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="03e3f-191">次の例では、3つのネットワークサブネットを定義し、それをベトナム、インドネシア、シンガポールという3つのネットワークサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-191">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="03e3f-192">仮想ネットワークトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="03e3f-192">Define the virtual network topology</span></span> 

<span data-ttu-id="03e3f-193">まず、テナント管理者は、CsOnlinePSTNGateway コマンドレットを使用して、関連する SBC ごとに新しい SBC 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-193">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="03e3f-194">テナント管理者は、CsOnlinePSTNGateway コマンドレットを使用して、PSTN ゲートウェイオブジェクトのネットワークサイトを指定することで、仮想ネットワークトポロジを定義します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-194">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="03e3f-195">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="03e3f-195">Note the following:</span></span> 
   - <span data-ttu-id="03e3f-196">顧客が1つの SBC を使用している場合は、-ProxySBC パラメーターは必須 $null または SBC FQDN 値 (集中型 trunks シナリオを持つ集中型 SBC) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-196">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="03e3f-197">ローカルメディアの最適化をサポートするには、-MediaBypass ・・・・・バイのパラメーターが $true に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-197">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="03e3f-198">SBC に-BypassMode パラメーターが設定されていない場合、X ミリ秒のヘッダーは送信されません。</span><span class="sxs-lookup"><span data-stu-id="03e3f-198">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="03e3f-199">すべてのパラメーターは大文字と小文字を区別するため、セットアップ時に使用したのと同じケースを確実に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-199">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="03e3f-200">(たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は、別のサイトとして扱われます)。</span><span class="sxs-lookup"><span data-stu-id="03e3f-200">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="03e3f-201">次の例では、APAC 領域の2つの SBCs をネットワークサイトに追加します。これは、モードが常にバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-201">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="03e3f-202">注: ローカルメディア最適化と位置情報に基づくルーティング (LBR) を同時に構成するときに中断のない操作を行うには、GatewaySiteLbrEnabled パラメーターを各下流の SBC の $true に設定して、下位の SBCs を LBR に対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-202">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="03e3f-203">(この設定はプロキシ SBC には必須ではありません)。</span><span class="sxs-lookup"><span data-stu-id="03e3f-203">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="03e3f-204">上記の情報に基づいて、次の表に示すように、直接ルーティングを行うと、SIP の招待に対しては3つの専用 SIP ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-204">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="03e3f-205">BypassMode が定義されている場合に、招待と再招待の際に直接ルーティングで導入された X-MS ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="03e3f-205">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="03e3f-206">ヘッダー名</span><span class="sxs-lookup"><span data-stu-id="03e3f-206">Header name</span></span> | <span data-ttu-id="03e3f-207">Values</span><span class="sxs-lookup"><span data-stu-id="03e3f-207">Values</span></span> | <span data-ttu-id="03e3f-208">コメント</span><span class="sxs-lookup"><span data-stu-id="03e3f-208">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="03e3f-209">エックス--UserLocation</span><span class="sxs-lookup"><span data-stu-id="03e3f-209">X-MS-UserLocation</span></span> | <span data-ttu-id="03e3f-210">内部/外部</span><span class="sxs-lookup"><span data-stu-id="03e3f-210">internal/external</span></span> | <span data-ttu-id="03e3f-211">ユーザーが内部と外部のどちらであるかを示します</span><span class="sxs-lookup"><span data-stu-id="03e3f-211">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="03e3f-212">要求-URI 招待 sip: + 84439263000@VNsbc.contoso.com SIP/2.0</span><span class="sxs-lookup"><span data-stu-id="03e3f-212">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="03e3f-213">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="03e3f-213">SBC FQDN</span></span> | <span data-ttu-id="03e3f-214">SBC が直接ルーティングに直接接続されていない場合でも、通話の対象となる FQDN</span><span class="sxs-lookup"><span data-stu-id="03e3f-214">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="03e3f-215">MediaPath</span><span class="sxs-lookup"><span data-stu-id="03e3f-215">X-MS-MediaPath</span></span> | <span data-ttu-id="03e3f-216">例: proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-216">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="03e3f-217">ユーザーとターゲットの間のメディアパスに使用する SBCs の順序です。</span><span class="sxs-lookup"><span data-stu-id="03e3f-217">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="03e3f-218">最後の SBC は常に最終です</span><span class="sxs-lookup"><span data-stu-id="03e3f-218">The final SBC is always last</span></span> |
| <span data-ttu-id="03e3f-219">-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="03e3f-219">X-MS-UserSite</span></span> | <span data-ttu-id="03e3f-220">usersiteID</span><span class="sxs-lookup"><span data-stu-id="03e3f-220">usersiteID</span></span> | <span data-ttu-id="03e3f-221">テナント管理者によって定義された文字列</span><span class="sxs-lookup"><span data-stu-id="03e3f-221">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="03e3f-222">コールフロー</span><span class="sxs-lookup"><span data-stu-id="03e3f-222">Call flows</span></span> 

<span data-ttu-id="03e3f-223">次に、2つのモードのコールフローを示します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-223">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="03e3f-224">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="03e3f-224">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="03e3f-225">ローカルユーザーのみ</span><span class="sxs-lookup"><span data-stu-id="03e3f-225">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="03e3f-226">常にバイパスモード</span><span class="sxs-lookup"><span data-stu-id="03e3f-226">Always Bypass mode</span></span>

<span data-ttu-id="03e3f-227">[常にバイパス] モードは、構成するのに最も簡単なオプションです。</span><span class="sxs-lookup"><span data-stu-id="03e3f-227">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="03e3f-228">テナント管理者は、すべてのユーザーに対して1つのサイトを構成することができます。すべてのサイトからすべての SBCs に到達可能である場合は、SBCs になります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-228">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="03e3f-229">次のシナリオでは、この例では常にバイパスモードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-229">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="03e3f-230">発信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-230">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="03e3f-231">着信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-231">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="03e3f-232">発信通話とユーザーは外部です</span><span class="sxs-lookup"><span data-stu-id="03e3f-232">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="03e3f-233">着信通話とユーザーは外部</span><span class="sxs-lookup"><span data-stu-id="03e3f-233">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="03e3f-234">次の表は、例で使用される FQDN と IP アドレスを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-234">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="03e3f-235">FQDN</span><span class="sxs-lookup"><span data-stu-id="03e3f-235">FQDN</span></span> | <span data-ttu-id="03e3f-236">SBC 外部 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="03e3f-236">SBC external IP address</span></span> | <span data-ttu-id="03e3f-237">SBC 内部 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="03e3f-237">SBC internal IP Address</span></span> | <span data-ttu-id="03e3f-238">内部サブネット</span><span class="sxs-lookup"><span data-stu-id="03e3f-238">Internal subnet</span></span> | <span data-ttu-id="03e3f-239">場所</span><span class="sxs-lookup"><span data-stu-id="03e3f-239">Location</span></span> | <span data-ttu-id="03e3f-240">外部 NAT (信頼できる IP)</span><span class="sxs-lookup"><span data-stu-id="03e3f-240">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="03e3f-241">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-241">VNsbc.contoso.com</span></span> | <span data-ttu-id="03e3f-242">なし</span><span class="sxs-lookup"><span data-stu-id="03e3f-242">None</span></span> | <span data-ttu-id="03e3f-243">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="03e3f-243">192.168.1.5</span></span> | <span data-ttu-id="03e3f-244">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="03e3f-244">192.168.1.0/24</span></span> | <span data-ttu-id="03e3f-245">ベトナム</span><span class="sxs-lookup"><span data-stu-id="03e3f-245">Vietnam</span></span> | <span data-ttu-id="03e3f-246">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="03e3f-246">172.16.240.110</span></span> |
| <span data-ttu-id="03e3f-247">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-247">IDsbc.contoso.com</span></span> | <span data-ttu-id="03e3f-248">なし</span><span class="sxs-lookup"><span data-stu-id="03e3f-248">None</span></span> | <span data-ttu-id="03e3f-249">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="03e3f-249">192.168.2.5</span></span> | <span data-ttu-id="03e3f-250">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="03e3f-250">192.168.2.0/24</span></span> | <span data-ttu-id="03e3f-251">インドネシア</span><span class="sxs-lookup"><span data-stu-id="03e3f-251">Indonesia</span></span> | <span data-ttu-id="03e3f-252">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="03e3f-252">172.16.240.120</span></span> |
| <span data-ttu-id="03e3f-253">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-253">proxysbc.contoso.com</span></span> | <span data-ttu-id="03e3f-254">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="03e3f-254">172.16.240.133</span></span> | <span data-ttu-id="03e3f-255">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="03e3f-255">192.168.3.5</span></span> | <span data-ttu-id="03e3f-256">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="03e3f-256">192.168.3.0/24</span></span> | <span data-ttu-id="03e3f-257">シンガポール</span><span class="sxs-lookup"><span data-stu-id="03e3f-257">Singapore</span></span> | <span data-ttu-id="03e3f-258">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="03e3f-258">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="03e3f-259">発信通話とユーザーは、常にバイパスの SBC と同じ場所にあります</span><span class="sxs-lookup"><span data-stu-id="03e3f-259">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="03e3f-260">モード</span><span class="sxs-lookup"><span data-stu-id="03e3f-260">Mode</span></span> |    <span data-ttu-id="03e3f-261">ユーザー</span><span class="sxs-lookup"><span data-stu-id="03e3f-261">User</span></span> |  <span data-ttu-id="03e3f-262">場所</span><span class="sxs-lookup"><span data-stu-id="03e3f-262">Location</span></span> |  <span data-ttu-id="03e3f-263">通話の方向</span><span class="sxs-lookup"><span data-stu-id="03e3f-263">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="03e3f-264">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="03e3f-264">AlwaysBypass</span></span> |    <span data-ttu-id="03e3f-265">内部</span><span class="sxs-lookup"><span data-stu-id="03e3f-265">Internal</span></span> |  <span data-ttu-id="03e3f-266">SBC と同じサイト</span><span class="sxs-lookup"><span data-stu-id="03e3f-266">The same site as SBC</span></span> |  <span data-ttu-id="03e3f-267">発信</span><span class="sxs-lookup"><span data-stu-id="03e3f-267">Outbound</span></span> |

<span data-ttu-id="03e3f-268">次の表は、エンドユーザーの構成とアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-268">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="03e3f-269">ユーザーの物理的な場所</span><span class="sxs-lookup"><span data-stu-id="03e3f-269">User physical location</span></span>| <span data-ttu-id="03e3f-270">ユーザーが電話番号を発信または受信した場合</span><span class="sxs-lookup"><span data-stu-id="03e3f-270">User makes or receives a call to/from number</span></span> | <span data-ttu-id="03e3f-271">ユーザの電話番号</span><span class="sxs-lookup"><span data-stu-id="03e3f-271">User phone number</span></span>  | <span data-ttu-id="03e3f-272">オンラインボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="03e3f-272">Online Voice Routing Policy</span></span> | <span data-ttu-id="03e3f-273">SBC 用に構成されたモード</span><span class="sxs-lookup"><span data-stu-id="03e3f-273">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="03e3f-274">ベトナム</span><span class="sxs-lookup"><span data-stu-id="03e3f-274">Vietnam</span></span> | <span data-ttu-id="03e3f-275">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="03e3f-275">+84 4 3926 3000</span></span> | <span data-ttu-id="03e3f-276">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="03e3f-276">+84 4 5555 5555</span></span>   | <span data-ttu-id="03e3f-277">優先度 1:\+^ 84 ({9}\d) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-277">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="03e3f-278">優先度 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-278">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="03e3f-279">VNsbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="03e3f-279">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="03e3f-280">proxysbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="03e3f-280">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="03e3f-281">次の図は、常にバイパスモードを使用した発信通話の SIP のはしごと、SBC と同じ場所にいるユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-281">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="03e3f-282">![発信通話を示す図](media/direct-routing-media-op-10.png "発信通話")</span><span class="sxs-lookup"><span data-stu-id="03e3f-282">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="03e3f-283">次の表は、直接ルーティングによって送信された X-MS ヘッダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-283">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="03e3f-284">パラメーター</span><span class="sxs-lookup"><span data-stu-id="03e3f-284">Parameter</span></span> | <span data-ttu-id="03e3f-285">説明</span><span class="sxs-lookup"><span data-stu-id="03e3f-285">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="03e3f-286">招待 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-286">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="03e3f-287">オンラインボイスルーティングポリシーで定義された SBC のターゲット名は、要求 URI で送信されます</span><span class="sxs-lookup"><span data-stu-id="03e3f-287">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="03e3f-288">X--UserLocation: internal</span><span class="sxs-lookup"><span data-stu-id="03e3f-288">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="03e3f-289">このフィールドは、ユーザーが企業ネットワーク内に配置されていることを示しています</span><span class="sxs-lookup"><span data-stu-id="03e3f-289">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="03e3f-290">MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-290">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="03e3f-291">クライアントがターゲット SBC にどの SBC を通過する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-291">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="03e3f-292">この例では、常にバイパスしているため、クライアントはヘッダーで唯一の名前として送信されるターゲット名です。</span><span class="sxs-lookup"><span data-stu-id="03e3f-292">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="03e3f-293">----UserSite: ベトナム</span><span class="sxs-lookup"><span data-stu-id="03e3f-293">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="03e3f-294">ユーザーが配置されているサイトで示されているフィールド。</span><span class="sxs-lookup"><span data-stu-id="03e3f-294">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="03e3f-295">着信通話とユーザーは、常にバイパスの SBC と同じ場所にあります</span><span class="sxs-lookup"><span data-stu-id="03e3f-295">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="03e3f-296">モード</span><span class="sxs-lookup"><span data-stu-id="03e3f-296">Mode</span></span> |    <span data-ttu-id="03e3f-297">ユーザー</span><span class="sxs-lookup"><span data-stu-id="03e3f-297">User</span></span> |  <span data-ttu-id="03e3f-298">場所</span><span class="sxs-lookup"><span data-stu-id="03e3f-298">Location</span></span> |  <span data-ttu-id="03e3f-299">通話の方向</span><span class="sxs-lookup"><span data-stu-id="03e3f-299">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="03e3f-300">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="03e3f-300">AlwaysBypass</span></span> |    <span data-ttu-id="03e3f-301">内部</span><span class="sxs-lookup"><span data-stu-id="03e3f-301">Internal</span></span> | <span data-ttu-id="03e3f-302">SBC と同じサイト</span><span class="sxs-lookup"><span data-stu-id="03e3f-302">The same site as SBC</span></span> | <span data-ttu-id="03e3f-303">トラフィック</span><span class="sxs-lookup"><span data-stu-id="03e3f-303">Inbound</span></span> |


<span data-ttu-id="03e3f-304">着信通話では、ユーザーの場所が不明であり、SBC はユーザーがどこにいるかを推測する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-304">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="03e3f-305">推測が正しくない場合は、再招待が必要になります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-305">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="03e3f-306">この例では、ユーザーが内部であることを前提としています。メディアは直接流れることができ、それ以上の操作は必要ありません (再招待)。</span><span class="sxs-lookup"><span data-stu-id="03e3f-306">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="03e3f-307">ダイレクトルーティングサービスに接続された SBC は、レコードルーティングと連絡先フィールドを提供して、送信元の SBC の位置情報を報告します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-307">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="03e3f-308">これらのフィールドに基づいて、メディアパスはダイレクトルーティングによって計算されます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-308">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="03e3f-309">注: ユーザーが複数のエンドポイントを持つことができる場合、183のサポートはできません。</span><span class="sxs-lookup"><span data-stu-id="03e3f-309">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="03e3f-310">この場合、直接ルーティングでは常に180呼び出しが使用されます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-310">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="03e3f-311">次の図は、Always バイパスモードの着信呼び出しでの SIP のはしごを示しています。ユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-311">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="03e3f-313">発信通話とユーザーは外部であり、常にバイパスする</span><span class="sxs-lookup"><span data-stu-id="03e3f-313">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="03e3f-314">モード</span><span class="sxs-lookup"><span data-stu-id="03e3f-314">Mode</span></span> |    <span data-ttu-id="03e3f-315">ユーザー</span><span class="sxs-lookup"><span data-stu-id="03e3f-315">User</span></span> |  <span data-ttu-id="03e3f-316">サイト</span><span class="sxs-lookup"><span data-stu-id="03e3f-316">Site</span></span> |  <span data-ttu-id="03e3f-317">通話の方向</span><span class="sxs-lookup"><span data-stu-id="03e3f-317">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="03e3f-318">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="03e3f-318">AlwaysBypass</span></span> |  <span data-ttu-id="03e3f-319">外部</span><span class="sxs-lookup"><span data-stu-id="03e3f-319">External</span></span> |  <span data-ttu-id="03e3f-320">N/A</span><span class="sxs-lookup"><span data-stu-id="03e3f-320">N/A</span></span> | <span data-ttu-id="03e3f-321">発信</span><span class="sxs-lookup"><span data-stu-id="03e3f-321">Outbound</span></span> |


<span data-ttu-id="03e3f-322">次の図は、常にバイパスモードの発信通話に関する SIP のはしごを示しています。ユーザーは外部であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-322">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-12.png)

<span data-ttu-id="03e3f-324">次の表は、ダイレクトルーティングサービスによって送信された X ミリ秒のヘッダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-324">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="03e3f-325">パラメーター</span><span class="sxs-lookup"><span data-stu-id="03e3f-325">Parameter</span></span> |   <span data-ttu-id="03e3f-326">説明</span><span class="sxs-lookup"><span data-stu-id="03e3f-326">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="03e3f-327">招待 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-327">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="03e3f-328">オンラインボイスルーティングポリシーで定義された SBC のターゲット名は、要求 URI で送信されます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-328">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="03e3f-329">X--UserLocation: external</span><span class="sxs-lookup"><span data-stu-id="03e3f-329">X-MS-UserLocation: external</span></span> | <span data-ttu-id="03e3f-330">このフィールドは、ユーザーが企業ネットワークの外部にあることを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-330">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="03e3f-331">MediaPath: proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="03e3f-332">クライアントがターゲット SBC にどの SBC を通過する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-332">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="03e3f-333">この例では、常にバイパスしており、クライアントは外部です。</span><span class="sxs-lookup"><span data-stu-id="03e3f-333">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="03e3f-334">着信通話とユーザーは外部であり、常にバイパスする</span><span class="sxs-lookup"><span data-stu-id="03e3f-334">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="03e3f-335">モード</span><span class="sxs-lookup"><span data-stu-id="03e3f-335">Mode</span></span> | <span data-ttu-id="03e3f-336">ユーザー</span><span class="sxs-lookup"><span data-stu-id="03e3f-336">User</span></span> | <span data-ttu-id="03e3f-337">サイト</span><span class="sxs-lookup"><span data-stu-id="03e3f-337">Site</span></span> |  <span data-ttu-id="03e3f-338">通話の方向</span><span class="sxs-lookup"><span data-stu-id="03e3f-338">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="03e3f-339">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="03e3f-339">AlwaysBypass</span></span> |  <span data-ttu-id="03e3f-340">外部</span><span class="sxs-lookup"><span data-stu-id="03e3f-340">External</span></span> |  <span data-ttu-id="03e3f-341">N/A</span><span class="sxs-lookup"><span data-stu-id="03e3f-341">N/A</span></span> |   <span data-ttu-id="03e3f-342">トラフィック</span><span class="sxs-lookup"><span data-stu-id="03e3f-342">Inbound</span></span> |

<span data-ttu-id="03e3f-343">着信通話の場合、直接ルーティングに接続された SBC は、ユーザーの場所が外部である場合は、再招待を送信する必要があります (既定では、ローカルメディア候補は常に提供されています)。</span><span class="sxs-lookup"><span data-stu-id="03e3f-343">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="03e3f-344">X-MediaPath は、指定されたレコードルートと SBC ユーザーに基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-344">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="03e3f-345">次の図は、常にバイパスモードの着信呼び出しに対する SIP のはしごを示しています。また、ユーザーは外部であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-345">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="03e3f-347">ローカルユーザーモードに対してのみ</span><span class="sxs-lookup"><span data-stu-id="03e3f-347">Only for local users mode</span></span>

<span data-ttu-id="03e3f-348">ターゲット SBC のローカルメディア候補は、ユーザーが SBC と同じ場所にいる場合にのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-348">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="03e3f-349">それ以外の場合、メディアはプロキシ SBC の内部または外部 IP 経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-349">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="03e3f-350">次のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-350">The following scenarios are described:</span></span>

- [<span data-ttu-id="03e3f-351">発信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-351">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="03e3f-352">着信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-352">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="03e3f-353">ユーザーは SBC と同じ場所にありませんが、企業ネットワーク内にある</span><span class="sxs-lookup"><span data-stu-id="03e3f-353">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="03e3f-354">着信通話とユーザーは内部にありますが、SBC と同じ場所にありません。</span><span class="sxs-lookup"><span data-stu-id="03e3f-354">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="03e3f-355">次の表は、エンドユーザーによる構成とアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-355">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="03e3f-356">ユーザーの物理的な場所</span><span class="sxs-lookup"><span data-stu-id="03e3f-356">User physical location</span></span> |  <span data-ttu-id="03e3f-357">ユーザーが電話番号を発信または受信した場合</span><span class="sxs-lookup"><span data-stu-id="03e3f-357">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="03e3f-358">ユーザの電話番号</span><span class="sxs-lookup"><span data-stu-id="03e3f-358">User phone number</span></span> | <span data-ttu-id="03e3f-359">オンラインボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="03e3f-359">Online Voice Routing Policy</span></span> |   <span data-ttu-id="03e3f-360">SBC 用に構成されたモード</span><span class="sxs-lookup"><span data-stu-id="03e3f-360">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="03e3f-361">ベトナム</span><span class="sxs-lookup"><span data-stu-id="03e3f-361">Vietnam</span></span> | <span data-ttu-id="03e3f-362">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="03e3f-362">+84 4 3926  3000</span></span> |  <span data-ttu-id="03e3f-363">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="03e3f-363">+84 4 5555 5555</span></span> | <span data-ttu-id="03e3f-364">優先度 1:\+^ 84 ({9}\d) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-364">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="03e3f-365">優先度 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03e3f-365">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="03e3f-366">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="03e3f-366">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="03e3f-367">発信通話とユーザーは、ローカルユーザーに対してのみ、SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-367">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="03e3f-368">モード</span><span class="sxs-lookup"><span data-stu-id="03e3f-368">Mode</span></span> | <span data-ttu-id="03e3f-369">ユーザー</span><span class="sxs-lookup"><span data-stu-id="03e3f-369">User</span></span> | <span data-ttu-id="03e3f-370">サイト</span><span class="sxs-lookup"><span data-stu-id="03e3f-370">Site</span></span> | <span data-ttu-id="03e3f-371">通話の方向</span><span class="sxs-lookup"><span data-stu-id="03e3f-371">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="03e3f-372">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="03e3f-372">OnlyForLocalUsers</span></span> |   <span data-ttu-id="03e3f-373">内部</span><span class="sxs-lookup"><span data-stu-id="03e3f-373">Internal</span></span> |<span data-ttu-id="03e3f-374">SBC と同じ</span><span class="sxs-lookup"><span data-stu-id="03e3f-374">Same as SBC</span></span>   | <span data-ttu-id="03e3f-375">発信</span><span class="sxs-lookup"><span data-stu-id="03e3f-375">Outbound</span></span> |

<span data-ttu-id="03e3f-376">次の図は、OnlyForLocalUsers モードを使った発信通話と、ユーザーが SBC と同じ場所にいることを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-376">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="03e3f-377">これは、[ユーザーが SBC と同じ場所にいるとき](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)の、[送信中の通話と同じフローを示します。</span><span class="sxs-lookup"><span data-stu-id="03e3f-377">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="03e3f-379">着信通話とユーザーは、ローカルユーザーに対してのみ、SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="03e3f-379">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="03e3f-380">モード</span><span class="sxs-lookup"><span data-stu-id="03e3f-380">Mode</span></span> | <span data-ttu-id="03e3f-381">ユーザー</span><span class="sxs-lookup"><span data-stu-id="03e3f-381">User</span></span> | <span data-ttu-id="03e3f-382">サイト</span><span class="sxs-lookup"><span data-stu-id="03e3f-382">Site</span></span> | <span data-ttu-id="03e3f-383">通話の方向</span><span class="sxs-lookup"><span data-stu-id="03e3f-383">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="03e3f-384">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="03e3f-384">OnlyForLocalUsers</span></span> |   <span data-ttu-id="03e3f-385">内部</span><span class="sxs-lookup"><span data-stu-id="03e3f-385">Internal</span></span> | <span data-ttu-id="03e3f-386">SBC と同じ</span><span class="sxs-lookup"><span data-stu-id="03e3f-386">Same as SBC</span></span> | <span data-ttu-id="03e3f-387">トラフィック</span><span class="sxs-lookup"><span data-stu-id="03e3f-387">Inbound</span></span> |

<span data-ttu-id="03e3f-388">次の図は、OnlyForLocalUsers モードを使った着信通話と、ユーザーが SBC と同じ場所にいることを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-388">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="03e3f-389">これは、[ユーザーが SBC と同じ場所にいるときに、着信通話](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)に表示されるフローと同じです。</span><span class="sxs-lookup"><span data-stu-id="03e3f-389">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="03e3f-391">ユーザーは SBC と同じ場所にありませんが、社内ネットワーク内にあるのはローカルユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="03e3f-391">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="03e3f-392">モード</span><span class="sxs-lookup"><span data-stu-id="03e3f-392">Mode</span></span> | <span data-ttu-id="03e3f-393">ユーザー</span><span class="sxs-lookup"><span data-stu-id="03e3f-393">User</span></span> | <span data-ttu-id="03e3f-394">サイト</span><span class="sxs-lookup"><span data-stu-id="03e3f-394">Site</span></span> |<span data-ttu-id="03e3f-395">通話の方向</span><span class="sxs-lookup"><span data-stu-id="03e3f-395">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="03e3f-396">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="03e3f-396">OnlyForLocalUsers</span></span>  | <span data-ttu-id="03e3f-397">内部</span><span class="sxs-lookup"><span data-stu-id="03e3f-397">Internal</span></span> |   <span data-ttu-id="03e3f-398">SBC と異なる</span><span class="sxs-lookup"><span data-stu-id="03e3f-398">Different from SBC</span></span> | <span data-ttu-id="03e3f-399">発信</span><span class="sxs-lookup"><span data-stu-id="03e3f-399">Outbound</span></span> |

<span data-ttu-id="03e3f-400">直接ルーティングでは、SBC で構成されたユーザーとモードの報告された場所に基づいて、X-MediaPath が計算されます。</span><span class="sxs-lookup"><span data-stu-id="03e3f-400">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="03e3f-401">次の図は、OnlyForLocalUsers モードを使った発信通話と、SBC と同じ場所にない内部ユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-401">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="03e3f-403">着信通話とユーザーは内部ですが、ローカルユーザーのみを含む SBC と同じ場所にありません。</span><span class="sxs-lookup"><span data-stu-id="03e3f-403">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="03e3f-404">モード</span><span class="sxs-lookup"><span data-stu-id="03e3f-404">Mode</span></span> |    <span data-ttu-id="03e3f-405">ユーザー</span><span class="sxs-lookup"><span data-stu-id="03e3f-405">User</span></span> |  <span data-ttu-id="03e3f-406">サイト</span><span class="sxs-lookup"><span data-stu-id="03e3f-406">Site</span></span> |  <span data-ttu-id="03e3f-407">通話の方向</span><span class="sxs-lookup"><span data-stu-id="03e3f-407">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="03e3f-408">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="03e3f-408">OnlyForLocalUsers</span></span> | <span data-ttu-id="03e3f-409">内部</span><span class="sxs-lookup"><span data-stu-id="03e3f-409">Internal</span></span> |    <span data-ttu-id="03e3f-410">SBC と異なる</span><span class="sxs-lookup"><span data-stu-id="03e3f-410">Different from SBC</span></span> |    <span data-ttu-id="03e3f-411">トラフィック</span><span class="sxs-lookup"><span data-stu-id="03e3f-411">Inbound</span></span> |

<span data-ttu-id="03e3f-412">次の図は、OnlyForLocalUsers モードの着信呼び出しと、SBC と同じ場所にない内部ユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="03e3f-412">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-17.png)









