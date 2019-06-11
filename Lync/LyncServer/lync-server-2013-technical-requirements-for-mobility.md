---
title: 'Lync Server 2013: モビリティの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac74f7e9e85829e500900e03d4b7cfedf89d1e0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="69d5e-102">Lync Server 2013 でのモビリティの技術要件</span><span class="sxs-lookup"><span data-stu-id="69d5e-102">Technical requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69d5e-103">_**最終更新日:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="69d5e-103">_**Topic Last Modified:** 2014-07-24_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="69d5e-104">モバイルユーザーは、特別な計画が必要なさまざまなモバイルアプリケーションシナリオを経験しています。</span><span class="sxs-lookup"><span data-stu-id="69d5e-104">Mobile users encounter various mobile application scenarios that require special planning.</span></span> <span data-ttu-id="69d5e-105">たとえば、他のユーザーが、3G ネットワーク経由で接続しているときに、職場から離れてモバイルアプリケーションの使用を開始する可能性がある場合は、職場に到着したときに企業の Wi-fi ネットワークに切り替え、建物を離れるときに3G に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-105">For example, someone might start using a mobile application while away from work by connecting through the 3G network, then switch to the corporate Wi-Fi network when arriving at work, and then switch back to 3G when leaving the building.</span></span> <span data-ttu-id="69d5e-106">環境を計画して、このようなネットワークの移行をサポートし、一貫したユーザーエクスペリエンスを保証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-106">You need to plan your environment to support such network transitions and guarantee a consistent user experience.</span></span> <span data-ttu-id="69d5e-107">このセクションでは、モバイルアプリケーションをサポートし、モビリティリソースを自動検出するために必要なインフラストラクチャの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-107">This section describes the infrastructure requirements that you must have in order to support mobile applications and automatic discovery of mobility resources.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69d5e-108">モバイルアプリケーションは、他の Lync Server 2013 サービスに接続することもできますが、すべてのモバイルアプリケーション web 要求を同じ外部 web 完全修飾ドメイン名 (FQDN) に送信するための要件は、Lync Server 2013 Mobility Service にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-108">Although mobile applications can also connect to other Lync Server 2013 services, the requirement to send all mobile application web requests to the same external web fully qualified domain name (FQDN) applies only to the Lync Server 2013 Mobility Service.</span></span> <span data-ttu-id="69d5e-109">その他のモバイルサービスでは、この構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="69d5e-109">Other mobility services do not require this configuration.</span></span>



</div>

<span data-ttu-id="69d5e-110">ハードウェアロードバランサーでの cookie の類似性の要件は大幅に削減されます。 lync 2013 Mobile を使用している場合は、[伝送制御プロトコル (TCP)] のアフィニティに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-110">The requirement for cookie affinity in hardware load balancers is dramatically reduced, and you substitute Transmission Control Protocol (TCP) affinity if you are using the Lync Mobile delivered with Lync Server 2013.</span></span> <span data-ttu-id="69d5e-111">Cookie の類似性は引き続き使用できますが、web サービスでは不要になりました。</span><span class="sxs-lookup"><span data-stu-id="69d5e-111">Cookie affinity can still be used, but the web services no longer require it.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="69d5e-112">すべてのモビリティーサービストラフィックは、発信元ポイントがどこにあるかにかかわらず、リバースプロキシを通過します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-112">All Mobility Service traffic goes through the reverse proxy, regardless of where the origination point is—internal or external.</span></span> <span data-ttu-id="69d5e-113">1つの逆プロキシまたはリバースプロキシのファームの場合、またはリバースプロキシ機能を提供するデバイスの場合、内部トラフィックがインターフェイスを使って egressing、同じインターフェイスですぐに入力を試みると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-113">In the case of a single reverse proxy or a farm of reverse proxies, or a device that is providing the reverse proxy function, an issue can arise when the internal traffic is egressing through an interface and attempting to immediately ingress on the same interface.</span></span> <span data-ttu-id="69d5e-114">これにより、多くの場合、TCP パケットスプーフィングまたはスプーフィングのみと呼ばれるセキュリティルール違反が発生します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-114">This often leads to a Security rule violation known as TCP packet spoofing or just spoofing.</span></span> <span data-ttu-id="69d5e-115"><EM>髪のピン留め</EM>(パケットまたは一連のパケットの出口と瞬時の受信) は、モビリティーが機能するために許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-115"><EM>Hair pinning</EM> (the egress and immediate ingress of a packet or series of packets) must be allowed in order for mobility to function.</span></span> <span data-ttu-id="69d5e-116">この問題を解決する1つの方法は、ファイアウォールから分離された逆プロキシを使用することです (スプーフィング防止ルールは、セキュリティのため、常にファイアウォールで適用する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="69d5e-116">One way to resolve this issue is to use a reverse proxy that is separate from the firewall (the spoofing prevention rule should always be enforced at the firewall, for security purposes).</span></span> <span data-ttu-id="69d5e-117">転送は、ファイアウォールの外部インターフェイスではなく、リバースプロキシの外部インターフェイスで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-117">The hairpin can occur at the external interface of the reverse proxy instead of the firewall external interface.</span></span> <span data-ttu-id="69d5e-118">ファイアウォールでスプーフィングを検出し、リバースプロキシでルールを緩和して、四肢に必要な転送を許可します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-118">You detect the spoofing at the firewall, and relax the rule at the reverse proxy, thereby allowing the hairpin that mobility requires.</span></span><BR><span data-ttu-id="69d5e-119">可能な限り、ドメインネームシステム (DNS) のホストまたは CNAME レコードを使用して、転送の動作 (ファイアウォールではなく) のリバースプロキシを定義します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-119">Use the Domain Name System (DNS) host or CNAME records to define the reverse proxy for the hairpin behavior (not the firewall), if at all possible.</span></span>



