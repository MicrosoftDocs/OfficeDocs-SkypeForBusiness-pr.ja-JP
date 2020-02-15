---
title: 'Lync Server 2013: モビリティの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb4c1eacf48940822ddb26ac41f238ccdb4452dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="786f3-102">Lync Server 2013 でのモビリティの技術要件</span><span class="sxs-lookup"><span data-stu-id="786f3-102">Technical requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="786f3-103">_**トピックの最終更新日:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="786f3-103">_**Topic Last Modified:** 2014-07-24_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="786f3-104">モバイル ユーザーは、特別な計画を必要とするさまざまなモバイル アプリケーション シナリオに直面します。</span><span class="sxs-lookup"><span data-stu-id="786f3-104">Mobile users encounter various mobile application scenarios that require special planning.</span></span> <span data-ttu-id="786f3-105">たとえば、他のユーザーは、3G ネットワーク経由で接続することでモバイルアプリケーションの使用を開始し、職場に到着したときに会社の Wi-fi ネットワークに切り替えてから、建物を離れたときに3G に戻ることがあります。</span><span class="sxs-lookup"><span data-stu-id="786f3-105">For example, someone might start using a mobile application while away from work by connecting through the 3G network, then switch to the corporate Wi-Fi network when arriving at work, and then switch back to 3G when leaving the building.</span></span> <span data-ttu-id="786f3-106">このようなネットワークの移行をサポートし、一貫したユーザー エクスペリエンスを確保するように、環境を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-106">You need to plan your environment to support such network transitions and guarantee a consistent user experience.</span></span> <span data-ttu-id="786f3-107">このセクションでは、モバイルアプリケーションとモビリティリソースの自動検出をサポートするために必要なインフラストラクチャ要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="786f3-107">This section describes the infrastructure requirements that you must have in order to support mobile applications and automatic discovery of mobility resources.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="786f3-108">モバイルアプリケーションは他の Lync Server 2013 サービスに接続することもできますが、すべてのモバイルアプリケーション web 要求を同じ外部 web 完全修飾ドメイン名 (FQDN) に送信するための要件は、Lync Server 2013 Mobility Service にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="786f3-108">Although mobile applications can also connect to other Lync Server 2013 services, the requirement to send all mobile application web requests to the same external web fully qualified domain name (FQDN) applies only to the Lync Server 2013 Mobility Service.</span></span> <span data-ttu-id="786f3-109">その他のモビリティサービスでは、この構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="786f3-109">Other mobility services do not require this configuration.</span></span>



</div>

<span data-ttu-id="786f3-110">ハードウェアロードバランサーの cookie アフィニティの要件は大幅に減少しており、Lync Server 2013 で配信された Lync Mobile を使用している場合は、伝送制御プロトコル (TCP) の類似性を代用します。</span><span class="sxs-lookup"><span data-stu-id="786f3-110">The requirement for cookie affinity in hardware load balancers is dramatically reduced, and you substitute Transmission Control Protocol (TCP) affinity if you are using the Lync Mobile delivered with Lync Server 2013.</span></span> <span data-ttu-id="786f3-111">Cookie の類似性を使用することはできますが、web サービスで不要になったことはありません。</span><span class="sxs-lookup"><span data-stu-id="786f3-111">Cookie affinity can still be used, but the web services no longer require it.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="786f3-112">すべての Mobility Service トラフィックは、発信元の場所に関係なく、リバースプロキシを経由します (内部または外部)。</span><span class="sxs-lookup"><span data-stu-id="786f3-112">All Mobility Service traffic goes through the reverse proxy, regardless of where the origination point is—internal or external.</span></span> <span data-ttu-id="786f3-113">単一のリバースプロキシまたはリバースプロキシのファームの場合、またはリバースプロキシ機能を提供するデバイスの場合、内部トラフィックがインターフェイスを介して egressing され、同じインターフェイス上ですぐに受信しようとすると、問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="786f3-113">In the case of a single reverse proxy or a farm of reverse proxies, or a device that is providing the reverse proxy function, an issue can arise when the internal traffic is egressing through an interface and attempting to immediately ingress on the same interface.</span></span> <span data-ttu-id="786f3-114">これは、多くの場合、TCP パケットスプーフィングまたはスプーフィングのみというセキュリティ規則違反につながります。</span><span class="sxs-lookup"><span data-stu-id="786f3-114">This often leads to a Security rule violation known as TCP packet spoofing or just spoofing.</span></span> <span data-ttu-id="786f3-115">モビリティーを機能させるには、<EM>ヘアピン</EM>(パケットまたは一連のパケットの出口と即時入力) を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-115"><EM>Hair pinning</EM> (the egress and immediate ingress of a packet or series of packets) must be allowed in order for mobility to function.</span></span> <span data-ttu-id="786f3-116">この問題を解決する方法の1つは、ファイアウォールとは別のリバースプロキシを使用することです (スプーフィング防止ルールは、セキュリティ上の理由から、必ずファイアウォールで常に適用する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="786f3-116">One way to resolve this issue is to use a reverse proxy that is separate from the firewall (the spoofing prevention rule should always be enforced at the firewall, for security purposes).</span></span> <span data-ttu-id="786f3-117">ヘアピンは、ファイアウォールの外部インターフェイスではなく、リバースプロキシの外部インターフェイスで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-117">The hairpin can occur at the external interface of the reverse proxy instead of the firewall external interface.</span></span> <span data-ttu-id="786f3-118">ファイアウォールでスプーフィングを検出し、リバースプロキシでルールを緩和して、モビリティに必要なヘアピンを許可します。</span><span class="sxs-lookup"><span data-stu-id="786f3-118">You detect the spoofing at the firewall, and relax the rule at the reverse proxy, thereby allowing the hairpin that mobility requires.</span></span><BR><span data-ttu-id="786f3-119">可能であれば、ドメインネームシステム (DNS) ホストまたは CNAME レコードを使用して、ヘアピンの動作 (ファイアウォールではない) のリバースプロキシを定義します。</span><span class="sxs-lookup"><span data-stu-id="786f3-119">Use the Domain Name System (DNS) host or CNAME records to define the reverse proxy for the hairpin behavior (not the firewall), if at all possible.</span></span>



