---
title: 'Lync Server 2013: 拡張ディレクタープール-ハードウェアロードバランサー'
description: 'Lync Server 2013: 拡張ディレクタープール-ハードウェアロードバランサー。'
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
ms.openlocfilehash: 022c5afb67687149f8ba24655be2a1461d4371f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578703"
---
# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="e6ffd-103">拡張ディレクタープール-Lync Server 2013 のハードウェアロードバランサー</span><span class="sxs-lookup"><span data-stu-id="e6ffd-103">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6ffd-104">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e6ffd-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e6ffd-105">拡張ディレクタープール。追加の容量を処理し、高可用性を実現するために複数のディレクターが展開されている場合、負荷分散によって、プールのすべてのメンバーにクライアントとサーバーの通信を分散する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6ffd-105">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="e6ffd-106">ディレクターは、フロントエンドプールによく似た web サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="e6ffd-106">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="e6ffd-107">Web サービスにはハードウェアによる負荷分散が必要です。</span><span class="sxs-lookup"><span data-stu-id="e6ffd-107">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="e6ffd-108">次のトピックでは、ハードウェア負荷分散を使用してディレクタープールを展開する際の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6ffd-108">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="e6ffd-109">ディレクタープールに対してハードウェア負荷分散と DNS 負荷分散を使用する場合は、「 [拡張ディレクタープール-dns 負荷分散」および「Lync Server 2013 のハードウェアロードバランサー](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) 」を参照してください。このトポロジの計画要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6ffd-109">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="e6ffd-110">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="e6ffd-110">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e6ffd-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e6ffd-111">In This Section</span></span>

  - [<span data-ttu-id="e6ffd-112">証明書の概要-Lync Server 2013 の拡張ディレクタープール、ハードウェアロードバランサー</span><span class="sxs-lookup"><span data-stu-id="e6ffd-112">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="e6ffd-113">ポートの概要-Lync Server 2013 の拡張ディレクタープール、ハードウェアロードバランサー</span><span class="sxs-lookup"><span data-stu-id="e6ffd-113">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="e6ffd-114">DNS の概要-Lync Server 2013 の拡張ディレクタープール、ハードウェアロードバランサー</span><span class="sxs-lookup"><span data-stu-id="e6ffd-114">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

