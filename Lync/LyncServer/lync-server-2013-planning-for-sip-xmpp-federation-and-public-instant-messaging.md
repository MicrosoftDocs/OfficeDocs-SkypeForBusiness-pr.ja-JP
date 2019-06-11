---
title: SIP、XMPP フェデレーション、パブリックインスタントメッセージの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88aa8c6f3f2f11b303a7e25eed96d5f0d7243cb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="f0d4f-102">Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画</span><span class="sxs-lookup"><span data-stu-id="f0d4f-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0d4f-103">_**最終更新日:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="f0d4f-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="f0d4f-104">エッジサーバーを構成して、内部と外部のユーザーがパートナーの組織またはサービスの連絡先にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="f0d4f-105">フェデレーションは、パートナー契約がわかっているため、パートナーフェデレーションまたはパートナーフェデレーションの連絡先に対して、組織内の連絡先に次のいずれか、またはすべてを提供できます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="f0d4f-106">インスタント メッセージングとプレゼンス</span><span class="sxs-lookup"><span data-stu-id="f0d4f-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="f0d4f-107">共同作業と会議 (例: Web 会議)</span><span class="sxs-lookup"><span data-stu-id="f0d4f-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="f0d4f-108">電話会議、ビデオ会議、またはその両方</span><span class="sxs-lookup"><span data-stu-id="f0d4f-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="f0d4f-109">場合によっては、インスタントメッセージング (IM) や Microsoft Lync Server 2013 との間のプレゼンス (XMPP) の連絡先との間での通信が、ピアツーピアのみであり、フェデレーションで自分と連絡先のみをサポートしていることがあります。パートナー.</span><span class="sxs-lookup"><span data-stu-id="f0d4f-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="f0d4f-110">Lync server、lync server 2010、lync Server 2013 フェデレーションなどの場合、複数の参加者が会話に参加するよう招待することができます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="f0d4f-111">Lync Server と Office Communications Server フェデレーション</span><span class="sxs-lookup"><span data-stu-id="f0d4f-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="f0d4f-112">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server 間のフェデレーションは、ピアツーピア通信とマルチパーティ通信をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="f0d4f-113">ピアツーピアの会話は、複数の相手との会話にエスカレーションして、臨時の会議を可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="f0d4f-114">会議– Web 会議や音声/ビジュアル会議–組織内の連絡先、およびフェデレーションするパートナーの連絡先を含めるようにスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="f0d4f-115">フェデレーションは、Microsoft Office Live Communications Server 2005 で初めて表示され、サポートされているフェデレーションの1つになります。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="f0d4f-116">直接フェデレーションでは、フェデレーションパートナーのセッション開始プロトコル (SIP) ドメインとパートナーのエッジサーバーの完全修飾ドメイン名 (FQDN) を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="f0d4f-117">SP1 での Live Communications Server 2005 には、フェデレーションパートナーがエッジサーバーを検索するために必要なすべてのフェデレーションの種類 (DNS) SRV レコードが導入されています。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="f0d4f-118">このリリースの用語は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="f0d4f-119">*拡張フェデレーションを開く*: すべての SIP ドメイン名を受け入れ、DNS SRV を使ってパートナーエッジサーバーを検索する</span><span class="sxs-lookup"><span data-stu-id="f0d4f-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="f0d4f-120">*拡張フェデレーション*: パートナーの SIP ドメイン名を組織のフェデレーションパートナーとして構成し、DNS SRV を使ってパートナーエッジサーバーを検索します。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="f0d4f-121">*直接フェデレーション*: パートナーの SIP ドメイン名と、パートナーのエッジサーバーに対して FQDN を構成する</span><span class="sxs-lookup"><span data-stu-id="f0d4f-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="f0d4f-122">*サーバーの許可リスト*: 任意のドメインを承諾し、DNS SRV を使って、ホスティングプロバイダーまたはパブリックインスタントメッセージング (IM) 接続プロバイダーのエッジサーバーを検索します。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="f0d4f-123">Microsoft Office Communications Server 2007 では、フェデレーションの種類の名前が更新され、各フェデレーションの種類が実際にどのように対応しているかがより明確になりました。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="f0d4f-124">オープン拡張フェデレーションが検出された*パートナードメイン*として認識される</span><span class="sxs-lookup"><span data-stu-id="f0d4f-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="f0d4f-125">拡張フェデレーションが*許可パートナードメイン*として認識される</span><span class="sxs-lookup"><span data-stu-id="f0d4f-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="f0d4f-126">直接フェデレーションが*許可パートナーサーバー*と呼ばれました</span><span class="sxs-lookup"><span data-stu-id="f0d4f-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="f0d4f-127">サーバーの許可リストは、*ホスティングプロバイダー*と*パブリック IM プロバイダー*と呼ばれます</span><span class="sxs-lookup"><span data-stu-id="f0d4f-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="f0d4f-128">Microsoft Lync Server 2010 は、Microsoft Lync Online 2010 と Microsoft Office 365 に準拠して、ホスティングプロバイダーの幅の狭い定義を導入しました。また、許可パートナードメインフェデレーションタイプで定義されたのと同じ許可一覧も適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="f0d4f-129">Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server の間のフェデレーションを有効にすると、エッジサーバーとリバースプロキシを使って、定義したルールと許可されたパートナードメインを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="f0d4f-130">計画の観点から、他の Lync Server とのフェデレーションを行うには、Office Communications Server で次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="f0d4f-131">トポロジビルダーでフェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="f0d4f-132">詳細については、「 [Lync Server 2013 で SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングを構成する展開に](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="f0d4f-133">フェデレーションドメイン探索の要件を決定する:</span><span class="sxs-lookup"><span data-stu-id="f0d4f-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="f0d4f-134">フェデレーションを手動で構成するには、パートナーのエッジサーバーとドメイン名の完全修飾ドメイン名 (FQDN)、および Lync Server コントロールパネル、**フェデレーション、外部アクセス**、SIP に入力されたオンラインドメイン名が必要です。 **フェデレーションドメイン**。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="f0d4f-135">ドメインを FQDN で許可またはブロックするには、**新しい**ポリシーを作成するか、既存のポリシーを**編集**します。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="f0d4f-136">フェデレーションパートナーのエッジサーバーを手動で構成すると、パートナーがエッジサーバーの IP アドレスを変更した場合にエラーが発生しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="f0d4f-137"><STRONG>新しい SIP フェデレーションドメイン</STRONG>の場合は、Microsoft Lync Online、microsoft Office 365 の<STRONG>ドメイン名 (または FQDN)</STRONG>を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="f0d4f-138">Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server の場合は、<STRONG>アクセスエッジサービス (FQDN)</STRONG>も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="f0d4f-139">パートナーがエッジサーバーを検出できる検出されたパートナーフェデレーションについては、外部 DNS- \_SIPFEDERATIONTLS で SRV レコードを作成します。\_Tcp.contoso.com –エッジサーバーのポート5061およびホスト (A) レコードを指します。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="f0d4f-140">Windows Phone または Apple iPhone、iPad、またはその他の Apple デバイスで Microsoft Lync モバイルクライアントをサポートしており、プッシュ通知サービスまたはプッシュ通知サービスを使っている場合は、_sipfederationtls を計画する必要があります。 _tcp</span><span class="sxs-lookup"><span data-stu-id="f0d4f-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="f0d4f-141">&lt;Lync モバイル&gt;クライアントを使用している sip ドメインごとに sip ドメイン SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="f0d4f-142">Android および Nokia Symbian Lync Mobile では、プッシュ通知は使用されず、この要件の対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="f0d4f-143">フェデレーションドメインをサポートするように外部ユーザーアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="f0d4f-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="f0d4f-144">有効にしているフェデレーションまたは連絡先に対応するために、セッション開始プロトコル (SIP)、web 会議、およびオーディオ/ビジュアル用のファイアウォールポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="f0d4f-145">詳細については、「 [Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="f0d4f-146">Microsoft Lync Server 2013 および Lync Server 2010 とのフェデレーションのための証明書、ポート/プロトコル、および DNS の要件を定義するには、次の情報を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="f0d4f-147">Microsoft Lync Server 2013 Edge サーバーを計画または展開した場合、通常、証明書、ファイアウォール、ポート/プロトコルの要件と DNS 要件を計画します。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="f0d4f-148">フェデレーションは、既存のエッジサーバーを使用する追加機能であるため、通常、計画の要件はエッジサーバーの計画と展開によって満たされます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="f0d4f-149">以下の表を使用して、要件を満たしていることを確認し、それに応じてポート/プロトコルと DNS を変更してください。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f0d4f-150">エッジサーバーのプールと Lync Server 2013 または Lync Server 2010 パートナーとのフェデレーションを行っている場合は、エッジサーバーの内部および外部のサイドで DNS 負荷分散またはハードウェアロードバランサーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="f0d4f-151">Office Communications Server 2007 または Office Communications Server 2007 R2 とのフェデレーションを行う場合、ハードウェア負荷分散によって、エッジサーバーのイベントに対するフェールオーバーサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="f0d4f-152">Office Communications Server 2007 と Office Communications Server 2007 R2 は、DNS 負荷分散に対応していません。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="f0d4f-153">パートナーエッジサーバーは、お使いのプールの最初のエッジサーバーとの通信を確立します。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="f0d4f-154">このエッジサーバーに障害が発生した場合、通信が自動的にフェイルオーバーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="f0d4f-155">通常、証明書の要件は、選択したエッジサーバーまたはプールされたエッジサーバープランの証明書の計画によって満たされます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="f0d4f-156">パブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="f0d4f-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="f0d4f-157">パブリックインスタントメッセージング接続はフェデレーションのクラスであり、内部および外部の Lync Server 2013 ユーザーが次のいずれかから連絡先を追加できるように構成されています。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="f0d4f-158">Messenger の連絡先</span><span class="sxs-lookup"><span data-stu-id="f0d4f-158">Messenger contacts</span></span>

  - <span data-ttu-id="f0d4f-159">!\!</span><span class="sxs-lookup"><span data-stu-id="f0d4f-159">Yahoo\!</span></span> <span data-ttu-id="f0d4f-160">連絡先</span><span class="sxs-lookup"><span data-stu-id="f0d4f-160">contacts</span></span>

  - <span data-ttu-id="f0d4f-161">America Online (AOL) の連絡先</span><span class="sxs-lookup"><span data-stu-id="f0d4f-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="f0d4f-162">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス (PIC USL) は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="f0d4f-163">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f0d4f-164">サービスの終了日までメッセンジャーを終了します (正確な日付はまだ決定されますが、2013年6月より前にはなりません)。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="f0d4f-165">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの1か月間のサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f0d4f-166">Messenger.</span><span class="sxs-lookup"><span data-stu-id="f0d4f-166">Messenger.</span></span> <span data-ttu-id="f0d4f-167">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されましたが、その基となる契約は更新されません。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="f0d4f-168">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f0d4f-169">Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f0d4f-170">Skype federation はこのリストに追加されるため、Lync ユーザーは IM や音声を通じて数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="f0d4f-171">このクラスのフェデレーションには、次の計画の考慮事項が必要です。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="f0d4f-172">Windows Live Messenger ユーザーは、インスタントメッセージに加えて、Lync Server 2013 ユーザーとのピアツーピアの音声/視覚的コミュニケーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="f0d4f-173">エッジサーバーは、特定のポートとプロトコルの要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="f0d4f-174">詳細については、「 [Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="f0d4f-175">Yahoo インスタントメッセージには、フェデレーションを提供している一般的なエッジサーバーの計画と展開で通常使用される要件以外の固有の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="f0d4f-176">America Online では、アクセスエッジサービスに割り当てられるエッジサーバー証明書に、クライアント拡張キー使用法 (EKU) が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="f0d4f-177">拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション</span><span class="sxs-lookup"><span data-stu-id="f0d4f-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="f0d4f-178">以前のバージョンの Lync Server と Office Communications Server では、拡張されたメッセージング機能とプレゼンスプロトコル (XMPP) ゲートウェイが提供されており、これを個別のサーバーの役割として展開して、XMPP の展開とのフェデレーションを可能にすることができました。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="f0d4f-179">Microsoft Lync Server 2013 では、XMPP 機能を機能として展開できます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="f0d4f-180">XMPP 機能は、Edge サーバー上で実行される XMPP プロキシと、フロントエンドサーバー上で実行される XMPP ゲートウェイの2つの部分でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="f0d4f-181">XMPP の展開と構成については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を対象としています。ファイアウォールでのポートとプロトコルのルールの定義、証明書の構成、DNS の追加などを行って、組織での xmpp のサポートを計画します。記録.</span><span class="sxs-lookup"><span data-stu-id="f0d4f-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="f0d4f-182">このセクションの次のトピックでは、展開用の XMPP フェデレーションを正常に計画するために必要な情報についてまとめます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f0d4f-p120">Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-p120">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f0d4f-185">XMPP フェデレーションは、survivable branch アプライアンスをホームにしているユーザーに対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="f0d4f-186">これは、プレゼンス情報の表示と IM メッセージの交換の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="f0d4f-187">次のトピックでは、サポートされているフェデレーションシナリオの証明書、ファイアウォールポート、DNS エントリの定義に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="f0d4f-188">証明書の概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="f0d4f-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    <span data-ttu-id="f0d4f-189">[[ポートの概要]-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)</span><span class="sxs-lookup"><span data-stu-id="f0d4f-189">[Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)</span></span>

  - <span></span>  
    [<span data-ttu-id="f0d4f-190">DNS 概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="f0d4f-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0d4f-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0d4f-191">See Also</span></span>


[<span data-ttu-id="f0d4f-192">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="f0d4f-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="f0d4f-193">Lync Server 2013 の外部ユーザー アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="f0d4f-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="f0d4f-194">Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="f0d4f-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="f0d4f-195">Lync Server 2013 の DNS の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="f0d4f-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="f0d4f-196">Lync Server 2013 での組織のアクセス エッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="f0d4f-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="f0d4f-197">Lync Server 2013 での組織の SIP フェデレーション ドメインの管理</span><span class="sxs-lookup"><span data-stu-id="f0d4f-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="f0d4f-198">Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="f0d4f-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

