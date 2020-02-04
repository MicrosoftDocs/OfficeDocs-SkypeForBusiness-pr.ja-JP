---
title: 'Lync Server 2013: エッジサーバーと機能の DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Edge Servers and features
ms:assetid: e3bf05c8-96fb-4dd2-acb1-f0d141c9e2ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721912(v=OCS.15)
ms:contentKeyID: 49733846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e9f0cb2eb68ed29984811f1c42a97dab4693a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="bb13e-102">Microsoft Lync Server 2013 での microsoft Edge サーバーと microsoft 機能の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="bb13e-102">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb13e-103">_**最終更新日:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="bb13e-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="bb13e-104">Lync Server 2013 Edge サーバー、エッジプール、リバースプロキシには、ドメインネームシステム (DNS) レコードの固有の要件があります。</span><span class="sxs-lookup"><span data-stu-id="bb13e-104">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="bb13e-105">Lync Server 2013 で IPv4 と IPv6 が使用されている場合は、host A レコードと AAAA レコードの両方を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb13e-105">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="bb13e-106">以下のトピックでは、展開計画での DNS レコードの使用を定義しています。</span><span class="sxs-lookup"><span data-stu-id="bb13e-106">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bb13e-107">このセクション中</span><span class="sxs-lookup"><span data-stu-id="bb13e-107">In This Section</span></span>

  - [<span data-ttu-id="bb13e-108">DNS の概要 - Lync Server 2013 の単一統合エッジ (NAT によるプライベート IP アドレスを使用)</span><span class="sxs-lookup"><span data-stu-id="bb13e-108">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="bb13e-109">DNS の概要 - Lync Server 2013 でパブリック IP アドレスを持つ単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="bb13e-109">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="bb13e-110">DNS の概要 - Lync Server 2013 での拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="bb13e-110">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="bb13e-111">DNS の概要 - Lync Server 2013 における拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="bb13e-111">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="bb13e-112">DNS の概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)</span><span class="sxs-lookup"><span data-stu-id="bb13e-112">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="bb13e-113">DNS の概要 - Lync Server 2013 でのリバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="bb13e-113">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="bb13e-114">DNS 概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="bb13e-114">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

