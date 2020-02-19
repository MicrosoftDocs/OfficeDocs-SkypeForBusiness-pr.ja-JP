---
title: 'Lync Server 2013: エンタープライズ Voip の展開ガイドライン'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc2aee745a362e58003c62f483dda6c63ab244f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="4f475-102">Lync Server 2013 でのエンタープライズ Voip の展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="4f475-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f475-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4f475-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4f475-104">このトピックでは、Lync Server 2013 およびエンタープライズ Voip ワークロードの展開を計画する際に考慮すべき前提条件およびその他のガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4f475-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="4f475-105">展開に関する前提条件</span><span class="sxs-lookup"><span data-stu-id="4f475-105">Deployment Prerequisites</span></span>

<span data-ttu-id="4f475-106">エンタープライズ Voip を展開する場合の最適な環境については、IT インフラストラクチャ、ネットワーク、およびシステムが次の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4f475-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="4f475-107">Lync Server 2013 Standard Edition または Enterprise Edition がインストールされており、ネットワーク上で運用できます。</span><span class="sxs-lookup"><span data-stu-id="4f475-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="4f475-108">エッジサーバーはすべて、エッジサーバー (アクセスエッジサービス、音声ビデオエッジサービス、Web 会議エッジサービス、リバースプロキシ) を含む境界ネットワークに展開され、動作します。</span><span class="sxs-lookup"><span data-stu-id="4f475-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="4f475-109">1人以上のユーザーが作成され、Lync Server に対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4f475-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="4f475-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) または最新のサービスパック、または Microsoft Exchange Server 2010 がインストールされている。</span><span class="sxs-lookup"><span data-stu-id="4f475-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="4f475-111">これらのうちの1つは、Exchange ユニファイドメッセージング (UM) と Lync Server を統合し、豊富な通知を提供したり、クライアントエンドポイントにログ情報を呼び出したりするために必要です。</span><span class="sxs-lookup"><span data-stu-id="4f475-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="4f475-112">エンタープライズ Voip が有効になっている各ユーザーの**msRTCSIP**属性に、一意のプライマリ電話番号が指定および正規化されています。</span><span class="sxs-lookup"><span data-stu-id="4f475-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f475-113">Lync Server は、e.164 番号と直接内向きではない (DID) 番号をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4f475-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="4f475-114">非 DID 番号は、プライベート内線番号がエンタープライズ全体で一意であることを要件として、 <STRONG> &lt;&gt;&lt;内線&gt; </STRONG>番号または内線番号の形式、または数字の文字列として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="4f475-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="4f475-115">たとえば、1001のプライベート番号は、 <STRONG>+ 1425550100、ext = 1001</STRONG>、または<STRONG>1001</STRONG>として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="4f475-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="4f475-116"><STRONG>1001</STRONG>として表される場合、このプライベート番号は企業全体で一意であることが期待されます。</span><span class="sxs-lookup"><span data-stu-id="4f475-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="4f475-117">エンタープライズ Voip を展開する管理者は、RTCUniversalServerAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f475-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="4f475-118">少なくとも、Office Communicator 2007 は正常に展開されています。</span><span class="sxs-lookup"><span data-stu-id="4f475-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="4f475-119">このリリースの新機能を使用するには、Lync 2013 が展開されています。</span><span class="sxs-lookup"><span data-stu-id="4f475-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="4f475-120">マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。</span><span class="sxs-lookup"><span data-stu-id="4f475-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="4f475-121">仲介サーバーをインストールする各コンピューターの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4f475-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="4f475-122">ドメインのメンバーサーバーで、Active Directory ドメインサービス用に準備されています。</span><span class="sxs-lookup"><span data-stu-id="4f475-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="4f475-123">Active Directory ドメインサービスの準備手順については、「展開」のドキュメントの「 [Active Directory ドメインサービスの Lync Server 2013 の準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f475-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4f475-124">次のいずれかのオペレーティング システムを実行していること。</span><span class="sxs-lookup"><span data-stu-id="4f475-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="4f475-125">64 ビット版の Windows Server 2008 Standard オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="4f475-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="4f475-126">64 ビット版の Windows Server 2008 Enterprise オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="4f475-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="4f475-p105">公衆交換電話網 (PSTN) または構内交換機 (PBX) への接続に時分割多重 (TDM) 接続を使用する場合は、1 つ以上の PSTN ゲートウェイを展開できること (接続に SIP トランクを使用する場合、PSTN ゲートウェイは不要です)。</span><span class="sxs-lookup"><span data-stu-id="4f475-p105">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment. (If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="4f475-129">電力、ネットワーク、または電話サービスの停止</span><span class="sxs-lookup"><span data-stu-id="4f475-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="4f475-130">お客様の場所で、停止、中断、その他の電源、ネットワーク、または電話サービスの低下が発生した場合、Lync Server の音声、インスタントメッセージング、プレゼンス、およびその他の機能が正しく動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="4f475-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="4f475-131">エンタープライズ VoIP が、サーバーの可用性と VoIP クライアントおよびハードウェアの正常動作に依存する</span><span class="sxs-lookup"><span data-stu-id="4f475-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="4f475-132">Lync Server との音声通信は、サーバーソフトウェアの可用性と、サーバーソフトウェアに接続する音声クライアントまたはハードウェア電話デバイスの適切な機能に依存しています。</span><span class="sxs-lookup"><span data-stu-id="4f475-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="4f475-133">緊急サービスへの代替アクセス手段</span><span class="sxs-lookup"><span data-stu-id="4f475-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="4f475-134">音声クライアント (Lync クライアントまたは Lync Phone Edition デバイスを実行している PC など) をインストールする場所については、電源障害が発生した場合に、ユーザーが緊急サービス (たとえば、911または 999) を呼び出すためのバックアップオプションを維持することをお勧めします。、Lync Server、Lync、Lync Phone Edition デバイスの動作を妨げる可能性がある、ネットワーク接続の低下、電話サービスの停止、その他の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="4f475-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="4f475-135">このような代替オプションには、標準公衆交換電話網回線に接続された電話、携帯電話などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f475-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="4f475-136">緊急呼び出しと複数回線電話システム</span><span class="sxs-lookup"><span data-stu-id="4f475-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="4f475-137">複数行の電話システム (MLTS) の使用は、U の対象となる場合があります。発信者が緊急サービスに発信されたときに、発信者の電話番号、内線、または物理的な場所を該当する緊急サービスに提供するために MLTS が必要とするその他の国/地域の法律または連邦法 (911 や999などのエマージェンシー・アクセス番号をダイヤルする場合など)。</span><span class="sxs-lookup"><span data-stu-id="4f475-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="4f475-138">このリリースでは、lync server [2013 での緊急サービス (E9-1-1) の計画](lync-server-2013-planning-for-emergency-services-e9-1-1.md)」に記載されているように、緊急サービスプロバイダーに発信者の物理的な場所を提供するように lync Server を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4f475-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="4f475-139">MLTS の法令に準拠するには、Lync Server、Lync クライアント、Lync Phone Edition デバイスの購入者の責任を負う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f475-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

