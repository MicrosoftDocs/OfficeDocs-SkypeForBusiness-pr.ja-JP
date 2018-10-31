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
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Cloud Connector エディションで複数の PSTN サイトを展開する方法について説明します。
ms.openlocfilehash: 388915d0ab22dc50378d84a82c01291cfd7c99eb
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851491"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="bc0a6-103">Cloud Connector でマルチサイトを展開する</span><span class="sxs-lookup"><span data-stu-id="bc0a6-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="bc0a6-104">Cloud Connector エディションで複数の PSTN サイトを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc0a6-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="bc0a6-p101">このセクションでは、複数の公衆交換電話網 (PSTN) サイトを展開する方法を説明します。サイトは、単一サイトの展開と同じ手順を使用して、一度に 1 つずつ展開します。このトピックでは、マルチサイト展開の考慮事項と、マルチサイト展開でのサイト間の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bc0a6-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="bc0a6-108">複数の公衆交換電話網 (PSTN) サイト</span><span class="sxs-lookup"><span data-stu-id="bc0a6-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="bc0a6-109">PSTN の別のサイトのビジネス クラウド コネクタ ・ エディションの Skype を配置する構成の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bc0a6-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="bc0a6-110">展開を開始する前に、構成設定が正しいこと確認してください。</span><span class="sxs-lookup"><span data-stu-id="bc0a6-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="bc0a6-111">PSTN サイト 1</span><span class="sxs-lookup"><span data-stu-id="bc0a6-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="bc0a6-112">PSTN サイト 2</span><span class="sxs-lookup"><span data-stu-id="bc0a6-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="bc0a6-113">サイトごとに PSTN を追加する、[クラウドのコネクタで 1 つのサイトの展開](deploy-a-single-site-in-cloud-connector.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bc0a6-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bc0a6-114">高可用性 (HA) を準備するための共有フォルダーは、PSTN サイト別です。</span><span class="sxs-lookup"><span data-stu-id="bc0a6-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="bc0a6-115">共有フォルダーは、PSTN サイトごとに異なる**必要があります**。</span><span class="sxs-lookup"><span data-stu-id="bc0a6-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="bc0a6-116">複数サイトに同じ共有フォルダーを使用しないで ></span><span class="sxs-lookup"><span data-stu-id="bc0a6-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="bc0a6-117">マルチサイト展開と高可用性 (HA) 対応の単一サイトの比較</span><span class="sxs-lookup"><span data-stu-id="bc0a6-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="bc0a6-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="bc0a6-118"></span></span>

<span data-ttu-id="bc0a6-119">次の表に、HA 対応の単一サイトとマルチサイト展開の違いのリストを示します。</span><span class="sxs-lookup"><span data-stu-id="bc0a6-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="bc0a6-120">**[カテゴリ]**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-120">**Category**</span></span>|<span data-ttu-id="bc0a6-121">**項目**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-121">**Item**</span></span>|<span data-ttu-id="bc0a6-122">**HA 対応の単一サイト**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-122">**Single-Site with HA**</span></span>|<span data-ttu-id="bc0a6-123">**マルチサイト**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc0a6-124">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-124">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-125">アプライアンスのホスト名</span><span class="sxs-lookup"><span data-stu-id="bc0a6-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="bc0a6-126">複数のアプライアンス全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-127">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bc0a6-128">セットアップ</span><span class="sxs-lookup"><span data-stu-id="bc0a6-128">Setup</span></span>  <br/> |<span data-ttu-id="bc0a6-129">共有フォルダー</span><span class="sxs-lookup"><span data-stu-id="bc0a6-129">Shared folder</span></span>  <br/> |<span data-ttu-id="bc0a6-130">アプライアンスの間で**同一**の共有フォルダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="bc0a6-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-131">複数のアプライアンス全体にわたって**異なる**共有フォルダーが必要</span><span class="sxs-lookup"><span data-stu-id="bc0a6-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="bc0a6-132">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-132">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="bc0a6-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="bc0a6-134">複数のアプライアンス全体にわたって**同じ**ドメインが必要</span><span class="sxs-lookup"><span data-stu-id="bc0a6-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-135">複数の PSTN サイト全体にわたって**同じ**ドメインが必要</span><span class="sxs-lookup"><span data-stu-id="bc0a6-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bc0a6-136">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-136">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-137">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="bc0a6-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="bc0a6-138">ドメイン名と注文する必要があります、**同じ**アプライアンスの間で</span><span class="sxs-lookup"><span data-stu-id="bc0a6-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-139">ドメイン名と順序は、**同じ**サイト間である PSTN</span><span class="sxs-lookup"><span data-stu-id="bc0a6-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bc0a6-140">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-140">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-141">サイト名</span><span class="sxs-lookup"><span data-stu-id="bc0a6-141">Site name</span></span>  <br/> |<span data-ttu-id="bc0a6-142">複数のアプライアンス全体にわたって**同じ**サイト名</span><span class="sxs-lookup"><span data-stu-id="bc0a6-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-143">複数の PSTN サイト全体にわたって**異なる**サイト名</span><span class="sxs-lookup"><span data-stu-id="bc0a6-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bc0a6-144">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-144">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-145">サーバー名</span><span class="sxs-lookup"><span data-stu-id="bc0a6-145">Server names</span></span>  <br/> |<span data-ttu-id="bc0a6-146">複数のアプライアンス全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-147">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bc0a6-148">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-148">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-149">内部プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="bc0a6-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="bc0a6-150">複数のアプライアンス全体にわたって**同じ**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-151">複数の PSTN サイト全体にわたって**同じ**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bc0a6-152">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-152">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-153">内部 IP</span><span class="sxs-lookup"><span data-stu-id="bc0a6-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="bc0a6-154">複数のアプライアンス全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-155">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bc0a6-156">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-156">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-157">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="bc0a6-157">External FQDN</span></span>  <br/> |<span data-ttu-id="bc0a6-158">複数のアプライアンス全体にわたって**同じ**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-159">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bc0a6-160">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-160">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-161">外部 IP</span><span class="sxs-lookup"><span data-stu-id="bc0a6-161">External IPs</span></span>  <br/> |<span data-ttu-id="bc0a6-162">複数のアプライアンス全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-163">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bc0a6-164">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-164">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-165">PSTN ゲートウェイの設定</span><span class="sxs-lookup"><span data-stu-id="bc0a6-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="bc0a6-166">複数のアプライアンス全体にわたって**同じ**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="bc0a6-167">複数の PSTN サイト全体にわたって**異なる**</span><span class="sxs-lookup"><span data-stu-id="bc0a6-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bc0a6-168">構成</span><span class="sxs-lookup"><span data-stu-id="bc0a6-168">Configure</span></span>  <br/> |<span data-ttu-id="bc0a6-169">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="bc0a6-169">DNS record</span></span>  <br/> |<span data-ttu-id="bc0a6-170">レコードを**同じ**外部アクセスの Fqdn と**異なる**IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="bc0a6-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="bc0a6-171">**異なる**外部アクセス FQDN と**異なる** IP アドレスを持つレコードを追加</span><span class="sxs-lookup"><span data-stu-id="bc0a6-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="bc0a6-172">セットアップ</span><span class="sxs-lookup"><span data-stu-id="bc0a6-172">Setup</span></span>  <br/> |<span data-ttu-id="bc0a6-173">ハイブリッド テナント</span><span class="sxs-lookup"><span data-stu-id="bc0a6-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="bc0a6-174">HybridPSTNSite の設定</span><span class="sxs-lookup"><span data-stu-id="bc0a6-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="bc0a6-175">フォールバック用 PeerDestination の設定</span><span class="sxs-lookup"><span data-stu-id="bc0a6-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="bc0a6-176">HybridPSTNSite の設定</span><span class="sxs-lookup"><span data-stu-id="bc0a6-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="bc0a6-177">フォールバック用 PeerDestination の設定</span><span class="sxs-lookup"><span data-stu-id="bc0a6-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="bc0a6-178">セットアップ</span><span class="sxs-lookup"><span data-stu-id="bc0a6-178">Setup</span></span>  <br/> |<span data-ttu-id="bc0a6-179">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="bc0a6-179">Gateway</span></span>  <br/> |<span data-ttu-id="bc0a6-180">このサイトでの MS GW **M:N** マッピング</span><span class="sxs-lookup"><span data-stu-id="bc0a6-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="bc0a6-181">各 PSTN サイトの PSTN ゲートウェイは、必ず同じサイトの仲介サーバーのみに接続します</span><span class="sxs-lookup"><span data-stu-id="bc0a6-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="bc0a6-182">セットアップ</span><span class="sxs-lookup"><span data-stu-id="bc0a6-182">Setup</span></span>  <br/> |<span data-ttu-id="bc0a6-183">ユーザー</span><span class="sxs-lookup"><span data-stu-id="bc0a6-183">User</span></span>  <br/> |<span data-ttu-id="bc0a6-184">UserPSTNSettings の設定</span><span class="sxs-lookup"><span data-stu-id="bc0a6-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="bc0a6-185">UserPSTNSettings の設定</span><span class="sxs-lookup"><span data-stu-id="bc0a6-185">Set UserPSTNSettings</span></span>  <br/> |
   

