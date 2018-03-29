---
title: 高度なエッジ サーバーの DNS を計画する Skype のビジネス サーバー 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- IT_Skype16
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: '概要: は、Skype のビジネス サーバー 2015 展開オプションのシナリオを確認します。 単一サーバーを使用したいと考えている場合も、DNS または HLB と共にサーバー プールを使用することを優先する場合も、このトピックは役に立ちます。'
ms.openlocfilehash: b3c9299586856b59a8f07f7f2bcb460268c6d687
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server-2015"></a><span data-ttu-id="78571-104">高度なエッジ サーバーの DNS を計画する Skype のビジネス サーバー 2015</span><span class="sxs-lookup"><span data-stu-id="78571-104">Advanced Edge Server DNS planning for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="78571-p102">**概要:** Skype for Business Server 2015 の展開オプションに関するシナリオを確認します。単一サーバーを使用したいと考えている場合も、DNS または HLB と共にサーバー プールを使用することを優先する場合も、このトピックは役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="78571-p102">**Summary:** Review scenarios for Skype for Business Server 2015 deployment options. Whether you want a single server or prefer a server pool with DNS or HLB, this topic should help.</span></span>
  
<span data-ttu-id="78571-107">Skype のビジネス サーバー 2015 のドメイン ネーム システム (DNS) を計画する際に、たくさんの要因、意思決定に果たすことがあります。</span><span class="sxs-lookup"><span data-stu-id="78571-107">When it comes to Domain Name System (DNS) planning for Skype for Business Server 2015, there are a lot of factors that may play into your decision.</span></span> <span data-ttu-id="78571-108">組織のドメイン構造が既に確立されている場合は、どのように作業を進めるか確認するための考慮事項になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78571-108">If your organization's domain structure's already in place, this may be a matter of reviewing how you're going to proceed.</span></span> <span data-ttu-id="78571-109">最初に、以下に示すトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="78571-109">We'll begin with the topics found below:</span></span>
  
