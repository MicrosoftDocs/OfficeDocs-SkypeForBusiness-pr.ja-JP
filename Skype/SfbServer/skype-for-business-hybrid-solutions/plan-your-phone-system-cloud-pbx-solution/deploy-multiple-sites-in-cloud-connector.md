---
title: Cloud Connector でマルチサイトを展開する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Cloud Connector エディションで複数の PSTN サイトを展開する方法について説明します。
ms.openlocfilehash: 04af3ffa69a0ba452277d497544d4ba6708b5cb8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="84226-103">Cloud Connector でマルチサイトを展開する</span><span class="sxs-lookup"><span data-stu-id="84226-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="84226-104">Cloud Connector エディションで複数の PSTN サイトを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84226-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="84226-p101">このセクションでは、複数の公衆交換電話網 (PSTN) サイトを展開する方法を説明します。サイトは、単一サイトの展開と同じ手順を使用して、一度に 1 つずつ展開します。このトピックでは、マルチサイト展開の考慮事項と、マルチサイト展開でのサイト間の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="84226-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="84226-108">複数の公衆交換電話網 (PSTN) サイト</span><span class="sxs-lookup"><span data-stu-id="84226-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="84226-109">PSTN の別のサイトのビジネス クラウド コネクタ ・ エディションの Skype を配置する構成の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="84226-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="84226-110">展開を開始する前に、構成設定が正しいこと確認してください。</span><span class="sxs-lookup"><span data-stu-id="84226-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="84226-111">PSTN サイト 1</span><span class="sxs-lookup"><span data-stu-id="84226-111">PSTN Site 1</span></span>
  
```
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

<span data-ttu-id="84226-112">PSTN サイト 2</span><span class="sxs-lookup"><span data-stu-id="84226-112">PSTN Site 2</span></span>
  
```
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

