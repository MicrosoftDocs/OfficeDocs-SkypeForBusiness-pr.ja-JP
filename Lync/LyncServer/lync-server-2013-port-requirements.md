---
title: Lync Server 2013 のポート要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4ac38534f7d52aca3df9c24cac10be10dee5be6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="6bfb9-102">Lync Server 2013 のポート要件</span><span class="sxs-lookup"><span data-stu-id="6bfb9-102">Port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bfb9-103">_**トピックの最終更新日:** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="6bfb9-103">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="6bfb9-104">Lync Server では、ファイアウォール上の特定のポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bfb9-104">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="6bfb9-105">さらに、組織でインターネット プロトコル セキュリティ (IPsec) が展開されている場合は、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートの範囲に対して IPsec を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bfb9-105">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6bfb9-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6bfb9-106">In This Section</span></span>

<span data-ttu-id="6bfb9-107">このセクションでは、以下のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6bfb9-107">This section includes the following topics:</span></span>

  - [<span data-ttu-id="6bfb9-108">Lync Server 2013 の内部サーバーのポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="6bfb9-108">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="6bfb9-109">Lync Server 2013 の IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="6bfb9-109">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="6bfb9-110">ポートの概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="6bfb9-110">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="6bfb9-111">ポートの概要-Lync Server 2013 でのパブリック IP アドレスを使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="6bfb9-111">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="6bfb9-112">ポートの概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="6bfb9-112">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="6bfb9-113">ポートの概要-Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="6bfb9-113">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="6bfb9-114">ポートの概要-Lync Server 2013 の拡張統合エッジ (ロードバランサー機器を含む)</span><span class="sxs-lookup"><span data-stu-id="6bfb9-114">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="6bfb9-115">ポートの概要-Lync Server 2013 のリバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="6bfb9-115">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="6bfb9-116">ポートの概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="6bfb9-116">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

