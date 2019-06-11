---
title: Lync Server と Office Communications Server フェデレーションの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c683092b61d278d380ad68cef86795d496498fbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="88e95-102">Lync Server 2013 と Office Communications Server フェデレーションの計画</span><span class="sxs-lookup"><span data-stu-id="88e95-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88e95-103">_**最終更新日:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="88e95-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="88e95-104">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server 間のフェデレーションは、ピアツーピア通信とマルチパーティ通信をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="88e95-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="88e95-105">ピアツーピアの会話は、複数の相手との会話にエスカレーションして、臨時の会議を可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="88e95-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="88e95-106">会議– Web 会議や音声/ビジュアル会議–組織内の連絡先、およびフェデレーションするパートナーの連絡先を含めるようにスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="88e95-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="88e95-107">フェデレーションは、Microsoft Office Live Communications Server 2005 で初めて表示され、サポートされているフェデレーションの1つになります。</span><span class="sxs-lookup"><span data-stu-id="88e95-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="88e95-108">直接フェデレーションでは、フェデレーションパートナーのセッション開始プロトコル (SIP) ドメインとパートナーのエッジサーバーの完全修飾ドメイン名 (FQDN) を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e95-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="88e95-109">SP1 での Live Communications Server 2005 には、フェデレーションパートナーがエッジサーバーを検索するために必要なすべてのフェデレーションの種類 (DNS) SRV レコードが導入されています。</span><span class="sxs-lookup"><span data-stu-id="88e95-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="88e95-110">このリリースの用語は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="88e95-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="88e95-111">*拡張フェデレーションを開く*: すべての SIP ドメイン名を受け入れ、DNS SRV を使ってパートナーエッジサーバーを検索する</span><span class="sxs-lookup"><span data-stu-id="88e95-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="88e95-112">*拡張フェデレーション*: パートナーの SIP ドメイン名を組織のフェデレーションパートナーとして構成し、DNS SRV を使ってパートナーエッジサーバーを検索します。</span><span class="sxs-lookup"><span data-stu-id="88e95-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="88e95-113">*直接フェデレーション*: パートナーの SIP ドメイン名と、パートナーのエッジサーバーに対して FQDN を構成する</span><span class="sxs-lookup"><span data-stu-id="88e95-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="88e95-114">*サーバーの許可リスト*: 任意のドメインを承諾し、DNS SRV を使って、ホスティングプロバイダーまたはパブリックインスタントメッセージング (IM) 接続プロバイダーのエッジサーバーを検索します。</span><span class="sxs-lookup"><span data-stu-id="88e95-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="88e95-115">Microsoft Office Communications Server 2007 では、フェデレーションの種類の名前が更新され、各フェデレーションの種類が実際にどのように対応しているかがより明確になりました。</span><span class="sxs-lookup"><span data-stu-id="88e95-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="88e95-116">オープン拡張フェデレーションが検出された*パートナードメイン*として認識される</span><span class="sxs-lookup"><span data-stu-id="88e95-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="88e95-117">拡張フェデレーションが*許可パートナードメイン*として認識される</span><span class="sxs-lookup"><span data-stu-id="88e95-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="88e95-118">直接フェデレーションが*許可パートナーサーバー*と呼ばれました</span><span class="sxs-lookup"><span data-stu-id="88e95-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="88e95-119">サーバーの許可リストは、*ホスティングプロバイダー*と*パブリック IM プロバイダー*と呼ばれます</span><span class="sxs-lookup"><span data-stu-id="88e95-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="88e95-120">Microsoft Lync Server 2010 は、Microsoft Lync Online 2010 と Microsoft Office 365 に準拠して、ホスティングプロバイダーの幅の狭い定義を導入しました。また、許可パートナードメインフェデレーションタイプで定義されたのと同じ許可一覧も適用されます。</span><span class="sxs-lookup"><span data-stu-id="88e95-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="88e95-121">Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server の間のフェデレーションを有効にすると、エッジサーバーとリバースプロキシを使って、定義したルールと許可されたパートナードメインを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="88e95-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="88e95-122">計画の観点から、他の Lync Server とのフェデレーションを行うには、Office Communications Server で次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e95-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="88e95-123">トポロジビルダーでフェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="88e95-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="88e95-124">詳細については、「 [Lync Server 2013 で SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングを構成する展開に](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e95-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="88e95-125">フェデレーションドメイン探索の要件を決定する:</span><span class="sxs-lookup"><span data-stu-id="88e95-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="88e95-126">フェデレーションを手動で構成するには、パートナーのエッジサーバーとドメイン名の完全修飾ドメイン名 (FQDN)、および Lync Server コントロールパネル、**フェデレーション、外部アクセス**、SIP に入力されたオンラインドメイン名が必要です。 **フェデレーションドメイン**。</span><span class="sxs-lookup"><span data-stu-id="88e95-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="88e95-127">ドメインを FQDN で許可またはブロックするには、**新しい**ポリシーを作成するか、既存のポリシーを**編集**します。</span><span class="sxs-lookup"><span data-stu-id="88e95-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="88e95-128">フェデレーションパートナーのエッジサーバーを手動で構成すると、パートナーがエッジサーバーの IP アドレスを変更した場合にエラーが発生しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="88e95-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="88e95-129"><STRONG>新しい SIP フェデレーションドメイン</STRONG>の場合は、Microsoft Lync Online、microsoft Office 365 の<STRONG>ドメイン名 (または FQDN)</STRONG>を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e95-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="88e95-130">Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server の場合は、<STRONG>アクセスエッジサービス (FQDN)</STRONG>も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e95-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="88e95-131">パートナーがエッジサーバーを検出できる検出されたパートナーフェデレーションについては、外部 DNS- \_SIPFEDERATIONTLS で SRV レコードを作成します。\_Tcp.contoso.com –エッジサーバーのポート5061およびホスト (A) レコードを指します。</span><span class="sxs-lookup"><span data-stu-id="88e95-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="88e95-132">Windows Phone または Apple iPhone、iPad、またはその他の Apple デバイスで Microsoft Lync モバイルクライアントをサポートしており、プッシュ通知サービスまたはプッシュ通知サービスを使っている場合は、_sipfederationtls を計画する必要があります。 _tcp</span><span class="sxs-lookup"><span data-stu-id="88e95-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="88e95-133">&lt;Lync モバイル&gt;クライアントを使用している sip ドメインごとに sip ドメイン SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="88e95-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="88e95-134">Android および Nokia Symbian Lync Mobile では、プッシュ通知は使用されず、この要件の対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="88e95-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="88e95-135">フェデレーションドメインをサポートするように外部ユーザーアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="88e95-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="88e95-136">有効にしているフェデレーションまたは連絡先に対応するために、セッション開始プロトコル (SIP)、web 会議、およびオーディオ/ビジュアル用のファイアウォールポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="88e95-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="88e95-137">詳細については、「 [Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e95-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="88e95-138">Microsoft Lync Server 2013 および Lync Server 2010 とのフェデレーションのための証明書、ポート/プロトコル、および DNS の要件を定義するには、次の情報を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="88e95-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="88e95-139">Microsoft Lync Server 2013 Edge サーバーを計画または展開した場合、通常、証明書、ファイアウォール、ポート/プロトコルの要件と DNS 要件を計画します。</span><span class="sxs-lookup"><span data-stu-id="88e95-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="88e95-140">フェデレーションは、既存のエッジサーバーを使用する追加機能であるため、通常、計画の要件はエッジサーバーの計画と展開によって満たされます。</span><span class="sxs-lookup"><span data-stu-id="88e95-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="88e95-141">以下の表を使用して、要件を満たしていることを確認し、それに応じてポート/プロトコルと DNS を変更してください。</span><span class="sxs-lookup"><span data-stu-id="88e95-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="88e95-142">エッジサーバーのプールと Lync Server 2013 または Lync Server 2010 パートナーとのフェデレーションを行っている場合は、エッジサーバーの内部および外部のサイドで DNS 負荷分散またはハードウェアロードバランサーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="88e95-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="88e95-143">Office Communications Server 2007 または Office Communications Server 2007 R2 とのフェデレーションを行う場合、ハードウェア負荷分散によって、エッジサーバーのイベントに対するフェールオーバーサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="88e95-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="88e95-144">Office Communications Server 2007 と Office Communications Server 2007 R2 は、DNS 負荷分散に対応していません。</span><span class="sxs-lookup"><span data-stu-id="88e95-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="88e95-145">パートナーエッジサーバーは、お使いのプールの最初のエッジサーバーとの通信を確立します。</span><span class="sxs-lookup"><span data-stu-id="88e95-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="88e95-146">このエッジサーバーに障害が発生した場合、通信が自動的にフェイルオーバーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="88e95-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="88e95-147">通常、証明書の要件は、選択したエッジサーバーまたはプールされたエッジサーバープランの証明書の計画によって満たされます。</span><span class="sxs-lookup"><span data-stu-id="88e95-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="88e95-148">このセクション中</span><span class="sxs-lookup"><span data-stu-id="88e95-148">In This Section</span></span>

  - [<span data-ttu-id="88e95-149">証明書の概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="88e95-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span data-ttu-id="88e95-150">[[ポートの概要]-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)</span><span class="sxs-lookup"><span data-stu-id="88e95-150">[Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)</span></span>

  - [<span data-ttu-id="88e95-151">DNS 概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="88e95-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88e95-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="88e95-152">See Also</span></span>


[<span data-ttu-id="88e95-153">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="88e95-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="88e95-154">Lync Server 2013 の外部ユーザー アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="88e95-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="88e95-155">Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="88e95-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="88e95-156">Lync Server 2013 の DNS の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="88e95-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="88e95-157">Lync Server 2013 での組織のアクセス エッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="88e95-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="88e95-158">Lync Server 2013 での組織の SIP フェデレーション ドメインの管理</span><span class="sxs-lookup"><span data-stu-id="88e95-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="88e95-159">Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="88e95-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