</div>

<span data-ttu-id="786f3-120">Lync Server 2013 は、Lync 2010 Mobile および Lync 2013 モバイルクライアントの mobility service をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="786f3-120">Lync Server 2013 supports mobility services for Lync 2010 Mobile and Lync 2013 mobile clients.</span></span> <span data-ttu-id="786f3-121">両方のクライアントは、Lync Server 2013 の自動検出サービスを使用して、そのモビリティエントリポイントを見つけますが、使用する mobility service は異なります。</span><span class="sxs-lookup"><span data-stu-id="786f3-121">Both clients use the Lync Server 2013 Autodiscover Service to find its mobility entry point, but differ on which mobility service they use.</span></span> <span data-ttu-id="786f3-122">Lync 2010 Mobile は*Mcx*と呼ばれる Mobility Service を使用します。これは、lync Server 2010 用の累積的な更新プログラム (11 月 11 2011 日) で導入されました。</span><span class="sxs-lookup"><span data-stu-id="786f3-122">Lync 2010 Mobile uses the Mobility Service known as *Mcx*, introduced with the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="786f3-123">Lync 2013 mobile クライアントは、mobility service プロバイダーとして統合コミュニケーション Web API または*Ucwa*を使用します。</span><span class="sxs-lookup"><span data-stu-id="786f3-123">Lync 2013 mobile clients use the Unified Communications Web API, or *UCWA*, as their mobility service provider.</span></span>

<div>

## <a name="internal-and-external-dns-configuration"></a><span data-ttu-id="786f3-124">内部および外部 DNS の構成</span><span class="sxs-lookup"><span data-stu-id="786f3-124">Internal and External DNS Configuration</span></span>

<span data-ttu-id="786f3-125">Mobility Service Mcx (Lync Server 2010:11 月 2011) および UCWA (Lync Server 2013 の累積的な更新プログラムで導入されました。 2 2013 月2日) は同じ方法で DNS を使用します。</span><span class="sxs-lookup"><span data-stu-id="786f3-125">The Mobility Services Mcx (introduced with the Cumulative Update for Lync Server 2010: November 2011) and UCWA (introduced in the Cumulative Updates for Lync Server 2013: February 2013) use DNS in the same way.</span></span>

