---
title: 'Lync Server 2013: 仲介サーバーコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b78a7903cb46ada3231d1d604ced2f8536699776
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="59210-102">Lync Server 2013 の仲介サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="59210-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59210-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="59210-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="59210-104">エンタープライズ Voip ワークロードを展開する場合は、Lync Server 2013、仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59210-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="59210-105">ここでは、基本機能、依存関係、基本的なトポロジ、および計画ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="59210-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="59210-106">仲介サーバーは、内部の Lync Server 2013、エンタープライズ Voip インフラストラクチャ、公衆交換電話網 (PSTN) ゲートウェイ、またはセッション開始プロトコル (SIP) トランク間のメディアの信号と、一部の構成におけるメディアを変換します。</span><span class="sxs-lookup"><span data-stu-id="59210-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="59210-107">Lync Server 2013 側では、仲介サーバーは単一の相互 TLS (MTLS) トランスポートアドレスでリッスンします。</span><span class="sxs-lookup"><span data-stu-id="59210-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="59210-108">ゲートウェイ側では、トポロジ ドキュメントで定義されたトランクに関連付けられているすべてのリッスン ポートをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="59210-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="59210-109">すべての認定ゲートウェイが TLS をサポートしている必要がありますが、TCP を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="59210-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="59210-110">TLS をサポートしないゲートウェイのために TCP がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="59210-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="59210-111">環境内に既存の構内交換業者 (PBX) がある場合、仲介サーバーはエンタープライズ Voip ユーザーと PBX 間の通話を処理します。</span><span class="sxs-lookup"><span data-stu-id="59210-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="59210-112">PBX が ip-pbx の場合は、PBX と仲介サーバーの間に直接 SIP 接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="59210-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="59210-113">PBX が Time ディビジョン多重 (TDM) PBX である場合は、仲介サーバーと PBX の間に PSTN ゲートウェイを展開する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="59210-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="59210-114">既定では、仲介サーバーはフロントエンドサーバーと併置されています。</span><span class="sxs-lookup"><span data-stu-id="59210-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="59210-115">パフォーマンス上の理由で、仲介サーバーをスタンドアロンプールに展開したり、SIP トランキングを展開したりすることもできます。この場合、スタンドアロンプールを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59210-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="59210-116">メディア バイパスと DNS 負荷分散をサポートする認定 PSTN ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンのfea-mediation-poolは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="59210-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="59210-117">スタンドアロンの仲介サーバー プールが必要でないのは、認定ゲートウェイが仲介サーバーのプールへの DNS 負荷分散に対応しており、プール内のすべての仲介サーバーからトラフィックを受信できるからです。</span><span class="sxs-lookup"><span data-stu-id="59210-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="59210-118">また、IP-PBX を展開している場合またはインターネット テレフォニー サーバー プロバイダーのセッション ボーダー コントローラー (SBC) に接続する場合に、以下のどちらかの条件に一致するときは、フロントエンド プールに仲介サーバーを併置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59210-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="59210-119">IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。</span><span class="sxs-lookup"><span data-stu-id="59210-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="59210-120">Ip-pbx はメディアバイパスをサポートしていませんが、仲介サーバーをホストしているフロントエンドプールは、メディアバイパスが適用されない通話の音声トランスコーディングを処理できます。</span><span class="sxs-lookup"><span data-stu-id="59210-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="59210-121">Microsoft Lync Server 2013、計画ツールを使用して、仲介サーバーを併置するフロントエンドプールが負荷を処理できるかどうかを評価できます。</span><span class="sxs-lookup"><span data-stu-id="59210-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="59210-122">これらの要件に適合しない環境では、スタンドアロン仲介サーバー プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59210-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="59210-123">仲介サーバーの主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="59210-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="59210-124">Lync Server 側での SRTP の暗号化と復号化</span><span class="sxs-lookup"><span data-stu-id="59210-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="59210-125">TCP 上の SIP (TLS がサポートされないゲートウェイ用) の相互 TLS 上の SIP への変換。</span><span class="sxs-lookup"><span data-stu-id="59210-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="59210-126">Lync Server と仲介サーバーのゲートウェイピアとの間のメディアストリームの変換</span><span class="sxs-lookup"><span data-stu-id="59210-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="59210-127">ネットワーク外部のクライアントから内部 ICE コンポーネントへの接続。これにより、メディアは NAT およびファイアウォールを通過できます。</span><span class="sxs-lookup"><span data-stu-id="59210-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="59210-128">ゲートウェイがサポートしていない通話フロー (エンタープライズ Voip クライアントでのリモートワーカーからの呼び出しなど) の仲介者としての役割を果たす</span><span class="sxs-lookup"><span data-stu-id="59210-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="59210-129">SIP トランキングを含む展開での SIP トランキング サービス プロバイダーとの連携による PSTN のサポートの提供。これにより、PSTN ゲートウェイを使用する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="59210-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="59210-130">次の図は、基本的な PSTN ゲートウェイおよびエンタープライズ Voip インフラストラクチャと通信するときに仲介サーバーによって使用される信号およびメディアプロトコルを示しています。</span><span class="sxs-lookup"><span data-stu-id="59210-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="59210-131">**仲介サーバーで使用される信号およびメディアのプロトコル**</span><span class="sxs-lookup"><span data-stu-id="59210-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="59210-132">![仲介サーバーのプロトコルの図](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "仲介サーバーのプロトコルの図")</span><span class="sxs-lookup"><span data-stu-id="59210-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59210-133">PSTN ゲートウェイと仲介サーバーの間のネットワークで TCP または RTP/RTCP (SRTP または SRTP ではなく) を使用している場合は、ネットワークのセキュリティとプライバシーを確保するために対策を講じることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59210-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="59210-134">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="59210-134">In This Section</span></span>

  - [<span data-ttu-id="59210-135">Lync Server 2013 の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="59210-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="59210-136">Lync Server 2013 での通話受付管理と仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="59210-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="59210-137">Lync Server 2013 の拡張 9-1-1 (E9-1-1) および仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="59210-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="59210-138">Lync Server 2013 のメディアバイパスと仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="59210-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="59210-139">Lync Server 2013 の仲介サーバーのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="59210-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="59210-140">Lync Server 2013 の仲介サーバーの展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="59210-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

