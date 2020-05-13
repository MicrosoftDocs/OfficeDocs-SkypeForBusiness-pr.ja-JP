---
title: SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4148cd97ec118a223e7e8b1b1e8c3825f51dbad6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="d600a-102">Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画</span><span class="sxs-lookup"><span data-stu-id="d600a-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d600a-103">_**トピックの最終更新日:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="d600a-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="d600a-104">エッジサーバーは、内部および外部ユーザーがパートナー組織またはサービスの連絡先にアクセスできるように構成できます。</span><span class="sxs-lookup"><span data-stu-id="d600a-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="d600a-105">パートナーとの合意が既知であるため、フェデレーションにより、以下のいずれかまたはすべての機能が、パートナー フェデレーションにおける自組織内の連絡先または自組織へのパートナー フェデレーション内の連絡先に提供されます。</span><span class="sxs-lookup"><span data-stu-id="d600a-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="d600a-106">インスタント メッセージングおよびプレゼンス</span><span class="sxs-lookup"><span data-stu-id="d600a-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="d600a-107">グループ作業と会議 (Web 会議など)</span><span class="sxs-lookup"><span data-stu-id="d600a-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="d600a-108">電話会議、ビデオ会議、またはその両方</span><span class="sxs-lookup"><span data-stu-id="d600a-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="d600a-109">Microsoft Lync Server 2013 と、拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) の連絡先の間のインスタントメッセージング (IM) やプレゼンスなどの通信は、ピアツーピアのみをサポートしている場合があります。これは、フェデレーションパートナーの自分と連絡先のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d600a-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="d600a-110">その他の場合 (lync server、Lync server 2010 から Lync Server 2013 フェデレーションなど)、複数の参加者が会話に参加するよう招待することができます。</span><span class="sxs-lookup"><span data-stu-id="d600a-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="d600a-111">Lync Server と Office Communications Server のフェデレーション</span><span class="sxs-lookup"><span data-stu-id="d600a-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="d600a-112">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の間のフェデレーションは、ピアツーピア通信と複数パーティ通信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d600a-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="d600a-113">ピアツーピアの会話をマルチパーティの会話にエスカレートでき、臨時の会議を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d600a-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="d600a-114">会議 – Web 会議または音声ビデオ会議をスケジュールし、組織内の連絡先およびフェデレーションしているパートナーの連絡先を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d600a-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="d600a-115">フェデレーションは、Microsoft Office Live Communications Server 2005 で初めて登場し、サポートされている1種類のフェデレーションである直接フェデレーションをサポートしていました。</span><span class="sxs-lookup"><span data-stu-id="d600a-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="d600a-116">直接フェデレーションでは、フェデレーションパートナーのセッション開始プロトコル (SIP) ドメインと、パートナーのエッジサーバーの完全修飾ドメイン名 (FQDN) を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="d600a-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="d600a-117">Live Communications Server 2005 SP1 では、追加のフェデレーションの種類が導入されており、すべての必要なドメインネームシステム (DNS) SRV レコードがフェデレーションパートナーによって公開され、そのエッジサーバーを特定します。</span><span class="sxs-lookup"><span data-stu-id="d600a-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="d600a-118">そのリリースで使用されていた用語は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d600a-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="d600a-119">*拡張フェデレーションを開く*: 任意の SIP ドメイン名を受け入れ、DNS SRV を使用してパートナーエッジサーバーを特定する</span><span class="sxs-lookup"><span data-stu-id="d600a-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="d600a-120">*拡張フェデレーション*: パートナーの SIP ドメイン名を組織のフェデレーションパートナーとして構成し、DNS SRV を使用してパートナーエッジサーバーを検索する</span><span class="sxs-lookup"><span data-stu-id="d600a-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="d600a-121">*直接フェデレーション*: パートナーの SIP ドメイン名と、パートナーのエッジサーバーに対する FQDN を構成する</span><span class="sxs-lookup"><span data-stu-id="d600a-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="d600a-122">*サーバーの許可一覧*: 任意のドメインを受け入れ、DNS SRV を使用してホスティングプロバイダーまたはパブリックインスタントメッセージング (IM) 接続プロバイダーのエッジサーバーを検索する</span><span class="sxs-lookup"><span data-stu-id="d600a-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="d600a-123">Microsoft Office Communications Server 2007 は、フェデレーションの種類に対して更新された命名を導入し、各フェデレーションの種類が実際に達成したことをより明確にしました。</span><span class="sxs-lookup"><span data-stu-id="d600a-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="d600a-124">オープン拡張フェデレーションは、*検出済みのパートナー ドメイン*に変更</span><span class="sxs-lookup"><span data-stu-id="d600a-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="d600a-125">拡張フェデレーションは、*許可されたパートナー ドメイン*に変更</span><span class="sxs-lookup"><span data-stu-id="d600a-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="d600a-126">直接フェデレーションは、*許可されたパートナー サーバー*に変更</span><span class="sxs-lookup"><span data-stu-id="d600a-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="d600a-127">サーバー許可リストは、*ホスティング プロバイダー*および*パブリック IM プロバイダー*に変更</span><span class="sxs-lookup"><span data-stu-id="d600a-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="d600a-128">Microsoft Lync Server 2010 では、Microsoft Lync Online 2010 および Microsoft Office 365 に従ってホスティングプロバイダーの定義が狭められ、また、許可されたパートナードメインのフェデレーションの種類によって定義されたものと同じ許可リストに従うようになりました。</span><span class="sxs-lookup"><span data-stu-id="d600a-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="d600a-129">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の間のフェデレーションを有効にするには、エッジサーバーとリバースプロキシを使用して、定義したルールおよび許可されたパートナードメインを適用します。</span><span class="sxs-lookup"><span data-stu-id="d600a-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="d600a-130">計画の観点から、他の Lync Server とのフェデレーションでは、Office Communications Server に次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="d600a-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="d600a-131">トポロジ ビルダーでフェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d600a-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="d600a-132">詳細については、「 [Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングの構成](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)」の展開に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d600a-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="d600a-133">フェデレーションされたドメインの検出に対する要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="d600a-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="d600a-134">フェデレーションを手動で構成するには、パートナーのエッジサーバーとドメイン名の完全修飾ドメイン名 (FQDN)、または Lync Server コントロールパネル、**フェデレーションと外部アクセス**、 **SIP フェデレーションドメイン**に入力されたオンラインドメイン名を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d600a-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="d600a-135">**新しい**ポリシーを作成するか、既存のポリシーを**編集**して、ドメインを FQDN で許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="d600a-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="d600a-136">パートナーがエッジサーバーの IP アドレスを変更した場合、フェデレーションパートナーのエッジサーバーを手動で構成すると、障害が発生しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="d600a-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="d600a-137"><STRONG>新しい SIP フェデレーションドメイン</STRONG>の場合は、Microsoft Lync Online および microsoft 365 または Office 365 の<STRONG>ドメイン名 (または FQDN)</STRONG>を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d600a-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online and Microsoft 365 or Office 365.</span></span> <span data-ttu-id="d600a-138">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の場合は、<STRONG>アクセスエッジサービス (FQDN)</STRONG>も提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d600a-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="d600a-139">パートナーがエッジサーバーを検出できる、検出されたパートナーフェデレーションについては、外部 DNS-sipfederationtls で SRV レコードを作成し \_ ます。 \_tcp.contoso.com –エッジサーバーのポート5061およびホスト (A) レコードを指します。</span><span class="sxs-lookup"><span data-stu-id="d600a-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="d600a-140">Windows Phone または Apple iPhone、iPad、またはその他の Apple デバイスで Microsoft Lync Mobile クライアントをサポートしていて、プッシュ通知サービスまたはプッシュ通知サービスを使用している場合は、_sipfederationtls の _tcp を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d600a-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="d600a-141">&lt;&gt;Lync Mobile クライアントを所有している各 sip ドメインの sip ドメイン SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="d600a-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="d600a-142">Android および Nokia Symbian Lync Mobile では、プッシュ通知を使用しないでください。この要件の対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="d600a-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="d600a-143">フェデレーションされたドメインをサポートするように外部ユーザー アクセス ポリシーを構成します</span><span class="sxs-lookup"><span data-stu-id="d600a-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="d600a-144">セッション開始プロトコル (SIP)、Web 会議、音声ビデオ用にファイアウォールのポートを開き、有効にしているフェデレーションまたは連絡先に対応します。</span><span class="sxs-lookup"><span data-stu-id="d600a-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="d600a-145">詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d600a-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="d600a-146">次の情報は、Microsoft Lync Server 2013 および Lync Server 2010 とのフェデレーションのための証明書、ポート、プロトコル、および DNS の要件を定義するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d600a-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="d600a-147">Microsoft Lync Server 2013 エッジサーバーを計画または展開している場合は、証明書、ファイアウォール、およびポート/プロトコルの要件、および DNS の要件を計画するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="d600a-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="d600a-148">フェデレーションは既存のエッジサーバーを使用する追加機能なので、計画の要件は通常、エッジサーバーの計画と展開によって満たされます。</span><span class="sxs-lookup"><span data-stu-id="d600a-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="d600a-149">次の表を使用して要件が満たされていることを確認し、それに従ってポート/プロトコルおよび DNS を変更します。</span><span class="sxs-lookup"><span data-stu-id="d600a-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d600a-150">エッジサーバーのプールがあり、Lync Server 2013 または Lync Server 2010 パートナーとのフェデレーションを行っている場合は、エッジサーバーの内部および外部の側で DNS 負荷分散またはハードウェアロードバランサーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d600a-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="d600a-151">Office Communications Server 2007 または Office Communications Server 2007 R2 を使用している場合は、ハードウェア負荷分散によって、エッジサーバーの障害に対するフェールオーバーサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d600a-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="d600a-152">Office Communications Server 2007 および Office Communications Server 2007 R2 は、DNS 負荷分散に対応していません。</span><span class="sxs-lookup"><span data-stu-id="d600a-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="d600a-153">パートナーエッジサーバーは、プール内で応答する最初のエッジサーバーとの通信を確立します。</span><span class="sxs-lookup"><span data-stu-id="d600a-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="d600a-154">エッジサーバーに障害が発生しても、通信が自動的にフェールオーバーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="d600a-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="d600a-155">通常、証明書の要件は、選択したエッジサーバーまたはプールのエッジサーバープランの証明書の計画によって満たされます。</span><span class="sxs-lookup"><span data-stu-id="d600a-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="d600a-156">パブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="d600a-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="d600a-157">パブリックインスタントメッセージング接続はフェデレーションのクラスであり、内部および外部の Lync Server 2013 ユーザーが次のいずれかの連絡先を追加できるように構成されています。</span><span class="sxs-lookup"><span data-stu-id="d600a-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="d600a-158">メッセンジャーの連絡先</span><span class="sxs-lookup"><span data-stu-id="d600a-158">Messenger contacts</span></span>

  - <span data-ttu-id="d600a-159">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="d600a-159">Yahoo\!</span></span> <span data-ttu-id="d600a-160">contacts</span><span class="sxs-lookup"><span data-stu-id="d600a-160">contacts</span></span>

  - <span data-ttu-id="d600a-161">America Online (AOL) の連絡先</span><span class="sxs-lookup"><span data-stu-id="d600a-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="d600a-162">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス (PIC USL) は、新規購入または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d600a-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="d600a-163">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="d600a-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d600a-164">サービスの終了日までメッセンジャー (正確な日付はまだ決定されていますが、2013年6月より前ではありません)。</span><span class="sxs-lookup"><span data-stu-id="d600a-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="d600a-165">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの1か月あたりのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="d600a-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d600a-166">Messenger.</span><span class="sxs-lookup"><span data-stu-id="d600a-166">Messenger.</span></span> <span data-ttu-id="d600a-167">このサービスを提供する Microsoft の機能は、Yahoo! からのサポートを受けています。これは、更新されない基になる契約です。</span><span class="sxs-lookup"><span data-stu-id="d600a-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="d600a-168">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="d600a-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d600a-169">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d600a-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d600a-170">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を通じて数十万のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="d600a-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d600a-171">このクラスのフェデレーションには、計画に関する次のような考慮が必要です。</span><span class="sxs-lookup"><span data-stu-id="d600a-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="d600a-172">Windows Live Messenger ユーザーは、インスタントメッセージングに加えて、Lync Server 2013 ユーザーとのピアツーピアの音声ビデオ通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d600a-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="d600a-173">エッジサーバーは、特定のポートとプロトコルの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d600a-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="d600a-174">詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を確認する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d600a-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="d600a-175">Yahoo インスタントメッセージングには、フェデレーションを提供する一般的なエッジサーバーの計画と展開で通常使用される要件以外に、固有の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="d600a-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="d600a-176">America Online では、アクセスエッジサービスに割り当てられているエッジサーバー証明書にクライアント拡張キー使用法 (EKU) が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d600a-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="d600a-177">拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション</span><span class="sxs-lookup"><span data-stu-id="d600a-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="d600a-178">以前のバージョンの Lync Server および Office Communications Server では、XMPP 展開とのフェデレーションを可能にするために、個別のサーバーの役割として展開できる拡張メッセージングおよびプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。</span><span class="sxs-lookup"><span data-stu-id="d600a-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="d600a-179">Microsoft Lync Server 2013 では、XMPP 機能を機能として展開できます。</span><span class="sxs-lookup"><span data-stu-id="d600a-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="d600a-180">XMPP 機能は、2つの部分で構成されています。これは、エッジサーバーと、フロントエンドサーバー上で実行される XMPP ゲートウェイ上で実行される xmpp プロキシです。</span><span class="sxs-lookup"><span data-stu-id="d600a-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="d600a-181">XMPP の展開と構成については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」に記載されています。ファイアウォールでポートとプロトコルルールを定義し、証明書を構成し、DNS レコードを追加することによって、組織での xmpp のサポートを計画します。</span><span class="sxs-lookup"><span data-stu-id="d600a-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="d600a-182">このセクションの以下のトピックでは、展開に対して XMPP フェデレーションを正常に計画するために必要な情報をまとめています。</span><span class="sxs-lookup"><span data-stu-id="d600a-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d600a-p120">Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。</span><span class="sxs-lookup"><span data-stu-id="d600a-p120">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d600a-185">XMPP フェデレーションは、存続可能 branch アプライアンスに所属しているユーザーに対してはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d600a-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="d600a-186">これは、プレゼンス情報の表示と IM メッセージの交換の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d600a-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="d600a-187">以下のトピックには、サポートされているフェデレーションシナリオの証明書、ファイアウォールのポート、および DNS エントリを定義するためのガイダンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d600a-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="d600a-188">証明書の概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="d600a-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="d600a-189">ポートの概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="d600a-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="d600a-190">Lync Server 2013 の DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="d600a-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d600a-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="d600a-191">See Also</span></span>


[<span data-ttu-id="d600a-192">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="d600a-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="d600a-193">Lync Server 2013 での外部ユーザーアクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="d600a-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="d600a-194">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="d600a-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="d600a-195">Lync Server 2013 の DNS 要件を決定する</span><span class="sxs-lookup"><span data-stu-id="d600a-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="d600a-196">Lync Server 2013 での組織のアクセスエッジ構成の管理</span><span class="sxs-lookup"><span data-stu-id="d600a-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="d600a-197">Lync Server 2013 での組織の SIP フェデレーションドメインの管理</span><span class="sxs-lookup"><span data-stu-id="d600a-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="d600a-198">Lync Server 2013 での組織の SIP フェデレーションプロバイダーの管理</span><span class="sxs-lookup"><span data-stu-id="d600a-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