<span data-ttu-id="84226-113">サイトごとに PSTN を追加する、[クラウドのコネクタで 1 つのサイトの展開](deploy-a-single-site-in-cloud-connector.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="84226-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="84226-114">高可用性 (HA) を準備するための共有フォルダーは、PSTN サイト別です。</span><span class="sxs-lookup"><span data-stu-id="84226-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="84226-115">共有フォルダーは、PSTN サイトごとに異なる**必要があります**。</span><span class="sxs-lookup"><span data-stu-id="84226-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="84226-116">複数サイトに同じ共有フォルダーを使用しないで ></span><span class="sxs-lookup"><span data-stu-id="84226-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="84226-117">マルチサイト展開と高可用性 (HA) 対応の単一サイトの比較</span><span class="sxs-lookup"><span data-stu-id="84226-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="84226-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="84226-118"></span></span>

<span data-ttu-id="84226-119">次の表に、HA 対応の単一サイトとマルチサイト展開の違いのリストを示します。</span><span class="sxs-lookup"><span data-stu-id="84226-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="84226-120">**[カテゴリ]**</span><span class="sxs-lookup"><span data-stu-id="84226-120">**Category**</span></span>|<span data-ttu-id="84226-121">**アイテム**</span><span class="sxs-lookup"><span data-stu-id="84226-121">**Item**</span></span>|<span data-ttu-id="84226-122">**HA では、1 つのサイト**</span><span class="sxs-lookup"><span data-stu-id="84226-122">**Single-Site with HA**</span></span>|<span data-ttu-id="84226-123">**複数のサイト**</span><span class="sxs-lookup"><span data-stu-id="84226-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84226-124">セットアップ</span><span class="sxs-lookup"><span data-stu-id="84226-124">Setup</span></span>  <br/> |<span data-ttu-id="84226-125">共有フォルダー</span><span class="sxs-lookup"><span data-stu-id="84226-125">Shared folder</span></span>  <br/> |<span data-ttu-id="84226-126">アプライアンスの間で**同一**の共有フォルダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="84226-126">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="84226-127">複数のアプライアンス全体にわたって**異なる**共有フォルダーが必要</span><span class="sxs-lookup"><span data-stu-id="84226-127">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="84226-128">構成</span><span class="sxs-lookup"><span data-stu-id="84226-128">Configure</span></span>  <br/> |<span data-ttu-id="84226-129">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="84226-129">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="84226-130">複数のアプライアンス全体にわたって**同じ**ドメインが必要</span><span class="sxs-lookup"><span data-stu-id="84226-130">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="84226-131">複数の PSTN サイト全体にわたって**同じ**ドメインが必要</span><span class="sxs-lookup"><span data-stu-id="84226-131">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="84226-132">構成</span><span class="sxs-lookup"><span data-stu-id="84226-132">Configure</span></span>  <br/> |<span data-ttu-id="84226-133">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="84226-133">SIPDomains</span></span>  <br/> |<span data-ttu-id="84226-134">ドメイン名と注文する必要があります、**同じ**アプライアンスの間で</span><span class="sxs-lookup"><span data-stu-id="84226-134">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="84226-135">ドメイン名と順序は、**同じ**サイト間である PSTN</span><span class="sxs-lookup"><span data-stu-id="84226-135">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="84226-136">構成</span><span class="sxs-lookup"><span data-stu-id="84226-136">Configure</span></span>  <br/> |<span data-ttu-id="84226-137">サイト名</span><span class="sxs-lookup"><span data-stu-id="84226-137">Site name</span></span>  <br/> |<span data-ttu-id="84226-138">複数のアプライアンス全体にわたって**同じ**サイト名</span><span class="sxs-lookup"><span data-stu-id="84226-138">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="84226-139">複数の PSTN サイト全体にわたって**異なる**サイト名</span><span class="sxs-lookup"><span data-stu-id="84226-139">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="84226-140">構成</span><span class="sxs-lookup"><span data-stu-id="84226-140">Configure</span></span>  <br/> |<span data-ttu-id="84226-141">サーバー名</span><span class="sxs-lookup"><span data-stu-id="84226-141">Server names</span></span>  <br/> |<span data-ttu-id="84226-142">複数のアプライアンス全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="84226-142">**Different** across appliances</span></span> <br/> |<span data-ttu-id="84226-143">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="84226-143">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="84226-144">構成</span><span class="sxs-lookup"><span data-stu-id="84226-144">Configure</span></span>  <br/> |<span data-ttu-id="84226-145">内部プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="84226-145">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="84226-146">複数のアプライアンス全体にわたって**同じ**</span><span class="sxs-lookup"><span data-stu-id="84226-146">**Same** across appliances</span></span> <br/> |<span data-ttu-id="84226-147">複数の PSTN サイト全体にわたって**同じ**</span><span class="sxs-lookup"><span data-stu-id="84226-147">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="84226-148">構成</span><span class="sxs-lookup"><span data-stu-id="84226-148">Configure</span></span>  <br/> |<span data-ttu-id="84226-149">内部 IP</span><span class="sxs-lookup"><span data-stu-id="84226-149">Internal IPs</span></span>  <br/> |<span data-ttu-id="84226-150">複数のアプライアンス全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="84226-150">**Different** across appliances</span></span> <br/> |<span data-ttu-id="84226-151">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="84226-151">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="84226-152">構成</span><span class="sxs-lookup"><span data-stu-id="84226-152">Configure</span></span>  <br/> |<span data-ttu-id="84226-153">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="84226-153">External FQDN</span></span>  <br/> |<span data-ttu-id="84226-154">複数のアプライアンス全体にわたって**同じ**</span><span class="sxs-lookup"><span data-stu-id="84226-154">**Same** across appliances</span></span> <br/> |<span data-ttu-id="84226-155">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="84226-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="84226-156">構成</span><span class="sxs-lookup"><span data-stu-id="84226-156">Configure</span></span>  <br/> |<span data-ttu-id="84226-157">外部 IP</span><span class="sxs-lookup"><span data-stu-id="84226-157">External IPs</span></span>  <br/> |<span data-ttu-id="84226-158">複数のアプライアンス全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="84226-158">**Different** across appliances</span></span> <br/> |<span data-ttu-id="84226-159">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="84226-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="84226-160">構成</span><span class="sxs-lookup"><span data-stu-id="84226-160">Configure</span></span>  <br/> |<span data-ttu-id="84226-161">PSTN ゲートウェイの設定</span><span class="sxs-lookup"><span data-stu-id="84226-161">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="84226-162">複数のアプライアンス全体にわたって**同じ**</span><span class="sxs-lookup"><span data-stu-id="84226-162">**Same** across appliances</span></span> <br/> |<span data-ttu-id="84226-163">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="84226-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="84226-164">構成</span><span class="sxs-lookup"><span data-stu-id="84226-164">Configure</span></span>  <br/> |<span data-ttu-id="84226-165">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="84226-165">DNS record</span></span>  <br/> |<span data-ttu-id="84226-166">レコードを**同じ**外部アクセスの Fqdn と**異なる**IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="84226-166">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="84226-167">**異なる**外部アクセス FQDN と**異なる** IP アドレスを持つレコードを追加</span><span class="sxs-lookup"><span data-stu-id="84226-167">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="84226-168">セットアップ</span><span class="sxs-lookup"><span data-stu-id="84226-168">Setup</span></span>  <br/> |<span data-ttu-id="84226-169">ハイブリッド テナント</span><span class="sxs-lookup"><span data-stu-id="84226-169">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="84226-170">HybridPSTNSite の設定</span><span class="sxs-lookup"><span data-stu-id="84226-170">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="84226-171">フォールバック用 PeerDestination の設定</span><span class="sxs-lookup"><span data-stu-id="84226-171">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="84226-172">HybridPSTNSite の設定</span><span class="sxs-lookup"><span data-stu-id="84226-172">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="84226-173">フォールバック用 PeerDestination の設定</span><span class="sxs-lookup"><span data-stu-id="84226-173">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="84226-174">セットアップ</span><span class="sxs-lookup"><span data-stu-id="84226-174">Setup</span></span>  <br/> |<span data-ttu-id="84226-175">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="84226-175">Gateway</span></span>  <br/> |<span data-ttu-id="84226-176">このサイトでの MS GW **M:N** マッピング</span><span class="sxs-lookup"><span data-stu-id="84226-176">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="84226-177">各 PSTN サイトの PSTN ゲートウェイは、必ず同じサイトの仲介サーバーのみに接続します</span><span class="sxs-lookup"><span data-stu-id="84226-177">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="84226-178">セットアップ</span><span class="sxs-lookup"><span data-stu-id="84226-178">Setup</span></span>  <br/> |<span data-ttu-id="84226-179">ユーザー</span><span class="sxs-lookup"><span data-stu-id="84226-179">User</span></span>  <br/> |<span data-ttu-id="84226-180">UserPSTNSettings の設定</span><span class="sxs-lookup"><span data-stu-id="84226-180">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="84226-181">UserPSTNSettings の設定</span><span class="sxs-lookup"><span data-stu-id="84226-181">Set UserPSTNSettings</span></span>  <br/> |
   