</div>

<span data-ttu-id="69d5e-120">Lync Server 2013 は、Lync 2010 Mobile および Lync 2013 モバイルクライアント用のモビリティサービスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="69d5e-120">Lync Server 2013 supports mobility services for Lync 2010 Mobile and Lync 2013 mobile clients.</span></span> <span data-ttu-id="69d5e-121">両方のクライアントは、モバイルのエントリポイントを見つけるために Lync Server 2013 自動検出サービスを使用しますが、どのモバイルサービスを使うかは異なります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-121">Both clients use the Lync Server 2013 Autodiscover Service to find its mobility entry point, but differ on which mobility service they use.</span></span> <span data-ttu-id="69d5e-122">Lync 2010 Mobile では、" *Mcx*" と呼ばれるモバイルサービスが使用されます。これは、lync Server 2010 の累積的な更新プログラム (2011 年11月) で導入されました。</span><span class="sxs-lookup"><span data-stu-id="69d5e-122">Lync 2010 Mobile uses the Mobility Service known as *Mcx*, introduced with the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="69d5e-123">Lync 2013 モバイルクライアントは、モバイルサービスプロバイダーとしてユニファイドコミュニケーション Web API または*Ucwa*を使用します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-123">Lync 2013 mobile clients use the Unified Communications Web API, or *UCWA*, as their mobility service provider.</span></span>

<div>

## <a name="internal-and-external-dns-configuration"></a><span data-ttu-id="69d5e-124">内部と外部の DNS 構成</span><span class="sxs-lookup"><span data-stu-id="69d5e-124">Internal and External DNS Configuration</span></span>

<span data-ttu-id="69d5e-125">モビリティーサービス Mcx (Lync Server 2010: 2011 年11月の累積更新プログラムで導入されました) と UCWA (Lync Server 2013 2013 の累積更新プログラムで導入されました) と、同じ方法で DNS を使用します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-125">The Mobility Services Mcx (introduced with the Cumulative Update for Lync Server 2010: November 2011) and UCWA (introduced in the Cumulative Updates for Lync Server 2013: February 2013) use DNS in the same way.</span></span>

