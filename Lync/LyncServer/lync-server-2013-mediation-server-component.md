---
title: 'Lync Server 2013: 仲介サーバーコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f3476f8b4e99b2abccb67f1d75446a126df03d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="6241b-102">Lync Server 2013 の仲介サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="6241b-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6241b-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6241b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6241b-104">エンタープライズボイスのワークロードを展開する場合は、Lync Server 2013 の仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6241b-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="6241b-105">このセクションでは、基本的な機能、依存関係、基本的なトポロジ、計画ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6241b-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="6241b-106">仲介サーバーは、内部の Lync Server 2013、エンタープライズ Voip インフラストラクチャ、公衆交換電話網 (PSTN) ゲートウェイ、またはセッション開始プロトコル (SIP) トランク間のメディアの変換を行います。</span><span class="sxs-lookup"><span data-stu-id="6241b-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="6241b-107">Lync Server 2013 側では、仲介サーバーが単一の相互 TLS (MTLS) トランスポートアドレスでリッスンします。</span><span class="sxs-lookup"><span data-stu-id="6241b-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="6241b-108">ゲートウェイ側では、仲介サーバーは、トポロジドキュメントで定義された trunks に関連付けられているすべての関連するリッスンポートをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="6241b-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="6241b-109">すべての認定ゲートウェイが TLS をサポートしている必要がありますが、TCP を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6241b-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="6241b-110">TLS をサポートしないゲートウェイのために TCP がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6241b-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="6241b-111">環境に既存のパブリックブランチ Exchange (PBX) がインストールされている場合は、仲介サーバーがエンタープライズボイスユーザーと PBX 間の通話を処理します。</span><span class="sxs-lookup"><span data-stu-id="6241b-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="6241b-112">PBX が ip-pbx の場合は、PBX と仲介サーバーの間の直接 SIP 接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="6241b-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="6241b-113">お使いの PBX が Time ディビジョンマルチプレクシング (TDM) PBX である場合は、仲介サーバーと PBX 間の PSTN ゲートウェイも展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6241b-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="6241b-114">仲介サーバーは、既定でフロントエンドサーバーと連携しています。</span><span class="sxs-lookup"><span data-stu-id="6241b-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="6241b-115">また、仲介サーバーは、パフォーマンス上の理由から単体プールに展開することもできます。 SIP トランクを展開する場合は、スタンドアロンプールを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6241b-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="6241b-116">メディアバイパスと DNS の負荷分散をサポートする限定 PSTN ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバープールは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6241b-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="6241b-117">認定ゲートウェイは、仲介サーバーのプールに対する DNS 負荷分散をサポートし、プール内の任意の仲介サーバーからトラフィックを受信できるため、スタンドアロンの仲介サーバープールは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6241b-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="6241b-118">また、次の条件のいずれかが満たされている限り、IP Pbx を展開した場合、またはインターネットテレフォニーサーバープロバイダーのセッションボーダーコントローラー (SBC) に接続している場合は、仲介サーバーをフロントエンドプールで検索することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6241b-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="6241b-119">IP PBX または SBC は、プール内の任意の仲介サーバーからトラフィックを受信し、プール内のすべての仲介サーバーに一律にトラフィックをルーティングできるように構成されています。</span><span class="sxs-lookup"><span data-stu-id="6241b-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="6241b-120">IP-PBX ではメディアのバイパスはサポートされていませんが、仲介サーバーをホストしているフロントエンドプールは、どのメディアのバイパスが適用されないかを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6241b-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="6241b-121">Microsoft Lync Server 2013 の計画ツールを使用すると、仲介サーバーを配置するフロントエンドプールが負荷を処理できるかどうかを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="6241b-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="6241b-122">環境がこれらの要件を満たしていない場合は、スタンドアロンの仲介サーバープールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6241b-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="6241b-123">仲介サーバーの主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6241b-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="6241b-124">Lync Server 側での SRTP の暗号化と暗号化解除</span><span class="sxs-lookup"><span data-stu-id="6241b-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="6241b-125">TCP 経由の SIP (TLS をサポートしていないゲートウェイ用) を相互 TLS 経由の SIP に変換する</span><span class="sxs-lookup"><span data-stu-id="6241b-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="6241b-126">Lync Server と仲介サーバーのゲートウェイピアの間でのメディアストリームの翻訳</span><span class="sxs-lookup"><span data-stu-id="6241b-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="6241b-127">ネットワーク外のクライアントを内部の ICE コンポーネントに接続して、NAT およびファイアウォールのメディアトラバーサルを有効にする</span><span class="sxs-lookup"><span data-stu-id="6241b-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="6241b-128">エンタープライズボイスクライアントでのリモートワーカーからの通話など、ゲートウェイでサポートされていないコールフローの中継として機能する</span><span class="sxs-lookup"><span data-stu-id="6241b-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="6241b-129">SIP トランクを含む展開では、pstn のサポートを提供するために SIP トランクサービスプロバイダを使用して、PSTN ゲートウェイの必要性を排除します。</span><span class="sxs-lookup"><span data-stu-id="6241b-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="6241b-130">次の図は、基本的な PSTN ゲートウェイとエンタープライズ Voip インフラストラクチャと通信するときに、仲介サーバーによって使用されるシグナリングとメディアプロトコルを示しています。</span><span class="sxs-lookup"><span data-stu-id="6241b-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="6241b-131">**仲介サーバーで使用される信号およびメディアのプロトコル**</span><span class="sxs-lookup"><span data-stu-id="6241b-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="6241b-132">![仲介サーバーのプロトコルの図](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "仲介サーバーのプロトコルの図")</span><span class="sxs-lookup"><span data-stu-id="6241b-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6241b-133">PSTN ゲートウェイと仲介サーバー間のネットワークで TCP または RTP/RTCP (SRTP または SRTP の代わりに) を使用している場合は、ネットワークのセキュリティとプライバシーの確保に役立つ対策を講じることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6241b-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6241b-134">このセクション中</span><span class="sxs-lookup"><span data-stu-id="6241b-134">In This Section</span></span>

  - [<span data-ttu-id="6241b-135">Lync Server 2013 の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="6241b-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="6241b-136">Lync Server 2013 の通話受付管理と仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="6241b-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="6241b-137">Lync Server 2013 の Enhanced 9-1-1 (E9-1-1) と仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="6241b-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="6241b-138">Lync Server 2013 のメディア バイパスと仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="6241b-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="6241b-139">Lync Server 2013 の仲介サーバーのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="6241b-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="6241b-140">Lync Server 2013 での仲介サーバーの展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="6241b-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

