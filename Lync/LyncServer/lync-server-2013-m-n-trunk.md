---
title: 'Lync Server 2013: M:N トランク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91c0878623a68863aea219d1b3f3735042abc085
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534594"
---
# <a name="mn-trunk-in-lync-server-2013"></a><span data-ttu-id="a3d6e-102">Lync Server 2013 の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="a3d6e-102">M:N trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3d6e-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a3d6e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a3d6e-104">Lync Server 2013 では、以前のリリースからの呼び出しルーティングを目的としたトランクの定義をより柔軟にサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-104">Lync Server 2013 supports greater flexibility in the definition of a trunk for call routing purposes from previous releases.</span></span> <span data-ttu-id="a3d6e-105">トランクとは、仲介サーバーとリスニングポート番号との間の論理的な関連付けのことで、ゲートウェイとリスニングポート番号があります。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-105">A trunk is a logical association between a Mediation Server and listening port number with a gateway and a listening port number.</span></span> <span data-ttu-id="a3d6e-106">これは、次のことを意味します。仲介サーバーは、同じゲートウェイに対して複数のトランクを持つことができます。仲介サーバーは、異なるゲートウェイに対して複数のトランクを持つことができます。反対に、ゲートウェイは、異なる仲介サーバーに対して複数のトランクを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-106">This implies several things: A Mediation Server can have multiple trunks to the same gateway; a Mediation Server can have multiple trunks to different gateways; conversely a gateway can have multiple trunks to different Mediation Servers.</span></span>

<span data-ttu-id="a3d6e-107">トポロジビルダーを使用して、ゲートウェイが Lync トポロジに追加された場合でも、ルートトランクを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-107">A root trunk is still required to be created when a gateway is added to the Lync topology using Topology Builder.</span></span> <span data-ttu-id="a3d6e-108">特定の仲介サーバーが処理できるゲートウェイの数は、混雑している時間帯のサーバーの処理能力によって決まります。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-108">The number of gateways that a given Mediation Server can handle depends on the processing capacity of the server during peak busy hours.</span></span> <span data-ttu-id="a3d6e-109">「サポート」のドキュメントの「 [サポートされる2013ハードウェア](lync-server-2013-supported-hardware.md) 」で説明しているように、lync server 2013 の最小ハードウェア要件を超えるハードウェアに仲介サーバーを展開する場合、スタンドアロンの仲介サーバーが処理できるアクティブな非バイパス通話の数の予測は、約1000呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-109">If you deploy a Mediation Server on hardware that exceeds the minimum hardware requirements for Lync Server 2013, as described in [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation, then the estimate of how many active non-bypass calls a stand-alone Mediation Server can handle is approximately 1000 calls.</span></span> <span data-ttu-id="a3d6e-110">ハードウェア上でこれらの仕様を使用して展開されている場合、仲介サーバーはトランスコーディングを実行することを想定していますが、ゲートウェイがメディアバイパスをサポートしていない場合でも、複数のゲートウェイの呼び出しをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-110">When deployed on hardware meeting these specifications, the Mediation Server is expected to perform transcoding, but still route calls for multiple gateways even if the gateways do not support media bypass.</span></span>

<span data-ttu-id="a3d6e-111">通話ルートを定義するときは、そのルートに関連付けられているトランクを指定しますが、そのルートに関連付けられている仲介サーバーを指定することはありません。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-111">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with that route.</span></span> <span data-ttu-id="a3d6e-112">代わりに、トポロジビルダーを使用してトランクを仲介サーバーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-112">Instead, you use Topology Builder to associate trunks with Mediation Servers.</span></span> <span data-ttu-id="a3d6e-113">つまり、ルーティングによって、呼び出しに使用するトランクが決定され、その後、そのトランクに関連付けられている仲介サーバーがその呼び出しの信号を送信します。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-113">In other words, routing determines which trunk to use for a call, and, subsequently, the Mediation Server associated with that trunk is sent the signaling for that call.</span></span>

