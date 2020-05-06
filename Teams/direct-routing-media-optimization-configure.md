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
ms.openlocfilehash: 518445e10b757adc9a21c426fb885bb04b7a878b
ms.sourcegitcommit: b143611d14765af054a4f84cca52e2003d35af1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44047856"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="5db09-103">直接ルーティング用のローカルメディア最適化を構成する</span><span class="sxs-lookup"><span data-stu-id="5db09-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="5db09-104">ローカルメディア最適化の構成は、場所に基づくルーティングや動的な緊急通話など、他のクラウド音声機能に共通するネットワーク設定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="5db09-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="5db09-105">ネットワーク領域、ネットワークサイト、ネットワークサブネット、および信頼された IP アドレスの詳細については、「[クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5db09-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="5db09-106">ローカルメディア最適化を構成する前に、「[直接ルーティング用のローカルメディアの最適化](direct-routing-media-optimization.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5db09-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="5db09-107">ローカルメディア最適化を構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="5db09-108">Teams 管理センターまたは PowerShell を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="5db09-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="5db09-109">詳細については、「[ネットワークトポロジを管理する](manage-your-network-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5db09-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="5db09-110">ユーザーと SBC サイトを構成します (この記事で説明します)。</span><span class="sxs-lookup"><span data-stu-id="5db09-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="5db09-111">(SBC ベンダー仕様に従って) ローカルメディア最適化用に SBCs を構成します。</span><span class="sxs-lookup"><span data-stu-id="5db09-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="5db09-112">次の図は、この記事の例で使用されているネットワークセットアップを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="5db09-113">![例のネットワークセットアップを示す図](media/direct-routing-media-op-9.png "ネットワークセットアップ例")</span><span class="sxs-lookup"><span data-stu-id="5db09-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="5db09-114">ユーザーと SBC サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="5db09-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="5db09-115">ユーザーと SBC サイトを構成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="5db09-116">[外部の信頼できる IP アドレスを管理](#manage-external-trusted-ip-addresses)する。</span><span class="sxs-lookup"><span data-stu-id="5db09-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="5db09-117">ネットワークの領域、ネットワークサイト、ネットワークサブネットを構成して、[ネットワークトポロジを定義](#define-the-network-topology)します。</span><span class="sxs-lookup"><span data-stu-id="5db09-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="5db09-118">関連するモードとプロキシの SBC 値を使って、サイトに SBC (s) を割り当てることで[、仮想ネットワークトポロジを定義](#define-the-virtual-network-topology)します。</span><span class="sxs-lookup"><span data-stu-id="5db09-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="5db09-119">SBC ベンダー仕様に従って、ローカルメディア最適化用に SBC を構成する</span><span class="sxs-lookup"><span data-stu-id="5db09-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="5db09-120">この記事では、Microsoft コンポーネントの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="5db09-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="5db09-121">SBC 構成の詳細については、SBC ベンダーの documenation を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5db09-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="5db09-122">ローカルメディア最適化は、次の SBC ベンダーによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5db09-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="5db09-123">仕入先</span><span class="sxs-lookup"><span data-stu-id="5db09-123">Vendor</span></span> | <span data-ttu-id="5db09-124">Product</span><span class="sxs-lookup"><span data-stu-id="5db09-124">Product</span></span> |    <span data-ttu-id="5db09-125">ソフトウェアのバージョン</span><span class="sxs-lookup"><span data-stu-id="5db09-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="5db09-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="5db09-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="5db09-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="5db09-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="5db09-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="5db09-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5db09-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="5db09-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="5db09-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="5db09-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5db09-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="5db09-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="5db09-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="5db09-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5db09-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="5db09-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="5db09-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="5db09-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5db09-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="5db09-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="5db09-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="5db09-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5db09-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="5db09-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="5db09-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="5db09-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5db09-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="5db09-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="5db09-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="5db09-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5db09-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="5db09-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="5db09-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="5db09-142">7.20A.256</span></span> |
| [<span data-ttu-id="5db09-143">リボンの SBC コア</span><span class="sxs-lookup"><span data-stu-id="5db09-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="5db09-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="5db09-144">SBC 5110</span></span>         | <span data-ttu-id="5db09-145">8.2</span><span class="sxs-lookup"><span data-stu-id="5db09-145">8.2</span></span>  |
|            |  <span data-ttu-id="5db09-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="5db09-146">SBC 5210</span></span>         | <span data-ttu-id="5db09-147">8.2</span><span class="sxs-lookup"><span data-stu-id="5db09-147">8.2</span></span>  |
|            |  <span data-ttu-id="5db09-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="5db09-148">SBC 5400</span></span>         | <span data-ttu-id="5db09-149">8.2</span><span class="sxs-lookup"><span data-stu-id="5db09-149">8.2</span></span>  |
|            |  <span data-ttu-id="5db09-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="5db09-150">SBC 7000</span></span>         | <span data-ttu-id="5db09-151">8.2</span><span class="sxs-lookup"><span data-stu-id="5db09-151">8.2</span></span>  |
|            |  <span data-ttu-id="5db09-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="5db09-152">SBC SWe</span></span>          | <span data-ttu-id="5db09-153">8.2</span><span class="sxs-lookup"><span data-stu-id="5db09-153">8.2</span></span>  |
| [<span data-ttu-id="5db09-154">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="5db09-154">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="5db09-155">anynode</span><span class="sxs-lookup"><span data-stu-id="5db09-155">anynode</span></span>          | <span data-ttu-id="5db09-156">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="5db09-156">4.0.1+</span></span> |
| [<span data-ttu-id="5db09-157">Oracle</span><span class="sxs-lookup"><span data-stu-id="5db09-157">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="5db09-158">AP 1100</span><span class="sxs-lookup"><span data-stu-id="5db09-158">AP 1100</span></span> | <span data-ttu-id="5db09-159">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5db09-159">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="5db09-160">AP 3900</span><span class="sxs-lookup"><span data-stu-id="5db09-160">AP 3900</span></span> | <span data-ttu-id="5db09-161">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5db09-161">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="5db09-162">AP 4600</span><span class="sxs-lookup"><span data-stu-id="5db09-162">AP 4600</span></span> | <span data-ttu-id="5db09-163">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5db09-163">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="5db09-164">AP 6300</span><span class="sxs-lookup"><span data-stu-id="5db09-164">AP 6300</span></span> | <span data-ttu-id="5db09-165">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5db09-165">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="5db09-166">AP 6350</span><span class="sxs-lookup"><span data-stu-id="5db09-166">AP 6350</span></span> | <span data-ttu-id="5db09-167">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5db09-167">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="5db09-168">VME</span><span class="sxs-lookup"><span data-stu-id="5db09-168">VME</span></span>     | <span data-ttu-id="5db09-169">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5db09-169">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="5db09-170">外部の信頼できる IP アドレスを管理する</span><span class="sxs-lookup"><span data-stu-id="5db09-170">Manage external trusted IP addresses</span></span>

<span data-ttu-id="5db09-171">外部の信頼できる Ip は、エンタープライズネットワークのインターネット外部 Ip です。</span><span class="sxs-lookup"><span data-stu-id="5db09-171">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="5db09-172">これらの IP アドレスは、microsoft Teams クライアントが Microsoft 365 に接続したときに使用される IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="5db09-172">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="5db09-173">ユーザーがローカルメディア最適化を使用しているサイトごとに、これらの外部 Ip を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-173">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="5db09-174">各サイトのパブリック IP アドレスを追加するには、CsTenantTrustedIPAddress コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5db09-174">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="5db09-175">1つのテナントに対して無制限の数の信頼できる IP アドレスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5db09-175">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="5db09-176">Microsoft 365 によって表示される外部 Ip が IPv4 アドレスと IPv6 アドレスの両方である場合は、両方の種類の IP アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-176">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="5db09-177">IPv4 の場合は、マスク32を使用します。</span><span class="sxs-lookup"><span data-stu-id="5db09-177">For IPv4, use mask 32.</span></span> <span data-ttu-id="5db09-178">IPv6 の場合は、マスク128を使用します。</span><span class="sxs-lookup"><span data-stu-id="5db09-178">For IPv6, use mask 128.</span></span> <span data-ttu-id="5db09-179">コマンドレットで異なる MaskBits を指定することで、個々の外部 IP アドレスと外部 IP サブネットの両方を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5db09-179">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="5db09-180">信頼された IP アドレスを追加する例。</span><span class="sxs-lookup"><span data-stu-id="5db09-180">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="5db09-181">ネットワークトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="5db09-181">Define the network topology</span></span>

<span data-ttu-id="5db09-182">このセクションでは、ネットワークトポロジのネットワーク領域、ネットワークサイト、ネットワークサブネットを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5db09-182">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="5db09-183">すべてのパラメーターは大文字と小文字を区別するため、セットアップ時に使用したのと同じケースを確実に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-183">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="5db09-184">(たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は、別のサイトとして扱われます)。</span><span class="sxs-lookup"><span data-stu-id="5db09-184">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="5db09-185">ネットワーク領域を定義する</span><span class="sxs-lookup"><span data-stu-id="5db09-185">Define network regions</span></span>

<span data-ttu-id="5db09-186">ネットワーク領域を定義するには、CsTenantNetworkRegion コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5db09-186">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="5db09-187">RegionID パラメーターは、地域の地理を表す論理名であり、依存関係または制限がありません。</span><span class="sxs-lookup"><span data-stu-id="5db09-187">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="5db09-188">CentralSite <site ID>パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5db09-188">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="5db09-189">次の例では、APAC という名前のネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="5db09-189">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="5db09-190">ネットワークサイトを定義する</span><span class="sxs-lookup"><span data-stu-id="5db09-190">Define network sites</span></span>

<span data-ttu-id="5db09-191">ネットワークサイトを定義するには、CsTenantNetworkSite コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5db09-191">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="5db09-192">各ネットワークサイトは、ネットワーク領域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-192">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="5db09-193">次の例では、APAC 地域で3つの新しいネットワークサイト、ベトナム、インドネシア、シンガポールを作成します。</span><span class="sxs-lookup"><span data-stu-id="5db09-193">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="5db09-194">ネットワークサブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="5db09-194">Define network subnets</span></span>

<span data-ttu-id="5db09-195">ネットワークサブネットを定義してネットワークサイトに関連付けるには、CsTenantNetworkSubnet コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5db09-195">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="5db09-196">各ネットワークサブネットは、1つのサイトにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5db09-196">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="5db09-197">次の例では、3つのネットワークサブネットを定義し、それをベトナム、インドネシア、シンガポールという3つのネットワークサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5db09-197">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="5db09-198">仮想ネットワークトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="5db09-198">Define the virtual network topology</span></span> 

<span data-ttu-id="5db09-199">まず、テナント管理者は、CsOnlinePSTNGateway コマンドレットを使用して、関連する SBC ごとに新しい SBC 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="5db09-199">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="5db09-200">テナント管理者は、CsOnlinePSTNGateway コマンドレットを使用して、PSTN ゲートウェイオブジェクトのネットワークサイトを指定することで、仮想ネットワークトポロジを定義します。</span><span class="sxs-lookup"><span data-stu-id="5db09-200">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="5db09-201">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5db09-201">Note the following:</span></span> 
   - <span data-ttu-id="5db09-202">顧客が1つの SBC を使用している場合は、-ProxySBC パラメーターは必須 $null または SBC FQDN 値 (集中型 trunks シナリオを持つ集中型 SBC) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-202">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="5db09-203">ローカルメディアの最適化をサポートするには、-MediaBypass ・・・・・バイのパラメーターが $true に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-203">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="5db09-204">SBC に-BypassMode パラメーターが設定されていない場合、X ミリ秒のヘッダーは送信されません。</span><span class="sxs-lookup"><span data-stu-id="5db09-204">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="5db09-205">すべてのパラメーターは大文字と小文字を区別するため、セットアップ時に使用したのと同じケースを確実に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-205">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="5db09-206">(たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は、別のサイトとして扱われます)。</span><span class="sxs-lookup"><span data-stu-id="5db09-206">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="5db09-207">次の例では、APAC 領域の2つの SBCs をネットワークサイトに追加します。これは、モードが常にバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="5db09-207">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="5db09-208">注: ローカルメディア最適化と位置情報に基づくルーティング (LBR) を同時に構成するときに中断のない操作を行うには、GatewaySiteLbrEnabled パラメーターを各下流の SBC の $true に設定して、下位の SBCs を LBR に対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-208">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="5db09-209">(この設定はプロキシ SBC には必須ではありません)。</span><span class="sxs-lookup"><span data-stu-id="5db09-209">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="5db09-210">上記の情報に基づいて、次の表に示すように、直接ルーティングを行うと、SIP の招待に対しては3つの専用 SIP ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5db09-210">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="5db09-211">BypassMode が定義されている場合に、招待と再招待の際に直接ルーティングで導入された X-MS ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="5db09-211">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="5db09-212">ヘッダー名</span><span class="sxs-lookup"><span data-stu-id="5db09-212">Header name</span></span> | <span data-ttu-id="5db09-213">Values</span><span class="sxs-lookup"><span data-stu-id="5db09-213">Values</span></span> | <span data-ttu-id="5db09-214">注釈</span><span class="sxs-lookup"><span data-stu-id="5db09-214">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="5db09-215">エックス--UserLocation</span><span class="sxs-lookup"><span data-stu-id="5db09-215">X-MS-UserLocation</span></span> | <span data-ttu-id="5db09-216">内部/外部</span><span class="sxs-lookup"><span data-stu-id="5db09-216">internal/external</span></span> | <span data-ttu-id="5db09-217">ユーザーが内部と外部のどちらであるかを示します</span><span class="sxs-lookup"><span data-stu-id="5db09-217">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="5db09-218">要求-URI 招待 sip: + 84439263000@VNsbc.contoso.com SIP/2.0</span><span class="sxs-lookup"><span data-stu-id="5db09-218">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="5db09-219">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="5db09-219">SBC FQDN</span></span> | <span data-ttu-id="5db09-220">SBC が直接ルーティングに直接接続されていない場合でも、通話の対象となる FQDN</span><span class="sxs-lookup"><span data-stu-id="5db09-220">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="5db09-221">MediaPath</span><span class="sxs-lookup"><span data-stu-id="5db09-221">X-MS-MediaPath</span></span> | <span data-ttu-id="5db09-222">例: proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-222">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="5db09-223">ユーザーとターゲットの間のメディアパスに使用する SBCs の順序です。</span><span class="sxs-lookup"><span data-stu-id="5db09-223">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="5db09-224">最後の SBC は常に最終です</span><span class="sxs-lookup"><span data-stu-id="5db09-224">The final SBC is always last</span></span> |
| <span data-ttu-id="5db09-225">-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="5db09-225">X-MS-UserSite</span></span> | <span data-ttu-id="5db09-226">usersiteID</span><span class="sxs-lookup"><span data-stu-id="5db09-226">usersiteID</span></span> | <span data-ttu-id="5db09-227">テナント管理者によって定義された文字列</span><span class="sxs-lookup"><span data-stu-id="5db09-227">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="5db09-228">コールフロー</span><span class="sxs-lookup"><span data-stu-id="5db09-228">Call flows</span></span> 

<span data-ttu-id="5db09-229">次に、2つのモードのコールフローを示します。</span><span class="sxs-lookup"><span data-stu-id="5db09-229">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="5db09-230">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="5db09-230">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="5db09-231">ローカルユーザーのみ</span><span class="sxs-lookup"><span data-stu-id="5db09-231">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="5db09-232">常にバイパスモード</span><span class="sxs-lookup"><span data-stu-id="5db09-232">Always Bypass mode</span></span>

<span data-ttu-id="5db09-233">[常にバイパス] モードは、構成するのに最も簡単なオプションです。</span><span class="sxs-lookup"><span data-stu-id="5db09-233">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="5db09-234">テナント管理者は、すべてのユーザーに対して1つのサイトを構成することができます。すべてのサイトからすべての SBCs に到達可能である場合は、SBCs になります。</span><span class="sxs-lookup"><span data-stu-id="5db09-234">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="5db09-235">次のシナリオでは、この例では常にバイパスモードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5db09-235">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="5db09-236">発信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="5db09-236">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="5db09-237">着信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="5db09-237">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="5db09-238">発信通話とユーザーは外部です</span><span class="sxs-lookup"><span data-stu-id="5db09-238">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="5db09-239">着信通話とユーザーは外部</span><span class="sxs-lookup"><span data-stu-id="5db09-239">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="5db09-240">次の表は、例で使用される FQDN と IP アドレスを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-240">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="5db09-241">FQDN</span><span class="sxs-lookup"><span data-stu-id="5db09-241">FQDN</span></span> | <span data-ttu-id="5db09-242">SBC 外部 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="5db09-242">SBC external IP address</span></span> | <span data-ttu-id="5db09-243">SBC 内部 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="5db09-243">SBC internal IP Address</span></span> | <span data-ttu-id="5db09-244">内部サブネット</span><span class="sxs-lookup"><span data-stu-id="5db09-244">Internal subnet</span></span> | <span data-ttu-id="5db09-245">場所</span><span class="sxs-lookup"><span data-stu-id="5db09-245">Location</span></span> | <span data-ttu-id="5db09-246">外部 NAT (信頼できる IP)</span><span class="sxs-lookup"><span data-stu-id="5db09-246">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5db09-247">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-247">VNsbc.contoso.com</span></span> | <span data-ttu-id="5db09-248">なし</span><span class="sxs-lookup"><span data-stu-id="5db09-248">None</span></span> | <span data-ttu-id="5db09-249">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="5db09-249">192.168.1.5</span></span> | <span data-ttu-id="5db09-250">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="5db09-250">192.168.1.0/24</span></span> | <span data-ttu-id="5db09-251">ベトナム</span><span class="sxs-lookup"><span data-stu-id="5db09-251">Vietnam</span></span> | <span data-ttu-id="5db09-252">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="5db09-252">172.16.240.110</span></span> |
| <span data-ttu-id="5db09-253">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-253">IDsbc.contoso.com</span></span> | <span data-ttu-id="5db09-254">なし</span><span class="sxs-lookup"><span data-stu-id="5db09-254">None</span></span> | <span data-ttu-id="5db09-255">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="5db09-255">192.168.2.5</span></span> | <span data-ttu-id="5db09-256">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="5db09-256">192.168.2.0/24</span></span> | <span data-ttu-id="5db09-257">インドネシア</span><span class="sxs-lookup"><span data-stu-id="5db09-257">Indonesia</span></span> | <span data-ttu-id="5db09-258">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="5db09-258">172.16.240.120</span></span> |
| <span data-ttu-id="5db09-259">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-259">proxysbc.contoso.com</span></span> | <span data-ttu-id="5db09-260">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="5db09-260">172.16.240.133</span></span> | <span data-ttu-id="5db09-261">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="5db09-261">192.168.3.5</span></span> | <span data-ttu-id="5db09-262">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="5db09-262">192.168.3.0/24</span></span> | <span data-ttu-id="5db09-263">シンガポール</span><span class="sxs-lookup"><span data-stu-id="5db09-263">Singapore</span></span> | <span data-ttu-id="5db09-264">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="5db09-264">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="5db09-265">発信通話とユーザーは、常にバイパスの SBC と同じ場所にあります</span><span class="sxs-lookup"><span data-stu-id="5db09-265">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="5db09-266">モード</span><span class="sxs-lookup"><span data-stu-id="5db09-266">Mode</span></span> |    <span data-ttu-id="5db09-267">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5db09-267">User</span></span> |  <span data-ttu-id="5db09-268">場所</span><span class="sxs-lookup"><span data-stu-id="5db09-268">Location</span></span> |  <span data-ttu-id="5db09-269">通話の方向</span><span class="sxs-lookup"><span data-stu-id="5db09-269">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="5db09-270">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="5db09-270">AlwaysBypass</span></span> |    <span data-ttu-id="5db09-271">内部</span><span class="sxs-lookup"><span data-stu-id="5db09-271">Internal</span></span> |  <span data-ttu-id="5db09-272">SBC と同じサイト</span><span class="sxs-lookup"><span data-stu-id="5db09-272">The same site as SBC</span></span> |  <span data-ttu-id="5db09-273">発信</span><span class="sxs-lookup"><span data-stu-id="5db09-273">Outbound</span></span> |

<span data-ttu-id="5db09-274">次の表は、エンドユーザーの構成とアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-274">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="5db09-275">ユーザーの物理的な場所</span><span class="sxs-lookup"><span data-stu-id="5db09-275">User physical location</span></span>| <span data-ttu-id="5db09-276">ユーザーが電話番号を発信または受信した場合</span><span class="sxs-lookup"><span data-stu-id="5db09-276">User makes or receives a call to/from number</span></span> | <span data-ttu-id="5db09-277">ユーザの電話番号</span><span class="sxs-lookup"><span data-stu-id="5db09-277">User phone number</span></span>  | <span data-ttu-id="5db09-278">オンラインボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="5db09-278">Online Voice Routing Policy</span></span> | <span data-ttu-id="5db09-279">SBC 用に構成されたモード</span><span class="sxs-lookup"><span data-stu-id="5db09-279">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5db09-280">ベトナム</span><span class="sxs-lookup"><span data-stu-id="5db09-280">Vietnam</span></span> | <span data-ttu-id="5db09-281">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="5db09-281">+84 4 3926 3000</span></span> | <span data-ttu-id="5db09-282">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="5db09-282">+84 4 5555 5555</span></span>   | <span data-ttu-id="5db09-283">優先度 1:\+^ 84 ({9}\d) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-283">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="5db09-284">優先度 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-284">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="5db09-285">VNsbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="5db09-285">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="5db09-286">proxysbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="5db09-286">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="5db09-287">次の図は、常にバイパスモードを使用した発信通話の SIP のはしごと、SBC と同じ場所にいるユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-287">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="5db09-288">![発信通話を示す図](media/direct-routing-media-op-10.png "発信通話")</span><span class="sxs-lookup"><span data-stu-id="5db09-288">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="5db09-289">次の表は、直接ルーティングによって送信された X-MS ヘッダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-289">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="5db09-290">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5db09-290">Parameter</span></span> | <span data-ttu-id="5db09-291">説明</span><span class="sxs-lookup"><span data-stu-id="5db09-291">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="5db09-292">招待 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-292">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="5db09-293">オンラインボイスルーティングポリシーで定義された SBC のターゲット名は、要求 URI で送信されます</span><span class="sxs-lookup"><span data-stu-id="5db09-293">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="5db09-294">X--UserLocation: internal</span><span class="sxs-lookup"><span data-stu-id="5db09-294">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="5db09-295">このフィールドは、ユーザーが企業ネットワーク内に配置されていることを示しています</span><span class="sxs-lookup"><span data-stu-id="5db09-295">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="5db09-296">MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-296">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="5db09-297">クライアントがターゲット SBC にどの SBC を通過する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5db09-297">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="5db09-298">この例では、常にバイパスしているため、クライアントはヘッダーで唯一の名前として送信されるターゲット名です。</span><span class="sxs-lookup"><span data-stu-id="5db09-298">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="5db09-299">----UserSite: ベトナム</span><span class="sxs-lookup"><span data-stu-id="5db09-299">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="5db09-300">ユーザーが配置されているサイトで示されているフィールド。</span><span class="sxs-lookup"><span data-stu-id="5db09-300">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="5db09-301">着信通話とユーザーは、常にバイパスの SBC と同じ場所にあります</span><span class="sxs-lookup"><span data-stu-id="5db09-301">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="5db09-302">モード</span><span class="sxs-lookup"><span data-stu-id="5db09-302">Mode</span></span> |    <span data-ttu-id="5db09-303">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5db09-303">User</span></span> |  <span data-ttu-id="5db09-304">場所</span><span class="sxs-lookup"><span data-stu-id="5db09-304">Location</span></span> |  <span data-ttu-id="5db09-305">通話の方向</span><span class="sxs-lookup"><span data-stu-id="5db09-305">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5db09-306">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="5db09-306">AlwaysBypass</span></span> |    <span data-ttu-id="5db09-307">内部</span><span class="sxs-lookup"><span data-stu-id="5db09-307">Internal</span></span> | <span data-ttu-id="5db09-308">SBC と同じサイト</span><span class="sxs-lookup"><span data-stu-id="5db09-308">The same site as SBC</span></span> | <span data-ttu-id="5db09-309">トラフィック</span><span class="sxs-lookup"><span data-stu-id="5db09-309">Inbound</span></span> |


<span data-ttu-id="5db09-310">着信通話では、ユーザーの場所が不明であり、SBC はユーザーがどこにいるかを推測する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5db09-310">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="5db09-311">推測が正しくない場合は、再招待が必要になります。</span><span class="sxs-lookup"><span data-stu-id="5db09-311">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="5db09-312">この例では、ユーザーが内部であることを前提としています。メディアは直接流れることができ、それ以上の操作は必要ありません (再招待)。</span><span class="sxs-lookup"><span data-stu-id="5db09-312">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="5db09-313">ダイレクトルーティングサービスに接続された SBC は、レコードルーティングと連絡先フィールドを提供して、送信元の SBC の位置情報を報告します。</span><span class="sxs-lookup"><span data-stu-id="5db09-313">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="5db09-314">これらのフィールドに基づいて、メディアパスはダイレクトルーティングによって計算されます。</span><span class="sxs-lookup"><span data-stu-id="5db09-314">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="5db09-315">注: ユーザーが複数のエンドポイントを持つことができる場合、183のサポートはできません。</span><span class="sxs-lookup"><span data-stu-id="5db09-315">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="5db09-316">この場合、直接ルーティングでは常に180呼び出しが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5db09-316">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="5db09-317">次の図は、Always バイパスモードの着信呼び出しでの SIP のはしごを示しています。ユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="5db09-317">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="5db09-319">発信通話とユーザーは外部であり、常にバイパスする</span><span class="sxs-lookup"><span data-stu-id="5db09-319">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="5db09-320">モード</span><span class="sxs-lookup"><span data-stu-id="5db09-320">Mode</span></span> |    <span data-ttu-id="5db09-321">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5db09-321">User</span></span> |  <span data-ttu-id="5db09-322">サイト</span><span class="sxs-lookup"><span data-stu-id="5db09-322">Site</span></span> |  <span data-ttu-id="5db09-323">通話の方向</span><span class="sxs-lookup"><span data-stu-id="5db09-323">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="5db09-324">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="5db09-324">AlwaysBypass</span></span> |  <span data-ttu-id="5db09-325">外部</span><span class="sxs-lookup"><span data-stu-id="5db09-325">External</span></span> |  <span data-ttu-id="5db09-326">該当なし</span><span class="sxs-lookup"><span data-stu-id="5db09-326">N/A</span></span> | <span data-ttu-id="5db09-327">発信</span><span class="sxs-lookup"><span data-stu-id="5db09-327">Outbound</span></span> |


<span data-ttu-id="5db09-328">次の図は、常にバイパスモードの発信通話に関する SIP のはしごを示しています。ユーザーは外部であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-328">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-12.png)

<span data-ttu-id="5db09-330">次の表は、ダイレクトルーティングサービスによって送信された X ミリ秒のヘッダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-330">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="5db09-331">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5db09-331">Parameter</span></span> |   <span data-ttu-id="5db09-332">説明</span><span class="sxs-lookup"><span data-stu-id="5db09-332">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="5db09-333">招待 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-333">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="5db09-334">オンラインボイスルーティングポリシーで定義された SBC のターゲット名は、要求 URI で送信されます。</span><span class="sxs-lookup"><span data-stu-id="5db09-334">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="5db09-335">X--UserLocation: external</span><span class="sxs-lookup"><span data-stu-id="5db09-335">X-MS-UserLocation: external</span></span> | <span data-ttu-id="5db09-336">このフィールドは、ユーザーが企業ネットワークの外部にあることを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-336">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="5db09-337">MediaPath: proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-337">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="5db09-338">クライアントがターゲット SBC にどの SBC を通過する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5db09-338">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="5db09-339">この例では、常にバイパスしており、クライアントは外部です。</span><span class="sxs-lookup"><span data-stu-id="5db09-339">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="5db09-340">着信通話とユーザーは外部であり、常にバイパスする</span><span class="sxs-lookup"><span data-stu-id="5db09-340">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="5db09-341">モード</span><span class="sxs-lookup"><span data-stu-id="5db09-341">Mode</span></span> | <span data-ttu-id="5db09-342">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5db09-342">User</span></span> | <span data-ttu-id="5db09-343">サイト</span><span class="sxs-lookup"><span data-stu-id="5db09-343">Site</span></span> |  <span data-ttu-id="5db09-344">通話の方向</span><span class="sxs-lookup"><span data-stu-id="5db09-344">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="5db09-345">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="5db09-345">AlwaysBypass</span></span> |  <span data-ttu-id="5db09-346">外部</span><span class="sxs-lookup"><span data-stu-id="5db09-346">External</span></span> |  <span data-ttu-id="5db09-347">該当なし</span><span class="sxs-lookup"><span data-stu-id="5db09-347">N/A</span></span> |   <span data-ttu-id="5db09-348">トラフィック</span><span class="sxs-lookup"><span data-stu-id="5db09-348">Inbound</span></span> |

<span data-ttu-id="5db09-349">着信通話の場合、直接ルーティングに接続された SBC は、ユーザーの場所が外部である場合は、再招待を送信する必要があります (既定では、ローカルメディア候補は常に提供されています)。</span><span class="sxs-lookup"><span data-stu-id="5db09-349">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="5db09-350">X-MediaPath は、指定されたレコードルートと SBC ユーザーに基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="5db09-350">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="5db09-351">次の図は、常にバイパスモードの着信呼び出しに対する SIP のはしごを示しています。また、ユーザーは外部であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-351">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="5db09-353">ローカルユーザーモードに対してのみ</span><span class="sxs-lookup"><span data-stu-id="5db09-353">Only for local users mode</span></span>

<span data-ttu-id="5db09-354">ターゲット SBC のローカルメディア候補は、ユーザーが SBC と同じ場所にいる場合にのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="5db09-354">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="5db09-355">それ以外の場合、メディアはプロキシ SBC の内部または外部 IP 経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="5db09-355">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="5db09-356">次のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5db09-356">The following scenarios are described:</span></span>

- [<span data-ttu-id="5db09-357">発信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="5db09-357">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="5db09-358">着信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="5db09-358">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="5db09-359">ユーザーは SBC と同じ場所にありませんが、企業ネットワーク内にある</span><span class="sxs-lookup"><span data-stu-id="5db09-359">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="5db09-360">着信通話とユーザーは内部にありますが、SBC と同じ場所にありません。</span><span class="sxs-lookup"><span data-stu-id="5db09-360">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="5db09-361">次の表は、エンドユーザーによる構成とアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-361">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="5db09-362">ユーザーの物理的な場所</span><span class="sxs-lookup"><span data-stu-id="5db09-362">User physical location</span></span> |  <span data-ttu-id="5db09-363">ユーザーが電話番号を発信または受信した場合</span><span class="sxs-lookup"><span data-stu-id="5db09-363">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="5db09-364">ユーザの電話番号</span><span class="sxs-lookup"><span data-stu-id="5db09-364">User phone number</span></span> | <span data-ttu-id="5db09-365">オンラインボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="5db09-365">Online Voice Routing Policy</span></span> |   <span data-ttu-id="5db09-366">SBC 用に構成されたモード</span><span class="sxs-lookup"><span data-stu-id="5db09-366">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5db09-367">ベトナム</span><span class="sxs-lookup"><span data-stu-id="5db09-367">Vietnam</span></span> | <span data-ttu-id="5db09-368">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="5db09-368">+84 4 3926  3000</span></span> |  <span data-ttu-id="5db09-369">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="5db09-369">+84 4 5555 5555</span></span> | <span data-ttu-id="5db09-370">優先度 1:\+^ 84 ({9}\d) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-370">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="5db09-371">優先度 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5db09-371">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="5db09-372">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="5db09-372">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5db09-373">発信通話とユーザーは、ローカルユーザーに対してのみ、SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="5db09-373">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5db09-374">モード</span><span class="sxs-lookup"><span data-stu-id="5db09-374">Mode</span></span> | <span data-ttu-id="5db09-375">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5db09-375">User</span></span> | <span data-ttu-id="5db09-376">サイト</span><span class="sxs-lookup"><span data-stu-id="5db09-376">Site</span></span> | <span data-ttu-id="5db09-377">通話の方向</span><span class="sxs-lookup"><span data-stu-id="5db09-377">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5db09-378">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5db09-378">OnlyForLocalUsers</span></span> |   <span data-ttu-id="5db09-379">内部</span><span class="sxs-lookup"><span data-stu-id="5db09-379">Internal</span></span> |<span data-ttu-id="5db09-380">SBC と同じ</span><span class="sxs-lookup"><span data-stu-id="5db09-380">Same as SBC</span></span>   | <span data-ttu-id="5db09-381">発信</span><span class="sxs-lookup"><span data-stu-id="5db09-381">Outbound</span></span> |

<span data-ttu-id="5db09-382">次の図は、OnlyForLocalUsers モードを使った発信通話と、ユーザーが SBC と同じ場所にいることを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-382">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="5db09-383">これは、[ユーザーが SBC と同じ場所にいるとき](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)の、[送信中の通話と同じフローを示します。</span><span class="sxs-lookup"><span data-stu-id="5db09-383">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5db09-385">着信通話とユーザーは、ローカルユーザーに対してのみ、SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="5db09-385">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5db09-386">モード</span><span class="sxs-lookup"><span data-stu-id="5db09-386">Mode</span></span> | <span data-ttu-id="5db09-387">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5db09-387">User</span></span> | <span data-ttu-id="5db09-388">サイト</span><span class="sxs-lookup"><span data-stu-id="5db09-388">Site</span></span> | <span data-ttu-id="5db09-389">通話の方向</span><span class="sxs-lookup"><span data-stu-id="5db09-389">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5db09-390">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5db09-390">OnlyForLocalUsers</span></span> |   <span data-ttu-id="5db09-391">内部</span><span class="sxs-lookup"><span data-stu-id="5db09-391">Internal</span></span> | <span data-ttu-id="5db09-392">SBC と同じ</span><span class="sxs-lookup"><span data-stu-id="5db09-392">Same as SBC</span></span> | <span data-ttu-id="5db09-393">トラフィック</span><span class="sxs-lookup"><span data-stu-id="5db09-393">Inbound</span></span> |

<span data-ttu-id="5db09-394">次の図は、OnlyForLocalUsers モードを使った着信通話と、ユーザーが SBC と同じ場所にいることを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-394">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="5db09-395">これは、[ユーザーが SBC と同じ場所にいるときに、着信通話](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)に表示されるフローと同じです。</span><span class="sxs-lookup"><span data-stu-id="5db09-395">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="5db09-397">ユーザーは SBC と同じ場所にありませんが、社内ネットワーク内にあるのはローカルユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="5db09-397">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="5db09-398">モード</span><span class="sxs-lookup"><span data-stu-id="5db09-398">Mode</span></span> | <span data-ttu-id="5db09-399">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5db09-399">User</span></span> | <span data-ttu-id="5db09-400">サイト</span><span class="sxs-lookup"><span data-stu-id="5db09-400">Site</span></span> |<span data-ttu-id="5db09-401">通話の方向</span><span class="sxs-lookup"><span data-stu-id="5db09-401">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5db09-402">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5db09-402">OnlyForLocalUsers</span></span>  | <span data-ttu-id="5db09-403">内部</span><span class="sxs-lookup"><span data-stu-id="5db09-403">Internal</span></span> |   <span data-ttu-id="5db09-404">SBC と異なる</span><span class="sxs-lookup"><span data-stu-id="5db09-404">Different from SBC</span></span> | <span data-ttu-id="5db09-405">発信</span><span class="sxs-lookup"><span data-stu-id="5db09-405">Outbound</span></span> |

<span data-ttu-id="5db09-406">直接ルーティングでは、SBC で構成されたユーザーとモードの報告された場所に基づいて、X-MediaPath が計算されます。</span><span class="sxs-lookup"><span data-stu-id="5db09-406">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="5db09-407">次の図は、OnlyForLocalUsers モードを使った発信通話と、SBC と同じ場所にない内部ユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-407">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5db09-409">着信通話とユーザーは内部ですが、ローカルユーザーのみを含む SBC と同じ場所にありません。</span><span class="sxs-lookup"><span data-stu-id="5db09-409">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5db09-410">モード</span><span class="sxs-lookup"><span data-stu-id="5db09-410">Mode</span></span> |    <span data-ttu-id="5db09-411">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5db09-411">User</span></span> |  <span data-ttu-id="5db09-412">サイト</span><span class="sxs-lookup"><span data-stu-id="5db09-412">Site</span></span> |  <span data-ttu-id="5db09-413">通話の方向</span><span class="sxs-lookup"><span data-stu-id="5db09-413">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5db09-414">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5db09-414">OnlyForLocalUsers</span></span> | <span data-ttu-id="5db09-415">内部</span><span class="sxs-lookup"><span data-stu-id="5db09-415">Internal</span></span> |    <span data-ttu-id="5db09-416">SBC と異なる</span><span class="sxs-lookup"><span data-stu-id="5db09-416">Different from SBC</span></span> |    <span data-ttu-id="5db09-417">トラフィック</span><span class="sxs-lookup"><span data-stu-id="5db09-417">Inbound</span></span> |

<span data-ttu-id="5db09-418">次の図は、OnlyForLocalUsers モードの着信呼び出しと、SBC と同じ場所にない内部ユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="5db09-418">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-17.png)