<span data-ttu-id="786f3-126">自動検出を使用する場合、モバイルデバイスは、DNS を使用してリソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="786f3-126">When you use Automatic Discovery, mobile devices use DNS to locate resources.</span></span> <span data-ttu-id="786f3-127">DNS 参照中に、内部 DNS レコード (lyncdiscoverinternal) に関連付けられている FQDN への接続が最初\<に試行されます。内部ドメイン名\>)。</span><span class="sxs-lookup"><span data-stu-id="786f3-127">During the DNS lookup, a connection is first attempted to the FQDN that is associated with the internal DNS record (lyncdiscoverinternal.\<internal domain name\>).</span></span> <span data-ttu-id="786f3-128">内部 DNS レコードを使用して接続を確立できない場合は、外部 DNS レコード (lyncdiscover) を使用して接続\<を試行します。microsoft.rtc.management.xds.sipdomain\>)</span><span class="sxs-lookup"><span data-stu-id="786f3-128">If a connection cannot be made by using the internal DNS record, a connection is attempted by using the external DNS record (lyncdiscover.\<sipdomain\>).</span></span> <span data-ttu-id="786f3-129">ネットワークの内部にあるモバイル デバイスは内部自動検出サービス URL に接続し、ネットワークの外部にあるモバイル デバイスは自動検出サービスの外部 URL に接続します。</span><span class="sxs-lookup"><span data-stu-id="786f3-129">A mobile device that is internal to the network connects to the internal Autodiscover Service URL, and a mobile device that is external to the network connects to the external Autodiscover Service URL.</span></span> <span data-ttu-id="786f3-130">外部自動検出要求はリバースプロキシを経由します。</span><span class="sxs-lookup"><span data-stu-id="786f3-130">External Autodiscover requests go through the reverse proxy.</span></span> <span data-ttu-id="786f3-131">Lync Server 2013 自動検出サービスは、Mobility Service (Mcx および UCWA) Url を含む、ユーザーのホームプールのすべての Web サービス Url を返します。</span><span class="sxs-lookup"><span data-stu-id="786f3-131">The Lync Server 2013 Autodiscover Service returns all Web Services URLs for the user's home pool, including the Mobility Service (Mcx and UCWA) URLs.</span></span> <span data-ttu-id="786f3-132">ただし、Mobility Service の内部 URL と Mobility Service の外部 URL は共に Web サービスの外部 FQDN に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="786f3-132">However, both the internal Mobility Service URL and the external Mobility Service URL are associated with the external Web Services FQDN.</span></span> <span data-ttu-id="786f3-133">したがって、モバイルデバイスがネットワークの内部と外部のどちらにあるかに関係なく、デバイスは常に、リバースプロキシを介して外部で Lync Server 2013 Mobility Service に接続します。</span><span class="sxs-lookup"><span data-stu-id="786f3-133">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Lync Server 2013 Mobility Service externally through the reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="786f3-134">展開には、内部および外部での複数の異なる名前空間を含めることができることを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="786f3-134">It is important to understand that your deployment can consist of multiple distinct namespaces for internal and external use.</span></span> <span data-ttu-id="786f3-135">SIP ドメイン名は、内部展開ドメイン名とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-135">Your SIP domain name may be different than the internal deployment domain name.</span></span> <span data-ttu-id="786f3-136">たとえば、自分の SIP ドメインは<STRONG>contoso.com</STRONG>の場合もありますが、内部展開は<STRONG>contoso.net</STRONG>の場合があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-136">For example, your SIP domain may be <STRONG>contoso.com</STRONG>, while your internal deployment may be <STRONG>contoso.net</STRONG>.</span></span> <span data-ttu-id="786f3-137">Lync Server にログインするユーザーは、 <STRONG>john@contoso.com</STRONG>などの SIP ドメイン名を使用します。</span><span class="sxs-lookup"><span data-stu-id="786f3-137">Users who log in to Lync Server will use the SIP domain name, such as <STRONG>john@contoso.com</STRONG>.</span></span> <span data-ttu-id="786f3-138">(トポロジビルダーで<STRONG>外部 web サービス</STRONG>として定義されている) 外部 web サービスにアドレス指定する場合、ドメイン名と SIP ドメイン名は、DNS での定義に従って一貫性が保たれます。</span><span class="sxs-lookup"><span data-stu-id="786f3-138">When addressing the external web services (defined in Topology Builder as <STRONG>External web services</STRONG>), the domain name and the SIP domain name will be consistent, as defined in DNS.</span></span> <span data-ttu-id="786f3-139">内部 web サービス (トポロジビルダーで<STRONG>内部 web サービス</STRONG>として定義されている) に対処する場合、内部 web サービスの既定の名前は、フロントエンドサーバー、フロントエンドプール、ディレクター、またはディレクタープールの FQDN になります。</span><span class="sxs-lookup"><span data-stu-id="786f3-139">When addressing the internal Web services (defined in Topology Builder as <STRONG>Internal web services</STRONG>), the default name of the internal web services will be the FQDN of the Front End Server, Front End pool, Director, or Director pool.</span></span> <span data-ttu-id="786f3-140">[内部 web サービス名] を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="786f3-140">You have the option to override the internal web services name.</span></span> <span data-ttu-id="786f3-141">内部 web サービスの場合は、(SIP ドメイン名ではなく) 内部ドメイン名を使用し、上書きされた名前を反映する DNS ホスト A (または IPv6 の場合は AAAA) レコードを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-141">You should use the internal domain name (and not the SIP domain name) for internal web services and define the DNS host A (or, for IPv6, AAAA) record to reflect the overridden name.</span></span> <span data-ttu-id="786f3-142">たとえば、既定の内部 web サービスの FQDN は<STRONG>pool01.contoso.net</STRONG>の場合があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-142">For example, the default internal web services FQDN may be <STRONG>pool01.contoso.net</STRONG>.</span></span> <span data-ttu-id="786f3-143">オーバーライドされた内部 web サービスの FQDN は<STRONG>webpool.contoso.net</STRONG>の場合があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-143">An overridden internal web services FQDN may be <STRONG>webpool.contoso.net</STRONG>.</span></span> <span data-ttu-id="786f3-144">この方法で web サービスを定義することにより、サービスの内部および外部の局所性と、それらを使用しているユーザーの局所性を確保することができます。</span><span class="sxs-lookup"><span data-stu-id="786f3-144">Defining the web services in this way helps to ensure that the internal and external locality of the services—and not the locality of the user who is using them—is observed.</span></span><BR><span data-ttu-id="786f3-145">ただし、トポロジビルダーでは web サービスが定義されており、結果の web サービス名、証明書を検証する証明書、およびそれを定義する DNS レコードが一貫している限り、その内部 web サービス名を上書きできます。必要なすべてのドメイン名 (SIP ドメイン名を含む) を持つ内部 web サービス。</span><span class="sxs-lookup"><span data-stu-id="786f3-145">However, because the web services are defined in Topology Builder and the internal web services name can be overridden, as long as the resulting web services name, the certificate that validates it, and the DNS records that define it, are consistent, you can define the internal web services with any domain name—including the SIP domain name—that you want.</span></span> <span data-ttu-id="786f3-146">最終的には、IP アドレスに対する名前の解決は、DNS ホストレコードと一貫した名前空間によって決まります。</span><span class="sxs-lookup"><span data-stu-id="786f3-146">Ultimately, the resolution for the name to the IP address is determined by DNS host records and a consistent namespace.</span></span><BR><span data-ttu-id="786f3-147">このトピックと例の目的のために、内部ドメイン名を使用してトポロジと DNS 定義を示します。</span><span class="sxs-lookup"><span data-stu-id="786f3-147">For the purposes of this topic and the examples, the internal domain name is used to illustrate the topology and the DNS definitions.</span></span>



