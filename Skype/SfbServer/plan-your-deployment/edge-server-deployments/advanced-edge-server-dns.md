---
title: Skype for Business Server の高度なエッジ サーバー DNS の計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: '概要: Skype for Business Server 展開オプションのシナリオを確認します。 単一サーバーを使用する場合も、DNS または HLB を使用するサーバー プールを使用する場合も、このトピックで説明します。'
ms.openlocfilehash: 8615e0111385163b73558e5b76130f670f5d2db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813827"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a><span data-ttu-id="edd28-104">Skype for Business Server の高度なエッジ サーバー DNS の計画</span><span class="sxs-lookup"><span data-stu-id="edd28-104">Advanced Edge Server DNS planning for Skype for Business Server</span></span>
 
<span data-ttu-id="edd28-105">**概要:** Skype for Business Server 展開オプションのシナリオを確認します。</span><span class="sxs-lookup"><span data-stu-id="edd28-105">**Summary:** Review scenarios for Skype for Business Server deployment options.</span></span> <span data-ttu-id="edd28-106">単一サーバーを使用する場合でも、DNS または HLB を使用するサーバー プールを使用する場合でも、このトピックは役立ちます。</span><span class="sxs-lookup"><span data-stu-id="edd28-106">Whether you want a single server or prefer a server pool with DNS or HLB, this topic should help.</span></span>
  
<span data-ttu-id="edd28-107">Skype for Business Server のドメイン ネーム システム (DNS) の計画に関しては、決定に影響を与える可能性がある多くの要因があります。</span><span class="sxs-lookup"><span data-stu-id="edd28-107">When it comes to Domain Name System (DNS) planning for Skype for Business Server, there are a lot of factors that may play into your decision.</span></span> <span data-ttu-id="edd28-108">組織のドメイン構造が既に設定されている場合は、手順を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edd28-108">If your organization's domain structure's already in place, this may be a matter of reviewing how you're going to proceed.</span></span> <span data-ttu-id="edd28-109">まず、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd28-109">We'll begin with the topics found below:</span></span>
  