<span data-ttu-id="69d5e-126">自動検出を使う場合、モバイルデバイスは DNS を使ってリソースを探します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-126">When you use Automatic Discovery, mobile devices use DNS to locate resources.</span></span> <span data-ttu-id="69d5e-127">DNS 参照時に、内部 DNS レコード (lyncdiscoverinternal) に関連付けられている FQDN への接続が最初\<に試行されます。内部ドメイン名\>)。</span><span class="sxs-lookup"><span data-stu-id="69d5e-127">During the DNS lookup, a connection is first attempted to the FQDN that is associated with the internal DNS record (lyncdiscoverinternal.\<internal domain name\>).</span></span> <span data-ttu-id="69d5e-128">内部 DNS レコードを使用して接続を確立できない場合は、外部 DNS レコード (lyncdiscover を使用して接続が\<試行されます。sipdomain\>)。</span><span class="sxs-lookup"><span data-stu-id="69d5e-128">If a connection cannot be made by using the internal DNS record, a connection is attempted by using the external DNS record (lyncdiscover.\<sipdomain\>).</span></span> <span data-ttu-id="69d5e-129">ネットワーク内部のモバイルデバイスが内部自動検出サービス URL に接続し、ネットワーク外部のモバイルデバイスが外部自動検出サービス URL に接続します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-129">A mobile device that is internal to the network connects to the internal Autodiscover Service URL, and a mobile device that is external to the network connects to the external Autodiscover Service URL.</span></span> <span data-ttu-id="69d5e-130">外部の自動検出要求は、リバースプロキシを通じて送信されます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-130">External Autodiscover requests go through the reverse proxy.</span></span> <span data-ttu-id="69d5e-131">Lync Server 2013 自動検出サービスは、モビリティサービス (Mcx および UCWA) Url を含む、ユーザーのホームプールのすべての Web サービスの Url を返します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-131">The Lync Server 2013 Autodiscover Service returns all Web Services URLs for the user's home pool, including the Mobility Service (Mcx and UCWA) URLs.</span></span> <span data-ttu-id="69d5e-132">ただし、内部のモビリティーサービス URL と外部モビリティーサービスの URL の両方が、外部 Web サービスの FQDN と関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="69d5e-132">However, both the internal Mobility Service URL and the external Mobility Service URL are associated with the external Web Services FQDN.</span></span> <span data-ttu-id="69d5e-133">そのため、モバイルデバイスがネットワークの内部と外部のどちらであるかに関係なく、デバイスは常にリバースプロキシ経由で外部の Lync Server 2013 モビリティサービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-133">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Lync Server 2013 Mobility Service externally through the reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69d5e-134">展開は、内部および外部使用のために複数の異なる名前空間で構成できることを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="69d5e-134">It is important to understand that your deployment can consist of multiple distinct namespaces for internal and external use.</span></span> <span data-ttu-id="69d5e-135">SIP ドメイン名は、内部展開ドメイン名とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-135">Your SIP domain name may be different than the internal deployment domain name.</span></span> <span data-ttu-id="69d5e-136">たとえば、お客様の SIP ドメインは<STRONG>contoso.com</STRONG>の場合もありますが、内部展開は<STRONG>contoso.net</STRONG>になることがあります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-136">For example, your SIP domain may be <STRONG>contoso.com</STRONG>, while your internal deployment may be <STRONG>contoso.net</STRONG>.</span></span> <span data-ttu-id="69d5e-137">Lync Server にログインしているユーザーは、 <STRONG>john@contoso.com</STRONG>などの SIP ドメイン名を使用します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-137">Users who log in to Lync Server will use the SIP domain name, such as <STRONG>john@contoso.com</STRONG>.</span></span> <span data-ttu-id="69d5e-138">外部 web サービス (Topology Builder で<STRONG>外部 web サービス</STRONG>として定義される) に対応する場合、ドメイン名と SIP ドメイン名は、DNS で定義されているように一貫性が保たれます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-138">When addressing the external web services (defined in Topology Builder as <STRONG>External web services</STRONG>), the domain name and the SIP domain name will be consistent, as defined in DNS.</span></span> <span data-ttu-id="69d5e-139">内部 web サービス (Topology Builder で<STRONG>内部 web サービス</STRONG>として定義されます) に対応する場合、内部 web サービスの既定の名前は、フロントエンドサーバー、フロントエンドプール、ディレクター、またはディレクタープールの FQDN になります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-139">When addressing the internal Web services (defined in Topology Builder as <STRONG>Internal web services</STRONG>), the default name of the internal web services will be the FQDN of the Front End Server, Front End pool, Director, or Director pool.</span></span> <span data-ttu-id="69d5e-140">内部 web サービス名を上書きするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-140">You have the option to override the internal web services name.</span></span> <span data-ttu-id="69d5e-141">内部 web サービスの場合は、SIP ドメイン名ではなく内部ドメイン名を使用し、上書きされた名前を反映する DNS host A (IPv6、AAAA) レコードを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-141">You should use the internal domain name (and not the SIP domain name) for internal web services and define the DNS host A (or, for IPv6, AAAA) record to reflect the overridden name.</span></span> <span data-ttu-id="69d5e-142">たとえば、既定の内部 web サービス FQDN は<STRONG>pool01.contoso.net</STRONG>である場合があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-142">For example, the default internal web services FQDN may be <STRONG>pool01.contoso.net</STRONG>.</span></span> <span data-ttu-id="69d5e-143">上書きされた内部 web サービス FQDN が<STRONG>webpool.contoso.net</STRONG>である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-143">An overridden internal web services FQDN may be <STRONG>webpool.contoso.net</STRONG>.</span></span> <span data-ttu-id="69d5e-144">この方法で web サービスを定義することで、サービスの内部および外部の地域において、それらを使用しているユーザーの局所性ではなく、サービスの内部および外部の地域を確実に確認することができます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-144">Defining the web services in this way helps to ensure that the internal and external locality of the services—and not the locality of the user who is using them—is observed.</span></span><BR><span data-ttu-id="69d5e-145">ただし、web サービスはトポロジビルダーで定義されており、結果の web サービス名、検証する証明書、および定義されている DNS レコードが一貫している限り、その web サービスの名前を上書きすることができます。必要なすべてのドメイン名 (SIP ドメイン名を含む) での内部 web サービス。</span><span class="sxs-lookup"><span data-stu-id="69d5e-145">However, because the web services are defined in Topology Builder and the internal web services name can be overridden, as long as the resulting web services name, the certificate that validates it, and the DNS records that define it, are consistent, you can define the internal web services with any domain name—including the SIP domain name—that you want.</span></span> <span data-ttu-id="69d5e-146">最終的に、IP アドレスに対する名前の解決は DNS ホストレコードと一貫性のある名前空間によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-146">Ultimately, the resolution for the name to the IP address is determined by DNS host records and a consistent namespace.</span></span><BR><span data-ttu-id="69d5e-147">このトピックと例のために、内部ドメイン名を使ってトポロジと DNS 定義を示します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-147">For the purposes of this topic and the examples, the internal domain name is used to illustrate the topology and the DNS definitions.</span></span>



