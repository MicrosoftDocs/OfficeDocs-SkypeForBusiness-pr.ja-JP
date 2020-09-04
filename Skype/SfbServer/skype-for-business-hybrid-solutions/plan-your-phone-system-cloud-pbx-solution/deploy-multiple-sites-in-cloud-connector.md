---
title: Cloud Connector での複数サイトの展開
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
description: Cloud Connector エディションに複数の PSTN サイトを展開する方法について説明します。
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358923"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="c8a83-103">Cloud Connector での複数サイトの展開</span><span class="sxs-lookup"><span data-stu-id="c8a83-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="c8a83-104">Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="c8a83-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="c8a83-105">組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8a83-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="c8a83-106">Cloud Connector エディションに複数の PSTN サイトを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8a83-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="c8a83-107">このセクションでは、複数の公衆交換電話網 (PSTN) サイトを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8a83-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="c8a83-108">サイトは、1つのサイトの展開と同じ手順を使用して、一度に1つずつ展開されます。</span><span class="sxs-lookup"><span data-stu-id="c8a83-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="c8a83-109">このトピックでは、複数のサイト展開におけるサイト間の考慮事項と相違点について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8a83-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="c8a83-110">複数の公衆交換電話網 (PSTN) サイト</span><span class="sxs-lookup"><span data-stu-id="c8a83-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="c8a83-111">以下は、異なる PSTN サイトに Skype for Business Cloud Connector エディションを展開するための構成例を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8a83-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="c8a83-112">展開を開始する前に、構成設定が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8a83-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="c8a83-113">PSTN サイト1</span><span class="sxs-lookup"><span data-stu-id="c8a83-113">PSTN Site 1</span></span>
  
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

<span data-ttu-id="c8a83-114">PSTN サイト2</span><span class="sxs-lookup"><span data-stu-id="c8a83-114">PSTN Site 2</span></span>
  
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

