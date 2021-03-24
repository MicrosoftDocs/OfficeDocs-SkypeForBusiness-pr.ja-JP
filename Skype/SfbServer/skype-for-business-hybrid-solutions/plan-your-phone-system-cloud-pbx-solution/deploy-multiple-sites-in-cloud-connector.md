---
title: クラウド コネクタでの複数サイトの展開
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: クラウド コネクタ エディションでの複数の PSTN サイトの展開について説明します。
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098403"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="4c8e4-103">クラウド コネクタでの複数サイトの展開</span><span class="sxs-lookup"><span data-stu-id="4c8e4-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="4c8e4-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="4c8e4-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="4c8e4-106">クラウド コネクタ エディションでの複数の PSTN サイトの展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="4c8e4-107">このセクションでは、複数の公衆交換電話網 (PSTN) サイトを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="4c8e4-108">サイトは、1 つのサイトの展開と同じ手順を使用して一度に 1 つ展開されます。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="4c8e4-109">このトピックでは、複数のサイト展開におけるサイトの考慮事項と相違点について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="4c8e4-110">複数の公衆交換電話網 (PSTN) サイト</span><span class="sxs-lookup"><span data-stu-id="4c8e4-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="4c8e4-111">次に、Skype for Business Cloud Connector Edition をさまざまな PSTN サイトに展開する構成例を示します。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="4c8e4-112">展開を開始する前に、構成設定が正しいか確認してください。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="4c8e4-113">PSTN サイト 1</span><span class="sxs-lookup"><span data-stu-id="4c8e4-113">PSTN Site 1</span></span>
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

<span data-ttu-id="4c8e4-114">PSTN サイト 2</span><span class="sxs-lookup"><span data-stu-id="4c8e4-114">PSTN Site 2</span></span>
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