</div>

<span data-ttu-id="69d5e-148">次の図は、内部と外部の DNS 構成を使用している場合のモビリティサービスと自動検出サービスに対するモバイルアプリケーション web 要求のフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="69d5e-148">The following diagram illustrates the flow of mobile application web requests for the Mobility Service and for the Autodiscover Service when using an internal and external DNS configuration.</span></span>

<span data-ttu-id="69d5e-149">**自動検出を使用したモビリティのサービスフロー**</span><span class="sxs-lookup"><span data-stu-id="69d5e-149">**Mobility service flow using AutoDiscover**</span></span>

<span data-ttu-id="69d5e-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span><span class="sxs-lookup"><span data-stu-id="69d5e-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69d5e-151">この図は、一般的な web サービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="69d5e-151">The diagram illustrates generic web services.</span></span> <span data-ttu-id="69d5e-152">Mobility という名前の仮想ディレクトリは、モビリティーサービス Mcx および UCWA を示しています。</span><span class="sxs-lookup"><span data-stu-id="69d5e-152">A virtual directory named Mobility depicts the Mobility services Mcx and/or UCWA.</span></span> <span data-ttu-id="69d5e-153">Lync Server 2013 の累積更新プログラムを適用していない場合: 2013 年2月、内部と外部の Web サービスで仮想ディレクトリ Ucwa が定義されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-153">If you have not applied the Cumulative Updates for Lync Server 2013: February 2013, you may or may not have the virtual directory Ucwa defined on your internal and external Web services.</span></span> <span data-ttu-id="69d5e-154">仮想ディレクトリの自動検出が行われ、仮想ディレクトリの Mcx が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-154">You will have a virtual directory Autodiscover, and you may have a virtual directory Mcx.</span></span><BR><span data-ttu-id="69d5e-155">展開したモビリティサービステクノロジに関係なく、自動検出とサービスの検出は同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-155">Autodiscover and the discovery of services work the same way, regardless of the mobility services technology that you have deployed.</span></span>



