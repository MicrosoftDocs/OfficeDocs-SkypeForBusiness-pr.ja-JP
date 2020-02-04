---
title: 'Lync Server 2013: 拡張ディレクター プール - ハードウェア負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3fc699a5d0904b3ed308928e5edec612b3af03c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="38c87-102">拡張ディレクター プール - Lync Server 2013 のハードウェア負荷分散</span><span class="sxs-lookup"><span data-stu-id="38c87-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38c87-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="38c87-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="38c87-104">スケーリングされたディレクタープール。追加の容量を処理し、高可用性を実現するために複数のディレクターが展開されている場合は、プールのすべてのメンバーにクライアントとサーバーの通信を配布するために負荷分散を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="38c87-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="38c87-105">ディレクターは、フロントエンドプールのような web サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="38c87-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="38c87-106">Web サービスにはハードウェア負荷分散が必要です。</span><span class="sxs-lookup"><span data-stu-id="38c87-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="38c87-107">次のトピックでは、ハードウェア負荷分散を使用してディレクタープールを展開する場合の計画に関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="38c87-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="38c87-108">ディレクタープールでハードウェア負荷分散と DNS 負荷分散を使用する場合は、そのトポロジの計画要件について説明している「[スケールディレクタープール-dns 負荷分散とハードウェアロード2013バランサー](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) 」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38c87-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="38c87-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="38c87-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="38c87-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="38c87-110">In This Section</span></span>

  - [<span data-ttu-id="38c87-111">証明書の概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="38c87-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="38c87-112">ポートの概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="38c87-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="38c87-113">DNS の概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー</span><span class="sxs-lookup"><span data-stu-id="38c87-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