<span data-ttu-id="4c8e4-115">追加する PSTN サイトごとに、「Cloud Connector で単一サイトを展開する」の [手順に従います](deploy-a-single-site-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4c8e4-116">高可用性 (HA) を準備するための共有フォルダーは、PSTN サイトごとに行います。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="4c8e4-117">共有フォルダーは **PSTN サイト** 間で異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="4c8e4-118">複数の sites.> に同じ共有フォルダーを使用></span><span class="sxs-lookup"><span data-stu-id="4c8e4-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="4c8e4-119">複数サイト展開と比較した高可用性 (HA) を備えた単一サイト</span><span class="sxs-lookup"><span data-stu-id="4c8e4-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="4c8e4-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="4c8e4-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="4c8e4-121">次の表に、HA をサポートする単一サイトと複数のサイト展開の違いを示します。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="4c8e4-122">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="4c8e4-122">**Category**</span></span>|<span data-ttu-id="4c8e4-123">**項目**</span><span class="sxs-lookup"><span data-stu-id="4c8e4-123">**Item**</span></span>|<span data-ttu-id="4c8e4-124">**HA を使用した単一サイト**</span><span class="sxs-lookup"><span data-stu-id="4c8e4-124">**Single-Site with HA**</span></span>|<span data-ttu-id="4c8e4-125">**マルチサイト**</span><span class="sxs-lookup"><span data-stu-id="4c8e4-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4c8e4-126">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-126">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-127">アプライアンスのホスト名</span><span class="sxs-lookup"><span data-stu-id="4c8e4-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="4c8e4-128">**アプライアンス間** で異なる</span><span class="sxs-lookup"><span data-stu-id="4c8e4-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-129">**PSTN サイト** 間で異なる</span><span class="sxs-lookup"><span data-stu-id="4c8e4-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="4c8e4-130">セットアップ</span><span class="sxs-lookup"><span data-stu-id="4c8e4-130">Setup</span></span>  <br/> |<span data-ttu-id="4c8e4-131">共有フォルダー</span><span class="sxs-lookup"><span data-stu-id="4c8e4-131">Shared folder</span></span>  <br/> |<span data-ttu-id="4c8e4-132">アプライアンス間 **で同じ** 共有フォルダーが必要</span><span class="sxs-lookup"><span data-stu-id="4c8e4-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-133">アプライアンス間 **で別の** 共有フォルダーが必要</span><span class="sxs-lookup"><span data-stu-id="4c8e4-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="4c8e4-134">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-134">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="4c8e4-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="4c8e4-136">アプライアンス間 **で同じ** ドメインが必要</span><span class="sxs-lookup"><span data-stu-id="4c8e4-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-137">PSTN サイト間 **で同** じドメインが必要</span><span class="sxs-lookup"><span data-stu-id="4c8e4-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="4c8e4-138">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-138">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="4c8e4-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="4c8e4-140">ドメイン名と順序は、アプライアンス間 **で同じ** である必要があります</span><span class="sxs-lookup"><span data-stu-id="4c8e4-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-141">ドメイン名と順序は PSTN サイト **間で** 同じである必要があります</span><span class="sxs-lookup"><span data-stu-id="4c8e4-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="4c8e4-142">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-142">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-143">サイト名</span><span class="sxs-lookup"><span data-stu-id="4c8e4-143">Site name</span></span>  <br/> |<span data-ttu-id="4c8e4-144">**同じ** アプライアンス間のサイト名</span><span class="sxs-lookup"><span data-stu-id="4c8e4-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-145">**異なる** PSTN サイト間のサイト名</span><span class="sxs-lookup"><span data-stu-id="4c8e4-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="4c8e4-146">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-146">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-147">サーバー名</span><span class="sxs-lookup"><span data-stu-id="4c8e4-147">Server names</span></span>  <br/> |<span data-ttu-id="4c8e4-148">**アプライアンス間** で異なる</span><span class="sxs-lookup"><span data-stu-id="4c8e4-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-149">**PSTN サイト** 間で異なる</span><span class="sxs-lookup"><span data-stu-id="4c8e4-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="4c8e4-150">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-150">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-151">内部プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="4c8e4-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="4c8e4-152">**アプライアンス間** で同じ</span><span class="sxs-lookup"><span data-stu-id="4c8e4-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-153">**PSTN サイト** 間で同じ</span><span class="sxs-lookup"><span data-stu-id="4c8e4-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="4c8e4-154">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-154">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-155">内部の IPs</span><span class="sxs-lookup"><span data-stu-id="4c8e4-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="4c8e4-156">**アプライアンス間** で異なる</span><span class="sxs-lookup"><span data-stu-id="4c8e4-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-157">**PSTN サイト** 間で異なる</span><span class="sxs-lookup"><span data-stu-id="4c8e4-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="4c8e4-158">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-158">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-159">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="4c8e4-159">External FQDN</span></span>  <br/> |<span data-ttu-id="4c8e4-160">**アプライアンス間** で同じ</span><span class="sxs-lookup"><span data-stu-id="4c8e4-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-161">**PSTN サイト** 間で異なる</span><span class="sxs-lookup"><span data-stu-id="4c8e4-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="4c8e4-162">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-162">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-163">外部 AP</span><span class="sxs-lookup"><span data-stu-id="4c8e4-163">External IPs</span></span>  <br/> |<span data-ttu-id="4c8e4-164">**アプライアンス間** で異なる</span><span class="sxs-lookup"><span data-stu-id="4c8e4-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-165">**PSTN サイト** 間で異なる</span><span class="sxs-lookup"><span data-stu-id="4c8e4-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="4c8e4-166">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-166">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-167">PSTN GW の設定</span><span class="sxs-lookup"><span data-stu-id="4c8e4-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="4c8e4-168">**アプライアンス間** で同じ</span><span class="sxs-lookup"><span data-stu-id="4c8e4-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="4c8e4-169">**PSTN サイト** 間で異なる</span><span class="sxs-lookup"><span data-stu-id="4c8e4-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="4c8e4-170">構成</span><span class="sxs-lookup"><span data-stu-id="4c8e4-170">Configure</span></span>  <br/> |<span data-ttu-id="4c8e4-171">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="4c8e4-171">DNS record</span></span>  <br/> |<span data-ttu-id="4c8e4-172">同じ外部アクセス FQDN **と** 異なる IP アドレスを持つ **レコードを** 追加する</span><span class="sxs-lookup"><span data-stu-id="4c8e4-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="4c8e4-173">異なる外部 **アクセス** FQDN と異なる IP アドレスを持つ **レコードを** 追加する</span><span class="sxs-lookup"><span data-stu-id="4c8e4-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="4c8e4-174">セットアップ</span><span class="sxs-lookup"><span data-stu-id="4c8e4-174">Setup</span></span>  <br/> |<span data-ttu-id="4c8e4-175">ハイブリッド テナント</span><span class="sxs-lookup"><span data-stu-id="4c8e4-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="4c8e4-176">HybridPSTNSite の設定</span><span class="sxs-lookup"><span data-stu-id="4c8e4-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="4c8e4-177">フォールバック用に PeerDestination を設定する</span><span class="sxs-lookup"><span data-stu-id="4c8e4-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="4c8e4-178">HybridPSTNSite の設定</span><span class="sxs-lookup"><span data-stu-id="4c8e4-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="4c8e4-179">フォールバック用に PeerDestination を設定する</span><span class="sxs-lookup"><span data-stu-id="4c8e4-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="4c8e4-180">セットアップ</span><span class="sxs-lookup"><span data-stu-id="4c8e4-180">Setup</span></span>  <br/> |<span data-ttu-id="4c8e4-181">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="4c8e4-181">Gateway</span></span>  <br/> |<span data-ttu-id="4c8e4-182">このサイトの MS GW **M:N** マッピング</span><span class="sxs-lookup"><span data-stu-id="4c8e4-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="4c8e4-183">各 PSTN サイトの PSTN ゲートウェイは、同じサイトの仲介サーバーにのみ接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c8e4-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="4c8e4-184">セットアップ</span><span class="sxs-lookup"><span data-stu-id="4c8e4-184">Setup</span></span>  <br/> |<span data-ttu-id="4c8e4-185">User</span><span class="sxs-lookup"><span data-stu-id="4c8e4-185">User</span></span>  <br/> |<span data-ttu-id="4c8e4-186">UserPSTNSettings の設定</span><span class="sxs-lookup"><span data-stu-id="4c8e4-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="4c8e4-187">UserPSTNSettings の設定</span><span class="sxs-lookup"><span data-stu-id="4c8e4-187">Set UserPSTNSettings</span></span>  <br/> |
