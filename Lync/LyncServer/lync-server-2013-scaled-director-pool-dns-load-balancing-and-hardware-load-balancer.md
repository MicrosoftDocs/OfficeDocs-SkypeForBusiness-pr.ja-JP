---
title: 拡張ディレクタープール-DNS 負荷分散とロードバランサー機器
description: 拡張ディレクタープール-DNS 負荷分散とロードバランサー機器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b30dfcc3515420ffb34343e4653e9518b1b9c3ed
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563463"
---
# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="e77ad-103">拡張ディレクタープール-Lync Server 2013 での DNS 負荷分散とロードバランサー機器</span><span class="sxs-lookup"><span data-stu-id="e77ad-103">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e77ad-104">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e77ad-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e77ad-105">拡張ディレクタープール。追加容量を処理し、高可用性を実現するために複数のディレクターが展開されている場合、負荷分散によってプールのすべてのメンバーにクライアントとサーバーの通信を分散する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e77ad-105">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="e77ad-106">ディレクターは、フロントエンドプールによく似た web サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="e77ad-106">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="e77ad-107">負荷分散を実現するには、ハードウェア負荷分散またはドメインネームシステム (DNS) 負荷分散とハードウェア負荷分散のどちらかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e77ad-107">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="e77ad-108">Web サービスにはハードウェア負荷分散が必要であり、DNS 負荷分散だけでは web サービスに必要な機能が提供されません。</span><span class="sxs-lookup"><span data-stu-id="e77ad-108">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="e77ad-109">次のトピックでは、DNS 負荷分散を使用してディレクタープールをハードウェア負荷分散と共に展開する際の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="e77ad-109">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="e77ad-110">ディレクタープールでハードウェア負荷分散を使用し、DNS 負荷分散を使用しない場合については、「 [拡張ディレクタープール-Lync Server 2013 のハードウェアロードバランサー](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) 」を参照してください。このトポロジの計画要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="e77ad-110">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="e77ad-111">![拡張ディレクター プール](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "拡張ディレクター プール")</span><span class="sxs-lookup"><span data-stu-id="e77ad-111">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e77ad-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e77ad-112">In This Section</span></span>

  - [<span data-ttu-id="e77ad-113">証明書の概要-Lync Server 2013 での DNS および HLB の負荷分散</span><span class="sxs-lookup"><span data-stu-id="e77ad-113">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="e77ad-114">ポートの概要-Lync Server 2013 での DNS および HLB の負荷分散</span><span class="sxs-lookup"><span data-stu-id="e77ad-114">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="e77ad-115">DNS の概要-Lync Server 2013 での DNS および HLB の負荷分散</span><span class="sxs-lookup"><span data-stu-id="e77ad-115">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

