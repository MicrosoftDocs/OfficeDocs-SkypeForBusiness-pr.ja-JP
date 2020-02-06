---
title: Skype for Business Server 向け Advanced Edge Server DNS の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server 展開オプションのシナリオを確認します。 単一サーバーを使用したいと考えている場合も、DNS または HLB と共にサーバー プールを使用することを優先する場合も、このトピックは役に立ちます。'
ms.openlocfilehash: 098d25a23745c035813cfc5c0ea6d291999c3704
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803387"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a><span data-ttu-id="1ef84-104">Skype for Business Server 向け Advanced Edge Server DNS の計画</span><span class="sxs-lookup"><span data-stu-id="1ef84-104">Advanced Edge Server DNS planning for Skype for Business Server</span></span>
 
<span data-ttu-id="1ef84-105">**概要:** Skype for Business Server 展開オプションのシナリオを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ef84-105">**Summary:** Review scenarios for Skype for Business Server deployment options.</span></span> <span data-ttu-id="1ef84-106">単一サーバーを使用したいと考えている場合も、DNS または HLB と共にサーバー プールを使用することを優先する場合も、このトピックは役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="1ef84-106">Whether you want a single server or prefer a server pool with DNS or HLB, this topic should help.</span></span>
  
<span data-ttu-id="1ef84-107">Skype for Business Server のドメインネームシステム (DNS) の計画については、多くの要因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="1ef84-107">When it comes to Domain Name System (DNS) planning for Skype for Business Server, there are a lot of factors that may play into your decision.</span></span> <span data-ttu-id="1ef84-108">組織のドメイン構造が既に確立されている場合は、どのように作業を進めるか確認するための考慮事項になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-108">If your organization's domain structure's already in place, this may be a matter of reviewing how you're going to proceed.</span></span> <span data-ttu-id="1ef84-109">最初に、以下に示すトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1ef84-109">We'll begin with the topics found below:</span></span>
  