</div>

<span data-ttu-id="69d5e-156">企業ネットワーク内外のモバイルユーザーをサポートするには、内部と外部の web Fqdn がいくつかの前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-156">To support mobile users from both inside and outside the corporate network, your internal and external web FQDNs must meet some prerequisites.</span></span> <span data-ttu-id="69d5e-157">さらに、実装することを選んだ機能に応じて、その他の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-157">In addition, you may need to meet other requirements, depending on the features you choose to implement:</span></span>

  - <span data-ttu-id="69d5e-158">自動検出のための新しい DNS、CNAME または (host、IPv6、AAAA) レコード</span><span class="sxs-lookup"><span data-stu-id="69d5e-158">New DNS, CNAME or A (host, if IPv6, AAAA) records, for automatic discovery.</span></span>

  - <span data-ttu-id="69d5e-159">新しいファイアウォール ルール - Wi-Fi ネットワーク経由でプッシュ通知をサポートする場合。</span><span class="sxs-lookup"><span data-stu-id="69d5e-159">New firewall rule, if you want to support push notifications through your Wi-Fi network.</span></span>

  - <span data-ttu-id="69d5e-160">自動検出のために、内部サーバー証明書と逆プロキシ証明書のサブジェクト別の名前。</span><span class="sxs-lookup"><span data-stu-id="69d5e-160">Subject alternative names on internal server certificates and reverse proxy certificates, for automatic discovery.</span></span>

  - <span data-ttu-id="69d5e-161">フロントエンドサーバーのハードウェアロードバランサー構成がソースの類似性を変更します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-161">Front End Server hardware load balancer configuration changes source affinity.</span></span>

<span data-ttu-id="69d5e-162">モビリティサービスと自動検出サービスをサポートするには、トポロジが次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-162">Your topology must meet the following requirements to support the Mobility Service and the Autodiscover Service:</span></span>

  - <span data-ttu-id="69d5e-163">フロントエンドプールの内部 web FQDN は、フロントエンドプールの外部 web FQDN とは別のものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-163">The Front End pool internal web FQDN must be distinct from the Front End pool external web FQDN.</span></span>

  - <span data-ttu-id="69d5e-164">内部 web FQDN は、企業ネットワーク内からのみ解決され、アクセス可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-164">The internal web FQDN must only resolve to and be accessible from inside the corporate network.</span></span>

  - <span data-ttu-id="69d5e-165">外部 web FQDN は、インターネット経由でのみ解決され、アクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-165">The external web FQDN must only resolve to and be accessible from the Internet.</span></span>

  - <span data-ttu-id="69d5e-166">企業ネットワーク内のユーザーの場合は、モビリティサービスの URL が外部 web FQDN に対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-166">For a user who is inside the corporate network, the Mobility Service URL must be addressed to the external web FQDN.</span></span> <span data-ttu-id="69d5e-167">この要件は、モバイルサービス用で、この URL にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-167">This requirement is for the Mobility Service and applies only to this URL.</span></span>

  - <span data-ttu-id="69d5e-168">企業ネットワークの外部にいるユーザーの場合、要求はフロントエンドプールまたはディレクターの外部 web FQDN にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-168">For a user who is outside the corporate network, the request must go to the external web FQDN of the Front End pool or Director.</span></span>

<span data-ttu-id="69d5e-169">自動検出をサポートしている場合は、SIP ドメインごとに次の DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-169">If you support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="69d5e-170">組織のネットワーク内から接続するモバイルユーザーをサポートする内部 DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="69d5e-170">An internal DNS record to support mobile users who connect from within your organization's network.</span></span>

  - <span data-ttu-id="69d5e-171">インターネットから接続するモバイルユーザーをサポートするための、外部またはパブリックの DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="69d5e-171">An external, or public, DNS record to support mobile users who connect from the Internet.</span></span>

