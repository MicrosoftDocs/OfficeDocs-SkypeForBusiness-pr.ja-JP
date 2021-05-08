---
title: 直接ルーティングのローカル メディアの最適化
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
description: 直接ルーティング用にローカル メディアの最適化を構成する
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576989"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="1cc61-103">直接ルーティング用にローカル メディアの最適化を構成する</span><span class="sxs-lookup"><span data-stu-id="1cc61-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="1cc61-104">ローカル メディア最適化の構成は、ルーティングや動的緊急通話などの他のクラウド音声機能に共通Location-Based設定に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="1cc61-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="1cc61-105">ネットワーク リージョン、ネットワーク サイト、ネットワーク サブネット、信頼済み IP アドレスの詳細については、「クラウド音声機能のネットワーク設定」 [を参照してください](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="1cc61-106">ローカル メディアの最適化を構成する前に、「直接ルーティングのための [ローカル メディアの最適化」を参照してください](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="1cc61-107">ローカル メディアの最適化を構成するには、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="1cc61-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="1cc61-108">管理センターまたは PowerShell Teamsを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="1cc61-109">詳細については、「ネットワーク トポロジ [の管理」を参照してください](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="1cc61-110">ユーザーと SBC サイトを構成します (この記事で説明します)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="1cc61-111">(SBC ベンダーの仕様に従って) ローカル メディアの最適化用に SBC を構成します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="1cc61-112">次の図は、この記事全体の例で使用されるネットワーク セットアップを示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="1cc61-113">![例のネットワークセットアップを示す図](media/direct-routing-media-op-9.png "例のネットワークセットアップ")</span><span class="sxs-lookup"><span data-stu-id="1cc61-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="1cc61-114">ユーザーと SBC サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="1cc61-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="1cc61-115">ユーザーと SBC サイトを構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="1cc61-116">[外部の信頼できる IP アドレスを管理します](#manage-external-trusted-ip-addresses)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="1cc61-117">[ネットワーク リージョン、ネットワーク サイト](#define-the-network-topology) 、ネットワーク サブネットを構成して、ネットワーク トポロジを定義します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="1cc61-118">[関連するモードとプロキシ](#define-the-virtual-network-topology) SBC 値を使用して SBC をサイトに割り当て、仮想ネットワーク トポロジを定義します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="1cc61-119">SBC ベンダーの仕様に従ってローカル メディアの最適化用に SBC を構成する</span><span class="sxs-lookup"><span data-stu-id="1cc61-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="1cc61-120">この記事では、Microsoft コンポーネントの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="1cc61-121">SBC 構成については、SBC ベンダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cc61-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="1cc61-122">ローカル メディアの最適化は、次の SBC ベンダーによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="1cc61-123">仕入先</span><span class="sxs-lookup"><span data-stu-id="1cc61-123">Vendor</span></span> | <span data-ttu-id="1cc61-124">Product</span><span class="sxs-lookup"><span data-stu-id="1cc61-124">Product</span></span> |    <span data-ttu-id="1cc61-125">ソフトウェアのバージョン</span><span class="sxs-lookup"><span data-stu-id="1cc61-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="1cc61-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="1cc61-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="1cc61-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="1cc61-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="1cc61-128">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1cc61-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1cc61-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="1cc61-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="1cc61-130">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1cc61-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1cc61-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="1cc61-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="1cc61-132">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1cc61-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1cc61-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="1cc61-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="1cc61-134">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1cc61-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1cc61-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="1cc61-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="1cc61-136">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1cc61-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1cc61-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="1cc61-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="1cc61-138">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1cc61-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1cc61-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="1cc61-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="1cc61-140">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1cc61-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1cc61-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="1cc61-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="1cc61-142">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1cc61-142">7.20A.256</span></span> |
| [<span data-ttu-id="1cc61-143">リボン SBC Core</span><span class="sxs-lookup"><span data-stu-id="1cc61-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="1cc61-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="1cc61-144">SBC 5110</span></span>         | <span data-ttu-id="1cc61-145">8.2</span><span class="sxs-lookup"><span data-stu-id="1cc61-145">8.2</span></span>  |
|            |  <span data-ttu-id="1cc61-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="1cc61-146">SBC 5210</span></span>         | <span data-ttu-id="1cc61-147">8.2</span><span class="sxs-lookup"><span data-stu-id="1cc61-147">8.2</span></span>  |
|            |  <span data-ttu-id="1cc61-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="1cc61-148">SBC 5400</span></span>         | <span data-ttu-id="1cc61-149">8.2</span><span class="sxs-lookup"><span data-stu-id="1cc61-149">8.2</span></span>  |
|            |  <span data-ttu-id="1cc61-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="1cc61-150">SBC 7000</span></span>         | <span data-ttu-id="1cc61-151">8.2</span><span class="sxs-lookup"><span data-stu-id="1cc61-151">8.2</span></span>  |
|            |  <span data-ttu-id="1cc61-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="1cc61-152">SBC SWe</span></span>          | <span data-ttu-id="1cc61-153">8.2</span><span class="sxs-lookup"><span data-stu-id="1cc61-153">8.2</span></span>  |
| [<span data-ttu-id="1cc61-154">リボン SBC Edge</span><span class="sxs-lookup"><span data-stu-id="1cc61-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="1cc61-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="1cc61-155">SBC SWe Lite</span></span> | <span data-ttu-id="1cc61-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="1cc61-156">8.1.5</span></span> |
|               | <span data-ttu-id="1cc61-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="1cc61-157">SBC 1000</span></span> | <span data-ttu-id="1cc61-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="1cc61-158">8.1.5</span></span>  |
|               | <span data-ttu-id="1cc61-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="1cc61-159">SBC 2000</span></span> | <span data-ttu-id="1cc61-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="1cc61-160">8.1.5</span></span>  |
| [<span data-ttu-id="1cc61-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="1cc61-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="1cc61-162">anynode</span><span class="sxs-lookup"><span data-stu-id="1cc61-162">anynode</span></span>          | <span data-ttu-id="1cc61-163">4.0.1+</span><span class="sxs-lookup"><span data-stu-id="1cc61-163">4.0.1+</span></span> |
| [<span data-ttu-id="1cc61-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="1cc61-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="1cc61-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="1cc61-165">AP 1100</span></span> | <span data-ttu-id="1cc61-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1cc61-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="1cc61-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="1cc61-167">AP 3900</span></span> | <span data-ttu-id="1cc61-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1cc61-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="1cc61-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="1cc61-169">AP 4600</span></span> | <span data-ttu-id="1cc61-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1cc61-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="1cc61-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="1cc61-171">AP 6300</span></span> | <span data-ttu-id="1cc61-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1cc61-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="1cc61-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="1cc61-173">AP 6350</span></span> | <span data-ttu-id="1cc61-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1cc61-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="1cc61-175">VME</span><span class="sxs-lookup"><span data-stu-id="1cc61-175">VME</span></span>     | <span data-ttu-id="1cc61-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1cc61-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="1cc61-177">外部の信頼済み IP アドレスを管理する</span><span class="sxs-lookup"><span data-stu-id="1cc61-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="1cc61-178">外部の信頼できる IPs は、エンタープライズ ネットワークのインターネット外部の IPS です。</span><span class="sxs-lookup"><span data-stu-id="1cc61-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="1cc61-179">これらの IP は、クライアントがクライアントに接続するときにMicrosoft Teamsによって使用される IP アドレスMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="1cc61-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="1cc61-180">ローカル メディアの最適化を使用するユーザーがいるサイトごとに、これらの外部 IPs を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="1cc61-181">各サイトのパブリック IP アドレスを追加するには、次のコマンドレットNew-CsTenantTrustedIPAddressします。</span><span class="sxs-lookup"><span data-stu-id="1cc61-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="1cc61-182">テナントの信頼できる IP アドレスの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="1cc61-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="1cc61-183">IPv4 アドレスと IPv6 Microsoft 365外部 IP アドレスが両方とも表示される場合は、両方の種類の IP アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="1cc61-184">IPv4 の場合は、マスク 32 を使用します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="1cc61-185">IPv6 の場合は、マスク 128 を使用します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="1cc61-186">コマンドレットで異なる MaskBits を指定することで、個々の外部 IP アドレスと外部 IP サブネットの両方を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="1cc61-187">信頼できる IP アドレスの追加の例。</span><span class="sxs-lookup"><span data-stu-id="1cc61-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="1cc61-188">ネットワーク トポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="1cc61-188">Define the network topology</span></span>

<span data-ttu-id="1cc61-189">このセクションでは、ネットワーク トポロジのネットワーク リージョン、ネットワーク サイト、ネットワーク サブネットを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="1cc61-190">すべてのパラメーターでは大文字と小文字が区別されます。そのため、セットアップ時に使用したのと同じ大文字と小文字を必ず使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="1cc61-191">(たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は異なるサイトとして扱います)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="1cc61-192">ネットワーク リージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="1cc61-192">Define network regions</span></span>

<span data-ttu-id="1cc61-193">ネットワーク リージョンを定義するには、次のコマンドレットNew-CsTenantNetworkRegionします。</span><span class="sxs-lookup"><span data-stu-id="1cc61-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="1cc61-194">RegionID パラメーターは、リージョンの地理を表す論理名であり、依存関係や制限はありません。</span><span class="sxs-lookup"><span data-stu-id="1cc61-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="1cc61-195">CentralSite パラメーター <site ID> は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1cc61-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="1cc61-196">次の例では、APAC という名前のネットワーク リージョンを作成します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="1cc61-197">ネットワーク サイトを定義する</span><span class="sxs-lookup"><span data-stu-id="1cc61-197">Define network sites</span></span>

<span data-ttu-id="1cc61-198">ネットワーク サイトを定義するには、次のコマンドレットNew-CsTenantNetworkSiteします。</span><span class="sxs-lookup"><span data-stu-id="1cc61-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="1cc61-199">各ネットワーク サイトは、ネットワーク リージョンに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="1cc61-200">次の例では、APAC リージョンに 3 つの新しいネットワーク サイト (ベトナム、インドネシア、シンガポール) を作成します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="1cc61-201">ネットワーク サブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="1cc61-201">Define network subnets</span></span>

<span data-ttu-id="1cc61-202">ネットワーク サブネットを定義し、ネットワーク サイトに関連付けるには、次のコマンドレットNew-CsTenantNetworkSubnetします。</span><span class="sxs-lookup"><span data-stu-id="1cc61-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="1cc61-203">各ネットワーク サブネットは、1 つのサイトにのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="1cc61-204">次の例では、3 つのネットワーク サブネットを定義し、3 つのネットワーク サイト (ベトナム、インドネシア、シンガポール) に関連付けします。</span><span class="sxs-lookup"><span data-stu-id="1cc61-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="1cc61-205">仮想ネットワーク トポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="1cc61-205">Define the virtual network topology</span></span> 

<span data-ttu-id="1cc61-206">最初に、テナント管理者は、 コマンドレットを使用して、関連する SBC ごとに新しい SBC New-CsOnlinePSTNGatewayします。</span><span class="sxs-lookup"><span data-stu-id="1cc61-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="1cc61-207">テナント管理者は、次のコマンドレットを使用して PSTN ゲートウェイ オブジェクトのネットワーク サイトを指定することで、仮想ネットワーク トポロジSet-CsOnlinePSTNGatewayします。</span><span class="sxs-lookup"><span data-stu-id="1cc61-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="1cc61-208">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1cc61-208">Note the following:</span></span> 
   - <span data-ttu-id="1cc61-209">顧客が 1 つの SBC を持っている場合、-ProxySBC パラメーターは必須の $null または SBC FQDN 値である必要があります (中央 SBC と一元化されたトランクのシナリオ)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="1cc61-210">ローカル メディアの最適化をサポートするには、-MediaBypass パラメーターを $true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="1cc61-211">SBC に -BypassMode パラメーターが設定されていない場合、X-MS ヘッダーは送信されません。</span><span class="sxs-lookup"><span data-stu-id="1cc61-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="1cc61-212">すべてのパラメーターでは大文字と小文字が区別されます。そのため、セットアップ時に使用したのと同じ大文字と小文字を必ず使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="1cc61-213">(たとえば、GatewaySiteID の値 "ベトナム" と "ベトナム" は異なるサイトとして扱います)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="1cc61-214">次の例では、モード Always bypass を使用して、APAC リージョンのベトナム、インドネシア、シンガポールのネットワーク サイトに 3 つの SBC を追加します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="1cc61-215">注: ローカル メディアの最適化と Location-Based ルーティング (LBR) が同時に構成されている場合に中断されない操作を確実に行う場合は、ダウンストリーム SBC ごとに GatewaySiteLbrEnabled パラメーターを $true に設定して、LBR に対してダウンストリーム SBC を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="1cc61-216">(この設定は、プロキシ SBC では必須ではありません)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="1cc61-217">上記の情報に基づいて、直接ルーティングには、次の表に示すように、SIP 招待と再招待に対する 3 つの独自の SIP ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="1cc61-218">BypassMode が定義されている場合は、「招待時の直接ルーティング」および「Re-Invites X-MS ヘッダー」で紹介されています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="1cc61-219">ヘッダー名</span><span class="sxs-lookup"><span data-stu-id="1cc61-219">Header name</span></span> | <span data-ttu-id="1cc61-220">値</span><span class="sxs-lookup"><span data-stu-id="1cc61-220">Values</span></span> | <span data-ttu-id="1cc61-221">注釈</span><span class="sxs-lookup"><span data-stu-id="1cc61-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="1cc61-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="1cc61-222">X-MS-UserLocation</span></span> | <span data-ttu-id="1cc61-223">internal/external</span><span class="sxs-lookup"><span data-stu-id="1cc61-223">internal/external</span></span> | <span data-ttu-id="1cc61-224">ユーザーが内部か外部かを示します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="1cc61-225">要求 URI INVITE SIP: +84439263000@VNsbc.contoso.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="1cc61-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="1cc61-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="1cc61-226">SBC FQDN</span></span> | <span data-ttu-id="1cc61-227">SBC が直接ルーティングに直接接続されていない場合でも、呼び出しの対象となる FQDN</span><span class="sxs-lookup"><span data-stu-id="1cc61-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="1cc61-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="1cc61-228">X-MS-MediaPath</span></span> | <span data-ttu-id="1cc61-229">例: proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="1cc61-230">ユーザーとターゲット SBC の間のメディア パスに使用する必要がある SBC の順序。</span><span class="sxs-lookup"><span data-stu-id="1cc61-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="1cc61-231">最後の SBC は常に最後です</span><span class="sxs-lookup"><span data-stu-id="1cc61-231">The final SBC is always last</span></span> |
| <span data-ttu-id="1cc61-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="1cc61-232">X-MS-UserSite</span></span> | <span data-ttu-id="1cc61-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="1cc61-233">usersiteID</span></span> | <span data-ttu-id="1cc61-234">テナント管理者によって定義された文字列</span><span class="sxs-lookup"><span data-stu-id="1cc61-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="1cc61-235">呼び出しフロー</span><span class="sxs-lookup"><span data-stu-id="1cc61-235">Call flows</span></span> 

<span data-ttu-id="1cc61-236">2 つのモードの呼び出しフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="1cc61-237">Always Bypass</span><span class="sxs-lookup"><span data-stu-id="1cc61-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="1cc61-238">ローカル ユーザーの場合のみ</span><span class="sxs-lookup"><span data-stu-id="1cc61-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="1cc61-239">常にバイパス モード</span><span class="sxs-lookup"><span data-stu-id="1cc61-239">Always Bypass mode</span></span>

<span data-ttu-id="1cc61-240">Always Bypass モードは、構成する最も簡単なオプションです。</span><span class="sxs-lookup"><span data-stu-id="1cc61-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="1cc61-241">すべての SBC に任意のサイトから到達可能な場合、テナント管理者は、すべてのユーザーと SBC に対して 1 つのサイトを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="1cc61-242">例では、次のシナリオの Always バイパス モードを示します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="1cc61-243">発信呼び出しとユーザーが SBC と同じ場所にある</span><span class="sxs-lookup"><span data-stu-id="1cc61-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="1cc61-244">受信呼び出しとユーザーが SBC と同じ場所にある</span><span class="sxs-lookup"><span data-stu-id="1cc61-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="1cc61-245">発信呼び出しとユーザーが外部</span><span class="sxs-lookup"><span data-stu-id="1cc61-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="1cc61-246">受信呼び出しとユーザーが外部</span><span class="sxs-lookup"><span data-stu-id="1cc61-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="1cc61-247">次の表は、例で使用されている FQDN と IP アドレスを示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="1cc61-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="1cc61-248">FQDN</span></span> | <span data-ttu-id="1cc61-249">SBC 外部 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="1cc61-249">SBC external IP address</span></span> | <span data-ttu-id="1cc61-250">SBC 内部 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="1cc61-250">SBC internal IP Address</span></span> | <span data-ttu-id="1cc61-251">内部サブネット</span><span class="sxs-lookup"><span data-stu-id="1cc61-251">Internal subnet</span></span> | <span data-ttu-id="1cc61-252">場所</span><span class="sxs-lookup"><span data-stu-id="1cc61-252">Location</span></span> | <span data-ttu-id="1cc61-253">外部 NAT (信頼済み IP)</span><span class="sxs-lookup"><span data-stu-id="1cc61-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1cc61-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="1cc61-255">なし</span><span class="sxs-lookup"><span data-stu-id="1cc61-255">None</span></span> | <span data-ttu-id="1cc61-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="1cc61-256">192.168.1.5</span></span> | <span data-ttu-id="1cc61-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="1cc61-257">192.168.1.0/24</span></span> | <span data-ttu-id="1cc61-258">ベトナム</span><span class="sxs-lookup"><span data-stu-id="1cc61-258">Vietnam</span></span> | <span data-ttu-id="1cc61-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="1cc61-259">172.16.240.110</span></span> |
| <span data-ttu-id="1cc61-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="1cc61-261">なし</span><span class="sxs-lookup"><span data-stu-id="1cc61-261">None</span></span> | <span data-ttu-id="1cc61-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="1cc61-262">192.168.2.5</span></span> | <span data-ttu-id="1cc61-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="1cc61-263">192.168.2.0/24</span></span> | <span data-ttu-id="1cc61-264">インドネシア</span><span class="sxs-lookup"><span data-stu-id="1cc61-264">Indonesia</span></span> | <span data-ttu-id="1cc61-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="1cc61-265">172.16.240.120</span></span> |
| <span data-ttu-id="1cc61-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="1cc61-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="1cc61-267">172.16.240.133</span></span> | <span data-ttu-id="1cc61-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="1cc61-268">192.168.3.5</span></span> | <span data-ttu-id="1cc61-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="1cc61-269">192.168.3.0/24</span></span> | <span data-ttu-id="1cc61-270">シンガポール</span><span class="sxs-lookup"><span data-stu-id="1cc61-270">Singapore</span></span> | <span data-ttu-id="1cc61-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="1cc61-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="1cc61-272">発信呼び出しとユーザーが Always Bypass を使用する SBC と同じ場所にある</span><span class="sxs-lookup"><span data-stu-id="1cc61-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="1cc61-273">モード</span><span class="sxs-lookup"><span data-stu-id="1cc61-273">Mode</span></span> |    <span data-ttu-id="1cc61-274">ユーザー</span><span class="sxs-lookup"><span data-stu-id="1cc61-274">User</span></span> |  <span data-ttu-id="1cc61-275">場所</span><span class="sxs-lookup"><span data-stu-id="1cc61-275">Location</span></span> |  <span data-ttu-id="1cc61-276">通話の方向</span><span class="sxs-lookup"><span data-stu-id="1cc61-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="1cc61-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1cc61-277">AlwaysBypass</span></span> |    <span data-ttu-id="1cc61-278">内部</span><span class="sxs-lookup"><span data-stu-id="1cc61-278">Internal</span></span> |  <span data-ttu-id="1cc61-279">SBC と同じサイト</span><span class="sxs-lookup"><span data-stu-id="1cc61-279">The same site as SBC</span></span> |  <span data-ttu-id="1cc61-280">発信</span><span class="sxs-lookup"><span data-stu-id="1cc61-280">Outbound</span></span> |

<span data-ttu-id="1cc61-281">次の表は、エンド ユーザーの構成とアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="1cc61-282">ユーザーの物理的な場所</span><span class="sxs-lookup"><span data-stu-id="1cc61-282">User physical location</span></span>| <span data-ttu-id="1cc61-283">ユーザーが番号に対して通話を行う、または番号から通話を受信する</span><span class="sxs-lookup"><span data-stu-id="1cc61-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="1cc61-284">ユーザーの電話番号</span><span class="sxs-lookup"><span data-stu-id="1cc61-284">User phone number</span></span>  | <span data-ttu-id="1cc61-285">オンライン音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="1cc61-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="1cc61-286">SBC 用に構成されたモード</span><span class="sxs-lookup"><span data-stu-id="1cc61-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1cc61-287">ベトナム</span><span class="sxs-lookup"><span data-stu-id="1cc61-287">Vietnam</span></span> | <span data-ttu-id="1cc61-288">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="1cc61-288">+84 4 3926 3000</span></span> | <span data-ttu-id="1cc61-289">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="1cc61-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="1cc61-290">優先度 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="1cc61-291">優先度 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="1cc61-292">VNsbc.contoso.com – Always Bypass</span><span class="sxs-lookup"><span data-stu-id="1cc61-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="1cc61-293">proxysbc.contoso.com – 常にバイパス</span><span class="sxs-lookup"><span data-stu-id="1cc61-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="1cc61-294">次の図は、Always バイパス モードの発信呼び出しの SIP ラダーと、SBC と同じ場所のユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="1cc61-295">![発信呼び出しを示す図](media/direct-routing-media-op-10.png "発信呼び出し")</span><span class="sxs-lookup"><span data-stu-id="1cc61-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="1cc61-296">次の表は、ダイレクト ルーティングによって送信される X-MS ヘッダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="1cc61-297">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1cc61-297">Parameter</span></span> | <span data-ttu-id="1cc61-298">説明</span><span class="sxs-lookup"><span data-stu-id="1cc61-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="1cc61-299">招待 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="1cc61-300">オンライン音声ルーティング ポリシーで定義されている SBC のターゲット FQDN は、要求 URI で送信されます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="1cc61-301">X-MS-UserLocation: internal</span><span class="sxs-lookup"><span data-stu-id="1cc61-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="1cc61-302">フィールドは、ユーザーが企業ネットワーク内に位置する</span><span class="sxs-lookup"><span data-stu-id="1cc61-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="1cc61-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="1cc61-304">クライアントがターゲット SBC に走査する必要がある SBC を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="1cc61-305">この場合は Always Bypass を使用し、クライアントはヘッダー内の唯一の名前として送信されるターゲット名の内部です。</span><span class="sxs-lookup"><span data-stu-id="1cc61-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="1cc61-306">X-MS-UserSite: ベトナム</span><span class="sxs-lookup"><span data-stu-id="1cc61-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="1cc61-307">ユーザーが位置するサイト内で示されるフィールド。</span><span class="sxs-lookup"><span data-stu-id="1cc61-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="1cc61-308">着信呼び出しとユーザーが Always Bypass を使用する SBC と同じ場所にある</span><span class="sxs-lookup"><span data-stu-id="1cc61-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="1cc61-309">モード</span><span class="sxs-lookup"><span data-stu-id="1cc61-309">Mode</span></span> |    <span data-ttu-id="1cc61-310">ユーザー</span><span class="sxs-lookup"><span data-stu-id="1cc61-310">User</span></span> |  <span data-ttu-id="1cc61-311">場所</span><span class="sxs-lookup"><span data-stu-id="1cc61-311">Location</span></span> |  <span data-ttu-id="1cc61-312">通話の方向</span><span class="sxs-lookup"><span data-stu-id="1cc61-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1cc61-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1cc61-313">AlwaysBypass</span></span> |    <span data-ttu-id="1cc61-314">内部</span><span class="sxs-lookup"><span data-stu-id="1cc61-314">Internal</span></span> | <span data-ttu-id="1cc61-315">SBC と同じサイト</span><span class="sxs-lookup"><span data-stu-id="1cc61-315">The same site as SBC</span></span> | <span data-ttu-id="1cc61-316">受信</span><span class="sxs-lookup"><span data-stu-id="1cc61-316">Inbound</span></span> |


<span data-ttu-id="1cc61-317">受信呼び出しでは、ユーザーの場所は不明であり、SBC はユーザーの場所を推測する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="1cc61-318">推測が正しくない場合は、再招待が必要になります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="1cc61-319">このケースでは、ユーザーが内部的であり、メディアが直接フローできると想定され、それ以上のアクションは必要ありません (再招待)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="1cc61-320">ダイレクト ルーティング サービスに接続されている SBC は、元の SBC の場所を報告します。この場合は、[Record-Route] フィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="1cc61-321">これらのフィールドに基づいて、メディア パスは直接ルーティングによって計算されます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="1cc61-322">注: ユーザーが複数のエンドポイントを持つ場合、183 はサポートできません。</span><span class="sxs-lookup"><span data-stu-id="1cc61-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="1cc61-323">この場合、ダイレクト ルーティングでは常に 180 リングが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="1cc61-324">次の図は、AlwaysBypass モードでの着信呼び出しの SIP ラダーを示しています。ユーザーは SBC と同じ場所にいます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![SIP ラダーを示す図](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="1cc61-326">発信呼び出しとユーザーが Always Bypass を使用して外部に</span><span class="sxs-lookup"><span data-stu-id="1cc61-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="1cc61-327">モード</span><span class="sxs-lookup"><span data-stu-id="1cc61-327">Mode</span></span> |    <span data-ttu-id="1cc61-328">ユーザー</span><span class="sxs-lookup"><span data-stu-id="1cc61-328">User</span></span> |  <span data-ttu-id="1cc61-329">サイト</span><span class="sxs-lookup"><span data-stu-id="1cc61-329">Site</span></span> |  <span data-ttu-id="1cc61-330">通話の方向</span><span class="sxs-lookup"><span data-stu-id="1cc61-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="1cc61-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1cc61-331">AlwaysBypass</span></span> |  <span data-ttu-id="1cc61-332">外部</span><span class="sxs-lookup"><span data-stu-id="1cc61-332">External</span></span> |  <span data-ttu-id="1cc61-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="1cc61-333">N/A</span></span> | <span data-ttu-id="1cc61-334">発信</span><span class="sxs-lookup"><span data-stu-id="1cc61-334">Outbound</span></span> |


<span data-ttu-id="1cc61-335">次の図は、AlwaysBypass モードの発信呼び出しの SIP ラダーを示しています。ユーザーは外部です。</span><span class="sxs-lookup"><span data-stu-id="1cc61-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![SIP ラダーを示す図](media/direct-routing-media-op-12.png)

<span data-ttu-id="1cc61-337">次の表は、ダイレクト ルーティング サービスによって送信される X-MS ヘッダーを示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="1cc61-338">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1cc61-338">Parameter</span></span> |   <span data-ttu-id="1cc61-339">説明</span><span class="sxs-lookup"><span data-stu-id="1cc61-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="1cc61-340">招待 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="1cc61-341">オンライン音声ルーティング ポリシーで定義されている SBC のターゲット FQDN は、要求 URI で送信されます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="1cc61-342">X-MS-UserLocation: external</span><span class="sxs-lookup"><span data-stu-id="1cc61-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="1cc61-343">フィールドは、ユーザーが企業ネットワークの外部に位置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cc61-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="1cc61-344">X-MS-MediaPath: proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="1cc61-345">クライアントがターゲット SBC に走査する必要がある SBC を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="1cc61-346">この場合は Always Bypass が使用され、クライアントは外部であるためです。</span><span class="sxs-lookup"><span data-stu-id="1cc61-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="1cc61-347">着信呼び出しとユーザーが Always Bypass を使用して外部に</span><span class="sxs-lookup"><span data-stu-id="1cc61-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="1cc61-348">モード</span><span class="sxs-lookup"><span data-stu-id="1cc61-348">Mode</span></span> | <span data-ttu-id="1cc61-349">ユーザー</span><span class="sxs-lookup"><span data-stu-id="1cc61-349">User</span></span> | <span data-ttu-id="1cc61-350">サイト</span><span class="sxs-lookup"><span data-stu-id="1cc61-350">Site</span></span> |  <span data-ttu-id="1cc61-351">通話の方向</span><span class="sxs-lookup"><span data-stu-id="1cc61-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="1cc61-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1cc61-352">AlwaysBypass</span></span> |  <span data-ttu-id="1cc61-353">外部</span><span class="sxs-lookup"><span data-stu-id="1cc61-353">External</span></span> |  <span data-ttu-id="1cc61-354">該当なし</span><span class="sxs-lookup"><span data-stu-id="1cc61-354">N/A</span></span> |   <span data-ttu-id="1cc61-355">受信</span><span class="sxs-lookup"><span data-stu-id="1cc61-355">Inbound</span></span> |

<span data-ttu-id="1cc61-356">着信呼び出しの場合、ユーザーの場所が外部にある場合、ダイレクト ルーティングに接続されている SBC は再招待を送信する必要があります (既定では、ローカル メディア候補は常に提供されます)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="1cc61-357">X-MediaPath は、指定された SBC Record-Routeに基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="1cc61-358">次の図は、AlwaysBypass モードの着信呼び出しの SIP ラダーを示しています。ユーザーは外部です。</span><span class="sxs-lookup"><span data-stu-id="1cc61-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![SIP ラダーを示す図](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="1cc61-360">ローカル ユーザー モードの場合のみ</span><span class="sxs-lookup"><span data-stu-id="1cc61-360">Only for local users mode</span></span>

<span data-ttu-id="1cc61-361">ターゲット SBC のローカル メディア候補は、ユーザーが SBC と同じ場所にある場合にのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="1cc61-362">それ以外のすべての場合、メディアはプロキシ SBC の内部 IP または外部 IP を経由します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="1cc61-363">次のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="1cc61-364">発信呼び出しとユーザーが SBC と同じ場所にある</span><span class="sxs-lookup"><span data-stu-id="1cc61-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="1cc61-365">受信呼び出しとユーザーが SBC と同じ場所にある</span><span class="sxs-lookup"><span data-stu-id="1cc61-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="1cc61-366">ユーザーが SBC と同じ場所ではなく、企業ネットワーク内にある</span><span class="sxs-lookup"><span data-stu-id="1cc61-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="1cc61-367">受信呼び出しとユーザーは内部的ですが、SBC と同じ場所ではありません</span><span class="sxs-lookup"><span data-stu-id="1cc61-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="1cc61-368">次の表は、エンド ユーザーの構成とアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="1cc61-369">ユーザーの物理的な場所</span><span class="sxs-lookup"><span data-stu-id="1cc61-369">User physical location</span></span> |  <span data-ttu-id="1cc61-370">ユーザーが番号に対して通話を行う、または番号から通話を受信する</span><span class="sxs-lookup"><span data-stu-id="1cc61-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="1cc61-371">ユーザーの電話番号</span><span class="sxs-lookup"><span data-stu-id="1cc61-371">User phone number</span></span> | <span data-ttu-id="1cc61-372">オンライン音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="1cc61-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="1cc61-373">SBC 用に構成されたモード</span><span class="sxs-lookup"><span data-stu-id="1cc61-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1cc61-374">ベトナム</span><span class="sxs-lookup"><span data-stu-id="1cc61-374">Vietnam</span></span> | <span data-ttu-id="1cc61-375">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="1cc61-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="1cc61-376">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="1cc61-376">+84 4 5555 5555</span></span> | <span data-ttu-id="1cc61-377">優先度 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="1cc61-378">優先度 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cc61-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="1cc61-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span><span class="sxs-lookup"><span data-stu-id="1cc61-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="1cc61-380">発信呼び出しとユーザーが SBC と同じ場所にある (ローカル ユーザーの場合のみ)</span><span class="sxs-lookup"><span data-stu-id="1cc61-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="1cc61-381">モード</span><span class="sxs-lookup"><span data-stu-id="1cc61-381">Mode</span></span> | <span data-ttu-id="1cc61-382">ユーザー</span><span class="sxs-lookup"><span data-stu-id="1cc61-382">User</span></span> | <span data-ttu-id="1cc61-383">サイト</span><span class="sxs-lookup"><span data-stu-id="1cc61-383">Site</span></span> | <span data-ttu-id="1cc61-384">通話の方向</span><span class="sxs-lookup"><span data-stu-id="1cc61-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1cc61-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1cc61-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="1cc61-386">内部</span><span class="sxs-lookup"><span data-stu-id="1cc61-386">Internal</span></span> |<span data-ttu-id="1cc61-387">SBC と同じ</span><span class="sxs-lookup"><span data-stu-id="1cc61-387">Same as SBC</span></span>   | <span data-ttu-id="1cc61-388">発信</span><span class="sxs-lookup"><span data-stu-id="1cc61-388">Outbound</span></span> |

<span data-ttu-id="1cc61-389">次の図は、OnlyForLocalUsers モードの発信呼び出しを示しています。ユーザーは SBC と同じ場所にいます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="1cc61-390">これは、ユーザーが SBC と同じ場所にある場合の送信呼び出しに [表示されるのと同じフローです](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP ラダーを示す図](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="1cc61-392">受信呼び出しとユーザーが SBC と同じ場所にいて、ローカル ユーザーの場合のみ</span><span class="sxs-lookup"><span data-stu-id="1cc61-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="1cc61-393">モード</span><span class="sxs-lookup"><span data-stu-id="1cc61-393">Mode</span></span> | <span data-ttu-id="1cc61-394">ユーザー</span><span class="sxs-lookup"><span data-stu-id="1cc61-394">User</span></span> | <span data-ttu-id="1cc61-395">サイト</span><span class="sxs-lookup"><span data-stu-id="1cc61-395">Site</span></span> | <span data-ttu-id="1cc61-396">通話の方向</span><span class="sxs-lookup"><span data-stu-id="1cc61-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1cc61-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1cc61-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="1cc61-398">内部</span><span class="sxs-lookup"><span data-stu-id="1cc61-398">Internal</span></span> | <span data-ttu-id="1cc61-399">SBC と同じ</span><span class="sxs-lookup"><span data-stu-id="1cc61-399">Same as SBC</span></span> | <span data-ttu-id="1cc61-400">受信</span><span class="sxs-lookup"><span data-stu-id="1cc61-400">Inbound</span></span> |

<span data-ttu-id="1cc61-401">次の図は、OnlyForLocalUsers モードの受信呼び出しを示しています。ユーザーは SBC と同じ場所にいます。</span><span class="sxs-lookup"><span data-stu-id="1cc61-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="1cc61-402">これは、ユーザーが SBC と同じ場所にある場合の受信呼び出しで示されている [のと同じフローです](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。</span><span class="sxs-lookup"><span data-stu-id="1cc61-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP ラダーを示す図](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="1cc61-404">ユーザーは SBC と同じ場所ではなく、ローカル ユーザーの場合のみと企業ネットワーク内にある</span><span class="sxs-lookup"><span data-stu-id="1cc61-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="1cc61-405">モード</span><span class="sxs-lookup"><span data-stu-id="1cc61-405">Mode</span></span> | <span data-ttu-id="1cc61-406">ユーザー</span><span class="sxs-lookup"><span data-stu-id="1cc61-406">User</span></span> | <span data-ttu-id="1cc61-407">サイト</span><span class="sxs-lookup"><span data-stu-id="1cc61-407">Site</span></span> |<span data-ttu-id="1cc61-408">通話の方向</span><span class="sxs-lookup"><span data-stu-id="1cc61-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1cc61-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1cc61-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="1cc61-410">内部</span><span class="sxs-lookup"><span data-stu-id="1cc61-410">Internal</span></span> |   <span data-ttu-id="1cc61-411">SBC とは異なる</span><span class="sxs-lookup"><span data-stu-id="1cc61-411">Different from SBC</span></span> | <span data-ttu-id="1cc61-412">発信</span><span class="sxs-lookup"><span data-stu-id="1cc61-412">Outbound</span></span> |

<span data-ttu-id="1cc61-413">ダイレクト ルーティングは、SBC で構成されたユーザーとモードの報告された場所に基づいて X-MediaPath を計算します。</span><span class="sxs-lookup"><span data-stu-id="1cc61-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="1cc61-414">次の図は、OnlyForLocalUsers モードの送信呼び出しと、SBC と同じ場所にいない内部ユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP ラダーを示す図](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="1cc61-416">受信呼び出しとユーザーは内部的ですが、ローカル ユーザーの場合のみ SBC と同じ場所ではありません</span><span class="sxs-lookup"><span data-stu-id="1cc61-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="1cc61-417">モード</span><span class="sxs-lookup"><span data-stu-id="1cc61-417">Mode</span></span> |    <span data-ttu-id="1cc61-418">ユーザー</span><span class="sxs-lookup"><span data-stu-id="1cc61-418">User</span></span> |  <span data-ttu-id="1cc61-419">サイト</span><span class="sxs-lookup"><span data-stu-id="1cc61-419">Site</span></span> |  <span data-ttu-id="1cc61-420">通話の方向</span><span class="sxs-lookup"><span data-stu-id="1cc61-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1cc61-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1cc61-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="1cc61-422">内部</span><span class="sxs-lookup"><span data-stu-id="1cc61-422">Internal</span></span> |    <span data-ttu-id="1cc61-423">SBC とは異なる</span><span class="sxs-lookup"><span data-stu-id="1cc61-423">Different from SBC</span></span> |    <span data-ttu-id="1cc61-424">受信</span><span class="sxs-lookup"><span data-stu-id="1cc61-424">Inbound</span></span> |

<span data-ttu-id="1cc61-425">次の図は、OnlyForLocalUsers モードでの受信呼び出しと、SBC と同じ場所にない内部ユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc61-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP ラダーを示す図](media/direct-routing-media-op-17.png)









