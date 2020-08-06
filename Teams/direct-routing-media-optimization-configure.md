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
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576989"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="06c0d-103">直接ルーティング用のローカルメディア最適化を構成する</span><span class="sxs-lookup"><span data-stu-id="06c0d-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="06c0d-104">ローカルメディア最適化の構成は、場所に基づくルーティングや動的な緊急通話など、他のクラウド音声機能に共通するネットワーク設定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="06c0d-105">ネットワーク領域、ネットワークサイト、ネットワークサブネット、および信頼された IP アドレスの詳細については、「[クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06c0d-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="06c0d-106">ローカルメディア最適化を構成する前に、「[直接ルーティング用のローカルメディアの最適化](direct-routing-media-optimization.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="06c0d-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="06c0d-107">ローカルメディア最適化を構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="06c0d-108">Teams 管理センターまたは PowerShell を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="06c0d-109">詳細については、「[ネットワークトポロジを管理する](manage-your-network-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06c0d-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="06c0d-110">ユーザーと SBC サイトを構成します (この記事で説明します)。</span><span class="sxs-lookup"><span data-stu-id="06c0d-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="06c0d-111">(SBC ベンダー仕様に従って) ローカルメディア最適化用に SBCs を構成します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="06c0d-112">次の図は、この記事の例で使用されているネットワークセットアップを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="06c0d-113">![例のネットワークセットアップを示す図](media/direct-routing-media-op-9.png "ネットワークセットアップ例")</span><span class="sxs-lookup"><span data-stu-id="06c0d-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="06c0d-114">ユーザーと SBC サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="06c0d-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="06c0d-115">ユーザーと SBC サイトを構成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="06c0d-116">[外部の信頼できる IP アドレスを管理](#manage-external-trusted-ip-addresses)する。</span><span class="sxs-lookup"><span data-stu-id="06c0d-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="06c0d-117">ネットワークの領域、ネットワークサイト、ネットワークサブネットを構成して、[ネットワークトポロジを定義](#define-the-network-topology)します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="06c0d-118">関連するモードとプロキシの SBC 値を使って、サイトに SBC (s) を割り当てることで[、仮想ネットワークトポロジを定義](#define-the-virtual-network-topology)します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="06c0d-119">SBC ベンダー仕様に従って、ローカルメディア最適化用に SBC を構成する</span><span class="sxs-lookup"><span data-stu-id="06c0d-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="06c0d-120">この記事では、Microsoft コンポーネントの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="06c0d-121">SBC 構成の詳細については、SBC ベンダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="06c0d-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="06c0d-122">ローカルメディア最適化は、次の SBC ベンダーによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="06c0d-123">仕入先</span><span class="sxs-lookup"><span data-stu-id="06c0d-123">Vendor</span></span> | <span data-ttu-id="06c0d-124">Product</span><span class="sxs-lookup"><span data-stu-id="06c0d-124">Product</span></span> |    <span data-ttu-id="06c0d-125">ソフトウェアのバージョン</span><span class="sxs-lookup"><span data-stu-id="06c0d-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="06c0d-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="06c0d-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="06c0d-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="06c0d-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="06c0d-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="06c0d-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="06c0d-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="06c0d-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="06c0d-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="06c0d-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="06c0d-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="06c0d-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="06c0d-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="06c0d-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="06c0d-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="06c0d-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="06c0d-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="06c0d-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="06c0d-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="06c0d-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="06c0d-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="06c0d-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="06c0d-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="06c0d-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="06c0d-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="06c0d-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="06c0d-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="06c0d-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="06c0d-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="06c0d-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="06c0d-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="06c0d-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="06c0d-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="06c0d-142">7.20A.256</span></span> |
| [<span data-ttu-id="06c0d-143">リボンの SBC コア</span><span class="sxs-lookup"><span data-stu-id="06c0d-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="06c0d-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="06c0d-144">SBC 5110</span></span>         | <span data-ttu-id="06c0d-145">8.2</span><span class="sxs-lookup"><span data-stu-id="06c0d-145">8.2</span></span>  |
|            |  <span data-ttu-id="06c0d-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="06c0d-146">SBC 5210</span></span>         | <span data-ttu-id="06c0d-147">8.2</span><span class="sxs-lookup"><span data-stu-id="06c0d-147">8.2</span></span>  |
|            |  <span data-ttu-id="06c0d-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="06c0d-148">SBC 5400</span></span>         | <span data-ttu-id="06c0d-149">8.2</span><span class="sxs-lookup"><span data-stu-id="06c0d-149">8.2</span></span>  |
|            |  <span data-ttu-id="06c0d-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="06c0d-150">SBC 7000</span></span>         | <span data-ttu-id="06c0d-151">8.2</span><span class="sxs-lookup"><span data-stu-id="06c0d-151">8.2</span></span>  |
|            |  <span data-ttu-id="06c0d-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="06c0d-152">SBC SWe</span></span>          | <span data-ttu-id="06c0d-153">8.2</span><span class="sxs-lookup"><span data-stu-id="06c0d-153">8.2</span></span>  |
| [<span data-ttu-id="06c0d-154">リボンの SBC エッジ</span><span class="sxs-lookup"><span data-stu-id="06c0d-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="06c0d-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="06c0d-155">SBC SWe Lite</span></span> | <span data-ttu-id="06c0d-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="06c0d-156">8.1.5</span></span> |
|               | <span data-ttu-id="06c0d-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="06c0d-157">SBC 1000</span></span> | <span data-ttu-id="06c0d-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="06c0d-158">8.1.5</span></span>  |
|               | <span data-ttu-id="06c0d-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="06c0d-159">SBC 2000</span></span> | <span data-ttu-id="06c0d-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="06c0d-160">8.1.5</span></span>  |
| [<span data-ttu-id="06c0d-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="06c0d-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="06c0d-162">anynode</span><span class="sxs-lookup"><span data-stu-id="06c0d-162">anynode</span></span>          | <span data-ttu-id="06c0d-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="06c0d-163">4.0.1+</span></span> |
| [<span data-ttu-id="06c0d-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="06c0d-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="06c0d-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="06c0d-165">AP 1100</span></span> | <span data-ttu-id="06c0d-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="06c0d-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="06c0d-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="06c0d-167">AP 3900</span></span> | <span data-ttu-id="06c0d-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="06c0d-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="06c0d-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="06c0d-169">AP 4600</span></span> | <span data-ttu-id="06c0d-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="06c0d-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="06c0d-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="06c0d-171">AP 6300</span></span> | <span data-ttu-id="06c0d-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="06c0d-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="06c0d-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="06c0d-173">AP 6350</span></span> | <span data-ttu-id="06c0d-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="06c0d-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="06c0d-175">VME</span><span class="sxs-lookup"><span data-stu-id="06c0d-175">VME</span></span>     | <span data-ttu-id="06c0d-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="06c0d-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="06c0d-177">外部の信頼できる IP アドレスを管理する</span><span class="sxs-lookup"><span data-stu-id="06c0d-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="06c0d-178">外部の信頼できる Ip は、エンタープライズネットワークのインターネット外部 Ip です。</span><span class="sxs-lookup"><span data-stu-id="06c0d-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="06c0d-179">これらの IP アドレスは、microsoft Teams クライアントが Microsoft 365 に接続したときに使用される IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="06c0d-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="06c0d-180">ユーザーがローカルメディア最適化を使用しているサイトごとに、これらの外部 Ip を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="06c0d-181">各サイトのパブリック IP アドレスを追加するには、CsTenantTrustedIPAddress コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="06c0d-182">1つのテナントに対して無制限の数の信頼できる IP アドレスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="06c0d-183">Microsoft 365 によって表示される外部 Ip が IPv4 アドレスと IPv6 アドレスの両方である場合は、両方の種類の IP アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="06c0d-184">IPv4 の場合は、マスク32を使用します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="06c0d-185">IPv6 の場合は、マスク128を使用します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="06c0d-186">コマンドレットで異なる MaskBits を指定することで、個々の外部 IP アドレスと外部 IP サブネットの両方を追加できます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="06c0d-187">信頼された IP アドレスを追加する例。</span><span class="sxs-lookup"><span data-stu-id="06c0d-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="06c0d-188">ネットワークトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="06c0d-188">Define the network topology</span></span>

<span data-ttu-id="06c0d-189">このセクションでは、ネットワークトポロジのネットワーク領域、ネットワークサイト、ネットワークサブネットを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="06c0d-190">すべてのパラメーターは大文字と小文字を区別するため、セットアップ時に使用したのと同じケースを確実に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="06c0d-191">(たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は、別のサイトとして扱われます)。</span><span class="sxs-lookup"><span data-stu-id="06c0d-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="06c0d-192">ネットワーク領域を定義する</span><span class="sxs-lookup"><span data-stu-id="06c0d-192">Define network regions</span></span>

<span data-ttu-id="06c0d-193">ネットワーク領域を定義するには、CsTenantNetworkRegion コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="06c0d-194">RegionID パラメーターは、地域の地理を表す論理名であり、依存関係または制限がありません。</span><span class="sxs-lookup"><span data-stu-id="06c0d-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="06c0d-195">CentralSite <site ID> パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="06c0d-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="06c0d-196">次の例では、APAC という名前のネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="06c0d-197">ネットワークサイトを定義する</span><span class="sxs-lookup"><span data-stu-id="06c0d-197">Define network sites</span></span>

<span data-ttu-id="06c0d-198">ネットワークサイトを定義するには、CsTenantNetworkSite コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="06c0d-199">各ネットワークサイトは、ネットワーク領域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="06c0d-200">次の例では、APAC 地域で3つの新しいネットワークサイト、ベトナム、インドネシア、シンガポールを作成します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="06c0d-201">ネットワークサブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="06c0d-201">Define network subnets</span></span>

<span data-ttu-id="06c0d-202">ネットワークサブネットを定義してネットワークサイトに関連付けるには、CsTenantNetworkSubnet コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="06c0d-203">各ネットワークサブネットは、1つのサイトにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="06c0d-204">次の例では、3つのネットワークサブネットを定義し、それをベトナム、インドネシア、シンガポールという3つのネットワークサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="06c0d-205">仮想ネットワークトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="06c0d-205">Define the virtual network topology</span></span> 

<span data-ttu-id="06c0d-206">まず、テナント管理者は、CsOnlinePSTNGateway コマンドレットを使用して、関連する SBC ごとに新しい SBC 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="06c0d-207">テナント管理者は、CsOnlinePSTNGateway コマンドレットを使用して、PSTN ゲートウェイオブジェクトのネットワークサイトを指定することで、仮想ネットワークトポロジを定義します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="06c0d-208">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="06c0d-208">Note the following:</span></span> 
   - <span data-ttu-id="06c0d-209">顧客が1つの SBC を使用している場合は、-ProxySBC パラメーターは必須 $null または SBC FQDN 値 (集中型 trunks シナリオを持つ集中型 SBC) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="06c0d-210">ローカルメディアの最適化をサポートするには、-MediaBypass ・・・・・バイのパラメーターが $true に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="06c0d-211">SBC に-BypassMode パラメーターが設定されていない場合、X ミリ秒のヘッダーは送信されません。</span><span class="sxs-lookup"><span data-stu-id="06c0d-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="06c0d-212">すべてのパラメーターは大文字と小文字を区別するため、セットアップ時に使用したのと同じケースを確実に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="06c0d-213">(たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は、別のサイトとして扱われます)。</span><span class="sxs-lookup"><span data-stu-id="06c0d-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="06c0d-214">次の例では、APAC 領域の2つの SBCs をネットワークサイトに追加します。これは、モードが常にバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="06c0d-215">注: ローカルメディア最適化と位置情報に基づくルーティング (LBR) を同時に構成するときに中断のない操作を行うには、GatewaySiteLbrEnabled パラメーターを各下流の SBC の $true に設定して、下位の SBCs を LBR に対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="06c0d-216">(この設定はプロキシ SBC には必須ではありません)。</span><span class="sxs-lookup"><span data-stu-id="06c0d-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="06c0d-217">上記の情報に基づいて、次の表に示すように、直接ルーティングを行うと、SIP の招待に対しては3つの専用 SIP ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="06c0d-218">BypassMode が定義されている場合に、招待と再招待の際に直接ルーティングで導入された X-MS ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="06c0d-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="06c0d-219">ヘッダー名</span><span class="sxs-lookup"><span data-stu-id="06c0d-219">Header name</span></span> | <span data-ttu-id="06c0d-220">Values</span><span class="sxs-lookup"><span data-stu-id="06c0d-220">Values</span></span> | <span data-ttu-id="06c0d-221">注釈</span><span class="sxs-lookup"><span data-stu-id="06c0d-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="06c0d-222">エックス--UserLocation</span><span class="sxs-lookup"><span data-stu-id="06c0d-222">X-MS-UserLocation</span></span> | <span data-ttu-id="06c0d-223">内部/外部</span><span class="sxs-lookup"><span data-stu-id="06c0d-223">internal/external</span></span> | <span data-ttu-id="06c0d-224">ユーザーが内部と外部のどちらであるかを示します</span><span class="sxs-lookup"><span data-stu-id="06c0d-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="06c0d-225">要求-URI 招待 sip: + 84439263000@VNsbc.contoso.com SIP/2.0</span><span class="sxs-lookup"><span data-stu-id="06c0d-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="06c0d-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="06c0d-226">SBC FQDN</span></span> | <span data-ttu-id="06c0d-227">SBC が直接ルーティングに直接接続されていない場合でも、通話の対象となる FQDN</span><span class="sxs-lookup"><span data-stu-id="06c0d-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="06c0d-228">MediaPath</span><span class="sxs-lookup"><span data-stu-id="06c0d-228">X-MS-MediaPath</span></span> | <span data-ttu-id="06c0d-229">例: proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="06c0d-230">ユーザーとターゲットの間のメディアパスに使用する SBCs の順序です。</span><span class="sxs-lookup"><span data-stu-id="06c0d-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="06c0d-231">最後の SBC は常に最終です</span><span class="sxs-lookup"><span data-stu-id="06c0d-231">The final SBC is always last</span></span> |
| <span data-ttu-id="06c0d-232">-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="06c0d-232">X-MS-UserSite</span></span> | <span data-ttu-id="06c0d-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="06c0d-233">usersiteID</span></span> | <span data-ttu-id="06c0d-234">テナント管理者によって定義された文字列</span><span class="sxs-lookup"><span data-stu-id="06c0d-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="06c0d-235">コールフロー</span><span class="sxs-lookup"><span data-stu-id="06c0d-235">Call flows</span></span> 

<span data-ttu-id="06c0d-236">次に、2つのモードのコールフローを示します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="06c0d-237">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="06c0d-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="06c0d-238">ローカルユーザーのみ</span><span class="sxs-lookup"><span data-stu-id="06c0d-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="06c0d-239">常にバイパスモード</span><span class="sxs-lookup"><span data-stu-id="06c0d-239">Always Bypass mode</span></span>

<span data-ttu-id="06c0d-240">[常にバイパス] モードは、構成するのに最も簡単なオプションです。</span><span class="sxs-lookup"><span data-stu-id="06c0d-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="06c0d-241">テナント管理者は、すべてのユーザーに対して1つのサイトを構成することができます。すべてのサイトからすべての SBCs に到達可能である場合は、SBCs になります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="06c0d-242">次のシナリオでは、この例では常にバイパスモードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="06c0d-243">発信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="06c0d-244">着信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="06c0d-245">発信通話とユーザーは外部です</span><span class="sxs-lookup"><span data-stu-id="06c0d-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="06c0d-246">着信通話とユーザーは外部</span><span class="sxs-lookup"><span data-stu-id="06c0d-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="06c0d-247">次の表は、例で使用される FQDN と IP アドレスを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="06c0d-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="06c0d-248">FQDN</span></span> | <span data-ttu-id="06c0d-249">SBC 外部 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="06c0d-249">SBC external IP address</span></span> | <span data-ttu-id="06c0d-250">SBC 内部 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="06c0d-250">SBC internal IP Address</span></span> | <span data-ttu-id="06c0d-251">内部サブネット</span><span class="sxs-lookup"><span data-stu-id="06c0d-251">Internal subnet</span></span> | <span data-ttu-id="06c0d-252">場所</span><span class="sxs-lookup"><span data-stu-id="06c0d-252">Location</span></span> | <span data-ttu-id="06c0d-253">外部 NAT (信頼できる IP)</span><span class="sxs-lookup"><span data-stu-id="06c0d-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="06c0d-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="06c0d-255">なし</span><span class="sxs-lookup"><span data-stu-id="06c0d-255">None</span></span> | <span data-ttu-id="06c0d-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="06c0d-256">192.168.1.5</span></span> | <span data-ttu-id="06c0d-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="06c0d-257">192.168.1.0/24</span></span> | <span data-ttu-id="06c0d-258">ベトナム</span><span class="sxs-lookup"><span data-stu-id="06c0d-258">Vietnam</span></span> | <span data-ttu-id="06c0d-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="06c0d-259">172.16.240.110</span></span> |
| <span data-ttu-id="06c0d-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="06c0d-261">なし</span><span class="sxs-lookup"><span data-stu-id="06c0d-261">None</span></span> | <span data-ttu-id="06c0d-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="06c0d-262">192.168.2.5</span></span> | <span data-ttu-id="06c0d-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="06c0d-263">192.168.2.0/24</span></span> | <span data-ttu-id="06c0d-264">インドネシア</span><span class="sxs-lookup"><span data-stu-id="06c0d-264">Indonesia</span></span> | <span data-ttu-id="06c0d-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="06c0d-265">172.16.240.120</span></span> |
| <span data-ttu-id="06c0d-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="06c0d-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="06c0d-267">172.16.240.133</span></span> | <span data-ttu-id="06c0d-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="06c0d-268">192.168.3.5</span></span> | <span data-ttu-id="06c0d-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="06c0d-269">192.168.3.0/24</span></span> | <span data-ttu-id="06c0d-270">シンガポール</span><span class="sxs-lookup"><span data-stu-id="06c0d-270">Singapore</span></span> | <span data-ttu-id="06c0d-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="06c0d-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="06c0d-272">発信通話とユーザーは、常にバイパスの SBC と同じ場所にあります</span><span class="sxs-lookup"><span data-stu-id="06c0d-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="06c0d-273">モード</span><span class="sxs-lookup"><span data-stu-id="06c0d-273">Mode</span></span> |    <span data-ttu-id="06c0d-274">ユーザー</span><span class="sxs-lookup"><span data-stu-id="06c0d-274">User</span></span> |  <span data-ttu-id="06c0d-275">場所</span><span class="sxs-lookup"><span data-stu-id="06c0d-275">Location</span></span> |  <span data-ttu-id="06c0d-276">通話の方向</span><span class="sxs-lookup"><span data-stu-id="06c0d-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="06c0d-277">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="06c0d-277">AlwaysBypass</span></span> |    <span data-ttu-id="06c0d-278">内部</span><span class="sxs-lookup"><span data-stu-id="06c0d-278">Internal</span></span> |  <span data-ttu-id="06c0d-279">SBC と同じサイト</span><span class="sxs-lookup"><span data-stu-id="06c0d-279">The same site as SBC</span></span> |  <span data-ttu-id="06c0d-280">発信</span><span class="sxs-lookup"><span data-stu-id="06c0d-280">Outbound</span></span> |

<span data-ttu-id="06c0d-281">次の表は、エンドユーザーの構成とアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="06c0d-282">ユーザーの物理的な場所</span><span class="sxs-lookup"><span data-stu-id="06c0d-282">User physical location</span></span>| <span data-ttu-id="06c0d-283">ユーザーが電話番号を発信または受信した場合</span><span class="sxs-lookup"><span data-stu-id="06c0d-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="06c0d-284">ユーザの電話番号</span><span class="sxs-lookup"><span data-stu-id="06c0d-284">User phone number</span></span>  | <span data-ttu-id="06c0d-285">オンラインボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="06c0d-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="06c0d-286">SBC 用に構成されたモード</span><span class="sxs-lookup"><span data-stu-id="06c0d-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="06c0d-287">ベトナム</span><span class="sxs-lookup"><span data-stu-id="06c0d-287">Vietnam</span></span> | <span data-ttu-id="06c0d-288">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="06c0d-288">+84 4 3926 3000</span></span> | <span data-ttu-id="06c0d-289">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="06c0d-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="06c0d-290">優先度 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="06c0d-291">優先度 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="06c0d-292">VNsbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="06c0d-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="06c0d-293">proxysbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="06c0d-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="06c0d-294">次の図は、常にバイパスモードを使用した発信通話の SIP のはしごと、SBC と同じ場所にいるユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="06c0d-295">![発信通話を示す図](media/direct-routing-media-op-10.png "発信通話")</span><span class="sxs-lookup"><span data-stu-id="06c0d-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="06c0d-296">次の表は、直接ルーティングによって送信された X-MS ヘッダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="06c0d-297">パラメーター</span><span class="sxs-lookup"><span data-stu-id="06c0d-297">Parameter</span></span> | <span data-ttu-id="06c0d-298">説明</span><span class="sxs-lookup"><span data-stu-id="06c0d-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="06c0d-299">招待 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="06c0d-300">オンラインボイスルーティングポリシーで定義された SBC のターゲット FQDN は、要求 URI で送信されます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="06c0d-301">X--UserLocation: internal</span><span class="sxs-lookup"><span data-stu-id="06c0d-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="06c0d-302">このフィールドは、ユーザーが企業ネットワーク内に配置されていることを示しています</span><span class="sxs-lookup"><span data-stu-id="06c0d-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="06c0d-303">MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="06c0d-304">クライアントがターゲット SBC にどの SBC を通過する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="06c0d-305">この例では、常にバイパスしているため、クライアントはヘッダーで唯一の名前として送信されるターゲット名です。</span><span class="sxs-lookup"><span data-stu-id="06c0d-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="06c0d-306">----UserSite: ベトナム</span><span class="sxs-lookup"><span data-stu-id="06c0d-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="06c0d-307">ユーザーが配置されているサイトで示されているフィールド。</span><span class="sxs-lookup"><span data-stu-id="06c0d-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="06c0d-308">着信通話とユーザーは、常にバイパスの SBC と同じ場所にあります</span><span class="sxs-lookup"><span data-stu-id="06c0d-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="06c0d-309">モード</span><span class="sxs-lookup"><span data-stu-id="06c0d-309">Mode</span></span> |    <span data-ttu-id="06c0d-310">ユーザー</span><span class="sxs-lookup"><span data-stu-id="06c0d-310">User</span></span> |  <span data-ttu-id="06c0d-311">場所</span><span class="sxs-lookup"><span data-stu-id="06c0d-311">Location</span></span> |  <span data-ttu-id="06c0d-312">通話の方向</span><span class="sxs-lookup"><span data-stu-id="06c0d-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="06c0d-313">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="06c0d-313">AlwaysBypass</span></span> |    <span data-ttu-id="06c0d-314">内部</span><span class="sxs-lookup"><span data-stu-id="06c0d-314">Internal</span></span> | <span data-ttu-id="06c0d-315">SBC と同じサイト</span><span class="sxs-lookup"><span data-stu-id="06c0d-315">The same site as SBC</span></span> | <span data-ttu-id="06c0d-316">トラフィック</span><span class="sxs-lookup"><span data-stu-id="06c0d-316">Inbound</span></span> |


<span data-ttu-id="06c0d-317">着信通話では、ユーザーの場所が不明であり、SBC はユーザーがどこにいるかを推測する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="06c0d-318">推測が正しくない場合は、再招待が必要になります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="06c0d-319">この例では、ユーザーが内部であることを前提としています。メディアは直接流れることができ、それ以上の操作は必要ありません (再招待)。</span><span class="sxs-lookup"><span data-stu-id="06c0d-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="06c0d-320">ダイレクトルーティングサービスに接続された SBC は、レコードルーティングと連絡先フィールドを提供して、送信元の SBC の位置情報を報告します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="06c0d-321">これらのフィールドに基づいて、メディアパスはダイレクトルーティングによって計算されます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="06c0d-322">注: ユーザーが複数のエンドポイントを持つことができる場合、183のサポートはできません。</span><span class="sxs-lookup"><span data-stu-id="06c0d-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="06c0d-323">この場合、直接ルーティングでは常に180呼び出しが使用されます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="06c0d-324">次の図は、Always バイパスモードの着信呼び出しでの SIP のはしごを示しています。ユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="06c0d-326">発信通話とユーザーは外部であり、常にバイパスする</span><span class="sxs-lookup"><span data-stu-id="06c0d-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="06c0d-327">モード</span><span class="sxs-lookup"><span data-stu-id="06c0d-327">Mode</span></span> |    <span data-ttu-id="06c0d-328">ユーザー</span><span class="sxs-lookup"><span data-stu-id="06c0d-328">User</span></span> |  <span data-ttu-id="06c0d-329">サイト</span><span class="sxs-lookup"><span data-stu-id="06c0d-329">Site</span></span> |  <span data-ttu-id="06c0d-330">通話の方向</span><span class="sxs-lookup"><span data-stu-id="06c0d-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="06c0d-331">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="06c0d-331">AlwaysBypass</span></span> |  <span data-ttu-id="06c0d-332">外部</span><span class="sxs-lookup"><span data-stu-id="06c0d-332">External</span></span> |  <span data-ttu-id="06c0d-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="06c0d-333">N/A</span></span> | <span data-ttu-id="06c0d-334">発信</span><span class="sxs-lookup"><span data-stu-id="06c0d-334">Outbound</span></span> |


<span data-ttu-id="06c0d-335">次の図は、常にバイパスモードの発信通話に関する SIP のはしごを示しています。ユーザーは外部であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-12.png)

<span data-ttu-id="06c0d-337">次の表は、ダイレクトルーティングサービスによって送信された X ミリ秒のヘッダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="06c0d-338">パラメーター</span><span class="sxs-lookup"><span data-stu-id="06c0d-338">Parameter</span></span> |   <span data-ttu-id="06c0d-339">説明</span><span class="sxs-lookup"><span data-stu-id="06c0d-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="06c0d-340">招待 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="06c0d-341">オンラインボイスルーティングポリシーで定義された SBC のターゲット FQDN は、要求 URI で送信されます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="06c0d-342">X--UserLocation: external</span><span class="sxs-lookup"><span data-stu-id="06c0d-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="06c0d-343">このフィールドは、ユーザーが企業ネットワークの外部にあることを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="06c0d-344">MediaPath: proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="06c0d-345">クライアントがターゲット SBC にどの SBC を通過する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="06c0d-346">この例では、常にバイパスしており、クライアントは外部です。</span><span class="sxs-lookup"><span data-stu-id="06c0d-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="06c0d-347">着信通話とユーザーは外部であり、常にバイパスする</span><span class="sxs-lookup"><span data-stu-id="06c0d-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="06c0d-348">モード</span><span class="sxs-lookup"><span data-stu-id="06c0d-348">Mode</span></span> | <span data-ttu-id="06c0d-349">ユーザー</span><span class="sxs-lookup"><span data-stu-id="06c0d-349">User</span></span> | <span data-ttu-id="06c0d-350">サイト</span><span class="sxs-lookup"><span data-stu-id="06c0d-350">Site</span></span> |  <span data-ttu-id="06c0d-351">通話の方向</span><span class="sxs-lookup"><span data-stu-id="06c0d-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="06c0d-352">常にバイパス</span><span class="sxs-lookup"><span data-stu-id="06c0d-352">AlwaysBypass</span></span> |  <span data-ttu-id="06c0d-353">外部</span><span class="sxs-lookup"><span data-stu-id="06c0d-353">External</span></span> |  <span data-ttu-id="06c0d-354">該当なし</span><span class="sxs-lookup"><span data-stu-id="06c0d-354">N/A</span></span> |   <span data-ttu-id="06c0d-355">トラフィック</span><span class="sxs-lookup"><span data-stu-id="06c0d-355">Inbound</span></span> |

<span data-ttu-id="06c0d-356">着信通話の場合、直接ルーティングに接続された SBC は、ユーザーの場所が外部である場合は、再招待を送信する必要があります (既定では、ローカルメディア候補は常に提供されています)。</span><span class="sxs-lookup"><span data-stu-id="06c0d-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="06c0d-357">X-MediaPath は、指定されたレコードルートと SBC ユーザーに基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="06c0d-358">次の図は、常にバイパスモードの着信呼び出しに対する SIP のはしごを示しています。また、ユーザーは外部であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="06c0d-360">ローカルユーザーモードに対してのみ</span><span class="sxs-lookup"><span data-stu-id="06c0d-360">Only for local users mode</span></span>

<span data-ttu-id="06c0d-361">ターゲット SBC のローカルメディア候補は、ユーザーが SBC と同じ場所にいる場合にのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="06c0d-362">それ以外の場合、メディアはプロキシ SBC の内部または外部 IP 経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="06c0d-363">次のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="06c0d-364">発信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="06c0d-365">着信通話とユーザーは SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="06c0d-366">ユーザーは SBC と同じ場所にありませんが、企業ネットワーク内にある</span><span class="sxs-lookup"><span data-stu-id="06c0d-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="06c0d-367">着信通話とユーザーは内部にありますが、SBC と同じ場所にありません。</span><span class="sxs-lookup"><span data-stu-id="06c0d-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="06c0d-368">次の表は、エンドユーザーによる構成とアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="06c0d-369">ユーザーの物理的な場所</span><span class="sxs-lookup"><span data-stu-id="06c0d-369">User physical location</span></span> |  <span data-ttu-id="06c0d-370">ユーザーが電話番号を発信または受信した場合</span><span class="sxs-lookup"><span data-stu-id="06c0d-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="06c0d-371">ユーザの電話番号</span><span class="sxs-lookup"><span data-stu-id="06c0d-371">User phone number</span></span> | <span data-ttu-id="06c0d-372">オンラインボイスルーティングポリシー</span><span class="sxs-lookup"><span data-stu-id="06c0d-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="06c0d-373">SBC 用に構成されたモード</span><span class="sxs-lookup"><span data-stu-id="06c0d-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="06c0d-374">ベトナム</span><span class="sxs-lookup"><span data-stu-id="06c0d-374">Vietnam</span></span> | <span data-ttu-id="06c0d-375">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="06c0d-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="06c0d-376">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="06c0d-376">+84 4 5555 5555</span></span> | <span data-ttu-id="06c0d-377">優先度 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="06c0d-378">優先度 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06c0d-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="06c0d-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com –常にバイパス</span><span class="sxs-lookup"><span data-stu-id="06c0d-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="06c0d-380">発信通話とユーザーは、ローカルユーザーに対してのみ、SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="06c0d-381">モード</span><span class="sxs-lookup"><span data-stu-id="06c0d-381">Mode</span></span> | <span data-ttu-id="06c0d-382">ユーザー</span><span class="sxs-lookup"><span data-stu-id="06c0d-382">User</span></span> | <span data-ttu-id="06c0d-383">サイト</span><span class="sxs-lookup"><span data-stu-id="06c0d-383">Site</span></span> | <span data-ttu-id="06c0d-384">通話の方向</span><span class="sxs-lookup"><span data-stu-id="06c0d-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="06c0d-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="06c0d-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="06c0d-386">内部</span><span class="sxs-lookup"><span data-stu-id="06c0d-386">Internal</span></span> |<span data-ttu-id="06c0d-387">SBC と同じ</span><span class="sxs-lookup"><span data-stu-id="06c0d-387">Same as SBC</span></span>   | <span data-ttu-id="06c0d-388">発信</span><span class="sxs-lookup"><span data-stu-id="06c0d-388">Outbound</span></span> |

<span data-ttu-id="06c0d-389">次の図は、OnlyForLocalUsers モードを使った発信通話と、ユーザーが SBC と同じ場所にいることを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="06c0d-390">これは、[ユーザーが SBC と同じ場所にいるとき](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)の、[送信中の通話と同じフローを示します。</span><span class="sxs-lookup"><span data-stu-id="06c0d-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="06c0d-392">着信通話とユーザーは、ローカルユーザーに対してのみ、SBC と同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="06c0d-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="06c0d-393">モード</span><span class="sxs-lookup"><span data-stu-id="06c0d-393">Mode</span></span> | <span data-ttu-id="06c0d-394">ユーザー</span><span class="sxs-lookup"><span data-stu-id="06c0d-394">User</span></span> | <span data-ttu-id="06c0d-395">サイト</span><span class="sxs-lookup"><span data-stu-id="06c0d-395">Site</span></span> | <span data-ttu-id="06c0d-396">通話の方向</span><span class="sxs-lookup"><span data-stu-id="06c0d-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="06c0d-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="06c0d-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="06c0d-398">内部</span><span class="sxs-lookup"><span data-stu-id="06c0d-398">Internal</span></span> | <span data-ttu-id="06c0d-399">SBC と同じ</span><span class="sxs-lookup"><span data-stu-id="06c0d-399">Same as SBC</span></span> | <span data-ttu-id="06c0d-400">トラフィック</span><span class="sxs-lookup"><span data-stu-id="06c0d-400">Inbound</span></span> |

<span data-ttu-id="06c0d-401">次の図は、OnlyForLocalUsers モードを使った着信通話と、ユーザーが SBC と同じ場所にいることを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="06c0d-402">これは、[ユーザーが SBC と同じ場所にいるときに、着信通話](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)に表示されるフローと同じです。</span><span class="sxs-lookup"><span data-stu-id="06c0d-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="06c0d-404">ユーザーは SBC と同じ場所にありませんが、社内ネットワーク内にあるのはローカルユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="06c0d-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="06c0d-405">モード</span><span class="sxs-lookup"><span data-stu-id="06c0d-405">Mode</span></span> | <span data-ttu-id="06c0d-406">ユーザー</span><span class="sxs-lookup"><span data-stu-id="06c0d-406">User</span></span> | <span data-ttu-id="06c0d-407">サイト</span><span class="sxs-lookup"><span data-stu-id="06c0d-407">Site</span></span> |<span data-ttu-id="06c0d-408">通話の方向</span><span class="sxs-lookup"><span data-stu-id="06c0d-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="06c0d-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="06c0d-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="06c0d-410">内部</span><span class="sxs-lookup"><span data-stu-id="06c0d-410">Internal</span></span> |   <span data-ttu-id="06c0d-411">SBC と異なる</span><span class="sxs-lookup"><span data-stu-id="06c0d-411">Different from SBC</span></span> | <span data-ttu-id="06c0d-412">発信</span><span class="sxs-lookup"><span data-stu-id="06c0d-412">Outbound</span></span> |

<span data-ttu-id="06c0d-413">直接ルーティングでは、SBC で構成されたユーザーとモードの報告された場所に基づいて、X-MediaPath が計算されます。</span><span class="sxs-lookup"><span data-stu-id="06c0d-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="06c0d-414">次の図は、OnlyForLocalUsers モードを使った発信通話と、SBC と同じ場所にない内部ユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="06c0d-416">着信通話とユーザーは内部ですが、ローカルユーザーのみを含む SBC と同じ場所にありません。</span><span class="sxs-lookup"><span data-stu-id="06c0d-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="06c0d-417">モード</span><span class="sxs-lookup"><span data-stu-id="06c0d-417">Mode</span></span> |    <span data-ttu-id="06c0d-418">ユーザー</span><span class="sxs-lookup"><span data-stu-id="06c0d-418">User</span></span> |  <span data-ttu-id="06c0d-419">サイト</span><span class="sxs-lookup"><span data-stu-id="06c0d-419">Site</span></span> |  <span data-ttu-id="06c0d-420">通話の方向</span><span class="sxs-lookup"><span data-stu-id="06c0d-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="06c0d-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="06c0d-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="06c0d-422">内部</span><span class="sxs-lookup"><span data-stu-id="06c0d-422">Internal</span></span> |    <span data-ttu-id="06c0d-423">SBC と異なる</span><span class="sxs-lookup"><span data-stu-id="06c0d-423">Different from SBC</span></span> |    <span data-ttu-id="06c0d-424">トラフィック</span><span class="sxs-lookup"><span data-stu-id="06c0d-424">Inbound</span></span> |

<span data-ttu-id="06c0d-425">次の図は、OnlyForLocalUsers モードの着信呼び出しと、SBC と同じ場所にない内部ユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="06c0d-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP はしごを示す図](media/direct-routing-media-op-17.png)