</div>

<span data-ttu-id="786f3-148">次の図は、内部および外部の DNS 構成を使用する場合の、Mobility Service および自動検出サービスのモバイルアプリケーション web 要求のフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="786f3-148">The following diagram illustrates the flow of mobile application web requests for the Mobility Service and for the Autodiscover Service when using an internal and external DNS configuration.</span></span>

<span data-ttu-id="786f3-149">**自動検出を使用したモビリティサービスフロー**</span><span class="sxs-lookup"><span data-stu-id="786f3-149">**Mobility service flow using AutoDiscover**</span></span>

<span data-ttu-id="786f3-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span><span class="sxs-lookup"><span data-stu-id="786f3-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="786f3-151">この図は、一般的な web サービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="786f3-151">The diagram illustrates generic web services.</span></span> <span data-ttu-id="786f3-152">Mobility という名前の仮想ディレクトリは、Mobility services Mcx および/または UCWA を示しています。</span><span class="sxs-lookup"><span data-stu-id="786f3-152">A virtual directory named Mobility depicts the Mobility services Mcx and/or UCWA.</span></span> <span data-ttu-id="786f3-153">Lync Server 2013 の累積的な更新プログラム (2013 年2月) を適用していない場合は、内部および外部の Web サービスで仮想ディレクトリ Ucwa が定義されていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="786f3-153">If you have not applied the Cumulative Updates for Lync Server 2013: February 2013, you may or may not have the virtual directory Ucwa defined on your internal and external Web services.</span></span> <span data-ttu-id="786f3-154">仮想ディレクトリの自動検出があり、仮想ディレクトリに Mcx がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-154">You will have a virtual directory Autodiscover, and you may have a virtual directory Mcx.</span></span><BR><span data-ttu-id="786f3-155">展開したモビリティサービステクノロジに関係なく、自動検出とサービスの検出は同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="786f3-155">Autodiscover and the discovery of services work the same way, regardless of the mobility services technology that you have deployed.</span></span>