- [<span data-ttu-id="78571-110">Walkthrough of Skype for Business clients locating services</span><span class="sxs-lookup"><span data-stu-id="78571-110">Walkthrough of Skype for Business clients locating services</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [<span data-ttu-id="78571-111">Split-brain DNS</span><span class="sxs-lookup"><span data-stu-id="78571-111">Split-brain DNS</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [<span data-ttu-id="78571-112">Automatic configuration without split-brain DNS</span><span class="sxs-lookup"><span data-stu-id="78571-112">Automatic configuration without split-brain DNS</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [<span data-ttu-id="78571-113">DNS disaster recovery</span><span class="sxs-lookup"><span data-stu-id="78571-113">DNS disaster recovery</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [<span data-ttu-id="78571-114">DNS load balancing</span><span class="sxs-lookup"><span data-stu-id="78571-114">DNS load balancing</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a><span data-ttu-id="78571-115">Walkthrough of Skype for Business clients locating services</span><span class="sxs-lookup"><span data-stu-id="78571-115">Walkthrough of Skype for Business clients locating services</span></span>
<span data-ttu-id="78571-116"><a name="WalkthroughOfSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="78571-116"></span></span>

<span data-ttu-id="78571-117">ビジネス クライアント用の Skype は、検索し、ビジネス サーバー 2015 の Skype のサービスへのアクセス方法での Lync クライアントの以前のバージョンに似ています。</span><span class="sxs-lookup"><span data-stu-id="78571-117">Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server 2015.</span></span> <span data-ttu-id="78571-118">ここではサーバー検索の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="78571-118">This section details the server location process.</span></span>
  
1. <span data-ttu-id="78571-119">lyncdiscoverinternal。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="78571-119">lyncdiscoverinternal.\<domain\></span></span>
    
     <span data-ttu-id="78571-120">*これは、内部 Web サービスを対象とした自動検出サービスの A ホスト レコードです。*</span><span class="sxs-lookup"><span data-stu-id="78571-120">*This is an A host record for the Autodiscover service on the internal web services.*</span></span> 
    
2. <span data-ttu-id="78571-121">lyncdiscover。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="78571-121">lyncdiscover.\<domain\></span></span>
    
     <span data-ttu-id="78571-122">*これは、外部 Web サービスを対象とした自動検出サービスのホスト レコードです。*</span><span class="sxs-lookup"><span data-stu-id="78571-122">*This is an A host record for the Autodiscover service on the external web services.*</span></span> 
    
3. <span data-ttu-id="78571-123">_sipinternaltls._tcp。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="78571-123">_sipinternaltls._tcp.\<domain\></span></span>
    
     <span data-ttu-id="78571-124">*これは、内部 TLS 接続用の SRV レコードです。*</span><span class="sxs-lookup"><span data-stu-id="78571-124">*This is a SRV record for internal TLS connections.*</span></span> 
    
4. <span data-ttu-id="78571-125">ゾーンに追加します。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="78571-125">_sip._tls.\<domain\></span></span>
    
     <span data-ttu-id="78571-126">*これは、外部 TLS 接続用の SRV レコードです。*</span><span class="sxs-lookup"><span data-stu-id="78571-126">*This is a SRV record for external TLS connections.*</span></span> 
    
5. <span data-ttu-id="78571-127">sipinternal。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="78571-127">sipinternal.\<domain\></span></span>
    
     <span data-ttu-id="78571-128">*これは、フロント エンド プールまたはディレクター、内部ネットワークでのみ名前解決の A ホスト レコードです。*</span><span class="sxs-lookup"><span data-stu-id="78571-128">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
6. <span data-ttu-id="78571-129">sip。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="78571-129">sip.\<domain\></span></span>
    
     <span data-ttu-id="78571-130">*これは、フロント エンド プールまたはディレクター、内部ネットワークでのみ名前解決の A ホスト レコードです。*</span><span class="sxs-lookup"><span data-stu-id="78571-130">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
7. <span data-ttu-id="78571-131">sipexternal。\<ドメイン\></span><span class="sxs-lookup"><span data-stu-id="78571-131">sipexternal.\<domain\></span></span>
    
     <span data-ttu-id="78571-132">*これは、クライアントが外部にある場合、アクセス エッジ サービスは、ホスト A レコードです。*</span><span class="sxs-lookup"><span data-stu-id="78571-132">*This is an A host record for the Access Edge service, when the client is external.*</span></span> 
    
<span data-ttu-id="78571-133">常に自動検出サービスを使用することが望まれます。これはサービス検出に関して優先される方法であり、他の方法はフォールバックの方法です。</span><span class="sxs-lookup"><span data-stu-id="78571-133">The Autodiscover service is always favored as that's the preferred method for service location, and the others are fallback methods.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78571-p105">SRV レコードを作成する場合は、DNS SRV レコードを作成するのと同じドメインにある DNS の A レコード (および、IPv6 アドレスを使用している場合は AAAA レコード) を指す必要があります。たとえば、SRV レコードが contoso.com にある場合、A (および AAAA) レコードが fabrikam.com を指すことはできません。</span><span class="sxs-lookup"><span data-stu-id="78571-p105">When you're creating SRV records, it's important to remember that they need to point to a DNS A (and AAAA if you're using IPv6 addressing) in the same domain in which the DNS SRV record's being created. For example, if they SRV record's in contoso.com, the A (and AAAA) record it points to can't be in fabrikam.com.</span></span> 
  
<span data-ttu-id="78571-p106">希望する場合は、サービスの手動検出に依存するようにモバイル デバイスを設定することもできます。この方法を採用しようとする場合は、各ユーザーが自らのモバイル デバイスで、次のようにプロトコルとパスを含め、内部と外部の完全な自動検出サービス URL を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78571-p106">If you're inclined to do it, you can set your mobile device up for manual discovery of services. If that's what you're looking to do, each user needs to configure their mobile device settings with the full internal and external Autodiscover service URIs, including the protocol and path, as follows:</span></span>
  
- <span data-ttu-id="78571-138">外部アクセス用: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="78571-138">For external access: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span></span>
    
- <span data-ttu-id="78571-139">内部アクセス用: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="78571-139">For internal access: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span></span>
    
<span data-ttu-id="78571-p107">手動検出ではなく、自動検出を使用することを強くお勧めします。ただし、トラブルシューティングやテストを実行する場合は、手動設定が非常に役に立つこともあります。</span><span class="sxs-lookup"><span data-stu-id="78571-p107">We do recommend you use automatic discovery as opposed to manual discovery. But if you're doing some troubleshooting or testing, manual settings can be very helpful.</span></span>
  
## <a name="split-brain-dns"></a><span data-ttu-id="78571-142">スプリットブレイン DNS</span><span class="sxs-lookup"><span data-stu-id="78571-142">Split-brain DNS</span></span>
<span data-ttu-id="78571-143"><a name="SplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="78571-143"></span></span>

<span data-ttu-id="78571-p108">これは、2 つの DNS ゾーンが同じ名前空間に存在する DNS 構成です。一方の DNS ゾーンは内部要求のみ、他方の DNS ゾーンは外部要求のみを処理します。</span><span class="sxs-lookup"><span data-stu-id="78571-p108">This is a DNS configuration where you have two DNS zones with the same namespace. The first DNS zone handles internal requests, while the second DNS zone handles external requests.</span></span>
  
<span data-ttu-id="78571-p109">企業がこの構成を採用するのはなぜでしょうか。これは、内部と外部で同じ名前空間を使用する場合の要件になることがあります。もちろん、この構成を採用すると、DNS の多数の SRV レコードと A レコードが一方のゾーン内または他方のゾーン内で一意になることが求められる結果につながります。重複が存在する場合は、これらのレコードに関連付けられる IP アドレスは一意になります。</span><span class="sxs-lookup"><span data-stu-id="78571-p109">Why would a company do this? They may have a requirement to use the same namespace internally and externally, but of course this will lead to many DNS SRV and A records being unique to one zone or another, and where there is duplication, the IP addresses associated with these records would be unique.</span></span>
  
<span data-ttu-id="78571-148">この構成を採用すると、いくつかの課題が発生します。</span><span class="sxs-lookup"><span data-stu-id="78571-148">This presents some challenges.</span></span> <span data-ttu-id="78571-149">最も重要なは、ブレイン DNS モビリティの**サポートされていない**のです。</span><span class="sxs-lookup"><span data-stu-id="78571-149">The most important is that split-brain DNS is **not supported** for Mobility.</span></span> <span data-ttu-id="78571-150">これは、LyncDiscover と LyncDiscoverInternal の各 DNS レコードが原因です (LyncDiscover は外部 DNS サーバー上で、また LyncDiscoverInternal は内部 DNS サーバー上で定義する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="78571-150">This is because of the LyncDiscover and LyncDiscoverInternal DNS records (LyncDiscover has to be defined on you external DNS server, while LyncDiscoverInternal has to be defined on your internal DNS server).</span></span>
  
<span data-ttu-id="78571-151">ゾーンについては、内部および外部ここでは、DNS レコードをリストしますが、エッジ サーバーの環境の必要条件のセクションで詳細な例を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="78571-151">We'll list the DNS records for the internal and external zones here, but you can find detailed examples on the Edge Server environmental requirements section.</span></span>
  
### <a name="internal-dns"></a><span data-ttu-id="78571-152">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="78571-152">Internal DNS</span></span>

- <span data-ttu-id="78571-153">(たとえば) contoso.com という信頼できる DNS ゾーンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="78571-153">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="78571-154">以下は、内部 contoso.com の内容です。</span><span class="sxs-lookup"><span data-stu-id="78571-154">This internal contoso.com contains:</span></span>
    
  - <span data-ttu-id="78571-155">DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合は、フロント エンド プール、ディレクター プールまたはディレクターのプール名、およびビジネス サーバー 2015 の Skype を実行して、組織のネットワーク内のすべての内部サーバーに記録されます。</span><span class="sxs-lookup"><span data-stu-id="78571-155">DNS A and AAAA (if you're using IPv6 addressing) records for your Front End pool, Director pool or Director pool name, and all internal servers running Skype for Business Server 2015 in your organization's network.</span></span>
    
  - <span data-ttu-id="78571-156">DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合、エッジの内部インターフェイスの各 Skype の記録ビジネス 2015 エッジ サーバーを境界ネットワーク内です。</span><span class="sxs-lookup"><span data-stu-id="78571-156">DNS A and AAAA (if you're using IPv6 addressing) records for your Edge internal interface for each Skype for Business Server 2015 Edge Server in your perimeter network.</span></span>
    
  - <span data-ttu-id="78571-157">(これは**省略可能な**リバース プロキシを管理するため) を境界ネットワーク内の各のリバース プロキシ サーバーの内部インターフェイスの DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合を記録します。</span><span class="sxs-lookup"><span data-stu-id="78571-157">DNS A and AAAA (if you're using IPv6 addressing) records for the internal interface of each reverse proxy server in your perimeter network (which is **optional** for management of a reverse proxy).</span></span>
    
  - <span data-ttu-id="78571-158">DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合、(これは**省略可能**) ビジネス サーバー 2015 クライアントの自動構成の内部の Skype の SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="78571-158">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server 2015 client autoconfiguration (which is **optional** ).</span></span>
    
  - <span data-ttu-id="78571-159">DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合、または (これは**省略可能**) ビジネス サーバー 2015 Web サービスの Skype の自動検出の CNAME レコード。</span><span class="sxs-lookup"><span data-stu-id="78571-159">DNS A and AAAA (if you're using IPv6 addressing) or CNAME records for automatic discovery of Skype for Business Server 2015 Web Services (which is **optional** ).</span></span>
    
- <span data-ttu-id="78571-160">ビジネス サーバー 2015 内部エッジのインタ フェースを境界ネットワーク内のすべての Skype は、contoso.com にクエリを解決するため、この内部 DNS ゾーンを使用します。</span><span class="sxs-lookup"><span data-stu-id="78571-160">All your Skype for Business Server 2015 internal Edge interfaces in your perimeter network use this internal DNS zone for resolving queries to contoso.com.</span></span>
    
- <span data-ttu-id="78571-161">ビジネス サーバー 2015 年およびビジネス サーバー 2015 の企業のネットワークでは、Skype を実行しているクライアントの Skype を実行しているすべてのサーバーは、contoso.com にクエリを解決するために内部の DNS サーバーをポイントまたは各エッジ サーバー] ボックスの一覧の A および AAAA のホスト ファイルを使用する場合IPv6 のアドレス指定を使用している) (具体的には、ディレクターまたはディレクター プールの VIP、フロント エンド プールの VIP、または Standard Edition サーバー) の次ホップのサーバーに記録します。</span><span class="sxs-lookup"><span data-stu-id="78571-161">All servers running Skype for Business Server 2015, and clients running Skype for Business Server 2015 in the corporate network, point to internal DNS servers for resolving queries to contoso.com, or they use the Host file on each Edge Server and list A and AAAA (if you're using IPv6 addressing) records for the next hop server (specifically for the Director or Director pool VIP, Front End pool VIP, or Standard Edition server).</span></span>
    
### <a name="external-dns"></a><span data-ttu-id="78571-162">外部 DNS</span><span class="sxs-lookup"><span data-stu-id="78571-162">External DNS</span></span>

- <span data-ttu-id="78571-163">(たとえば) contoso.com という信頼できる DNS ゾーンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="78571-163">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="78571-164">以下は、外部 contoso.com の内容です。</span><span class="sxs-lookup"><span data-stu-id="78571-164">This external contoso.com contains:</span></span>
    
  - <span data-ttu-id="78571-165">DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合は、CNAME は、Skype のビジネス サーバー 2015 web サービス用の自動検出機能を記録します。</span><span class="sxs-lookup"><span data-stu-id="78571-165">DNS A and AAAA (if you're using IPv6 addressing), or CNAME records, for automatic discovery of Skype for Business Server 2015 web services.</span></span> <span data-ttu-id="78571-166">これは移動に使用します。</span><span class="sxs-lookup"><span data-stu-id="78571-166">This is for use with mobility.</span></span>
    
  - <span data-ttu-id="78571-167">DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合、エッジの外部インターフェイス ビジネス 2015 エッジ サーバーまたはハードウェアの負荷を各 Skype の SRV レコードは、境界ネットワーク内の (HLB) の VIP を分散しました。</span><span class="sxs-lookup"><span data-stu-id="78571-167">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server 2015 Edge Server or hardware load balanced (HLB) VIP in the perimeter network.</span></span>
    
  - <span data-ttu-id="78571-168">(リバース プロキシ サーバーのプールの VIP)、またはリバース プロキシ サーバーの外部インターフェイスのネットワーク境界に DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合、SRV が記録されます。</span><span class="sxs-lookup"><span data-stu-id="78571-168">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.</span></span>
    
  - <span data-ttu-id="78571-169">DNS の A および AAAA (IPv6 のアドレス指定を使用している) 場合や SRV レコード Skype のビジネス サーバー 2015 クライアントの自動構成が (**省略可能**) のです。</span><span class="sxs-lookup"><span data-stu-id="78571-169">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server 2015 client autoconfiguration (**optional**).</span></span>
    
## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="78571-170">スプリットブレイン DNS なしの自動構成</span><span class="sxs-lookup"><span data-stu-id="78571-170">Automatic configuration without split-brain DNS</span></span>
<span data-ttu-id="78571-171"><a name="NoSplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="78571-171"></span></span>

<span data-ttu-id="78571-172">ブレイン DNS を使用しない、あるここでの回避策のいずれかを使用している場合を除き、Skype のビジネスを実行しているクライアントの内部の自動構成は機能しません。</span><span class="sxs-lookup"><span data-stu-id="78571-172">If you don't use split-brain DNS, internal automatic configuration of clients running Skype for Business won't work unless you're using one of the workarounds we have here.</span></span> <span data-ttu-id="78571-173">なぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="78571-173">Why not?</span></span> <span data-ttu-id="78571-174">ビジネス サーバー 2015 の Skype では、ユーザーの SIP URI は、自動構成用に指定されたフロント エンド プールのドメインと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78571-174">Because Skype for Business Server 2015 requires the user's SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="78571-175">これは、Lync Server の以前のバージョンから変更されていません。</span><span class="sxs-lookup"><span data-stu-id="78571-175">This hasn't changed from earlier versions of Lync Server.</span></span>
  
<span data-ttu-id="78571-176">たとえば、使用されている SIP ドメインが 2 つある場合、次の DNS SRV レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="78571-176">So, if you have two SIP domains in use, you'd need these DNS SRV records:</span></span>
  
- <span data-ttu-id="78571-177">_sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-177">_sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>
    
     <span data-ttu-id="78571-178">*Bob@contoso.com として、ユーザーがサインインしている場合このレコードはどおりに動作を自動的に構成、ユーザーの SIP ドメイン (contoso.com) のフロント エンド プールのドメインと一致します。*</span><span class="sxs-lookup"><span data-stu-id="78571-178">*If a user signs in as bob@contoso.com, this record would work for automatic configuration, as the user's SIP domain matches the domain of the Front End pool (contoso.com).*</span></span> 
    
- <span data-ttu-id="78571-179">_sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="78571-179">_sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="78571-180">*Alice@fabrikam.com として、ユーザーがサインインしている場合は、SIP ドメインはそのドメイン内のフロント エンド プールを一致するためを自動的に構成の 2 つ目のドメインでは、もう一度このレコードが動作は。*</span><span class="sxs-lookup"><span data-stu-id="78571-180">*If a user signs in as alice@fabrikam.com, this record would work for automatic configuration of the second domain, again because the SIP domain matches the Front End pool for that domain.*</span></span> 
    
<span data-ttu-id="78571-181">ここまでの例を使用すると、次のレコードは機能しません。</span><span class="sxs-lookup"><span data-stu-id="78571-181">To take the example further, this would not work:</span></span>
  
- <span data-ttu-id="78571-182">_sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="78571-182">_sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="78571-183">*tim@litwareinc.com としてサインインしたユーザーの場合は、自動構成は機能しません。このユーザーの SIP ドメイン (litwareinc.com) は、プール内のドメイン (fabrikam.com) と一致しないためです。*</span><span class="sxs-lookup"><span data-stu-id="78571-183">*A user signing in as tim@litwareinc.com won't work for automatic configuration, because his SIP domain (litwareinc.com) doesn't match the domain in the pool (fabrikam.com).*</span></span> 
    
<span data-ttu-id="78571-184">わかったところで、DNS の分散管理をビジネスのクライアントの Skype の自動要件が必要な場合は、これらのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="78571-184">So now that we know all that, if you need automatic requirement for your Skype for Business clients without split-brain DNS, you have these options:</span></span>
  
- <span data-ttu-id="78571-185">**グループ ポリシー オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="78571-185">**Group Policy Objects**</span></span>
    
    <span data-ttu-id="78571-186">グループ ポリシー オブジェクト (GPO) を使用して、適切なサーバーの値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="78571-186">You can use Group Policy Objects (GPOs) to populate the correct server values.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78571-p113">このオプションを使用しても自動構成は有効になりませんが、手動構成が自動化されます。この方法を使用した場合、自動構成に関連付ける SRV レコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="78571-p113">This option doesn't enable automatic configuration, but it does automate manual configuration. If this approach is used, the SRV records associated with automatic configuration aren't required.</span></span> 
  
- <span data-ttu-id="78571-189">**内部ゾーンの一致**</span><span class="sxs-lookup"><span data-stu-id="78571-189">**Matching internal zone**</span></span>
    
    <span data-ttu-id="78571-190">外部 DNS ゾーン (たとえば、contoso.com) に一致する内部 DNS にゾーンを作成し、DNS の A (および AAAA IPv6 のアドレス指定を使用する場合) を作成する必要がありますビジネス サーバー 2015 プールの自動使用の Skype に対応するレコード構成します。</span><span class="sxs-lookup"><span data-stu-id="78571-190">You'll need to create a zone in your internal DNS that matches your external DNS zone (for example, contoso.com), and then create DNS A (and AAAA if you're using IPv6 addressing) records that correspond to the Skype for Business Server 2015 pool used for automatic configuration.</span></span>
    
    <span data-ttu-id="78571-191">などがある場合、ユーザーが置かれている記号ですが、pool01.contoso.net、Skype に bob@contoso.com、ビジネスは、contoso.com と呼ばれる内部の DNS ゾーンを作成し、その中には、DNS の A (および AAAA 使用されている IPv6 アドレスの場合) を作成する必要がレコードpool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="78571-191">For example, if you have a user homed on pool01.contoso.net, but signs into Skype for Business as bob@contoso.com, create an internal DNS zone called contoso.com, and inside it you need to create a DNS A (and AAAA if IPv6 addressing's being used) record for pool01.contoso.com.</span></span>
    
- <span data-ttu-id="78571-192">**ピンポイントの内部ゾーン**</span><span class="sxs-lookup"><span data-stu-id="78571-192">**Pin-point internal zone**</span></span>
    
    <span data-ttu-id="78571-p114">内部 DNS 内にゾーン全体を作成することが適切なオプションではない場合は、自動構成で必要とされる複数の SRV レコードに対応するピンポイント (専用) ゾーンを作成し、dnscmd.exe を使用してそれらのゾーンを設定することができます。DNS ユーザー インターフェイスはピンポイント ゾーンの作成をサポートしていないため、Dnscmd.exe が必須です。</span><span class="sxs-lookup"><span data-stu-id="78571-p114">If creating an entire zone in your internal DNS isn't an option for you, you can create pin-point (dedicated) zones that correspond to the SRV records required for automatic configuration, and populate those zones using dnscmd.exe. Dnscmd.exe is required because the DNS user interface won't support the creation of pin-point zones.</span></span>
    
    <span data-ttu-id="78571-195">などの場合は、SIP ドメインは、contoso.com を使用して 2 つのフロント エンド サーバーを含む pool01 と呼ばれるフロント エンド プール、する必要があります次のピン ・ ポイントのゾーン レコードおよび a レコード内部 DNS に。</span><span class="sxs-lookup"><span data-stu-id="78571-195">For example, if your SIP domain is contoso.com, and you have a Front End pool called pool01 that contains two Front End Servers, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    <span data-ttu-id="78571-p115">環境内で 2 番目の SIP ドメインを用意することもできます。この場合は、内部 DNS 内で以下のピンポイント ゾーンと A レコードが必要になります。</span><span class="sxs-lookup"><span data-stu-id="78571-p115">You may have a second SIP domain in your environment. In that case, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
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
> <span data-ttu-id="78571-198">フロント エンド プールを 2 回ですが、2 つの異なる IP アドレスと FQDN が表示されますが表示されます。</span><span class="sxs-lookup"><span data-stu-id="78571-198">You'll see the Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="78571-199">DNS 負荷分散を使用しているためです。</span><span class="sxs-lookup"><span data-stu-id="78571-199">That's because DNS load balancing is used.</span></span> <span data-ttu-id="78571-200">HLB が使用されている場合だけでしょう、1 つのフロント エンド プール エントリ。</span><span class="sxs-lookup"><span data-stu-id="78571-200">If HLB is used, there'd only be a single Front End pool entry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="78571-201">フロント エンド プールの FQDN の値を変更する、contoso.com と fabrikam.com の例との間も、IP アドレスは変わりません。</span><span class="sxs-lookup"><span data-stu-id="78571-201">Also, the Front End pool FQDN values change between the contoso.com and fabrikam.com examples, but the IP addresses remain the same.</span></span> <span data-ttu-id="78571-202">いずれかの SIP ドメインからサインインしているユーザーが自動構成に同じフロント エンド プールを使用するためです。</span><span class="sxs-lookup"><span data-stu-id="78571-202">That's because users who're signing in from either SIP domain will be using the same Front End pool for automatic configuration.</span></span> 
  
## <a name="dns-disaster-recovery"></a><span data-ttu-id="78571-203">DNS 障害復旧</span><span class="sxs-lookup"><span data-stu-id="78571-203">DNS disaster recovery</span></span>
<span data-ttu-id="78571-204"><a name="DNSDR"> </a></span><span class="sxs-lookup"><span data-stu-id="78571-204"></span></span>

<span data-ttu-id="78571-205">障害回復 (DR) とフェイル オーバー ・ サイトに web トラフィックをビジネス サーバー 2015 の Skype をリダイレクトするように DNS を構成するには GeoDNS をサポートしているプロバイダーの DNS を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78571-205">To configure DNS to redirect Skype for Business Server 2015 web traffic to your disaster recover (DR) and failover sites, you need to use a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="78571-206">Web サービスを使用する機能は、全体のフロント エンド プールを 1 つがダウンした場合でもを続行するためは、災害リカバリをサポートするために DNS レコードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="78571-206">You can set up your DNS records to support disaster recover, so that features that use web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="78571-207">この障害復旧機能では、自動検出、会議、およびダイヤルインの簡易 URL をサポートします。</span><span class="sxs-lookup"><span data-stu-id="78571-207">This DR feature supports the Autodiscover, Meet and Dial-in simple URLs.</span></span>
  
<span data-ttu-id="78571-208">定義し、(AAAA IPv6 を使用する場合) は、GeoDNS プロバイダーで web サービスの内部および外部の解像度の記録その他の DNS ホストを構成します。</span><span class="sxs-lookup"><span data-stu-id="78571-208">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider.</span></span> <span data-ttu-id="78571-209">以下の詳細は、地理的に分散している、一対のプールを想定していて、ラウンド ロビン DNS **、または**プロバイダー**か**でサポートされている GeoDNS を持っている Pool1 をプライマリとして使用するように構成されて Pool2 に、通信の発生時にフェイル オーバー損失または電源障害が発生。</span><span class="sxs-lookup"><span data-stu-id="78571-209">The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span></span>
  
<span data-ttu-id="78571-210">この表の DNS レコードは、いずれも例です。</span><span class="sxs-lookup"><span data-stu-id="78571-210">All the DNS records in this table are examples.</span></span>
  
|<span data-ttu-id="78571-211">**GeoDNS レコード**</span><span class="sxs-lookup"><span data-stu-id="78571-211">**GeoDNS record**</span></span>|<span data-ttu-id="78571-212">**プールのレコード**</span><span class="sxs-lookup"><span data-stu-id="78571-212">**Pool records**</span></span>|<span data-ttu-id="78571-213">**CNAME レコード**</span><span class="sxs-lookup"><span data-stu-id="78571-213">**CNAME records**</span></span>|<span data-ttu-id="78571-214">**(1 つのオプションを選択します)、DNS の設定**</span><span class="sxs-lookup"><span data-stu-id="78571-214">**DNS settings (select one option)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="78571-215">対応 int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-215">Meet-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-216">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-216">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-217">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-217">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-218">エイリアス Meet.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-218">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-219">エイリアス Meet.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-219">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-220">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="78571-220">Round Robin between pools</span></span>  <br/> <span data-ttu-id="78571-221">**または**</span><span class="sxs-lookup"><span data-stu-id="78571-221">**OR**</span></span> <br/> <span data-ttu-id="78571-222">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="78571-222">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="78571-223">対応 ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-223">Meet-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-224">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-224">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-225">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-225">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-226">エイリアス Meet.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-226">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-227">エイリアス Meet.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-227">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-228">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="78571-228">Round Robin between pools</span></span>  <br/> <span data-ttu-id="78571-229">**または**</span><span class="sxs-lookup"><span data-stu-id="78571-229">**OR**</span></span> <br/> <span data-ttu-id="78571-230">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="78571-230">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="78571-231">ダイヤルイン int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-231">Dialin-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-232">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-232">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-233">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-233">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-234">エイリアス Dialin.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-234">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-235">エイリアス Dialin.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-235">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-236">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="78571-236">Round Robin between pools</span></span>  <br/> <span data-ttu-id="78571-237">**または**</span><span class="sxs-lookup"><span data-stu-id="78571-237">**OR**</span></span> <br/> <span data-ttu-id="78571-238">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="78571-238">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="78571-239">ダイヤルイン ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-239">Dialin-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-240">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-240">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-241">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-241">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-242">エイリアス Dialin.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-242">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-243">エイリアス Dialin.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-243">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-244">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="78571-244">Round Robin between pools</span></span>  <br/> <span data-ttu-id="78571-245">**または**</span><span class="sxs-lookup"><span data-stu-id="78571-245">**OR**</span></span> <br/> <span data-ttu-id="78571-246">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="78571-246">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="78571-247">Lyncdiscoverint int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-247">Lyncdiscoverint-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-248">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-248">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-249">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-249">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-250">エイリアス Lyncdiscoverinternal.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-250">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-251">エイリアス Lyncdiscoverinternal.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-251">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-252">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="78571-252">Round Robin between pools</span></span>  <br/> <span data-ttu-id="78571-253">**または**</span><span class="sxs-lookup"><span data-stu-id="78571-253">**OR**</span></span> <br/> <span data-ttu-id="78571-254">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="78571-254">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="78571-255">Lyncdiscover ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-255">Lyncdiscover-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-256">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-256">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-257">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-257">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-258">エイリアス Lyncdiscover.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-258">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-259">エイリアス Lyncdiscover.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-259">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-260">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="78571-260">Round Robin between pools</span></span>  <br/> <span data-ttu-id="78571-261">**または**</span><span class="sxs-lookup"><span data-stu-id="78571-261">**OR**</span></span> <br/> <span data-ttu-id="78571-262">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="78571-262">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="78571-263">スケジューラ int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-263">Scheduler-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-264">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-264">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-265">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-265">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-266">エイリアス Scheduler.contoso.com を Pool1InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-266">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-267">エイリアス Scheduler.contoso.com を Pool2InternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-267">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-268">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="78571-268">Round Robin between pools</span></span>  <br/> <span data-ttu-id="78571-269">**または**</span><span class="sxs-lookup"><span data-stu-id="78571-269">**OR**</span></span> <br/> <span data-ttu-id="78571-270">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="78571-270">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="78571-271">スケジューラ ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-271">Scheduler-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-272">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-272">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-273">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-273">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-274">エイリアス Scheduler.contoso.com を Pool1ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-274">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="78571-275">エイリアス Scheduler.contoso.com を Pool2ExternalWebFQDN.contoso.com に指定</span><span class="sxs-lookup"><span data-stu-id="78571-275">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-276">プール間のラウンド ロビン</span><span class="sxs-lookup"><span data-stu-id="78571-276">Round Robin between pools</span></span>  <br/> <span data-ttu-id="78571-277">**または**</span><span class="sxs-lookup"><span data-stu-id="78571-277">**OR**</span></span> <br/> <span data-ttu-id="78571-278">プライマリを使用し、障害発生時はセカンダリに接続</span><span class="sxs-lookup"><span data-stu-id="78571-278">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="78571-279">DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="78571-279">DNS load balancing</span></span>
<span data-ttu-id="78571-280"><a name="DNSLB"> </a></span><span class="sxs-lookup"><span data-stu-id="78571-280"></span></span>

<span data-ttu-id="78571-281">DNS 負荷分散は一般的に、アプリケーション レベルで実装されます。</span><span class="sxs-lookup"><span data-stu-id="78571-281">DNS load balancing is usually implemented at the application level.</span></span> <span data-ttu-id="78571-282">返される IP アドレスのいずれかに接続することによって、プール内のサーバーに接続しようとするアプリケーション (たとえば、クライアント ビジネスの Skype を実行している)、DNS の A および AAAA (IPv6 のアドレス指定が使用されます) の場合は、プールの FQDN についてのクエリを記録します。</span><span class="sxs-lookup"><span data-stu-id="78571-282">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool FQDN.</span></span>
  
<span data-ttu-id="78571-283">たとえば、pool01.contoso.com をという名前のプールで 3 つのフロント エンド サーバーがある場合は、次が発生します。</span><span class="sxs-lookup"><span data-stu-id="78571-283">For example, if there are three Front End Servers in a pool named pool01.contoso.com, the following would happen:</span></span>
  
- <span data-ttu-id="78571-284">ビジネス用の Skype を実行しているクライアントは、pool01.contoso.com の DNS を照会します。クエリでは、3 つの IP アドレスが返され、次のように (順序) でキャッシュに保持します。</span><span class="sxs-lookup"><span data-stu-id="78571-284">Clients running Skype for Business query DNS for pool01.contoso.com. The query returns three IP addresses and caches them as follows (in some order):</span></span>
    
   |||
   |:-----|:-----|
   |<span data-ttu-id="78571-285">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-285">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-286">192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="78571-286">192.168.10.90</span></span>  <br/> |
   |<span data-ttu-id="78571-287">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-287">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-288">192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="78571-288">192.168.10.91</span></span>  <br/> |
   |<span data-ttu-id="78571-289">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78571-289">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="78571-290">192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="78571-290">192.168.10.92</span></span>  <br/> |
   
- <span data-ttu-id="78571-p121">次に、クライアントは IP アドレスの 1 つに対して TCP 接続を確立しようとします。それが失敗した場合は、一覧の中にキャッシュされている次の IP アドレスを試します。</span><span class="sxs-lookup"><span data-stu-id="78571-p121">The client tries to establish a TCP connection to one of the IP addresses. If that fails, it'll try the next IP address it's cached from that list.</span></span>
    
- <span data-ttu-id="78571-293">TCP 接続が成功した場合、クライアントは TLS のネゴシエーションを行い、pool01.contoso.com のプライマリ レジストラーに接続します。</span><span class="sxs-lookup"><span data-stu-id="78571-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="78571-294">クライアントには、キャッシュされているすべてのエントリが正常に接続しなくてもしようとすると、ユーザーは、ビジネス サーバー 2015 の Skype を実行しているサーバーがある時点で通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="78571-294">If the client tries all cached entries without a successful connection, the user receives a notification that no servers running Skype for Business Server 2015 are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="78571-p122">DNS ベースの負荷分散は、一般的に、DNS を利用してプール内のサーバーの IP アドレスを別の順序で提供して負荷分散を行うことを指す DNS ラウンド ロビン (DNS RR) と異なります。一般的に、DNS RR は負荷分散が可能で、フェールオーバー機能を実現しません。たとえば、DNS A (または IPv6 のシナリオを使用している場合は AAAA) クエリで返された 1 つの IP アドレスに対する接続が失敗した場合、その接続は失敗します。したがって、DNS RR は DNS ベースの負荷分散より信頼性が劣りますが、上記の目的で、DNS 負荷分散と共に DNS RR を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="78571-p122">DNS-based load balancing is different from DNS round robin (DNS RR), which typically refers to load balancing by relying on DNS to give a different order of IP addresses for the servers in your pool. Typically, DNS RR enables load distribution, but it won't allow you to enable failover. For example, if the connection to the one IP address returned by your DNS A (or AAAA in an IPv6 scenario) query fails, that connection will fail. That makes DNS RR less reliable than DNS-based load balancing. You can still use DNS RR in conjunction with DNS-based load balancing if you need to do that.</span></span> 
  
<span data-ttu-id="78571-300">DNS 負荷分散の用途:</span><span class="sxs-lookup"><span data-stu-id="78571-300">You use DNS load balancing to:</span></span>
  
- <span data-ttu-id="78571-301">負荷は、サーバーからサーバー、エッジ サーバーに SIP を分散します。</span><span class="sxs-lookup"><span data-stu-id="78571-301">Load balance server-to-server SIP to the Edge Servers.</span></span>
    
- <span data-ttu-id="78571-302">会議自動アテンダント、応答グループ、コール パークなどの統合コミュニケーション アプリケーション サービス (UCAS) アプリケーションの負荷分散</span><span class="sxs-lookup"><span data-stu-id="78571-302">Load balance Unified Communication Application Services (UCAS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.</span></span>
    
- <span data-ttu-id="78571-303">UCAS アプリケーションへの新規接続の禁止(ドレインとも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="78571-303">Prevent new connections to UCAS applications (also known as draining).</span></span>
    
- <span data-ttu-id="78571-304">負荷は、クライアントとエッジ サーバー間のすべてのクライアントからサーバーへのトラフィックを分散します。</span><span class="sxs-lookup"><span data-stu-id="78571-304">Load balance all client-to-server traffic between clients and Edge Servers.</span></span>
    
<span data-ttu-id="78571-305">DNS 負荷分散を使用できない用途:</span><span class="sxs-lookup"><span data-stu-id="78571-305">You can't use DNS load balancing for:</span></span>
  
- <span data-ttu-id="78571-306">クライアントからサーバーへの web トラフィックは、フロント エンド サーバーまたはディレクター。</span><span class="sxs-lookup"><span data-stu-id="78571-306">Client-to-server web traffic to your Front End Servers or a Director.</span></span>
    
<span data-ttu-id="78571-307">タイ ブレーカーの場合、複数の DNS レコードがアクセス エッジ サービスを常に、クエリによって返された優先度の低い数値のレコードを選択するときに、DNS SRV レコードを選択する方法で、もう少し詳細を移動するために必要な最大の数値の重量。</span><span class="sxs-lookup"><span data-stu-id="78571-307">To go a little more in-depth on how a DNS SRV record's selected when mutiple DNS records are returned by a query, the Access Edge service always picks the record with the lowest numeric priority and, if a tie-breaker is needed, the highest numeric weight.</span></span> <span data-ttu-id="78571-308">これは、[インターネット技術標準化委員会ドキュメント](https://www.ietf.org/rfc/rfc2782.txt)と一致します。</span><span class="sxs-lookup"><span data-stu-id="78571-308">This is consistent with [Internet Engineering Task Force documentation](https://www.ietf.org/rfc/rfc2782.txt).</span></span>
  
<span data-ttu-id="78571-p124">そのため、たとえば最初の DNS SRV レコードの重み付けが 20 で、優先順位が 40、また 2 番目の DNS SRV レコードの重み付けが 10 で、優先順位が 50 の場合は、優先順位が 40 である最初のレコードが選択されます。常に優先順位が最初に考慮され、クライアントが最初にターゲットにするホストになります。同じ優先順位を持つターゲットが 2 つ存在する場合はどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="78571-p124">So, for example, if your first DNS SRV record has a weight of 20 and a priority of 40, and your second DNS SRV record has a weight of 10 and a priority of 50, the first record's going to be chosen because it has the lower priority of 40. Priority always goes first, and that's the host that a client will target first. What if there are two targets with the same priority?</span></span> 
  
<span data-ttu-id="78571-p125">この場合は、重み付けが考慮されます。この状況では、重み付けが大きいほど、選択される確率が高くなります。サーバー選択を行わない場合は、DNS 管理者は重み付け 0 を使用する必要があります。0 より大きい重み付けを持つレコードが存在するとき、重み付け 0 のレコードが選択される可能性は非常に小さくなります。</span><span class="sxs-lookup"><span data-stu-id="78571-p125">In that case, weight comes into consideration. Larger weights should be given a high probability, in this circumstance, of being selected. DNS administrators should use weight 0 when there isn't any server selection to do. In the presence of records containing weights greater than 0, records with weight 0 have a very small chance of bring selected.</span></span>
  
<span data-ttu-id="78571-316">同じ優先度と重み付けを持つ複数の DNS SRV レコードが返された場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="78571-316">So, then, what happens if multiple DNS SRV records with equal priority and weight as returned?</span></span> <span data-ttu-id="78571-317">このような場合、アクセス エッジ サービスは、取得した DNS サーバーから最初の SRV レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="78571-317">In this situation the Access Edge service will choose the SRV record that it got from the DNS server first.</span></span>
  