<span data-ttu-id="a3d6e-114">仲介サーバーはプールとして展開できます。このプールは、フロントエンドプールと併置することも、スタンドアロンプールとして展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-114">The Mediation Server can be deployed as a pool; this pool can be collocated with a Front End pool, or it can be deployed as a stand-alone pool.</span></span> <span data-ttu-id="a3d6e-115">仲介サーバーがフロントエンドプールと併置されている場合、プールサイズは最大 12 (レジストラープールサイズの制限) にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-115">When a Mediation Server is collocated with a Front End pool, the pool size can be at most 12 (the limit of the Registrar pool size).</span></span> <span data-ttu-id="a3d6e-116">これらの新機能を組み合わせることで、仲介サーバーの信頼性と展開の柔軟性が向上しますが、次のピアエンティティの関連機能が必要になります。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-116">Taken together, these new capabilities increase the reliability and deployment flexibility for Mediation Servers, but they require associated capabilities in the following peer entities:</span></span>

  - <span data-ttu-id="a3d6e-117">**PSTN ゲートウェイ。**</span><span class="sxs-lookup"><span data-stu-id="a3d6e-117">**PSTN gateway.**</span></span> <span data-ttu-id="a3d6e-118">Lync Server 2013 認定ゲートウェイは、DNS 負荷分散を実装する必要があります。これにより、限定された公衆交換電話網 (PSTN) ゲートウェイが仲介サーバーの1つのプールのロードバランサーとして機能し、プール間で通話の負荷分散を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-118">A Lync Server 2013 qualified gateway must implement DNS load balancing, which enables a qualified public switched telephone network (PSTN) gateway to act as a load balancer for one pool of Mediation Servers, and thereby to load-balance calls across the pool.</span></span>

  - <span data-ttu-id="a3d6e-119">**セッションボーダーコントローラー。**</span><span class="sxs-lookup"><span data-stu-id="a3d6e-119">**Session Border Controller.**</span></span> <span data-ttu-id="a3d6e-120">SIP トランクの場合、ピアエンティティは、インターネットテレフォニーサービスプロバイダーのセッションボーダーコントローラー (SBC) です。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-120">For a SIP trunk, the peer entity is a Session Border Controller (SBC) at an Internet telephony service provider.</span></span> <span data-ttu-id="a3d6e-121">仲介サーバープールから SBC への方向では、SBC はプール内の任意の仲介サーバーからの接続を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-121">In the direction from the Mediation Server pool to the SBC, the SBC can receive connections from any Mediation Server in the pool.</span></span> <span data-ttu-id="a3d6e-122">SBC からプールへの方向で、プール内の任意の仲介サーバーにトラフィックを送信できます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-122">In the direction from the SBC to the pool, traffic can be sent to any Mediation Server in the pool.</span></span> <span data-ttu-id="a3d6e-123">これを実現する1つの方法は、サービスプロバイダーと SBC でサポートされている場合に DNS 負荷分散を使用することです。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-123">One method of achieving this is through DNS load balancing, if supported by the service provider and SBC.</span></span> <span data-ttu-id="a3d6e-124">別の方法として、サービスプロバイダーにプール内のすべての仲介サーバーの IP アドレスを付与することができます。また、サービスプロバイダーは、これらを各仲介サーバーの個別の SIP トランクとして SBC にプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-124">An alternative is to give the service provider the IP addresses of all Mediation Servers in the pool, and the service provider will provision these in their SBC as a separate SIP trunk for each Mediation Server.</span></span> <span data-ttu-id="a3d6e-125">その後、サービスプロバイダーは、独自のサーバーの負荷分散を処理します。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-125">The service provider will then handle the load balancing for its own servers.</span></span> <span data-ttu-id="a3d6e-126">これらの機能は、すべてのサービスプロバイダーまたは SBCs でサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-126">Not all service providers or SBCs may support these capabilities.</span></span> <span data-ttu-id="a3d6e-127">さらに、サービスプロバイダーは、この機能に対して特別なチャージを加えることができます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-127">Furthermore, the service provider may charge extra for this capability.</span></span> <span data-ttu-id="a3d6e-128">通常、SBC に対する各 SIP トランクは月単位の料金を負担します。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-128">Typically, each SIP trunk to the SBC incurs a monthly fee.</span></span>

  - <span data-ttu-id="a3d6e-129">**IP-PBX。**</span><span class="sxs-lookup"><span data-stu-id="a3d6e-129">**IP-PBX.**</span></span> <span data-ttu-id="a3d6e-130">仲介サーバープールから IP-PBX SIP ターミネーションへの方向において、ip-pbx はプール内の任意の仲介サーバーからの接続を受信できます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-130">In the direction from the Mediation Server pool to the IP-PBX SIP termination, the IP-PBX can receive connections from any Mediation Server in the pool.</span></span> <span data-ttu-id="a3d6e-131">Ip-pbx からプールへの方向では、プール内の任意の仲介サーバーにトラフィックを送信できます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-131">In the direction from the IP-PBX to the pool, traffic can be sent to any Mediation Server in the pool.</span></span> <span data-ttu-id="a3d6e-132">ほとんどの IP-PBXs は DNS 負荷分散をサポートしていないため、IP-PBX からプール内の各仲介サーバーへの個別の直接 SIP 接続を定義することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-132">Because most IP-PBXs do not support DNS load balancing, we recommend that individual direct SIP connections be defined from the IP-PBX to each Mediation Server in the pool.</span></span> <span data-ttu-id="a3d6e-133">その後、ip-pbx はトランクグループにトラフィックを分散することによって、自身の負荷分散を処理します。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-133">The IP-PBX will then handle its own load balancing by distributing traffic over the trunk group.</span></span> <span data-ttu-id="a3d6e-134">トランクグループには、ip-pbx のルーティングルールの一貫したセットがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-134">The assumption is that the trunk group has a consistent set of routing rules at the IP-PBX.</span></span> <span data-ttu-id="a3d6e-135">特定の ip-pbx がこのトランクグループの概念をサポートしているかどうか、およびそれが ip-pbx の独自の冗長性とどのように交差しているかを判断するには、仲介サーバーのクラスターが ip-pbx と正しく対話できるかどうかを判断する前に、クラスタリングアーキテクチャを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-135">Whether a particular IP-PBX supports this trunk group concept and how it intersects with the IP-PBX’s own redundancy and clustering architecture needs to be determined before you can decide whether a Mediation Server cluster can interact correctly with an IP-PBX.</span></span>