- [<span data-ttu-id="edd28-110">Skype for Business クライアント検索サービスのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="edd28-110">Walkthrough of Skype for Business clients locating services</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [<span data-ttu-id="edd28-111">スプリットブレイン DNS</span><span class="sxs-lookup"><span data-stu-id="edd28-111">Split-brain DNS</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [<span data-ttu-id="edd28-112">スプリットブレイン DNS を使用しない自動構成</span><span class="sxs-lookup"><span data-stu-id="edd28-112">Automatic configuration without split-brain DNS</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [<span data-ttu-id="edd28-113">DNS 障害復旧</span><span class="sxs-lookup"><span data-stu-id="edd28-113">DNS disaster recovery</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [<span data-ttu-id="edd28-114">DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="edd28-114">DNS load balancing</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a><span data-ttu-id="edd28-115">Skype for Business クライアント検索サービスのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="edd28-115">Walkthrough of Skype for Business clients locating services</span></span>
<span data-ttu-id="edd28-116"><a name="WalkthroughOfSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="edd28-116"><a name="WalkthroughOfSkype"> </a></span></span>

<span data-ttu-id="edd28-117">Skype for Business クライアントは、Skype for Business Server でサービスを検索してアクセスする方法について、以前のバージョンの Lync クライアントに似ています。</span><span class="sxs-lookup"><span data-stu-id="edd28-117">Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server.</span></span> <span data-ttu-id="edd28-118">このセクションでは、サーバーの場所の処理について詳しい説明を示します。</span><span class="sxs-lookup"><span data-stu-id="edd28-118">This section details the server location process.</span></span>
  
1. <span data-ttu-id="edd28-119">lyncdiscoverinternal。\<domain\></span><span class="sxs-lookup"><span data-stu-id="edd28-119">lyncdiscoverinternal.\<domain\></span></span>
    
     <span data-ttu-id="edd28-120">*これは、内部 Web サービス上の自動検出サービスの A ホスト レコードです。*</span><span class="sxs-lookup"><span data-stu-id="edd28-120">*This is an A host record for the Autodiscover service on the internal web services.*</span></span> 
    
2. <span data-ttu-id="edd28-121">lyncdiscover。\<domain\></span><span class="sxs-lookup"><span data-stu-id="edd28-121">lyncdiscover.\<domain\></span></span>
    
     <span data-ttu-id="edd28-122">*これは、外部 Web サービス上の自動検出サービスの A ホスト レコードです。*</span><span class="sxs-lookup"><span data-stu-id="edd28-122">*This is an A host record for the Autodiscover service on the external web services.*</span></span> 
    
3. <span data-ttu-id="edd28-123">_sipinternaltls._tcp。\<domain\></span><span class="sxs-lookup"><span data-stu-id="edd28-123">_sipinternaltls._tcp.\<domain\></span></span>
    
     <span data-ttu-id="edd28-124">*これは、内部 TLS 接続の SRV レコードです。*</span><span class="sxs-lookup"><span data-stu-id="edd28-124">*This is a SRV record for internal TLS connections.*</span></span> 
    
4. <span data-ttu-id="edd28-125">_sip._tls。\<domain\></span><span class="sxs-lookup"><span data-stu-id="edd28-125">_sip._tls.\<domain\></span></span>
    
     <span data-ttu-id="edd28-126">*これは、外部 TLS 接続の SRV レコードです。*</span><span class="sxs-lookup"><span data-stu-id="edd28-126">*This is a SRV record for external TLS connections.*</span></span> 
    
5. <span data-ttu-id="edd28-127">sipinternal。\<domain\></span><span class="sxs-lookup"><span data-stu-id="edd28-127">sipinternal.\<domain\></span></span>
    
     <span data-ttu-id="edd28-128">*これはフロント エンド プールまたはディレクターの A ホスト レコードで、内部ネットワーク上でのみ解決できます。*</span><span class="sxs-lookup"><span data-stu-id="edd28-128">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
6. <span data-ttu-id="edd28-129">sip.\<domain\></span><span class="sxs-lookup"><span data-stu-id="edd28-129">sip.\<domain\></span></span>
    
     <span data-ttu-id="edd28-130">*これはフロント エンド プールまたはディレクターの A ホスト レコードで、内部ネットワーク上でのみ解決できます。*</span><span class="sxs-lookup"><span data-stu-id="edd28-130">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
7. <span data-ttu-id="edd28-131">sipexternal。\<domain\></span><span class="sxs-lookup"><span data-stu-id="edd28-131">sipexternal.\<domain\></span></span>
    
     <span data-ttu-id="edd28-132">*クライアントが外部の場合、これはアクセス エッジ サービスの A ホスト レコードです。*</span><span class="sxs-lookup"><span data-stu-id="edd28-132">*This is an A host record for the Access Edge service, when the client is external.*</span></span> 
    
<span data-ttu-id="edd28-133">自動検出サービスは常に優先され、サービスの場所の推奨される方法であり、他の方法はフォールバックメソッドです。</span><span class="sxs-lookup"><span data-stu-id="edd28-133">The Autodiscover service is always favored as that's the preferred method for service location, and the others are fallback methods.</span></span>
  
> [!NOTE]
> <span data-ttu-id="edd28-134">SRV レコードを作成する場合、DNS SRV レコードが作成されているのと同じドメイン内の DNS A (および IPv6 アドレスを使用している場合は AAAA) をポイントする必要がある点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="edd28-134">When you're creating SRV records, it's important to remember that they need to point to a DNS A (and AAAA if you're using IPv6 addressing) in the same domain in which the DNS SRV record's being created.</span></span> <span data-ttu-id="edd28-135">たとえば、SRV レコードが contoso.com にある場合、そのレコードがポイントしている A (および AAAA) レコードは、fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="edd28-135">For example, if they SRV record's in contoso.com, the A (and AAAA) record it points to can't be in fabrikam.com.</span></span> 
  
<span data-ttu-id="edd28-136">これを行う必要がある場合は、サービスを手動で検出するためにモバイル デバイスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="edd28-136">If you're inclined to do it, you can set your mobile device up for manual discovery of services.</span></span> <span data-ttu-id="edd28-137">これが必要な場合は、次に示すプロトコルとパスを含む、内部および外部の完全な自動検出サービス URI を使用して、各ユーザーがモバイル デバイス設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edd28-137">If that's what you're looking to do, each user needs to configure their mobile device settings with the full internal and external Autodiscover service URIs, including the protocol and path, as follows:</span></span>
  
- <span data-ttu-id="edd28-138">外部アクセスの場合: https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="edd28-138">For external access: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span></span>
    
- <span data-ttu-id="edd28-139">内部アクセスの場合: https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="edd28-139">For internal access: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span></span>
    
<span data-ttu-id="edd28-140">手動検出ではなく、自動検出を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="edd28-140">We do recommend you use automatic discovery as opposed to manual discovery.</span></span> <span data-ttu-id="edd28-141">ただし、トラブルシューティングやテストを行う場合は、手動設定が非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="edd28-141">But if you're doing some troubleshooting or testing, manual settings can be very helpful.</span></span>
  
## <a name="split-brain-dns"></a><span data-ttu-id="edd28-142">スプリットブレイン DNS</span><span class="sxs-lookup"><span data-stu-id="edd28-142">Split-brain DNS</span></span>
<span data-ttu-id="edd28-143"><a name="SplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="edd28-143"><a name="SplitBrainDNS"> </a></span></span>

<span data-ttu-id="edd28-144">これは、同じ名前空間を持つ 2 つの DNS ゾーンがある DNS 構成です。</span><span class="sxs-lookup"><span data-stu-id="edd28-144">This is a DNS configuration where you have two DNS zones with the same namespace.</span></span> <span data-ttu-id="edd28-145">最初の DNS ゾーンは内部要求を処理し、2 番目の DNS ゾーンは外部要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="edd28-145">The first DNS zone handles internal requests, while the second DNS zone handles external requests.</span></span>
  
<span data-ttu-id="edd28-146">企業がこれを行う理由</span><span class="sxs-lookup"><span data-stu-id="edd28-146">Why would a company do this?</span></span> <span data-ttu-id="edd28-147">内部および外部で同じ名前空間を使用する必要がある場合がありますが、もちろん、これにより、多くの DNS SRV レコードと A レコードが 1 つのゾーンまたは別のゾーンに一意で、重複がある場合、これらのレコードに関連付けられた IP アドレスは一意になります。</span><span class="sxs-lookup"><span data-stu-id="edd28-147">They may have a requirement to use the same namespace internally and externally, but of course this will lead to many DNS SRV and A records being unique to one zone or another, and where there is duplication, the IP addresses associated with these records would be unique.</span></span>
  
<span data-ttu-id="edd28-148">これはいくつかの課題を示しています。</span><span class="sxs-lookup"><span data-stu-id="edd28-148">This presents some challenges.</span></span> <span data-ttu-id="edd28-149">最も重要なのは、スプリットブレイン DNS が Mobility **でサポートされていない** 点です。</span><span class="sxs-lookup"><span data-stu-id="edd28-149">The most important is that split-brain DNS is **not supported** for Mobility.</span></span> <span data-ttu-id="edd28-150">これは、LyncDiscover と LyncDiscoverInternal DNS レコード (LyncDiscover は外部 DNS サーバーで定義する必要があるのに対し、LyncDiscoverInternal は内部 DNS サーバーで定義する必要がある) ためです。</span><span class="sxs-lookup"><span data-stu-id="edd28-150">This is because of the LyncDiscover and LyncDiscoverInternal DNS records (LyncDiscover has to be defined on you external DNS server, while LyncDiscoverInternal has to be defined on your internal DNS server).</span></span>
  
<span data-ttu-id="edd28-151">ここでは、内部ゾーンと外部ゾーンの DNS レコードを一覧表示しますが、詳細な例については、「エッジ サーバーの環境要件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd28-151">We'll list the DNS records for the internal and external zones here, but you can find detailed examples on the Edge Server environmental requirements section.</span></span>
  
### <a name="internal-dns"></a><span data-ttu-id="edd28-152">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="edd28-152">Internal DNS</span></span>

- <span data-ttu-id="edd28-153">権限がある (たとえば) contoso.com DNS ゾーンが含まれている。</span><span class="sxs-lookup"><span data-stu-id="edd28-153">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="edd28-154">この内部contoso.com次の情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="edd28-154">This internal contoso.com contains:</span></span>
    
  - <span data-ttu-id="edd28-155">フロント エンド プール、ディレクター プールまたはディレクター プール名、および組織のネットワーク内で Skype for Business Server を実行しているすべての内部サーバーの DNS A および AAAA (IPv6 アドレス指定を使用している場合) レコード。</span><span class="sxs-lookup"><span data-stu-id="edd28-155">DNS A and AAAA (if you're using IPv6 addressing) records for your Front End pool, Director pool or Director pool name, and all internal servers running Skype for Business Server in your organization's network.</span></span>
    
  - <span data-ttu-id="edd28-156">境界ネットワーク内の各 Skype for Business Server エッジ サーバーのエッジ内部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合) レコード。</span><span class="sxs-lookup"><span data-stu-id="edd28-156">DNS A and AAAA (if you're using IPv6 addressing) records for your Edge internal interface for each Skype for Business Server Edge Server in your perimeter network.</span></span>
    
  - <span data-ttu-id="edd28-157">境界ネットワーク内の各リバース プロキシ サーバーの内部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合) レコード (リバース プロキシの管理にはオプション)。</span><span class="sxs-lookup"><span data-stu-id="edd28-157">DNS A and AAAA (if you're using IPv6 addressing) records for the internal interface of each reverse proxy server in your perimeter network (which is **optional** for management of a reverse proxy).</span></span>
    
  - <span data-ttu-id="edd28-158">内部 Skype for Business Server クライアントの自動構成用の DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード **(オプション)。**</span><span class="sxs-lookup"><span data-stu-id="edd28-158">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server client autoconfiguration (which is **optional** ).</span></span>
    
  - <span data-ttu-id="edd28-159">DNS A および AAAA (IPv6 アドレス指定を使用している場合) または CNAME レコードを使用して、Skype for Business Server Web サービスの自動検出を行います (**オプション)。**</span><span class="sxs-lookup"><span data-stu-id="edd28-159">DNS A and AAAA (if you're using IPv6 addressing) or CNAME records for automatic discovery of Skype for Business Server Web Services (which is **optional** ).</span></span>
    
- <span data-ttu-id="edd28-160">境界ネットワーク内のすべての Skype for Business Server 内部エッジ インターフェイスは、この内部 DNS ゾーンを使用してクエリを解決contoso.com。</span><span class="sxs-lookup"><span data-stu-id="edd28-160">All your Skype for Business Server internal Edge interfaces in your perimeter network use this internal DNS zone for resolving queries to contoso.com.</span></span>
    
- <span data-ttu-id="edd28-161">Skype for Business Server を実行しているすべてのサーバー、および企業ネットワークで Skype for Business Server を実行しているクライアントは、contoso.com へのクエリを解決するために内部 DNS サーバーをポイントするか、各エッジ サーバーのホスト ファイルを使用して次ホップ サーバー (特にディレクターまたはディレクター プールの VIP 用) の A および AAAA (IPv6 アドレス指定を使用している場合) レコードを一覧表示します。、フロントエンド プールの VIP、または Standard Edition サーバー)。</span><span class="sxs-lookup"><span data-stu-id="edd28-161">All servers running Skype for Business Server, and clients running Skype for Business Server in the corporate network, point to internal DNS servers for resolving queries to contoso.com, or they use the Host file on each Edge Server and list A and AAAA (if you're using IPv6 addressing) records for the next hop server (specifically for the Director or Director pool VIP, Front End pool VIP, or Standard Edition server).</span></span>
    
### <a name="external-dns"></a><span data-ttu-id="edd28-162">外部 DNS</span><span class="sxs-lookup"><span data-stu-id="edd28-162">External DNS</span></span>

- <span data-ttu-id="edd28-163">権限がある (たとえば) contoso.com DNS ゾーンが含まれている。</span><span class="sxs-lookup"><span data-stu-id="edd28-163">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="edd28-164">この外部contoso.com次の情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="edd28-164">This external contoso.com contains:</span></span>
    
  - <span data-ttu-id="edd28-165">Skype for Business Server Web サービスの自動検出用の DNS A および AAAA (IPv6 アドレスを使用している場合)、または CNAME レコード。</span><span class="sxs-lookup"><span data-stu-id="edd28-165">DNS A and AAAA (if you're using IPv6 addressing), or CNAME records, for automatic discovery of Skype for Business Server web services.</span></span> <span data-ttu-id="edd28-166">これはモビリティで使用するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="edd28-166">This is for use with mobility.</span></span>
    
  - <span data-ttu-id="edd28-167">境界ネットワーク内の各 Skype for Business Server エッジ サーバーまたはハードウェア負荷分散 (HLB) VIP のエッジ外部インターフェイスの DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="edd28-167">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server Edge Server or hardware load balanced (HLB) VIP in the perimeter network.</span></span>
    
  - <span data-ttu-id="edd28-168">境界ネットワーク内のリバース プロキシ サーバーの外部インターフェイスまたは (リバース プロキシ サーバーのプールの VIP) の DNS A および AAAA (IPv6 アドレスを使用している場合) および SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="edd28-168">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.</span></span>
    
  - <span data-ttu-id="edd28-169">Skype for Business Server クライアントの自動構成用の DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード ( **オプション** )。</span><span class="sxs-lookup"><span data-stu-id="edd28-169">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server client autoconfiguration ( **optional** ).</span></span>
    
## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="edd28-170">スプリットブレイン DNS を使用しない自動構成</span><span class="sxs-lookup"><span data-stu-id="edd28-170">Automatic configuration without split-brain DNS</span></span>
<span data-ttu-id="edd28-171"><a name="NoSplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="edd28-171"><a name="NoSplitBrainDNS"> </a></span></span>

<span data-ttu-id="edd28-172">スプリットブレイン DNS を使用しない場合は、ここに示す回避策のいずれかを使用しない限り、Skype for Business を実行しているクライアントの内部自動構成は機能しません。</span><span class="sxs-lookup"><span data-stu-id="edd28-172">If you don't use split-brain DNS, internal automatic configuration of clients running Skype for Business won't work unless you're using one of the workarounds we have here.</span></span> <span data-ttu-id="edd28-173">どうしてでしょうか?</span><span class="sxs-lookup"><span data-stu-id="edd28-173">Why not?</span></span> <span data-ttu-id="edd28-174">Skype for Business Server では、自動構成用に指定されたフロントエンド プールのドメインと一致するユーザーの SIP URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="edd28-174">Because Skype for Business Server requires the user's SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="edd28-175">これは、以前のバージョンの Lync Server から変更されていない。</span><span class="sxs-lookup"><span data-stu-id="edd28-175">This hasn't changed from earlier versions of Lync Server.</span></span>
  
<span data-ttu-id="edd28-176">したがって、2 つの SIP ドメインが使用されている場合は、次の DNS SRV レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="edd28-176">So, if you have two SIP domains in use, you'd need these DNS SRV records:</span></span>
  
- <span data-ttu-id="edd28-177">_sipinternaltls._tcp.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="edd28-177">_sipinternaltls._tcp.contoso.com.</span></span> <span data-ttu-id="edd28-178">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-178">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>
    
     <span data-ttu-id="edd28-179">*ユーザーが bob@contoso.com としてサインインすると、ユーザーの SIP ドメインがフロントエンド プール (contoso.com) のドメインと一致する場合、このレコードは自動構成で機能します。*</span><span class="sxs-lookup"><span data-stu-id="edd28-179">*If a user signs in as bob@contoso.com, this record would work for automatic configuration, as the user's SIP domain matches the domain of the Front End pool (contoso.com).*</span></span> 
    
- <span data-ttu-id="edd28-180">_sipinternaltls._tcp.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="edd28-180">_sipinternaltls._tcp.fabrikam.com.</span></span> <span data-ttu-id="edd28-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="edd28-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="edd28-182">*ユーザーが alice@fabrikam.com としてサインインすると、SIP ドメインがドメインのフロント エンド プールと一致する場合も、このレコードは 2 番目のドメインの自動構成で機能します。*</span><span class="sxs-lookup"><span data-stu-id="edd28-182">*If a user signs in as alice@fabrikam.com, this record would work for automatic configuration of the second domain, again because the SIP domain matches the Front End pool for that domain.*</span></span> 
    
<span data-ttu-id="edd28-183">この例をさらに詳しくは、次の方法では動作しません。</span><span class="sxs-lookup"><span data-stu-id="edd28-183">To take the example further, this would not work:</span></span>
  
- <span data-ttu-id="edd28-184">_sipinternaltls._tcp.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="edd28-184">_sipinternaltls._tcp.litwareinc.com.</span></span> <span data-ttu-id="edd28-185">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="edd28-185">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="edd28-186">*SIP ドメイン litwareinc.com (tim@litwareinc.com) がプール内のドメイン (fabrikam.com) と一致しないので、ユーザーが tim@litwareinc.com としてサインインしても自動構成は機能しません。*</span><span class="sxs-lookup"><span data-stu-id="edd28-186">*A user signing in as tim@litwareinc.com won't work for automatic configuration, because his SIP domain (litwareinc.com) doesn't match the domain in the pool (fabrikam.com).*</span></span> 
    
<span data-ttu-id="edd28-187">これで、スプリットブレイン DNS を使用しない Skype for Business クライアントの自動要件が必要な場合は、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="edd28-187">So now that we know all that, if you need automatic requirement for your Skype for Business clients without split-brain DNS, you have these options:</span></span>
  
- <span data-ttu-id="edd28-188">**グループ ポリシー オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="edd28-188">**Group Policy Objects**</span></span>
    
    <span data-ttu-id="edd28-189">グループ ポリシー オブジェクト (GPO) を使用して、正しいサーバー値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="edd28-189">You can use Group Policy Objects (GPOs) to populate the correct server values.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="edd28-190">このオプションは自動構成を有効にしないが、手動構成を自動化する。</span><span class="sxs-lookup"><span data-stu-id="edd28-190">This option doesn't enable automatic configuration, but it does automate manual configuration.</span></span> <span data-ttu-id="edd28-191">この方法を使用する場合、自動構成に関連付けられている SRV レコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="edd28-191">If this approach is used, the SRV records associated with automatic configuration aren't required.</span></span> 
  
- <span data-ttu-id="edd28-192">**内部ゾーンの一致**</span><span class="sxs-lookup"><span data-stu-id="edd28-192">**Matching internal zone**</span></span>
    
    <span data-ttu-id="edd28-193">外部 DNS ゾーン (contoso.com など) に一致するゾーンを内部 DNS に作成し、自動構成に使用される Skype for Business Server プールに対応する DNS A (および IPv6 アドレス指定を使用している場合は AAAA) レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edd28-193">You'll need to create a zone in your internal DNS that matches your external DNS zone (for example, contoso.com), and then create DNS A (and AAAA if you're using IPv6 addressing) records that correspond to the Skype for Business Server pool used for automatic configuration.</span></span>
    
    <span data-ttu-id="edd28-194">たとえば、ユーザーが pool01.contoso.net にホームとしていて、Skype for Business に bob@contoso.com としてサインインしている場合は、contoso.com という内部 DNS ゾーンを作成し、その内部に pool01.contoso.com の DNS A (および IPv6 アドレス指定が使用されている場合は AAAA) レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edd28-194">For example, if you have a user homed on pool01.contoso.net, but signs into Skype for Business as bob@contoso.com, create an internal DNS zone called contoso.com, and inside it you need to create a DNS A (and AAAA if IPv6 addressing's being used) record for pool01.contoso.com.</span></span>
    
- <span data-ttu-id="edd28-195">**ピンポイントの内部ゾーン**</span><span class="sxs-lookup"><span data-stu-id="edd28-195">**Pin-point internal zone**</span></span>
    
    <span data-ttu-id="edd28-196">内部 DNS でゾーン全体を作成するオプションではない場合は、自動構成に必要な SRV レコードに対応するピンポイント (専用) ゾーンを作成し、dnscmd.exe を使用してこれらのゾーンにデータを設定できます。</span><span class="sxs-lookup"><span data-stu-id="edd28-196">If creating an entire zone in your internal DNS isn't an option for you, you can create pin-point (dedicated) zones that correspond to the SRV records required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="edd28-197">Dnscmd.exe DNS ユーザー インターフェイスはピンポイント ゾーンの作成をサポートしないので、この設定は必須です。</span><span class="sxs-lookup"><span data-stu-id="edd28-197">Dnscmd.exe is required because the DNS user interface won't support the creation of pin-point zones.</span></span>
    
    <span data-ttu-id="edd28-198">たとえば、SIP ドメインが contoso.com で、pool01 というフロントエンド プールに 2 つのフロントエンド サーバーが含まれている場合、内部 DNS には次のピンポイント ゾーンと A レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="edd28-198">For example, if your SIP domain is contoso.com, and you have a Front End pool called pool01 that contains two Front End Servers, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    <span data-ttu-id="edd28-199">環境内に 2 番目の SIP ドメインがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="edd28-199">You may have a second SIP domain in your environment.</span></span> <span data-ttu-id="edd28-200">その場合は、内部 DNS に次のピンポイント ゾーンと A レコードが必要になります。</span><span class="sxs-lookup"><span data-stu-id="edd28-200">In that case, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> <span data-ttu-id="edd28-201">フロントエンド プールの FQDN が 2 回表示されますが、2 つの異なる IP アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edd28-201">You'll see the Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="edd28-202">これは、DNS 負荷分散が使用されているからです。</span><span class="sxs-lookup"><span data-stu-id="edd28-202">That's because DNS load balancing is used.</span></span> <span data-ttu-id="edd28-203">HLB を使用する場合、フロントエンド プール エントリは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="edd28-203">If HLB is used, there'd only be a single Front End pool entry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="edd28-204">また、フロントエンド プールの FQDN の値は、contoso.com と fabrikam.comの間で変更されますが、IP アドレスは変わりません。</span><span class="sxs-lookup"><span data-stu-id="edd28-204">Also, the Front End pool FQDN values change between the contoso.com and fabrikam.com examples, but the IP addresses remain the same.</span></span> <span data-ttu-id="edd28-205">これは、いずれかの SIP ドメインからサインインしているユーザーが、自動構成に同じフロントエンド プールを使用するからです。</span><span class="sxs-lookup"><span data-stu-id="edd28-205">That's because users who're signing in from either SIP domain will be using the same Front End pool for automatic configuration.</span></span> 
  
## <a name="dns-disaster-recovery"></a><span data-ttu-id="edd28-206">DNS 障害復旧</span><span class="sxs-lookup"><span data-stu-id="edd28-206">DNS disaster recovery</span></span>
<span data-ttu-id="edd28-207"><a name="DNSDR"> </a></span><span class="sxs-lookup"><span data-stu-id="edd28-207"><a name="DNSDR"> </a></span></span>

<span data-ttu-id="edd28-208">Skype for Business Server Web トラフィックを障害復旧 (DR) およびフェールオーバー サイトにリダイレクトする DNS を構成するには、GeoDNS をサポートする DNS プロバイダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edd28-208">To configure DNS to redirect Skype for Business Server web traffic to your disaster recover (DR) and failover sites, you need to use a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="edd28-209">障害復旧をサポートする DNS レコードを設定して、1 つのフロントエンド プール全体がダウンしても Web サービスを使用する機能を続行できます。</span><span class="sxs-lookup"><span data-stu-id="edd28-209">You can set up your DNS records to support disaster recover, so that features that use web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="edd28-210">この DR 機能は、自動検出、会議、ダイヤルインの簡易 URL をサポートします。</span><span class="sxs-lookup"><span data-stu-id="edd28-210">This DR feature supports the Autodiscover, Meet and Dial-in simple URLs.</span></span>
  
<span data-ttu-id="edd28-211">追加の DNS ホスト A (IPv6 を使用する場合は AAAA) レコードを定義して構成し、GeoDNS プロバイダーで Web サービスの内部および外部の解決を行います。</span><span class="sxs-lookup"><span data-stu-id="edd28-211">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider.</span></span> <span data-ttu-id="edd28-212">次の詳細は、ペアのプールが地理的に分散し、プロバイダーがサポートする GeoDNS がラウンドロビン **DNS** を持っているか、Pool1 をプライマリとして使用するように構成され、通信損失や停電が発生した場合に Pool2 に障害が発生した場合に Pool2 に障害が発生したと想定しています。</span><span class="sxs-lookup"><span data-stu-id="edd28-212">The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span></span>
  
<span data-ttu-id="edd28-213">この表に示す DNS レコードはすべて例です。</span><span class="sxs-lookup"><span data-stu-id="edd28-213">All the DNS records in this table are examples.</span></span>
  
|<span data-ttu-id="edd28-214">**GeoDNS レコード**</span><span class="sxs-lookup"><span data-stu-id="edd28-214">**GeoDNS record**</span></span>|<span data-ttu-id="edd28-215">**プール レコード**</span><span class="sxs-lookup"><span data-stu-id="edd28-215">**Pool records**</span></span>|<span data-ttu-id="edd28-216">**CNAME レコード**</span><span class="sxs-lookup"><span data-stu-id="edd28-216">**CNAME records**</span></span>|<span data-ttu-id="edd28-217">**DNS 設定 (1 つのオプションを選択)**</span><span class="sxs-lookup"><span data-stu-id="edd28-217">**DNS settings (select one option)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="edd28-218">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-218">Meet-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-219">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-219">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="edd28-220">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-220">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-221">Meet.contoso.comをMeet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-221">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>  <br/>   <br/> |<span data-ttu-id="edd28-222">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="edd28-222">Round Robin between pools</span></span>  <br/> <span data-ttu-id="edd28-223">**または**</span><span class="sxs-lookup"><span data-stu-id="edd28-223">**OR**</span></span> <br/> <span data-ttu-id="edd28-224">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="edd28-224">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="edd28-225">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-225">Meet-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-226">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-226">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="edd28-227">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-227">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-228">Meet.contoso.comをMeet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-228">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>   <br/> |<span data-ttu-id="edd28-229">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="edd28-229">Round Robin between pools</span></span>  <br/> <span data-ttu-id="edd28-230">**または**</span><span class="sxs-lookup"><span data-stu-id="edd28-230">**OR**</span></span> <br/> <span data-ttu-id="edd28-231">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="edd28-231">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="edd28-232">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-232">Dialin-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-233">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-233">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="edd28-234">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-234">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-235">Meet.contoso.comをMeet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-235">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="edd28-236">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="edd28-236">Round Robin between pools</span></span>  <br/> <span data-ttu-id="edd28-237">**または**</span><span class="sxs-lookup"><span data-stu-id="edd28-237">**OR**</span></span> <br/> <span data-ttu-id="edd28-238">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="edd28-238">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="edd28-239">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-239">Dialin-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-240">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-240">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="edd28-241">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-241">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-242">Meet.contoso.comをMeet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-242">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>  <br/> |<span data-ttu-id="edd28-243">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="edd28-243">Round Robin between pools</span></span>  <br/> <span data-ttu-id="edd28-244">**または**</span><span class="sxs-lookup"><span data-stu-id="edd28-244">**OR**</span></span> <br/> <span data-ttu-id="edd28-245">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="edd28-245">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="edd28-246">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-246">Lyncdiscoverint-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-247">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-247">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="edd28-248">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-248">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-249">Meet.contoso.comをMeet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-249">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>   <br/> |<span data-ttu-id="edd28-250">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="edd28-250">Round Robin between pools</span></span>  <br/> <span data-ttu-id="edd28-251">**または**</span><span class="sxs-lookup"><span data-stu-id="edd28-251">**OR**</span></span> <br/> <span data-ttu-id="edd28-252">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="edd28-252">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="edd28-253">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-253">Lyncdiscover-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-254">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-254">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="edd28-255">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-255">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-256">Meet.contoso.comをMeet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-256">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>  <br/> |<span data-ttu-id="edd28-257">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="edd28-257">Round Robin between pools</span></span>  <br/> <span data-ttu-id="edd28-258">**または**</span><span class="sxs-lookup"><span data-stu-id="edd28-258">**OR**</span></span> <br/> <span data-ttu-id="edd28-259">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="edd28-259">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="edd28-260">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-260">Scheduler-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-261">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-261">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="edd28-262">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-262">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-263">Meet.contoso.comをMeet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-263">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="edd28-264">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="edd28-264">Round Robin between pools</span></span>  <br/> <span data-ttu-id="edd28-265">**または**</span><span class="sxs-lookup"><span data-stu-id="edd28-265">**OR**</span></span> <br/> <span data-ttu-id="edd28-266">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="edd28-266">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="edd28-267">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-267">Scheduler-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-268">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-268">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="edd28-269">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-269">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-270">Meet.contoso.comをMeet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-270">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="edd28-271">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="edd28-271">Round Robin between pools</span></span>  <br/> <span data-ttu-id="edd28-272">**または**</span><span class="sxs-lookup"><span data-stu-id="edd28-272">**OR**</span></span> <br/> <span data-ttu-id="edd28-273">プライマリを使用し、障害が発生した場合はセカンダリに接続する</span><span class="sxs-lookup"><span data-stu-id="edd28-273">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="edd28-274">DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="edd28-274">DNS load balancing</span></span>
<span data-ttu-id="edd28-275"><a name="DNSLB"> </a></span><span class="sxs-lookup"><span data-stu-id="edd28-275"><a name="DNSLB"> </a></span></span>

<span data-ttu-id="edd28-276">DNS 負荷分散は、通常、アプリケーション レベルで実装されます。</span><span class="sxs-lookup"><span data-stu-id="edd28-276">DNS load balancing is usually implemented at the application level.</span></span> <span data-ttu-id="edd28-277">アプリケーション (たとえば、Skype for Business を実行しているクライアント) は、プール FQDN の DNS A および AAAA (IPv6 アドレスが使用されている場合) レコード クエリから返された IP アドレスの 1 つに接続して、プール内のサーバーへの接続を試行します。</span><span class="sxs-lookup"><span data-stu-id="edd28-277">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool FQDN.</span></span>
  
<span data-ttu-id="edd28-278">たとえば、pool01.contoso.com という名前のプールに 3 つのフロントエンド サーバーがある場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="edd28-278">For example, if there are three Front End Servers in a pool named pool01.contoso.com, the following would happen:</span></span>
  
- <span data-ttu-id="edd28-279">Skype for Business を実行しているクライアントは、DNS にクエリをpool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="edd28-279">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="edd28-280">クエリは 3 つの IP アドレスを返し、次のようにキャッシュします (順序は次のとおりです)。</span><span class="sxs-lookup"><span data-stu-id="edd28-280">The query returns three IP addresses and caches them as follows (in some order):</span></span>
    
   |||
   |:-----|:-----|
   |<span data-ttu-id="edd28-281">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-281">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-282">192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="edd28-282">192.168.10.90</span></span>  <br/> |
   |<span data-ttu-id="edd28-283">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-283">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-284">192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="edd28-284">192.168.10.91</span></span>  <br/> |
   |<span data-ttu-id="edd28-285">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edd28-285">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="edd28-286">192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="edd28-286">192.168.10.92</span></span>  <br/> |
   
- <span data-ttu-id="edd28-287">クライアントは、IP アドレスの 1 つへの TCP 接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="edd28-287">The client tries to establish a TCP connection to one of the IP addresses.</span></span> <span data-ttu-id="edd28-288">失敗した場合は、そのリストからキャッシュされている次の IP アドレスを試します。</span><span class="sxs-lookup"><span data-stu-id="edd28-288">If that fails, it'll try the next IP address it's cached from that list.</span></span>
    
- <span data-ttu-id="edd28-289">TCP 接続が成功した場合、クライアントは TLS をネゴシエートして、サーバー上のプライマリ レジストラー pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="edd28-289">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="edd28-290">クライアントが接続に成功せずにすべてのキャッシュされたエントリを試みる場合、ユーザーは、現時点では Skype for Business Server を実行しているサーバーが利用できないという通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="edd28-290">If the client tries all cached entries without a successful connection, the user receives a notification that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="edd28-291">DNS ベースの負荷分散は、DNS ラウンド ロビン (DNS RR) とは異なります。DNS ラウンド ロビン (DNS RR) とは、通常、DNS に依存してプール内のサーバーに異なる順序の IP アドレスを与える負荷分散を指します。</span><span class="sxs-lookup"><span data-stu-id="edd28-291">DNS-based load balancing is different from DNS round robin (DNS RR), which typically refers to load balancing by relying on DNS to give a different order of IP addresses for the servers in your pool.</span></span> <span data-ttu-id="edd28-292">通常、DNS RR は負荷分散を有効にしますが、フェールオーバーを有効にしません。</span><span class="sxs-lookup"><span data-stu-id="edd28-292">Typically, DNS RR enables load distribution, but it won't allow you to enable failover.</span></span> <span data-ttu-id="edd28-293">たとえば、DNS A (または IPv6 シナリオの AAAA) クエリによって返された 1 つの IP アドレスへの接続が失敗した場合、その接続は失敗します。</span><span class="sxs-lookup"><span data-stu-id="edd28-293">For example, if the connection to the one IP address returned by your DNS A (or AAAA in an IPv6 scenario) query fails, that connection will fail.</span></span> <span data-ttu-id="edd28-294">これにより、DNS RR の信頼性が DNS ベースの負荷分散よりも低くなされます。</span><span class="sxs-lookup"><span data-stu-id="edd28-294">That makes DNS RR less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="edd28-295">必要に応じて、DNS RR を DNS ベースの負荷分散と組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="edd28-295">You can still use DNS RR in conjunction with DNS-based load balancing if you need to do that.</span></span> 
  
<span data-ttu-id="edd28-296">DNS 負荷分散を使用して、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="edd28-296">You use DNS load balancing to:</span></span>
  
- <span data-ttu-id="edd28-297">サーバー間 SIP をエッジ サーバーに負荷分散します。</span><span class="sxs-lookup"><span data-stu-id="edd28-297">Load balance server-to-server SIP to the Edge Servers.</span></span>
    
- <span data-ttu-id="edd28-298">会議サービス、応答グループ、コール パークなど、統合コミュニケーション 自動応答 (UCAS) アプリケーションの負荷分散。</span><span class="sxs-lookup"><span data-stu-id="edd28-298">Load balance Unified Communication Application Services (UCAS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.</span></span>
    
- <span data-ttu-id="edd28-299">UCAS アプリケーションへの新しい接続を防止する (ドレインとも呼ばれる)。</span><span class="sxs-lookup"><span data-stu-id="edd28-299">Prevent new connections to UCAS applications (also known as draining).</span></span>
    
- <span data-ttu-id="edd28-300">クライアントとエッジ サーバー間のすべてのクライアント間トラフィックの負荷分散。</span><span class="sxs-lookup"><span data-stu-id="edd28-300">Load balance all client-to-server traffic between clients and Edge Servers.</span></span>
    
<span data-ttu-id="edd28-301">次の場合に DNS 負荷分散を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="edd28-301">You can't use DNS load balancing for:</span></span>
  
- <span data-ttu-id="edd28-302">フロントエンド サーバーまたはディレクターへのクライアントからサーバーへの Web トラフィック。</span><span class="sxs-lookup"><span data-stu-id="edd28-302">Client-to-server web traffic to your Front End Servers or a Director.</span></span>
    
<span data-ttu-id="edd28-303">クエリによって複数の DNS レコードが返された場合に DNS SRV レコードがどのように選択されるのかについてもう少し詳しい情報を得る場合、アクセス エッジ サービスは常に数値の優先順位が最も低いレコードを選択し、タイ ブレーカーが必要な場合は数値ウェイトが最も高くなります。</span><span class="sxs-lookup"><span data-stu-id="edd28-303">To go a little more in-depth on how a DNS SRV record's selected when mutiple DNS records are returned by a query, the Access Edge service always picks the record with the lowest numeric priority and, if a tie-breaker is needed, the highest numeric weight.</span></span> <span data-ttu-id="edd28-304">これは、インターネットエンジニアリングタスク [フォースのドキュメントと一致しています](https://www.ietf.org/rfc/rfc2782.txt)。</span><span class="sxs-lookup"><span data-stu-id="edd28-304">This is consistent with [Internet Engineering Task Force documentation](https://www.ietf.org/rfc/rfc2782.txt).</span></span>
  
<span data-ttu-id="edd28-305">たとえば、最初の DNS SRV レコードの重み付け値が 20、優先順位が 40 で、2 番目の DNS SRV レコードの重み付けが 10 で優先順位が 50 の場合、優先順位が 40 より低いので、最初のレコードが選択されます。</span><span class="sxs-lookup"><span data-stu-id="edd28-305">So, for example, if your first DNS SRV record has a weight of 20 and a priority of 40, and your second DNS SRV record has a weight of 10 and a priority of 50, the first record's going to be chosen because it has the lower priority of 40.</span></span> <span data-ttu-id="edd28-306">優先度は常に最初に行き、クライアントが最初にターゲットとするホストです。</span><span class="sxs-lookup"><span data-stu-id="edd28-306">Priority always goes first, and that's the host that a client will target first.</span></span> <span data-ttu-id="edd28-307">同じ優先度を持つターゲットが 2 つある場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="edd28-307">What if there are two targets with the same priority?</span></span> 
  
<span data-ttu-id="edd28-308">その場合は、重みを考慮します。</span><span class="sxs-lookup"><span data-stu-id="edd28-308">In that case, weight comes into consideration.</span></span> <span data-ttu-id="edd28-309">この状況では、より大きな重みを選択する可能性が高い必要があります。</span><span class="sxs-lookup"><span data-stu-id="edd28-309">Larger weights should be given a high probability, in this circumstance, of being selected.</span></span> <span data-ttu-id="edd28-310">DNS 管理者は、実行するサーバーが選択されていない場合は、重み 0 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edd28-310">DNS administrators should use weight 0 when there isn't any server selection to do.</span></span> <span data-ttu-id="edd28-311">重み付けが 0 より大きいレコードが存在する場合、重み付け 0 のレコードが選択される可能性は非常に小さいです。</span><span class="sxs-lookup"><span data-stu-id="edd28-311">In the presence of records containing weights greater than 0, records with weight 0 have a very small chance of bring selected.</span></span>
  
<span data-ttu-id="edd28-312">では、同じ優先度と重みを持つ複数の DNS SRV レコードが返された場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="edd28-312">So, then, what happens if multiple DNS SRV records with equal priority and weight as returned?</span></span> <span data-ttu-id="edd28-313">この場合、アクセス エッジ サービスは、最初に DNS サーバーから取得した SRV レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="edd28-313">In this situation the Access Edge service will choose the SRV record that it got from the DNS server first.</span></span>
  