<span data-ttu-id="69d5e-172">内部の自動検出 URL は、ネットワークの外部からのアドレス指定を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="69d5e-172">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="69d5e-173">外部の自動検出 URL は、ネットワーク内からアドレス指定できません。</span><span class="sxs-lookup"><span data-stu-id="69d5e-173">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="69d5e-174">ただし、外部 URL に対してこの要件を満たしていない場合は、内部 URL が常に最初に試行されるため、モバイルクライアントの機能が影響を受ける可能性は高くなります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-174">However, if you cannot meet this requirement for the external URL, mobile client functionally will probably not be affected, because the internal URL is always tried first.</span></span>

<span data-ttu-id="69d5e-175">DNS レコードは、CNAME レコードまたは (IPv6、AAAA の場合は host) レコードのいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-175">The DNS records can be either CNAME records or A (host, if IPv6, AAAA) records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69d5e-176">モバイルデバイスクライアントは、異なるドメインからの複数の Secure Sockets Layer (SSL) 証明書をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="69d5e-176">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="69d5e-177">したがって、異なるドメインへの CNAME リダイレクションは HTTPS 経由ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="69d5e-177">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="69d5e-178">たとえば、director.contoso.net のアドレスにリダイレクトされる lyncdiscover.contoso.com の DNS CNAME レコードは HTTPS ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="69d5e-178">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="69d5e-179">このようなトポロジでは、モバイルデバイスクライアントは、最初の要求に対して HTTP を使う必要があるため、CNAME リダイレクションが HTTP で解決されます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-179">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="69d5e-180">それ以降の要求では HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-180">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="69d5e-181">このシナリオをサポートするには、ポート 80 (HTTP) 用の web 公開ルールを使用してリバースプロキシを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-181">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="69d5e-182">詳細については、「 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 でモビリティのリバースプロキシを構成</A>する」の「ポート80用の web 公開ルールを作成するには」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69d5e-182">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="69d5e-183">同じドメインへの CNAME リダイレクションは HTTPS 経由でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="69d5e-183">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="69d5e-184">この場合、宛先ドメインの証明書は元のドメインを対象としています。</span><span class="sxs-lookup"><span data-stu-id="69d5e-184">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<span data-ttu-id="69d5e-185">シナリオに必要な DNS レコードの詳細については、「 [dns の概要-Lync Server 2013 での自動検出](lync-server-2013-dns-summary-autodiscover.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69d5e-185">For details about the DNS records required for your scenario, see [DNS summary - Autodiscover in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="port-and-firewall-requirements"></a><span data-ttu-id="69d5e-186">ポートとファイアウォールの要件</span><span class="sxs-lookup"><span data-stu-id="69d5e-186">Port and Firewall Requirements</span></span>

<span data-ttu-id="69d5e-187">プッシュ通知をサポートしていて、Apple モバイルデバイスで Wi-fi ネットワーク経由でプッシュ通知を受信できるようにする場合は、エンタープライズ Wi-fi ネットワークでポート5223を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-187">If you support push notifications and want Apple mobile devices to receive push notifications over your Wi-Fi network, you also need to open port 5223 on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="69d5e-188">ポート5223は、Apple Push Notification Service (APNS) で使用される送信 TCP ポートです。</span><span class="sxs-lookup"><span data-stu-id="69d5e-188">Port 5223 is an outbound TCP port used by the Apple Push Notification Service (APNS).</span></span> <span data-ttu-id="69d5e-189">モバイルデバイスから接続が開始されます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-189">The mobile device initiates the connection.</span></span> <span data-ttu-id="69d5e-190">詳細について[http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629)は、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69d5e-190">For details, see [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) .</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="69d5e-191">Lync 2013 モバイルクライアントを使っている Apple デバイスでは、プッシュ通知は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="69d5e-191">An Apple device using the Lync 2013 Mobile client does not require push notifications.</span></span>



</div>

<span data-ttu-id="69d5e-192">ユーザーが Survivable Branch Appliance (SBA) をホームにしている場合は、次のポートが必要になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="69d5e-192">Note that if a user is homed on a Survivable Branch Appliance (SBA) then the following ports are required:</span></span>

  - <span data-ttu-id="69d5e-193">Ucの Ipexternallisteningport には、ポート5088が必要です</span><span class="sxs-lookup"><span data-stu-id="69d5e-193">UcwaSipExternalListeningPort requires port 5088</span></span>

  - <span data-ttu-id="69d5e-194">Ucの Ipprimarylisteningport にはポート5089が必要です</span><span class="sxs-lookup"><span data-stu-id="69d5e-194">UcwaSipPrimaryListeningPort requires port 5089</span></span>

<span data-ttu-id="69d5e-195">自動検出のポートとプロトコルの要件の詳細とガイダンスについては、「[ポートの概要-Lync Server 2013 での自動検出](lync-server-2013-port-summary-autodiscover.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69d5e-195">For additional details and guidance on port and protocol requirements for Autodiscover, see [Port summary - Autodiscover in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="certificate-requirements"></a><span data-ttu-id="69d5e-196">証明書の要件</span><span class="sxs-lookup"><span data-stu-id="69d5e-196">Certificate Requirements</span></span>

<span data-ttu-id="69d5e-197">Lync モバイルクライアントの自動検出をサポートしている場合は、モバイルクライアントからのセキュリティで保護された接続をサポートするために、証明書のサブジェクトの代替名の一覧を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-197">If you support automatic discovery for Lync mobile clients, you need to modify the subject alternative name lists on certificates to support secure connections from the mobile clients.</span></span> <span data-ttu-id="69d5e-198">自動検出サービスを実行する各フロントエンドサーバーとディレクターについて、このセクションで説明されているサブジェクト代替名のエントリを追加して、新しい証明書を要求して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-198">You need to request and assign new certificates, adding the subject alternative name entries described in this section, for each Front End Server and Director that runs the Autodiscover Service.</span></span> <span data-ttu-id="69d5e-199">推奨される方法は、リバースプロキシの証明書のサブジェクト代替名の一覧も変更することです。</span><span class="sxs-lookup"><span data-stu-id="69d5e-199">The recommended approach is to also modify the subject alternative names lists on certificates for your reverse proxies.</span></span> <span data-ttu-id="69d5e-200">組織内のすべての SIP ドメインに対してサブジェクト代替名のエントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-200">You need to add subject alternative name entries for every SIP domain in your organization.</span></span>

<span data-ttu-id="69d5e-201">内部証明機関を使った証明書の再発行は、通常は単純なプロセスですが、複数のサブジェクト代替名エントリをリバースプロキシによって使用されるパブリック証明書に追加するのはコストがかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-201">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="69d5e-202">多数の SIP ドメインがあり、サブジェクトの代替名を追加した場合は、HTTPS (既定の構成) を使ったポート443ではなく、HTTP を使用して、ポート80で最初の自動検出サービス要求を行うようにリバースプロキシを構成できます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-202">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to make the initial Autodiscover Service request over port 80 using HTTP, instead of port 443 using HTTPS (the default configuration).</span></span> <span data-ttu-id="69d5e-203">要求は、ディレクターまたはフロントエンドプールの [ポート 8080] にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-203">The request is then redirected to port 8080 on the Director or Front End pool.</span></span> <span data-ttu-id="69d5e-204">ポート80で最初の自動検出サービス要求を発行する場合、要求では HTTPS ではなく HTTP が使用されるため、リバースプロキシの証明書を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="69d5e-204">When you publish the initial Autodiscover Service request on port 80, you do not need to change certificates for the reverse proxy, because the request uses HTTP rather than HTTPS.</span></span> <span data-ttu-id="69d5e-205">この方法はサポートされていますが、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="69d5e-205">This approach is supported, but we do not recommend it.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="69d5e-206">インターネットインフォメーションサービス (IIS) の要件</span><span class="sxs-lookup"><span data-stu-id="69d5e-206">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="69d5e-207">モバイルでは、IIS 7.5、IIS 8.0、または IIS 8.5 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69d5e-207">We recommend that you use IIS 7.5, IIS 8.0, or IIS 8.5 for mobility.</span></span> <span data-ttu-id="69d5e-208">Mobility Service installer は、パフォーマンスを向上させるために、ASP.NET にフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="69d5e-208">The Mobility Service installer sets flags in ASP.NET to improve performance.</span></span> <span data-ttu-id="69d5e-209">IIS 7.5 は、Windows Server 2008 R2 の既定でインストールされます。 windows Server 2012 には IIS 8.0 がインストールされており、IIS 8.5 は Windows Server 2012 R2 にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="69d5e-209">IIS 7.5 is installed by default on Windows Server 2008 R2, IIS 8.0 is installed on Windows Server 2012, and IIS 8.5 is installed on Windows Server 2012 R2.</span></span> <span data-ttu-id="69d5e-210">モビリティサービスのインストーラーによって、ASP.NET の設定が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-210">The Mobility Service installer automatically changes the ASP.NET settings.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="69d5e-211">ロード バランサー機器の要件</span><span class="sxs-lookup"><span data-stu-id="69d5e-211">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="69d5e-212">フロントエンドプールをサポートしているハードウェアロードバランサーでは、Web サービストラフィックの外部 Web サービス仮想 Ip (Vip) をソース用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-212">On the hardware load balancer that is supporting the Front End pool, the external Web Services virtual IPs (VIPs) for Web Services traffic must be configured for source.</span></span> <span data-ttu-id="69d5e-213">ソースのアフィニティは、1つのクライアントからの複数の接続を1つのサーバーに送信してセッション状態を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-213">Source affinity helps to ensure that multiple connections from a single client are sent to one server to maintain session state.</span></span> <span data-ttu-id="69d5e-214">アフィニティ要件の詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69d5e-214">For details about affinity requirements, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<span data-ttu-id="69d5e-215">内部の Wi-fi ネットワーク経由でのみ Lync モバイルクライアントをサポートする予定の場合は、「外部 Web サービス Vip の説明に従って、ソース用の内部 Web サービスの VIP を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69d5e-215">If you plan to support Lync mobile clients only over your internal Wi-Fi network, you should configure the internal Web Services VIPS for source as described for external Web Services VIPs.</span></span> <span data-ttu-id="69d5e-216">この場合は、ハードウェアロードバランサー上\_の内部 Web サービス vip に対して、source addr (または TCP) アフィニティを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-216">In this situation, you should use source\_addr (or TCP) affinity for the internal Web Services VIPs on the hardware load balancer.</span></span> <span data-ttu-id="69d5e-217">詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69d5e-217">For details, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="69d5e-218">プロキシのリバース要件</span><span class="sxs-lookup"><span data-stu-id="69d5e-218">Reverse Proxy Requirements</span></span>

<span data-ttu-id="69d5e-219">Lync モバイルクライアントの自動検出をサポートしている場合は、次のように現在の公開ルールを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d5e-219">If you support automatic discovery for Lync mobile clients, you need to update the current publishing rule as follows:</span></span>

  - <span data-ttu-id="69d5e-220">リバースプロキシ証明書のサブジェクト代替名の一覧を更新して、最初の自動検出サービス要求に HTTPS を使用する場合は、lyncdiscover の web 公開ルールを更新する必要があります。\<sipdomain\>。</span><span class="sxs-lookup"><span data-stu-id="69d5e-220">If you decide to update the subject alternative names lists on the reverse proxy certificates and use HTTPS for the initial Autodiscover Service request, you must update the web publishing rule for lyncdiscover.\<sipdomain\>.</span></span> <span data-ttu-id="69d5e-221">通常、これは、フロントエンドプールの外部 Web サービス URL の公開ルールと組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="69d5e-221">Typically, this is combined with the publishing rule for the external Web Services URL on the Front End pool.</span></span>

  - <span data-ttu-id="69d5e-222">最初の自動検出サービス要求に対して HTTP を使用して、リバースプロキシ証明書のサブジェクト代替名の一覧を更新する必要がない場合は、ポート HTTP/TCP 80 に新しい web 公開ルールを作成する必要があります (まだ存在していない場合)。</span><span class="sxs-lookup"><span data-stu-id="69d5e-222">If you decide to use HTTP for the initial Autodiscover Service request so that you do not need to update the subject alternative names list on the reverse proxy certificates, you must create a new web publishing rule for port HTTP/TCP 80, if one does not already exist.</span></span> <span data-ttu-id="69d5e-223">HTTP/TCP 80 のルールが既に存在する場合は、そのルールを更新して、lyncdiscover を含めることができます。\<sipdomain\>エントリ。</span><span class="sxs-lookup"><span data-stu-id="69d5e-223">If a rule for HTTP/TCP 80 does already exist, you can update that rule to include the lyncdiscover.\<sipdomain\> entry.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