- [<span data-ttu-id="1ef84-110">Walkthrough of Skype for Business clients locating services</span><span class="sxs-lookup"><span data-stu-id="1ef84-110">Walkthrough of Skype for Business clients locating services</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [<span data-ttu-id="1ef84-111">Split-brain DNS</span><span class="sxs-lookup"><span data-stu-id="1ef84-111">Split-brain DNS</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [<span data-ttu-id="1ef84-112">Automatic configuration without split-brain DNS</span><span class="sxs-lookup"><span data-stu-id="1ef84-112">Automatic configuration without split-brain DNS</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [<span data-ttu-id="1ef84-113">DNS disaster recovery</span><span class="sxs-lookup"><span data-stu-id="1ef84-113">DNS disaster recovery</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [<span data-ttu-id="1ef84-114">DNS load balancing</span><span class="sxs-lookup"><span data-stu-id="1ef84-114">DNS load balancing</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a><span data-ttu-id="1ef84-115">Walkthrough of Skype for Business clients locating services</span><span class="sxs-lookup"><span data-stu-id="1ef84-115">Walkthrough of Skype for Business clients locating services</span></span>
<span data-ttu-id="1ef84-116"><a name="WalkthroughOfSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef84-116"><a name="WalkthroughOfSkype"> </a></span></span>

<span data-ttu-id="1ef84-117">Skype for Business クライアントは、以前のバージョンの Lync クライアントと似ていますが、Skype for Business Server でのサービスの検索とアクセス方法が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ef84-117">Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server.</span></span> <span data-ttu-id="1ef84-118">ここではサーバー検索の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ef84-118">This section details the server location process.</span></span>
  
1. <span data-ttu-id="1ef84-119">lyncdiscoverinternal.\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="1ef84-119">lyncdiscoverinternal.\<domain\></span></span>
    
     <span data-ttu-id="1ef84-120">*これは、内部 Web サービスを対象とした自動検出サービスの A ホスト レコードです。*</span><span class="sxs-lookup"><span data-stu-id="1ef84-120">*This is an A host record for the Autodiscover service on the internal web services.*</span></span> 
    
2. <span data-ttu-id="1ef84-121">lyncdiscover.\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="1ef84-121">lyncdiscover.\<domain\></span></span>
    
     <span data-ttu-id="1ef84-122">*これは、外部 Web サービスを対象とした自動検出サービスのホスト レコードです。*</span><span class="sxs-lookup"><span data-stu-id="1ef84-122">*This is an A host record for the Autodiscover service on the external web services.*</span></span> 
    
3. <span data-ttu-id="1ef84-123">_sipinternaltls _tcp。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="1ef84-123">_sipinternaltls._tcp.\<domain\></span></span>
    
     <span data-ttu-id="1ef84-124">*これは、内部 TLS 接続用の SRV レコードです。*</span><span class="sxs-lookup"><span data-stu-id="1ef84-124">*This is a SRV record for internal TLS connections.*</span></span> 
    
4. <span data-ttu-id="1ef84-125">_sip _tls。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="1ef84-125">_sip._tls.\<domain\></span></span>
    
     <span data-ttu-id="1ef84-126">*これは、外部 TLS 接続用の SRV レコードです。*</span><span class="sxs-lookup"><span data-stu-id="1ef84-126">*This is a SRV record for external TLS connections.*</span></span> 
    
5. <span data-ttu-id="1ef84-127">sipinternal.\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="1ef84-127">sipinternal.\<domain\></span></span>
    
     <span data-ttu-id="1ef84-128">*これは、内部ネットワーク上でのみ解決可能なフロントエンドプールまたはディレクターのホストレコードです。*</span><span class="sxs-lookup"><span data-stu-id="1ef84-128">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
6. <span data-ttu-id="1ef84-129">フェデレーション.\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="1ef84-129">sip.\<domain\></span></span>
    
     <span data-ttu-id="1ef84-130">*これは、内部ネットワーク上でのみ解決可能なフロントエンドプールまたはディレクターのホストレコードです。*</span><span class="sxs-lookup"><span data-stu-id="1ef84-130">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
7. <span data-ttu-id="1ef84-131">sipexternal.\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="1ef84-131">sipexternal.\<domain\></span></span>
    
     <span data-ttu-id="1ef84-132">*これは、クライアントが外部の場合に、アクセスエッジサービスのホストレコードです。*</span><span class="sxs-lookup"><span data-stu-id="1ef84-132">*This is an A host record for the Access Edge service, when the client is external.*</span></span> 
    
<span data-ttu-id="1ef84-133">常に自動検出サービスを使用することが望まれます。これはサービス検出に関して優先される方法であり、他の方法はフォールバックの方法です。</span><span class="sxs-lookup"><span data-stu-id="1ef84-133">The Autodiscover service is always favored as that's the preferred method for service location, and the others are fallback methods.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ef84-p105">SRV レコードを作成する場合は、DNS SRV レコードを作成するのと同じドメインにある DNS の A レコード (および、IPv6 アドレスを使用している場合は AAAA レコード) を指す必要があります。たとえば、SRV レコードが contoso.com にある場合、A (および AAAA) レコードが fabrikam.com を指すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p105">When you're creating SRV records, it's important to remember that they need to point to a DNS A (and AAAA if you're using IPv6 addressing) in the same domain in which the DNS SRV record's being created. For example, if they SRV record's in contoso.com, the A (and AAAA) record it points to can't be in fabrikam.com.</span></span> 
  
<span data-ttu-id="1ef84-p106">希望する場合は、サービスの手動検出に依存するようにモバイル デバイスを設定することもできます。この方法を採用しようとする場合は、各ユーザーが自らのモバイル デバイスで、次のようにプロトコルとパスを含め、内部と外部の完全な自動検出サービス URL を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p106">If you're inclined to do it, you can set your mobile device up for manual discovery of services. If that's what you're looking to do, each user needs to configure their mobile device settings with the full internal and external Autodiscover service URIs, including the protocol and path, as follows:</span></span>
  
- <span data-ttu-id="1ef84-138">外部アクセスの場合:\<Https://extpoolfqdn\>/Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="1ef84-138">For external access: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span></span>
    
- <span data-ttu-id="1ef84-139">内部アクセスの場合:\<Https://intpoolfqdn\>/AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="1ef84-139">For internal access: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span></span>
    
<span data-ttu-id="1ef84-p107">手動検出ではなく、自動検出を使用することを強くお勧めします。ただし、トラブルシューティングやテストを実行する場合は、手動設定が非常に役に立つこともあります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p107">We do recommend you use automatic discovery as opposed to manual discovery. But if you're doing some troubleshooting or testing, manual settings can be very helpful.</span></span>
  
## <a name="split-brain-dns"></a><span data-ttu-id="1ef84-142">スプリットブレイン DNS</span><span class="sxs-lookup"><span data-stu-id="1ef84-142">Split-brain DNS</span></span>
<span data-ttu-id="1ef84-143"><a name="SplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef84-143"><a name="SplitBrainDNS"> </a></span></span>

<span data-ttu-id="1ef84-p108">これは、2 つの DNS ゾーンが同じ名前空間に存在する DNS 構成です。一方の DNS ゾーンは内部要求のみ、他方の DNS ゾーンは外部要求のみを処理します。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p108">This is a DNS configuration where you have two DNS zones with the same namespace. The first DNS zone handles internal requests, while the second DNS zone handles external requests.</span></span>
  
<span data-ttu-id="1ef84-p109">企業がこの構成を採用するのはなぜでしょうか。これは、内部と外部で同じ名前空間を使用する場合の要件になることがあります。もちろん、この構成を採用すると、DNS の多数の SRV レコードと A レコードが一方のゾーン内または他方のゾーン内で一意になることが求められる結果につながります。重複が存在する場合は、これらのレコードに関連付けられる IP アドレスは一意になります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p109">Why would a company do this? They may have a requirement to use the same namespace internally and externally, but of course this will lead to many DNS SRV and A records being unique to one zone or another, and where there is duplication, the IP addresses associated with these records would be unique.</span></span>
  
<span data-ttu-id="1ef84-148">この構成を採用すると、いくつかの課題が発生します。</span><span class="sxs-lookup"><span data-stu-id="1ef84-148">This presents some challenges.</span></span> <span data-ttu-id="1ef84-149">最も重要なことは、スプリットブレイン DNS はモビリティでサポートされて**いない**ことです。</span><span class="sxs-lookup"><span data-stu-id="1ef84-149">The most important is that split-brain DNS is **not supported** for Mobility.</span></span> <span data-ttu-id="1ef84-150">これは、LyncDiscover と LyncDiscoverInternal の各 DNS レコードが原因です (LyncDiscover は外部 DNS サーバー上で、また LyncDiscoverInternal は内部 DNS サーバー上で定義する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="1ef84-150">This is because of the LyncDiscover and LyncDiscoverInternal DNS records (LyncDiscover has to be defined on you external DNS server, while LyncDiscoverInternal has to be defined on your internal DNS server).</span></span>
  
<span data-ttu-id="1ef84-151">ここでは、内部と外部のゾーンの DNS レコードについて説明しますが、「microsoft Edge Server の環境要件」セクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="1ef84-151">We'll list the DNS records for the internal and external zones here, but you can find detailed examples on the Edge Server environmental requirements section.</span></span>
  
### <a name="internal-dns"></a><span data-ttu-id="1ef84-152">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="1ef84-152">Internal DNS</span></span>

- <span data-ttu-id="1ef84-153">(たとえば) contoso.com という信頼できる DNS ゾーンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ef84-153">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="1ef84-154">以下は、内部 contoso.com の内容です。</span><span class="sxs-lookup"><span data-stu-id="1ef84-154">This internal contoso.com contains:</span></span>
    
  - <span data-ttu-id="1ef84-155">フロントエンドプール、ディレクタープールまたはディレクタープールの名前、および組織のネットワーク内で Skype for Business Server を実行しているすべての内部サーバーに対して、DNS A と AAAA (IPv6 アドレス指定を使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="1ef84-155">DNS A and AAAA (if you're using IPv6 addressing) records for your Front End pool, Director pool or Director pool name, and all internal servers running Skype for Business Server in your organization's network.</span></span>
    
  - <span data-ttu-id="1ef84-156">境界ネットワーク内の各 Skype for Business Server Edge サーバーの Edge 内部インターフェイスの (IPv6 アドレス指定を使用している場合は) DNS A と AAAA。</span><span class="sxs-lookup"><span data-stu-id="1ef84-156">DNS A and AAAA (if you're using IPv6 addressing) records for your Edge internal interface for each Skype for Business Server Edge Server in your perimeter network.</span></span>
    
  - <span data-ttu-id="1ef84-157">DNS A と AAAA (IPv6 アドレス指定を使用している場合) 境界ネットワーク内の各リバースプロキシサーバーの内部インターフェイスのレコード (リバースプロキシを管理するための**オプション**)。</span><span class="sxs-lookup"><span data-stu-id="1ef84-157">DNS A and AAAA (if you're using IPv6 addressing) records for the internal interface of each reverse proxy server in your perimeter network (which is **optional** for management of a reverse proxy).</span></span>
    
  - <span data-ttu-id="1ef84-158">DNS A と AAAA (IPv6 アドレス指定を使用している場合)、および内部の Skype for Business Server クライアントの自動構成の SRV レコード (**オプション**)。</span><span class="sxs-lookup"><span data-stu-id="1ef84-158">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server client autoconfiguration (which is **optional** ).</span></span>
    
  - <span data-ttu-id="1ef84-159">Skype for Business Server Web サービスを自動的に検出するための DNS A と AAAA (IPv6 アドレスを使用している場合) または CNAME レコード (**オプション**)。</span><span class="sxs-lookup"><span data-stu-id="1ef84-159">DNS A and AAAA (if you're using IPv6 addressing) or CNAME records for automatic discovery of Skype for Business Server Web Services (which is **optional** ).</span></span>
    
- <span data-ttu-id="1ef84-160">境界ネットワーク内のすべての Skype for Business Server 内部エッジインターフェイスは、この内部 DNS ゾーンを使って、contoso.com へのクエリを解決します。</span><span class="sxs-lookup"><span data-stu-id="1ef84-160">All your Skype for Business Server internal Edge interfaces in your perimeter network use this internal DNS zone for resolving queries to contoso.com.</span></span>
    
- <span data-ttu-id="1ef84-161">Skype for Business Server を実行しているすべてのサーバー、および企業ネットワーク内の Skype for Business Server を実行しているクライアント、contoso.com へのクエリを解決するための内部 DNS サーバー、または各エッジサーバー上のホストファイルを使用している場合は、(使用している場合)IPv6 アドレス) 次ホップサーバーのレコード (特にディレクターまたはディレクタープール VIP、フロントエンドプール VIP、または Standard Edition server)。</span><span class="sxs-lookup"><span data-stu-id="1ef84-161">All servers running Skype for Business Server, and clients running Skype for Business Server in the corporate network, point to internal DNS servers for resolving queries to contoso.com, or they use the Host file on each Edge Server and list A and AAAA (if you're using IPv6 addressing) records for the next hop server (specifically for the Director or Director pool VIP, Front End pool VIP, or Standard Edition server).</span></span>
    
### <a name="external-dns"></a><span data-ttu-id="1ef84-162">外部 DNS</span><span class="sxs-lookup"><span data-stu-id="1ef84-162">External DNS</span></span>

- <span data-ttu-id="1ef84-163">(たとえば) contoso.com という信頼できる DNS ゾーンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ef84-163">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="1ef84-164">以下は、外部 contoso.com の内容です。</span><span class="sxs-lookup"><span data-stu-id="1ef84-164">This external contoso.com contains:</span></span>
    
  - <span data-ttu-id="1ef84-165">Skype for Business Server web サービスを自動的に検出するために、DNS A と AAAA (IPv6 アドレス指定を使用している場合)、または CNAME レコード。</span><span class="sxs-lookup"><span data-stu-id="1ef84-165">DNS A and AAAA (if you're using IPv6 addressing), or CNAME records, for automatic discovery of Skype for Business Server web services.</span></span> <span data-ttu-id="1ef84-166">これは、モビリティでの使用に適しています。</span><span class="sxs-lookup"><span data-stu-id="1ef84-166">This is for use with mobility.</span></span>
    
  - <span data-ttu-id="1ef84-167">DNS A と AAAA (IPv6 アドレスを使用している場合)、および境界ネットワークでの各 Skype for Business Server Edge サーバーまたはハードウェア負荷分散 (HLB) VIP のエッジ外部インターフェイスの SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="1ef84-167">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server Edge Server or hardware load balanced (HLB) VIP in the perimeter network.</span></span>
    
  - <span data-ttu-id="1ef84-168">境界ネットワークの DNS A および AAAA (IPv6 アドレス指定を使用している場合) および SRV レコード (リバースプロキシサーバーの外部インターフェイスまたはリバースプロキシサーバーのプール用 VIP)。</span><span class="sxs-lookup"><span data-stu-id="1ef84-168">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.</span></span>
    
  - <span data-ttu-id="1ef84-169">DNS A と AAAA (IPv6 アドレス指定を使用している場合)、および Skype for Business Server クライアント自動構成の SRV レコード (**オプション**)。</span><span class="sxs-lookup"><span data-stu-id="1ef84-169">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server client autoconfiguration ( **optional** ).</span></span>
    
## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="1ef84-170">スプリットブレイン DNS なしの自動構成</span><span class="sxs-lookup"><span data-stu-id="1ef84-170">Automatic configuration without split-brain DNS</span></span>
<span data-ttu-id="1ef84-171"><a name="NoSplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef84-171"><a name="NoSplitBrainDNS"> </a></span></span>

<span data-ttu-id="1ef84-172">スプリットブレイン DNS を使用していない場合は、次の回避策のいずれかを使用しない限り、Skype for Business を実行しているクライアントの内部自動構成は機能しません。</span><span class="sxs-lookup"><span data-stu-id="1ef84-172">If you don't use split-brain DNS, internal automatic configuration of clients running Skype for Business won't work unless you're using one of the workarounds we have here.</span></span> <span data-ttu-id="1ef84-173">なぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1ef84-173">Why not?</span></span> <span data-ttu-id="1ef84-174">Skype for Business Server は、自動構成用に指定されたフロントエンドプールのドメインと一致するようにユーザーの SIP URI を要求するためです。</span><span class="sxs-lookup"><span data-stu-id="1ef84-174">Because Skype for Business Server requires the user's SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="1ef84-175">これは、以前のバージョンの Lync Server から変更されていません。</span><span class="sxs-lookup"><span data-stu-id="1ef84-175">This hasn't changed from earlier versions of Lync Server.</span></span>
  
<span data-ttu-id="1ef84-176">たとえば、使用されている SIP ドメインが 2 つある場合、次の DNS SRV レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="1ef84-176">So, if you have two SIP domains in use, you'd need these DNS SRV records:</span></span>
  
- <span data-ttu-id="1ef84-p113">_sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-p113">_sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>
    
     <span data-ttu-id="1ef84-179">*ユーザーが bob@contoso.com としてサインインした場合、ユーザーの SIP ドメインはフロントエンドプールのドメイン (contoso.com) と一致するため、このレコードは自動構成で動作します。*</span><span class="sxs-lookup"><span data-stu-id="1ef84-179">*If a user signs in as bob@contoso.com, this record would work for automatic configuration, as the user's SIP domain matches the domain of the Front End pool (contoso.com).*</span></span> 
    
- <span data-ttu-id="1ef84-180">_sipinternaltls._tcp.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="1ef84-180">_sipinternaltls._tcp.fabrikam.com.</span></span> <span data-ttu-id="1ef84-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="1ef84-182">*ユーザーが alice@fabrikam.com としてサインインした場合、SIP ドメインがそのドメインのフロントエンドプールと一致するため、このレコードは2番目のドメインの自動構成に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="1ef84-182">*If a user signs in as alice@fabrikam.com, this record would work for automatic configuration of the second domain, again because the SIP domain matches the Front End pool for that domain.*</span></span> 
    
<span data-ttu-id="1ef84-183">ここまでの例を使用すると、次のレコードは機能しません。</span><span class="sxs-lookup"><span data-stu-id="1ef84-183">To take the example further, this would not work:</span></span>
  
- <span data-ttu-id="1ef84-p115">_sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-p115">_sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="1ef84-186">*tim@litwareinc.com としてサインインしたユーザーの場合は、自動構成は機能しません。このユーザーの SIP ドメイン (litwareinc.com) は、プール内のドメイン (fabrikam.com) と一致しないためです。*</span><span class="sxs-lookup"><span data-stu-id="1ef84-186">*A user signing in as tim@litwareinc.com won't work for automatic configuration, because his SIP domain (litwareinc.com) doesn't match the domain in the pool (fabrikam.com).*</span></span> 
    
<span data-ttu-id="1ef84-187">これで、スプリットブレイン DNS を使わずに Skype for Business クライアントの自動要件が必要な場合は、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-187">So now that we know all that, if you need automatic requirement for your Skype for Business clients without split-brain DNS, you have these options:</span></span>
  
- <span data-ttu-id="1ef84-188">**グループ ポリシー オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="1ef84-188">**Group Policy Objects**</span></span>
    
    <span data-ttu-id="1ef84-189">グループ ポリシー オブジェクト (GPO) を使用して、適切なサーバーの値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1ef84-189">You can use Group Policy Objects (GPOs) to populate the correct server values.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1ef84-p116">このオプションを使用しても自動構成は有効になりませんが、手動構成が自動化されます。この方法を使用した場合、自動構成に関連付ける SRV レコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p116">This option doesn't enable automatic configuration, but it does automate manual configuration. If this approach is used, the SRV records associated with automatic configuration aren't required.</span></span> 
  
- <span data-ttu-id="1ef84-192">**内部ゾーンの一致**</span><span class="sxs-lookup"><span data-stu-id="1ef84-192">**Matching internal zone**</span></span>
    
    <span data-ttu-id="1ef84-193">外部 DNS ゾーン (contoso.com など) に一致する内部 DNS のゾーンを作成して、自動で使用される Skype for Business Server プールに対応するレコードを作成する必要があります (IPv6 アドレスを使っている場合は、AAAA の場合)。構成.</span><span class="sxs-lookup"><span data-stu-id="1ef84-193">You'll need to create a zone in your internal DNS that matches your external DNS zone (for example, contoso.com), and then create DNS A (and AAAA if you're using IPv6 addressing) records that correspond to the Skype for Business Server pool used for automatic configuration.</span></span>
    
    <span data-ttu-id="1ef84-194">たとえば、ユーザーが pool01.contoso.net をホームにしていて、bob@contoso.com として Skype for Business にサインインしている場合、contoso.com という名前の内部 DNS ゾーンを作成し、その内部に pool01.contoso.com の DNS A (IPv6 アドレスを使用する場合は AAAA) レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-194">For example, if you have a user homed on pool01.contoso.net, but signs into Skype for Business as bob@contoso.com, create an internal DNS zone called contoso.com, and inside it you need to create a DNS A (and AAAA if IPv6 addressing's being used) record for pool01.contoso.com.</span></span>
    
- <span data-ttu-id="1ef84-195">**ピンポイントの内部ゾーン**</span><span class="sxs-lookup"><span data-stu-id="1ef84-195">**Pin-point internal zone**</span></span>
    
    <span data-ttu-id="1ef84-p117">内部 DNS 内にゾーン全体を作成することが適切なオプションではない場合は、自動構成で必要とされる複数の SRV レコードに対応するピンポイント (専用) ゾーンを作成し、dnscmd.exe を使用してそれらのゾーンを設定することができます。DNS ユーザー インターフェイスはピンポイント ゾーンの作成をサポートしていないため、Dnscmd.exe が必須です。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p117">If creating an entire zone in your internal DNS isn't an option for you, you can create pin-point (dedicated) zones that correspond to the SRV records required for automatic configuration, and populate those zones using dnscmd.exe. Dnscmd.exe is required because the DNS user interface won't support the creation of pin-point zones.</span></span>
    
    <span data-ttu-id="1ef84-198">たとえば、SIP ドメインが contoso.com で、2つのフロントエンドサーバーを含む pool01 というフロントエンドプールがある場合、次のピンポイントゾーンと内部 DNS 内のレコードが必要になります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-198">For example, if your SIP domain is contoso.com, and you have a Front End pool called pool01 that contains two Front End Servers, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    <span data-ttu-id="1ef84-p118">環境内で 2 番目の SIP ドメインを用意することもできます。この場合は、内部 DNS 内で以下のピンポイント ゾーンと A レコードが必要になります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p118">You may have a second SIP domain in your environment. In that case, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> <span data-ttu-id="1ef84-201">フロントエンドプールの FQDN が2回表示されますが、2つの異なる IP アドレスがあります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-201">You'll see the Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="1ef84-202">DNS 負荷分散を使用しているためです。</span><span class="sxs-lookup"><span data-stu-id="1ef84-202">That's because DNS load balancing is used.</span></span> <span data-ttu-id="1ef84-203">HLB を使っている場合は、1つのフロントエンドプールエントリしかありません。</span><span class="sxs-lookup"><span data-stu-id="1ef84-203">If HLB is used, there'd only be a single Front End pool entry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1ef84-204">また、contoso.com と fabrikam.com の例では、フロントエンドプールの FQDN 値が変更されますが、IP アドレスは変わりません。</span><span class="sxs-lookup"><span data-stu-id="1ef84-204">Also, the Front End pool FQDN values change between the contoso.com and fabrikam.com examples, but the IP addresses remain the same.</span></span> <span data-ttu-id="1ef84-205">その理由は、いずれかの SIP ドメインからサインインしているユーザーが、自動構成で同じフロントエンドプールを使用しているためです。</span><span class="sxs-lookup"><span data-stu-id="1ef84-205">That's because users who're signing in from either SIP domain will be using the same Front End pool for automatic configuration.</span></span> 
  
## <a name="dns-disaster-recovery"></a><span data-ttu-id="1ef84-206">DNS 障害復旧</span><span class="sxs-lookup"><span data-stu-id="1ef84-206">DNS disaster recovery</span></span>
<span data-ttu-id="1ef84-207"><a name="DNSDR"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef84-207"><a name="DNSDR"> </a></span></span>

<span data-ttu-id="1ef84-208">Skype for Business Server の web トラフィックを disaster recover (DR) とフェールオーバーサイトにリダイレクトするように DNS を構成するには、GeoDNS をサポートする DNS プロバイダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-208">To configure DNS to redirect Skype for Business Server web traffic to your disaster recover (DR) and failover sites, you need to use a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="1ef84-209">障害回復をサポートするように DNS レコードを設定することができます。これにより、フロントエンドプール全体が停止した場合でも、web サービスを使う機能が続行されます。</span><span class="sxs-lookup"><span data-stu-id="1ef84-209">You can set up your DNS records to support disaster recover, so that features that use web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="1ef84-210">この障害復旧機能では、自動検出、会議、およびダイヤルインの簡易 URL をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1ef84-210">This DR feature supports the Autodiscover, Meet and Dial-in simple URLs.</span></span>
  
<span data-ttu-id="1ef84-p122">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider. The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span><span class="sxs-lookup"><span data-stu-id="1ef84-p122">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider. The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span></span>
  
<span data-ttu-id="1ef84-213">この表の DNS レコードは、いずれも例です。</span><span class="sxs-lookup"><span data-stu-id="1ef84-213">All the DNS records in this table are examples.</span></span>
  
|<span data-ttu-id="1ef84-214">**GeoDNS レコード**</span><span class="sxs-lookup"><span data-stu-id="1ef84-214">**GeoDNS record**</span></span>|<span data-ttu-id="1ef84-215">**プール レコード**</span><span class="sxs-lookup"><span data-stu-id="1ef84-215">**Pool records**</span></span>|<span data-ttu-id="1ef84-216">**CNAME レコード**</span><span class="sxs-lookup"><span data-stu-id="1ef84-216">**CNAME records**</span></span>|<span data-ttu-id="1ef84-217">**DNS 設定 (オプションを 1 つ選択する)**</span><span class="sxs-lookup"><span data-stu-id="1ef84-217">**DNS settings (select one option)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ef84-218">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-218">Meet-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-219">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-219">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1ef84-220">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-220">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-221">Meet.contoso.com Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-221">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>  <br/>   <br/> |<span data-ttu-id="1ef84-222">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ef84-222">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1ef84-223">**または**</span><span class="sxs-lookup"><span data-stu-id="1ef84-223">**OR**</span></span> <br/> <span data-ttu-id="1ef84-224">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="1ef84-224">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1ef84-225">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-225">Meet-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-226">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-226">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1ef84-227">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-227">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-228">Meet.contoso.com Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-228">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>   <br/> |<span data-ttu-id="1ef84-229">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ef84-229">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1ef84-230">**または**</span><span class="sxs-lookup"><span data-stu-id="1ef84-230">**OR**</span></span> <br/> <span data-ttu-id="1ef84-231">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="1ef84-231">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1ef84-232">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-232">Dialin-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-233">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-233">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1ef84-234">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-234">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-235">Meet.contoso.com Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-235">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="1ef84-236">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ef84-236">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1ef84-237">**または**</span><span class="sxs-lookup"><span data-stu-id="1ef84-237">**OR**</span></span> <br/> <span data-ttu-id="1ef84-238">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="1ef84-238">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1ef84-239">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-239">Dialin-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-240">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-240">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1ef84-241">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-241">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-242">Meet.contoso.com Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-242">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>  <br/> |<span data-ttu-id="1ef84-243">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ef84-243">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1ef84-244">**または**</span><span class="sxs-lookup"><span data-stu-id="1ef84-244">**OR**</span></span> <br/> <span data-ttu-id="1ef84-245">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="1ef84-245">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1ef84-246">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-246">Lyncdiscoverint-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-247">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-247">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1ef84-248">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-248">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-249">Meet.contoso.com Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-249">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>   <br/> |<span data-ttu-id="1ef84-250">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ef84-250">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1ef84-251">**または**</span><span class="sxs-lookup"><span data-stu-id="1ef84-251">**OR**</span></span> <br/> <span data-ttu-id="1ef84-252">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="1ef84-252">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1ef84-253">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-253">Lyncdiscover-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-254">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-254">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1ef84-255">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-255">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-256">Meet.contoso.com Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-256">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>  <br/> |<span data-ttu-id="1ef84-257">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ef84-257">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1ef84-258">**または**</span><span class="sxs-lookup"><span data-stu-id="1ef84-258">**OR**</span></span> <br/> <span data-ttu-id="1ef84-259">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="1ef84-259">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1ef84-260">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-260">Scheduler-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-261">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-261">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1ef84-262">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-262">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-263">Meet.contoso.com Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-263">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="1ef84-264">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ef84-264">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1ef84-265">**または**</span><span class="sxs-lookup"><span data-stu-id="1ef84-265">**OR**</span></span> <br/> <span data-ttu-id="1ef84-266">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="1ef84-266">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1ef84-267">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-267">Scheduler-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-268">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-268">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1ef84-269">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-269">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-270">Meet.contoso.com Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-270">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="1ef84-271">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="1ef84-271">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1ef84-272">**または**</span><span class="sxs-lookup"><span data-stu-id="1ef84-272">**OR**</span></span> <br/> <span data-ttu-id="1ef84-273">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="1ef84-273">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="1ef84-274">DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="1ef84-274">DNS load balancing</span></span>
<span data-ttu-id="1ef84-275"><a name="DNSLB"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef84-275"><a name="DNSLB"> </a></span></span>

<span data-ttu-id="1ef84-276">DNS 負荷分散は一般的に、アプリケーション レベルで実装されます。</span><span class="sxs-lookup"><span data-stu-id="1ef84-276">DNS load balancing is usually implemented at the application level.</span></span> <span data-ttu-id="1ef84-277">このアプリケーション (たとえば、Skype for Business を実行しているクライアント) は、DNS A と AAAA から返された IP アドレスの1つ (IPv6 アドレスが使用されている場合) に接続して、プールの FQDN のレコードクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="1ef84-277">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool FQDN.</span></span>
  
<span data-ttu-id="1ef84-278">たとえば、pool01.contoso.com という名前のプールに3台のフロントエンドサーバーがある場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-278">For example, if there are three Front End Servers in a pool named pool01.contoso.com, the following would happen:</span></span>
  
- <span data-ttu-id="1ef84-279">Skype for Business の DNS クエリを実行しているクライアント pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1ef84-279">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="1ef84-280">このクエリは 3 つの IP アドレスを返し、それらを次のようにキャッシュに格納します (順序は任意)。</span><span class="sxs-lookup"><span data-stu-id="1ef84-280">The query returns three IP addresses and caches them as follows (in some order):</span></span>
    
   |||
   |:-----|:-----|
   |<span data-ttu-id="1ef84-281">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-281">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-282">192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="1ef84-282">192.168.10.90</span></span>  <br/> |
   |<span data-ttu-id="1ef84-283">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-283">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-284">192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="1ef84-284">192.168.10.91</span></span>  <br/> |
   |<span data-ttu-id="1ef84-285">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ef84-285">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="1ef84-286">192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="1ef84-286">192.168.10.92</span></span>  <br/> |
   
- <span data-ttu-id="1ef84-p125">次に、クライアントは IP アドレスの 1 つに対して TCP 接続を確立しようとします。それが失敗した場合は、一覧の中にキャッシュされている次の IP アドレスを試します。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p125">The client tries to establish a TCP connection to one of the IP addresses. If that fails, it'll try the next IP address it's cached from that list.</span></span>
    
- <span data-ttu-id="1ef84-289">TCP 接続が成功した場合、クライアントは TLS のネゴシエーションを行い、pool01.contoso.com のプライマリ レジストラーに接続します。</span><span class="sxs-lookup"><span data-stu-id="1ef84-289">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="1ef84-290">クライアントがすべてのキャッシュエントリを正常に接続していない場合は、Skype for Business Server が実行されているサーバーが現在利用できないという通知がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ef84-290">If the client tries all cached entries without a successful connection, the user receives a notification that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1ef84-p126">DNS ベースの負荷分散は、一般的に、DNS を利用してプール内のサーバーの IP アドレスを別の順序で提供して負荷分散を行うことを指す DNS ラウンド ロビン (DNS RR) と異なります。一般的に、DNS RR は負荷分散が可能で、フェールオーバー機能を実現しません。たとえば、DNS A (または IPv6 のシナリオを使用している場合は AAAA) クエリで返された 1 つの IP アドレスに対する接続が失敗した場合、その接続は失敗します。したがって、DNS RR は DNS ベースの負荷分散より信頼性が劣りますが、上記の目的で、DNS 負荷分散と共に DNS RR を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p126">DNS-based load balancing is different from DNS round robin (DNS RR), which typically refers to load balancing by relying on DNS to give a different order of IP addresses for the servers in your pool. Typically, DNS RR enables load distribution, but it won't allow you to enable failover. For example, if the connection to the one IP address returned by your DNS A (or AAAA in an IPv6 scenario) query fails, that connection will fail. That makes DNS RR less reliable than DNS-based load balancing. You can still use DNS RR in conjunction with DNS-based load balancing if you need to do that.</span></span> 
  
<span data-ttu-id="1ef84-296">DNS 負荷分散の用途:</span><span class="sxs-lookup"><span data-stu-id="1ef84-296">You use DNS load balancing to:</span></span>
  
- <span data-ttu-id="1ef84-297">サーバー間 SIP の負荷分散をエッジサーバーに対して行います。</span><span class="sxs-lookup"><span data-stu-id="1ef84-297">Load balance server-to-server SIP to the Edge Servers.</span></span>
    
- <span data-ttu-id="1ef84-298">会議自動アテンダント、応答グループ、コール パークなどの統合コミュニケーション アプリケーション サービス (UCAS) アプリケーションの負荷分散</span><span class="sxs-lookup"><span data-stu-id="1ef84-298">Load balance Unified Communication Application Services (UCAS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.</span></span>
    
- <span data-ttu-id="1ef84-299">UCAS アプリケーションへの新規接続の禁止(ドレインとも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="1ef84-299">Prevent new connections to UCAS applications (also known as draining).</span></span>
    
- <span data-ttu-id="1ef84-300">クライアントとエッジサーバー間のクライアント間トラフィックはすべて負荷分散されます。</span><span class="sxs-lookup"><span data-stu-id="1ef84-300">Load balance all client-to-server traffic between clients and Edge Servers.</span></span>
    
<span data-ttu-id="1ef84-301">DNS 負荷分散を使用できない用途:</span><span class="sxs-lookup"><span data-stu-id="1ef84-301">You can't use DNS load balancing for:</span></span>
  
- <span data-ttu-id="1ef84-302">フロントエンドサーバーまたはディレクターへのクライアント対サーバー web トラフィック。</span><span class="sxs-lookup"><span data-stu-id="1ef84-302">Client-to-server web traffic to your Front End Servers or a Director.</span></span>
    
<span data-ttu-id="1ef84-303">Mutiple DNS レコードがクエリによって返されたときの DNS SRV レコードの選択方法についてさらに詳しく理解するために、アクセスエッジサービスは常に最も低い数値の優先度を持つレコードを選びます。また、タイのブレーカーが必要な場合は、最も高い数値の重みにします。</span><span class="sxs-lookup"><span data-stu-id="1ef84-303">To go a little more in-depth on how a DNS SRV record's selected when mutiple DNS records are returned by a query, the Access Edge service always picks the record with the lowest numeric priority and, if a tie-breaker is needed, the highest numeric weight.</span></span> <span data-ttu-id="1ef84-304">これは、[インターネットエンジニアリングタスクのフォースに関するドキュメント](https://www.ietf.org/rfc/rfc2782.txt)と一貫性があります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-304">This is consistent with [Internet Engineering Task Force documentation](https://www.ietf.org/rfc/rfc2782.txt).</span></span>
  
<span data-ttu-id="1ef84-p128">そのため、たとえば最初の DNS SRV レコードの重み付けが 20 で、優先順位が 40、また 2 番目の DNS SRV レコードの重み付けが 10 で、優先順位が 50 の場合は、優先順位が 40 である最初のレコードが選択されます。常に優先順位が最初に考慮され、クライアントが最初にターゲットにするホストになります。同じ優先順位を持つターゲットが 2 つ存在する場合はどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p128">So, for example, if your first DNS SRV record has a weight of 20 and a priority of 40, and your second DNS SRV record has a weight of 10 and a priority of 50, the first record's going to be chosen because it has the lower priority of 40. Priority always goes first, and that's the host that a client will target first. What if there are two targets with the same priority?</span></span> 
  
<span data-ttu-id="1ef84-p129">この場合は、重み付けが考慮されます。この状況では、重み付けが大きいほど、選択される確率が高くなります。サーバー選択を行わない場合は、DNS 管理者は重み付け 0 を使用する必要があります。0 より大きい重み付けを持つレコードが存在するとき、重み付け 0 のレコードが選択される可能性は非常に小さくなります。</span><span class="sxs-lookup"><span data-stu-id="1ef84-p129">In that case, weight comes into consideration. Larger weights should be given a high probability, in this circumstance, of being selected. DNS administrators should use weight 0 when there isn't any server selection to do. In the presence of records containing weights greater than 0, records with weight 0 have a very small chance of bring selected.</span></span>
  
<span data-ttu-id="1ef84-312">同じ優先度と重み付けを持つ複数の DNS SRV レコードが返された場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1ef84-312">So, then, what happens if multiple DNS SRV records with equal priority and weight as returned?</span></span> <span data-ttu-id="1ef84-313">この場合、アクセスエッジサービスによって、DNS サーバーから取得した SRV レコードが最初に選択されます。</span><span class="sxs-lookup"><span data-stu-id="1ef84-313">In this situation the Access Edge service will choose the SRV record that it got from the DNS server first.</span></span>
  

