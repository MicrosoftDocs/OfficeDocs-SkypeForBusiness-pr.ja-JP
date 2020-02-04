---
title: 'Lync Server 2013: エンタープライズ VoIP の展開ガイドライン'
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
ms.openlocfilehash: 221c09fc5dadda267baad35f4784c22cc4f3c9c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="61624-102">Lync Server 2013 のエンタープライズ VoIP の展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="61624-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61624-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="61624-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="61624-104">このトピックでは、Lync Server 2013 およびエンタープライズボイスワークロードの展開を計画する際に考慮する必要のある前提条件およびその他のガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="61624-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="61624-105">展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="61624-105">Deployment Prerequisites</span></span>

<span data-ttu-id="61624-106">エンタープライズ Voip を展開するときに最適なエクスペリエンスを実現するには、IT インフラストラクチャ、ネットワーク、システムが次の前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61624-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="61624-107">Lync Server 2013 Standard Edition または Enterprise Edition がネットワークにインストールされ、動作する。</span><span class="sxs-lookup"><span data-stu-id="61624-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="61624-108">すべてのエッジサーバーは、アクセスエッジサービス、A/V Edge サービス、Web 会議エッジサービス、リバースプロキシなどのエッジサーバーを含む境界ネットワークに展開され、動作します。</span><span class="sxs-lookup"><span data-stu-id="61624-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="61624-109">Lync Server の1人以上のユーザーが作成され、有効になっている。</span><span class="sxs-lookup"><span data-stu-id="61624-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="61624-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) または最新の Service pack、または Microsoft Exchange Server 2010 がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="61624-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="61624-111">これらのいずれかを使用するには、Exchange ユニファイドメッセージング (UM) を Lync Server と統合し、クライアントエンドポイントに対して豊富な通知と通話ログ情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61624-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="61624-112">エンタープライズ Voip が有効になっている各ユーザーの**msrtcsip-userenabled true**属性に、固有のプライマリ電話番号が指定、正規化、コピーされました。</span><span class="sxs-lookup"><span data-stu-id="61624-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61624-113">Lync Server は、電子番号をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="61624-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="61624-114">非表示の数値は、" <STRONG> &lt;e.i&gt;&lt;&gt; </STRONG> " または "内線" の形式で表すことができます。また、秘密の内線番号は企業全体で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="61624-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="61624-115">たとえば、1001の秘密番号は、 <STRONG>+ 1425550100; ext = 1001</STRONG>、または<STRONG>1001</STRONG>として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="61624-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="61624-116"><STRONG>1001</STRONG>として表現された場合、このプライベート番号は企業全体で一意であるという期待があります。</span><span class="sxs-lookup"><span data-stu-id="61624-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="61624-117">エンタープライズボイスを展開する管理者は、RTCUniversalServerAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="61624-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="61624-118">少なくとも、Office Communicator 2007 が正常に展開されました。</span><span class="sxs-lookup"><span data-stu-id="61624-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="61624-119">このリリースの新機能を使用するには、Lync 2013 が展開されています。</span><span class="sxs-lookup"><span data-stu-id="61624-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="61624-120">管理キー基盤 (MKI) は、Microsoft またはサードパーティの証明機関 (CA) インフラストラクチャを使用して展開および構成されます。</span><span class="sxs-lookup"><span data-stu-id="61624-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="61624-121">仲介サーバーをインストールするコンピューターごとに、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="61624-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="61624-122">ドメインのメンバーサーバーで、Active Directory ドメインサービスの準備ができていること。</span><span class="sxs-lookup"><span data-stu-id="61624-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="61624-123">Active Directory ドメインサービスの準備手順については、展開ドキュメントで「 [Lync Server 2013 用 Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61624-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="61624-124">次のいずれかのオペレーティングシステムを実行している。</span><span class="sxs-lookup"><span data-stu-id="61624-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="61624-125">64ビット版の Windows Server 2008 標準オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="61624-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="61624-126">Windows Server 2008 Enterprise オペレーティングシステムの64ビット版</span><span class="sxs-lookup"><span data-stu-id="61624-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="61624-127">公衆交換電話網 (PSTN) または構内交換機 (PBX) への接続が、Time 除算多重 (TDM) 接続によって使用されている場合は、1つ以上の PSTN ゲートウェイを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="61624-127">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment.</span></span> <span data-ttu-id="61624-128">(接続が SIP トランクを使っている場合、PSTN ゲートウェイは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="61624-128">(If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="61624-129">電源、ネットワーク、または電話サービスの停止</span><span class="sxs-lookup"><span data-stu-id="61624-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="61624-130">お客様の所在地での電源、ネットワーク、または電話サービスの停止、中断、またはその他のパフォーマンス低下が発生した場合は、Lync Server および Lync Server に接続されたデバイスの音声、インスタントメッセージ、プレゼンス、その他の機能が正常に動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="61624-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="61624-131">エンタープライズ Voip は、サーバーの可用性と音声クライアントとハードウェアの運用性に依存</span><span class="sxs-lookup"><span data-stu-id="61624-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="61624-132">Lync Server との音声通信は、サーバーソフトウェアの可用性と、サーバーソフトウェアに接続する音声クライアントまたはハードウェア電話デバイスの適切な機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="61624-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="61624-133">緊急サービスへのアクセスの代替手段</span><span class="sxs-lookup"><span data-stu-id="61624-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="61624-134">音声クライアント (たとえば、Lync クライアントまたは Lync Phone Edition のデバイスを実行している PC) をインストールする場合は、電源障害が発生した場合に緊急サービス (911 や999など) を呼び出すためのバックアップオプションを維持することをお勧めします。または、ネットワーク接続の低下、電話サービスの停止、lync Server、Lync、Lync Phone Edition のデバイスの操作を妨げる可能性があるその他の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="61624-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="61624-135">このような代替オプションには、標準の公衆交換電話網回線または携帯電話に接続された電話が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="61624-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="61624-136">緊急通話と複数回線電話システム</span><span class="sxs-lookup"><span data-stu-id="61624-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="61624-137">複数行の電話システム (MLTS) を使用すると、U の対象となる場合があります。 S 州または連邦法 (または、911や999などのエマージェンシーアクセス番号をダイヤルする場合など) に発信者の電話番号、内線番号、または物理的な場所を該当する緊急サービスに提供するために、MLTS が必要となる他の国/地域の法律。</span><span class="sxs-lookup"><span data-stu-id="61624-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="61624-138">このリリースでは、 [lync server 2013 の緊急サービス (E9) の計画](lync-server-2013-planning-for-emergency-services-e9-1-1.md)に記載されているように、発信者の物理的な場所を緊急サービスプロバイダーに提供するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="61624-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="61624-139">MLTS 法へのコンプライアンスは、Lync Server、Lync クライアント、Lync Phone Edition デバイスの購入者に対する唯一の責任となります。</span><span class="sxs-lookup"><span data-stu-id="61624-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