</div>

<span data-ttu-id="786f3-p110">社内ネットワークの内側と外側からのモバイル ユーザーをサポートするには、内部と外部の Web FQDN について、いくつかの前提条件が満たされる必要があります。また、実装するように選択した機能に応じて、他の要件を満たすことが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="786f3-p110">To support mobile users from both inside and outside the corporate network, your internal and external web FQDNs must meet some prerequisites. In addition, you may need to meet other requirements, depending on the features you choose to implement:</span></span>

  - <span data-ttu-id="786f3-158">自動検出のための新しい DNS、CNAME または A (host、if IPv6、AAAA) レコード。</span><span class="sxs-lookup"><span data-stu-id="786f3-158">New DNS, CNAME or A (host, if IPv6, AAAA) records, for automatic discovery.</span></span>

  - <span data-ttu-id="786f3-159">新しいファイアウォールルール。 Wi-fi ネットワーク経由でプッシュ通知をサポートする場合。</span><span class="sxs-lookup"><span data-stu-id="786f3-159">New firewall rule, if you want to support push notifications through your Wi-Fi network.</span></span>

  - <span data-ttu-id="786f3-160">内部サーバー証明書およびリバースプロキシ証明書のサブジェクトの別名 (自動検出用)。</span><span class="sxs-lookup"><span data-stu-id="786f3-160">Subject alternative names on internal server certificates and reverse proxy certificates, for automatic discovery.</span></span>

  - <span data-ttu-id="786f3-161">フロントエンドサーバーのハードウェアロードバランサーの構成変更ソースの類似性。</span><span class="sxs-lookup"><span data-stu-id="786f3-161">Front End Server hardware load balancer configuration changes source affinity.</span></span>

<span data-ttu-id="786f3-162">Mobility Service および自動検出サービスをサポートするためには、トポロジが次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-162">Your topology must meet the following requirements to support the Mobility Service and the Autodiscover Service:</span></span>

  - <span data-ttu-id="786f3-163">フロントエンドプールの内部 web FQDN は、フロントエンドプールの外部 web FQDN とは別のものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-163">The Front End pool internal web FQDN must be distinct from the Front End pool external web FQDN.</span></span>

  - <span data-ttu-id="786f3-164">内部 Web FQDN は、社内ネットワークにのみ解決し、社内ネットワークの内側からのみアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-164">The internal web FQDN must only resolve to and be accessible from inside the corporate network.</span></span>

  - <span data-ttu-id="786f3-165">外部 web FQDN は、インターネットからのみ解決し、インターネットからアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-165">The external web FQDN must only resolve to and be accessible from the Internet.</span></span>

  - <span data-ttu-id="786f3-p111">社内ネットワークの内側にいるユーザーの場合、Mobility Service の URL は、外部 Web FQDN にアドレス指定される必要があります。この要件は Mobility Service 向けであり、この URL にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="786f3-p111">For a user who is inside the corporate network, the Mobility Service URL must be addressed to the external web FQDN. This requirement is for the Mobility Service and applies only to this URL.</span></span>

  - <span data-ttu-id="786f3-168">企業ネットワークの外部にいるユーザーの場合、要求はフロントエンドプールまたはディレクターの外部 web FQDN に送られる必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-168">For a user who is outside the corporate network, the request must go to the external web FQDN of the Front End pool or Director.</span></span>

<span data-ttu-id="786f3-169">自動検出をサポートする場合、SIP ドメインごとに以下の DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-169">If you support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="786f3-170">組織のネットワーク内から接続するモバイルユーザーをサポートするための内部 DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="786f3-170">An internal DNS record to support mobile users who connect from within your organization's network.</span></span>

  - <span data-ttu-id="786f3-171">インターネットから接続するモバイルユーザーをサポートするための外部 (パブリック) DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="786f3-171">An external, or public, DNS record to support mobile users who connect from the Internet.</span></span>