<span data-ttu-id="c8a83-115">追加する PSTN サイトごとに、「 [Deploy a single site In Cloud Connector](deploy-a-single-site-in-cloud-connector.md)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c8a83-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c8a83-116">高可用性 (HA) を準備するための共有フォルダーは、PSTN サイトごとです。</span><span class="sxs-lookup"><span data-stu-id="c8a83-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="c8a83-117">共有フォルダーは、PSTN サイト間で異なる **必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="c8a83-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="c8a83-118">複数のサイトに同じ共有フォルダーを使用しないでください。 ></span><span class="sxs-lookup"><span data-stu-id="c8a83-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="c8a83-119">マルチサイト展開と比較した高可用性 (HA) を備えた単一サイト</span><span class="sxs-lookup"><span data-stu-id="c8a83-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="c8a83-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="c8a83-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="c8a83-121">次の表に、HA サポートを備えた単一サイトと複数サイト展開の相違点を示します。</span><span class="sxs-lookup"><span data-stu-id="c8a83-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="c8a83-122">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="c8a83-122">**Category**</span></span>|<span data-ttu-id="c8a83-123">**項目**</span><span class="sxs-lookup"><span data-stu-id="c8a83-123">**Item**</span></span>|<span data-ttu-id="c8a83-124">**HA を備えた単一サイト**</span><span class="sxs-lookup"><span data-stu-id="c8a83-124">**Single-Site with HA**</span></span>|<span data-ttu-id="c8a83-125">**複数サイト**</span><span class="sxs-lookup"><span data-stu-id="c8a83-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c8a83-126">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-126">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-127">アプライアンスのホスト名</span><span class="sxs-lookup"><span data-stu-id="c8a83-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="c8a83-128">アプライアンス間での**違い**</span><span class="sxs-lookup"><span data-stu-id="c8a83-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c8a83-129">PSTN サイト間で**異なる**</span><span class="sxs-lookup"><span data-stu-id="c8a83-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c8a83-130">セットアップ</span><span class="sxs-lookup"><span data-stu-id="c8a83-130">Setup</span></span>  <br/> |<span data-ttu-id="c8a83-131">共有フォルダー</span><span class="sxs-lookup"><span data-stu-id="c8a83-131">Shared folder</span></span>  <br/> |<span data-ttu-id="c8a83-132">複数のアプライアンス間で **同じ** 共有フォルダーが必要</span><span class="sxs-lookup"><span data-stu-id="c8a83-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="c8a83-133">**複数のアプライアンス**間で共有フォルダーが必要</span><span class="sxs-lookup"><span data-stu-id="c8a83-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="c8a83-134">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-134">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="c8a83-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="c8a83-136">複数のアプライアンス間で **同じ** ドメインが必要</span><span class="sxs-lookup"><span data-stu-id="c8a83-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="c8a83-137">PSTN サイト間で **同じ** ドメインが必要</span><span class="sxs-lookup"><span data-stu-id="c8a83-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c8a83-138">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-138">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="c8a83-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="c8a83-140">ドメイン名と順序は、アプライアンス間で **同じ** である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8a83-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="c8a83-141">ドメイン名と順序は、PSTN サイト全体で **同じ** である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8a83-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c8a83-142">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-142">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-143">サイト名</span><span class="sxs-lookup"><span data-stu-id="c8a83-143">Site name</span></span>  <br/> |<span data-ttu-id="c8a83-144">**同じ** 複数のアプライアンスにまたがるサイト名</span><span class="sxs-lookup"><span data-stu-id="c8a83-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="c8a83-145">**異なる** PSTN サイト全体のサイト名</span><span class="sxs-lookup"><span data-stu-id="c8a83-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c8a83-146">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-146">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-147">サーバー名</span><span class="sxs-lookup"><span data-stu-id="c8a83-147">Server names</span></span>  <br/> |<span data-ttu-id="c8a83-148">アプライアンス間での**違い**</span><span class="sxs-lookup"><span data-stu-id="c8a83-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c8a83-149">PSTN サイト間で**異なる**</span><span class="sxs-lookup"><span data-stu-id="c8a83-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c8a83-150">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-150">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-151">内部プールの Fqdn</span><span class="sxs-lookup"><span data-stu-id="c8a83-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="c8a83-152">アプライアンス間で**同じ**</span><span class="sxs-lookup"><span data-stu-id="c8a83-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="c8a83-153">PSTN サイト間で**同じ**</span><span class="sxs-lookup"><span data-stu-id="c8a83-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c8a83-154">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-154">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-155">内部 Ip</span><span class="sxs-lookup"><span data-stu-id="c8a83-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="c8a83-156">アプライアンス間での**違い**</span><span class="sxs-lookup"><span data-stu-id="c8a83-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c8a83-157">PSTN サイト間で**異なる**</span><span class="sxs-lookup"><span data-stu-id="c8a83-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c8a83-158">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-158">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-159">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="c8a83-159">External FQDN</span></span>  <br/> |<span data-ttu-id="c8a83-160">アプライアンス間で**同じ**</span><span class="sxs-lookup"><span data-stu-id="c8a83-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="c8a83-161">PSTN サイト間で**異なる**</span><span class="sxs-lookup"><span data-stu-id="c8a83-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c8a83-162">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-162">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-163">外部 Ip</span><span class="sxs-lookup"><span data-stu-id="c8a83-163">External IPs</span></span>  <br/> |<span data-ttu-id="c8a83-164">アプライアンス間での**違い**</span><span class="sxs-lookup"><span data-stu-id="c8a83-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c8a83-165">PSTN サイト間で**異なる**</span><span class="sxs-lookup"><span data-stu-id="c8a83-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c8a83-166">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-166">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-167">PSTN GW 設定</span><span class="sxs-lookup"><span data-stu-id="c8a83-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="c8a83-168">アプライアンス間で**同じ**</span><span class="sxs-lookup"><span data-stu-id="c8a83-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="c8a83-169">PSTN サイト間で**異なる**</span><span class="sxs-lookup"><span data-stu-id="c8a83-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c8a83-170">構成</span><span class="sxs-lookup"><span data-stu-id="c8a83-170">Configure</span></span>  <br/> |<span data-ttu-id="c8a83-171">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="c8a83-171">DNS record</span></span>  <br/> |<span data-ttu-id="c8a83-172">**同じ**外部アクセス fqdn と**異なる**IP アドレスを持つレコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c8a83-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="c8a83-173">**異なる**外部アクセス fqdn と**異なる**IP アドレスを持つレコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c8a83-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="c8a83-174">セットアップ</span><span class="sxs-lookup"><span data-stu-id="c8a83-174">Setup</span></span>  <br/> |<span data-ttu-id="c8a83-175">ハイブリッドテナント</span><span class="sxs-lookup"><span data-stu-id="c8a83-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="c8a83-176">HybridPSTNSite の設定</span><span class="sxs-lookup"><span data-stu-id="c8a83-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="c8a83-177">フォールバックのための PeerDestination の設定</span><span class="sxs-lookup"><span data-stu-id="c8a83-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="c8a83-178">HybridPSTNSite の設定</span><span class="sxs-lookup"><span data-stu-id="c8a83-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="c8a83-179">フォールバックのための PeerDestination の設定</span><span class="sxs-lookup"><span data-stu-id="c8a83-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="c8a83-180">セットアップ</span><span class="sxs-lookup"><span data-stu-id="c8a83-180">Setup</span></span>  <br/> |<span data-ttu-id="c8a83-181">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="c8a83-181">Gateway</span></span>  <br/> |<span data-ttu-id="c8a83-182">このサイトの MS GW **M:N** マッピング</span><span class="sxs-lookup"><span data-stu-id="c8a83-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="c8a83-183">各 PSTN サイトの PSTN ゲートウェイは、同じサイトの仲介サーバーにのみ接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8a83-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="c8a83-184">セットアップ</span><span class="sxs-lookup"><span data-stu-id="c8a83-184">Setup</span></span>  <br/> |<span data-ttu-id="c8a83-185">ユーザー</span><span class="sxs-lookup"><span data-stu-id="c8a83-185">User</span></span>  <br/> |<span data-ttu-id="c8a83-186">UserPSTNSettings の設定</span><span class="sxs-lookup"><span data-stu-id="c8a83-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="c8a83-187">UserPSTNSettings の設定</span><span class="sxs-lookup"><span data-stu-id="c8a83-187">Set UserPSTNSettings</span></span>  <br/> |
   