<span data-ttu-id="a3d6e-136">仲介サーバープールは、それが作用するピアゲートウェイの統一されたビューを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-136">A Mediation Server pool must have a uniform view of the peer gateway with which it interacts.</span></span> <span data-ttu-id="a3d6e-137">これは、プールのすべてのメンバーが、構成ストアからのピアゲートウェイの同じ定義にアクセスすることを意味します。また、送信呼び出しでも同じように操作する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-137">This means that all members of the pool access the same definition of the peer gateway from the configuration store and are equally likely to interact with it for outgoing calls.</span></span> <span data-ttu-id="a3d6e-138">そのため、一部の仲介サーバーが発信呼び出しに対して特定のゲートウェイピアのみと通信するようにプールを分割する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-138">Therefore, there is no way to segment the pool so that some Mediation Servers communicate with only certain gateway peers for outgoing calls.</span></span> <span data-ttu-id="a3d6e-139">このようなセグメンテーションが必要な場合は、別の仲介サーバープールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-139">If such segmentation is necessary, a separate pool of Mediation Servers must be used.</span></span> <span data-ttu-id="a3d6e-140">これに該当するのは、このトピックで前述したように、PSTN ゲートウェイ、SIP トランク、または IP-PBXs がプールを操作するために使用する機能が存在しない場合などです。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-140">This would be the case, for example, if the associated capabilities in PSTN gateways, SIP trunks, or IP-PBXs to interact with a pool as detailed earlier in this topic are not present.</span></span>

<span data-ttu-id="a3d6e-141">特定の PSTN ゲートウェイ、ip-pbx、または SIP トランクピアは、複数の仲介サーバーまたはトランクにルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-141">A particular PSTN gateway, IP-PBX, or SIP trunk peer can route to multiple Mediation Servers or trunks.</span></span> <span data-ttu-id="a3d6e-142">仲介サーバーの特定のプールが制御できるゲートウェイの数は、メディアバイパスを使用する通話の数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-142">The number of gateways that a particular pool of Mediation Servers can control depends on the number of calls that use media bypass.</span></span> <span data-ttu-id="a3d6e-143">多数の通話でメディアバイパスが使用されている場合、プール内の仲介サーバーは、信号層の処理のみが必要になるため、多くの通話を処理できます。</span><span class="sxs-lookup"><span data-stu-id="a3d6e-143">If a large number of calls use media bypass, a Mediation Server in the pool can handle many more calls, because only signaling layer processing is necessary.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