<span data-ttu-id="786f3-172">内部の自動検出 URL は、ネットワークの外部からアドレス指定できません。</span><span class="sxs-lookup"><span data-stu-id="786f3-172">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="786f3-173">外部自動検出 URL は、ネットワーク内からアドレス指定できません。</span><span class="sxs-lookup"><span data-stu-id="786f3-173">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="786f3-174">ただし、外部 URL に対してこの要件を満たしていない場合は、常に内部 URL が最初に試行されるので、モバイルクライアントの機能に影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="786f3-174">However, if you cannot meet this requirement for the external URL, mobile client functionally will probably not be affected, because the internal URL is always tried first.</span></span>

<span data-ttu-id="786f3-175">DNS レコードは、CNAME レコードまたは A (IPv6、AAAA の場合は host) レコードのいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="786f3-175">The DNS records can be either CNAME records or A (host, if IPv6, AAAA) records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="786f3-176">モバイル デバイスのクライアントでは、異なるドメインからの複数の SSL (Secure Sockets Layer) 証明書がサポートされません。</span><span class="sxs-lookup"><span data-stu-id="786f3-176">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="786f3-177">つまり、HTTPS では、異なるドメインへの CNAME のリダイレクトがサポートされません。</span><span class="sxs-lookup"><span data-stu-id="786f3-177">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="786f3-178">たとえば、director.contoso.net のアドレスにリダイレクトされる lyncdiscover.contoso.com の DNS CNAME レコードは、HTTPS ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="786f3-178">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="786f3-179">このようなトポロジでは、CNAME のリダイレクトが HTTP で解決されるように、モバイル デバイスのクライアントは、最初の要求に対して HTTP を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-179">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="786f3-180">その後、以降の要求については HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="786f3-180">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="786f3-181">このシナリオをサポートするには、ポート 80 (HTTP) の Web 公開ルールを使用して、リバース プロキシを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-181">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="786f3-182">詳細については、「 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 でモビリティのリバースプロキシを構成</A>する」の「ポート80の web 公開ルールを作成するには」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="786f3-182">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="786f3-183">HTTPS では、同じドメインへの CNAME のリダイレクトはサポートされます。</span><span class="sxs-lookup"><span data-stu-id="786f3-183">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="786f3-184">この例では、宛先ドメインの証明書が元のドメインを対象としています。</span><span class="sxs-lookup"><span data-stu-id="786f3-184">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<span data-ttu-id="786f3-185">シナリオに必要な DNS レコードの詳細については、「 [dns の概要-Lync Server 2013 での自動検出](lync-server-2013-dns-summary-autodiscover.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="786f3-185">For details about the DNS records required for your scenario, see [DNS summary - Autodiscover in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="port-and-firewall-requirements"></a><span data-ttu-id="786f3-186">ポートとファイアウォールの要件</span><span class="sxs-lookup"><span data-stu-id="786f3-186">Port and Firewall Requirements</span></span>

<span data-ttu-id="786f3-187">また、プッシュ通知をサポートし、Apple モバイル デバイスで Wi-Fi ネットワーク経由のプッシュ通知を受信する場合、社内の Wi-Fi ネットワークのポート 5223 も開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-187">If you support push notifications and want Apple mobile devices to receive push notifications over your Wi-Fi network, you also need to open port 5223 on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="786f3-188">ポート 5223 は、送信 TCP ポートであり、Apple Push Notification Service (APNS) で使用されます。</span><span class="sxs-lookup"><span data-stu-id="786f3-188">Port 5223 is an outbound TCP port used by the Apple Push Notification Service (APNS).</span></span> <span data-ttu-id="786f3-189">モバイルデバイスが接続を開始します。</span><span class="sxs-lookup"><span data-stu-id="786f3-189">The mobile device initiates the connection.</span></span> <span data-ttu-id="786f3-190">詳細について[http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629)は、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="786f3-190">For details, see [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) .</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="786f3-191">Lync 2013 Mobile クライアントを使用している Apple デバイスでは、プッシュ通知は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="786f3-191">An Apple device using the Lync 2013 Mobile client does not require push notifications.</span></span>



</div>

<span data-ttu-id="786f3-192">ユーザーが存続可能ブランチアプライアンス (SBA) に所属している場合は、次のポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="786f3-192">Note that if a user is homed on a Survivable Branch Appliance (SBA) then the following ports are required:</span></span>

  - <span data-ttu-id="786f3-193">Ucの Ipexternallisteningport にはポート5088が必要です</span><span class="sxs-lookup"><span data-stu-id="786f3-193">UcwaSipExternalListeningPort requires port 5088</span></span>

  - <span data-ttu-id="786f3-194">Ucは、ポート5089を必要とします。</span><span class="sxs-lookup"><span data-stu-id="786f3-194">UcwaSipPrimaryListeningPort requires port 5089</span></span>

<span data-ttu-id="786f3-195">自動検出のポートとプロトコルの要件の詳細とガイダンスについては、「 [port summary-Lync Server 2013 での自動検出](lync-server-2013-port-summary-autodiscover.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="786f3-195">For additional details and guidance on port and protocol requirements for Autodiscover, see [Port summary - Autodiscover in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="certificate-requirements"></a><span data-ttu-id="786f3-196">証明書の要件</span><span class="sxs-lookup"><span data-stu-id="786f3-196">Certificate Requirements</span></span>

<span data-ttu-id="786f3-197">Lync モバイル クライアントに対して自動検出をサポートする場合、証明書のサブジェクトの別名リストを変更し、モバイル クライアントからのセキュリティで保護された接続をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-197">If you support automatic discovery for Lync mobile clients, you need to modify the subject alternative name lists on certificates to support secure connections from the mobile clients.</span></span> <span data-ttu-id="786f3-198">自動検出サービスを実行するフロントエンドサーバーとディレクターごとに、新しい証明書を要求および割り当て、このセクションで説明するサブジェクトの別名エントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-198">You need to request and assign new certificates, adding the subject alternative name entries described in this section, for each Front End Server and Director that runs the Autodiscover Service.</span></span> <span data-ttu-id="786f3-199">この方法として、リバース プロキシ用の証明書のサブジェクトの別名リストも変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="786f3-199">The recommended approach is to also modify the subject alternative names lists on certificates for your reverse proxies.</span></span> <span data-ttu-id="786f3-200">組織内のすべての SIP ドメインに対してサブジェクトの別名エントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-200">You need to add subject alternative name entries for every SIP domain in your organization.</span></span>

<span data-ttu-id="786f3-201">通常、内部の証明機関を使用した証明書の再発行は簡単なプロセスですが、サブジェクトの複数の別名エントリを、リバース プロキシで使用されるパブリック証明書に追加するには、高い費用がかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-201">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="786f3-202">多くの SIP ドメインがある場合 (サブジェクトの別名を追加する処理が非常に高価になります)、初期の自動検出サービス要求を、HTTPS を使用してポート 443 (既定の構成) で送信する代わりに、HTTP を使用してポート 80 で送信するようにリバース プロキシを構成できます。</span><span class="sxs-lookup"><span data-stu-id="786f3-202">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to make the initial Autodiscover Service request over port 80 using HTTP, instead of port 443 using HTTPS (the default configuration).</span></span> <span data-ttu-id="786f3-203">その後、要求はディレクターまたはフロントエンドプールのポート8080にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="786f3-203">The request is then redirected to port 8080 on the Director or Front End pool.</span></span> <span data-ttu-id="786f3-204">初期の自動検出サービス要求をポート 80 で発行すると、要求で HTTPS ではなく HTTP が使用されるため、リバース プロキシの証明書を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="786f3-204">When you publish the initial Autodiscover Service request on port 80, you do not need to change certificates for the reverse proxy, because the request uses HTTP rather than HTTPS.</span></span> <span data-ttu-id="786f3-205">この方法はサポートされていますが、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="786f3-205">This approach is supported, but we do not recommend it.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="786f3-206">インターネット インフォメーション サービス (IIS) の要件</span><span class="sxs-lookup"><span data-stu-id="786f3-206">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="786f3-207">モバイル用に IIS 7.5、IIS 8.0、または IIS 8.5 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="786f3-207">We recommend that you use IIS 7.5, IIS 8.0, or IIS 8.5 for mobility.</span></span> <span data-ttu-id="786f3-208">Mobility Service installer は、パフォーマンスを向上させるために ASP.NET にフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="786f3-208">The Mobility Service installer sets flags in ASP.NET to improve performance.</span></span> <span data-ttu-id="786f3-209">IIS 7.5 が既定でインストールされる Windows Server 2008 R2、IIS 8.0 は windows Server 2012 にインストールされ、IIS 8.5 は Windows Server 2012 R2 にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="786f3-209">IIS 7.5 is installed by default on Windows Server 2008 R2, IIS 8.0 is installed on Windows Server 2012, and IIS 8.5 is installed on Windows Server 2012 R2.</span></span> <span data-ttu-id="786f3-210">Mobility Service インストーラーは、ASP.NET の設定を自動的に変更します。</span><span class="sxs-lookup"><span data-stu-id="786f3-210">The Mobility Service installer automatically changes the ASP.NET settings.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="786f3-211">ハードウェア ロード バランサーの要件</span><span class="sxs-lookup"><span data-stu-id="786f3-211">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="786f3-212">フロントエンドプールをサポートするロードバランサー機器で、Web サービストラフィック用の外部 Web サービス仮想 Ip (Vip) をソース用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-212">On the hardware load balancer that is supporting the Front End pool, the external Web Services virtual IPs (VIPs) for Web Services traffic must be configured for source.</span></span> <span data-ttu-id="786f3-213">ソースアフィニティを使用すると、1つのクライアントからの複数の接続が、セッション状態を維持するために1台のサーバーに送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="786f3-213">Source affinity helps to ensure that multiple connections from a single client are sent to one server to maintain session state.</span></span> <span data-ttu-id="786f3-214">アフィニティ要件の詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="786f3-214">For details about affinity requirements, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<span data-ttu-id="786f3-215">内部 Wi-fi ネットワーク上でのみ Lync mobile クライアントをサポートする場合は、「外部 Web サービスの Vip」に記載されているように、ソースに対して内部 Web サービス VIP を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-215">If you plan to support Lync mobile clients only over your internal Wi-Fi network, you should configure the internal Web Services VIPS for source as described for external Web Services VIPs.</span></span> <span data-ttu-id="786f3-216">このような状況では、ハードウェア\_ロードバランサーの内部 Web サービス vip に対して、source addr (または TCP) アフィニティを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-216">In this situation, you should use source\_addr (or TCP) affinity for the internal Web Services VIPs on the hardware load balancer.</span></span> <span data-ttu-id="786f3-217">詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="786f3-217">For details, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="786f3-218">リバース プロキシの要件</span><span class="sxs-lookup"><span data-stu-id="786f3-218">Reverse Proxy Requirements</span></span>

<span data-ttu-id="786f3-219">Lync mobile クライアントの自動検出をサポートしている場合は、現在の公開ルールを次のように更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786f3-219">If you support automatic discovery for Lync mobile clients, you need to update the current publishing rule as follows:</span></span>

  - <span data-ttu-id="786f3-220">リバースプロキシ証明書のサブジェクトの別名の一覧を更新し、最初の自動検出サービス要求に HTTPS を使用する場合は、lyncdiscover の web 公開ルールを更新する必要があります。\<microsoft.rtc.management.xds.sipdomain\>。</span><span class="sxs-lookup"><span data-stu-id="786f3-220">If you decide to update the subject alternative names lists on the reverse proxy certificates and use HTTPS for the initial Autodiscover Service request, you must update the web publishing rule for lyncdiscover.\<sipdomain\>.</span></span> <span data-ttu-id="786f3-221">通常、これはフロントエンドプールの外部 Web サービス URL の公開ルールと組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="786f3-221">Typically, this is combined with the publishing rule for the external Web Services URL on the Front End pool.</span></span>

  - <span data-ttu-id="786f3-222">リバースプロキシ証明書のサブジェクトの別名リストを更新する必要がないように、最初の自動検出サービス要求に HTTP を使用する場合は、ポート HTTP/TCP 80 用の新しい web 公開ルールを作成する必要があります (まだ存在しない場合)。</span><span class="sxs-lookup"><span data-stu-id="786f3-222">If you decide to use HTTP for the initial Autodiscover Service request so that you do not need to update the subject alternative names list on the reverse proxy certificates, you must create a new web publishing rule for port HTTP/TCP 80, if one does not already exist.</span></span> <span data-ttu-id="786f3-223">HTTP/TCP 80 のルールが既に存在する場合は、そのルールを更新して lyncdiscover を含めることができます。\<microsoft.rtc.management.xds.sipdomain\>エントリ。</span><span class="sxs-lookup"><span data-stu-id="786f3-223">If a rule for HTTP/TCP 80 does already exist, you can update that rule to include the lyncdiscover.\<sipdomain\> entry.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

