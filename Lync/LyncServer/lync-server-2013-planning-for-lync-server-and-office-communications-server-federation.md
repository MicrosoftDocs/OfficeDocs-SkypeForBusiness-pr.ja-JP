---
title: Lync Server と Office Communications Server のフェデレーションの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 801237e4390cd81ac634a928f4963be1c930d01e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522024"
---
# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="c89c8-102">Lync Server 2013 および Office Communications Server のフェデレーションの計画</span><span class="sxs-lookup"><span data-stu-id="c89c8-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c89c8-103">_**トピックの最終更新日:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="c89c8-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="c89c8-104">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の間のフェデレーションは、ピアツーピア通信と複数パーティ通信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c89c8-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="c89c8-105">ピアツーピアの会話をマルチパーティの会話にエスカレートでき、臨時の会議を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c89c8-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="c89c8-106">会議 – Web 会議または音声ビデオ会議をスケジュールし、組織内の連絡先およびフェデレーションしているパートナーの連絡先を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c89c8-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="c89c8-107">フェデレーションは、Microsoft Office Live Communications Server 2005 で初めて登場し、サポートされている1種類のフェデレーションである直接フェデレーションをサポートしていました。</span><span class="sxs-lookup"><span data-stu-id="c89c8-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="c89c8-108">直接フェデレーションでは、フェデレーションパートナーのセッション開始プロトコル (SIP) ドメインと、パートナーのエッジサーバーの完全修飾ドメイン名 (FQDN) を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="c89c8-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="c89c8-109">Live Communications Server 2005 SP1 では、追加のフェデレーションの種類が導入されており、すべての必要なドメインネームシステム (DNS) SRV レコードがフェデレーションパートナーによって公開され、そのエッジサーバーを特定します。</span><span class="sxs-lookup"><span data-stu-id="c89c8-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="c89c8-110">そのリリースで使用されていた用語は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c89c8-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="c89c8-111">*拡張フェデレーションを開く*: 任意の SIP ドメイン名を受け入れ、DNS SRV を使用してパートナーエッジサーバーを特定する</span><span class="sxs-lookup"><span data-stu-id="c89c8-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="c89c8-112">*拡張フェデレーション*: パートナーの SIP ドメイン名を組織のフェデレーションパートナーとして構成し、DNS SRV を使用してパートナーエッジサーバーを検索する</span><span class="sxs-lookup"><span data-stu-id="c89c8-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="c89c8-113">*直接フェデレーション*: パートナーの SIP ドメイン名と、パートナーのエッジサーバーに対する FQDN を構成する</span><span class="sxs-lookup"><span data-stu-id="c89c8-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="c89c8-114">*サーバーの許可一覧*: 任意のドメインを受け入れ、DNS SRV を使用してホスティングプロバイダーまたはパブリックインスタントメッセージング (IM) 接続プロバイダーのエッジサーバーを検索する</span><span class="sxs-lookup"><span data-stu-id="c89c8-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="c89c8-115">Microsoft Office Communications Server 2007 は、フェデレーションの種類に対して更新された命名を導入し、各フェデレーションの種類が実際に達成したことをより明確にしました。</span><span class="sxs-lookup"><span data-stu-id="c89c8-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="c89c8-116">オープン拡張フェデレーションは、*検出済みのパートナー ドメイン*に変更</span><span class="sxs-lookup"><span data-stu-id="c89c8-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="c89c8-117">拡張フェデレーションは、*許可されたパートナー ドメイン*に変更</span><span class="sxs-lookup"><span data-stu-id="c89c8-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="c89c8-118">直接フェデレーションは、*許可されたパートナー サーバー*に変更</span><span class="sxs-lookup"><span data-stu-id="c89c8-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="c89c8-119">サーバー許可リストは、*ホスティング プロバイダー*および*パブリック IM プロバイダー*に変更</span><span class="sxs-lookup"><span data-stu-id="c89c8-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="c89c8-120">Microsoft Lync Server 2010 では、Microsoft Lync Online 2010 および Microsoft Office 365 に従ってホスティングプロバイダーの定義が狭められ、また、許可されたパートナードメインのフェデレーションの種類によって定義されたものと同じ許可リストに従うようになりました。</span><span class="sxs-lookup"><span data-stu-id="c89c8-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="c89c8-121">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の間のフェデレーションを有効にするには、エッジサーバーとリバースプロキシを使用して、定義したルールおよび許可されたパートナードメインを適用します。</span><span class="sxs-lookup"><span data-stu-id="c89c8-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="c89c8-122">計画の観点から、他の Lync Server とのフェデレーションでは、Office Communications Server に次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="c89c8-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="c89c8-123">トポロジ ビルダーでフェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c89c8-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="c89c8-124">詳細については、「 [Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングの構成](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)」の展開に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c89c8-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="c89c8-125">フェデレーションされたドメインの検出に対する要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="c89c8-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="c89c8-126">フェデレーションを手動で構成するには、パートナーのエッジサーバーとドメイン名の完全修飾ドメイン名 (FQDN)、または Lync Server コントロールパネル、 **フェデレーションと外部アクセス**、 **SIP フェデレーションドメイン**に入力されたオンラインドメイン名を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c89c8-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="c89c8-127">**新しい**ポリシーを作成するか、既存のポリシーを**編集**して、ドメインを FQDN で許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="c89c8-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="c89c8-128">パートナーがエッジサーバーの IP アドレスを変更した場合、フェデレーションパートナーのエッジサーバーを手動で構成すると、障害が発生しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="c89c8-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="c89c8-129"><STRONG>新しい SIP フェデレーションドメイン</STRONG>の場合は、Microsoft Lync Online および microsoft 365 または Office 365 の<STRONG>ドメイン名 (または FQDN)</STRONG>を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c89c8-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online and Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c89c8-130">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の場合は、<STRONG>アクセスエッジサービス (FQDN)</STRONG>も提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c89c8-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="c89c8-131">パートナーがエッジサーバーを検出できる、検出されたパートナーフェデレーションについては、外部 DNS-sipfederationtls で SRV レコードを作成し \_ ます。 \_tcp.contoso.com –エッジサーバーのポート5061およびホスト (A) レコードを指します。</span><span class="sxs-lookup"><span data-stu-id="c89c8-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="c89c8-132">Windows Phone または Apple iPhone、iPad、またはその他の Apple デバイスで Microsoft Lync Mobile クライアントをサポートしていて、プッシュ通知サービスまたはプッシュ通知サービスを使用している場合は、_sipfederationtls を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c89c8-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="c89c8-133">&lt;&gt;Lync Mobile クライアントを所有している各 sip ドメインの sip ドメイン SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="c89c8-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="c89c8-134">Android および Nokia Symbian Lync Mobile では、プッシュ通知を使用しないでください。この要件の対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="c89c8-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="c89c8-135">フェデレーションされたドメインをサポートするように外部ユーザー アクセス ポリシーを構成します</span><span class="sxs-lookup"><span data-stu-id="c89c8-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="c89c8-136">セッション開始プロトコル (SIP)、Web 会議、音声ビデオ用にファイアウォールのポートを開き、有効にしているフェデレーションまたは連絡先に対応します。</span><span class="sxs-lookup"><span data-stu-id="c89c8-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="c89c8-137">詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c89c8-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="c89c8-138">次の情報は、Microsoft Lync Server 2013 および Lync Server 2010 とのフェデレーションのための証明書、ポート、プロトコル、および DNS の要件を定義するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c89c8-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="c89c8-139">Microsoft Lync Server 2013 エッジサーバーを計画または展開している場合は、証明書、ファイアウォール、およびポート/プロトコルの要件、および DNS の要件を計画するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="c89c8-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="c89c8-140">フェデレーションは既存のエッジサーバーを使用する追加機能なので、計画の要件は通常、エッジサーバーの計画と展開によって満たされます。</span><span class="sxs-lookup"><span data-stu-id="c89c8-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="c89c8-141">次の表を使用して要件が満たされていることを確認し、それに従ってポート/プロトコルおよび DNS を変更します。</span><span class="sxs-lookup"><span data-stu-id="c89c8-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c89c8-142">エッジサーバーのプールがあり、Lync Server 2013 または Lync Server 2010 パートナーとのフェデレーションを行っている場合は、エッジサーバーの内部および外部の側で DNS 負荷分散またはハードウェアロードバランサーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c89c8-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="c89c8-143">Office Communications Server 2007 または Office Communications Server 2007 R2 を使用している場合は、ハードウェア負荷分散によって、エッジサーバーの障害に対するフェールオーバーサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c89c8-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="c89c8-144">Office Communications Server 2007 および Office Communications Server 2007 R2 は、DNS 負荷分散に対応していません。</span><span class="sxs-lookup"><span data-stu-id="c89c8-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="c89c8-145">パートナーエッジサーバーは、プール内で応答する最初のエッジサーバーとの通信を確立します。</span><span class="sxs-lookup"><span data-stu-id="c89c8-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="c89c8-146">エッジサーバーに障害が発生しても、通信が自動的にフェールオーバーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="c89c8-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="c89c8-147">通常、証明書の要件は、選択したエッジサーバーまたはプールのエッジサーバープランの証明書の計画によって満たされます。</span><span class="sxs-lookup"><span data-stu-id="c89c8-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c89c8-148">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c89c8-148">In This Section</span></span>

  - [<span data-ttu-id="c89c8-149">証明書の概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="c89c8-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="c89c8-150">ポートの概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="c89c8-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="c89c8-151">Lync Server 2013 の DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="c89c8-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c89c8-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="c89c8-152">See Also</span></span>


[<span data-ttu-id="c89c8-153">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="c89c8-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="c89c8-154">Lync Server 2013 での外部ユーザーアクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c89c8-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="c89c8-155">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="c89c8-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="c89c8-156">Lync Server 2013 の DNS 要件を決定する</span><span class="sxs-lookup"><span data-stu-id="c89c8-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="c89c8-157">Lync Server 2013 での組織のアクセスエッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="c89c8-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="c89c8-158">Lync Server 2013 での組織の SIP フェデレーションドメインの管理</span><span class="sxs-lookup"><span data-stu-id="c89c8-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="c89c8-159">Lync Server 2013 での組織の SIP フェデレーションプロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="c89c8-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

