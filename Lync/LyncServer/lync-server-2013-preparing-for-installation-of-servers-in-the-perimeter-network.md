---
title: 境界ネットワークへのサーバーのインストールの準備
description: 境界ネットワークへのサーバーのインストールの準備。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for installation of servers in the perimeter network
ms:assetid: 5e6c457a-f964-4ef7-a709-97abda9c673a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398416(v=OCS.15)
ms:contentKeyID: 48184292
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5689d7990cc1ddf91ad6487d8abed08f40cd3db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549923"
---
# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="dcd8b-103">Lync Server 2013 の境界ネットワークへのサーバーのインストールの準備</span><span class="sxs-lookup"><span data-stu-id="dcd8b-103">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcd8b-104">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="dcd8b-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="dcd8b-105">エッジ サーバー コンポーネントを設定する前に、設定しているコンピューターがシステム要件を満たしていることを確認し、エッジ サーバー コンポーネントの展開に必要な他の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd8b-105">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="dcd8b-106">開始する前に、「計画」のドキュメントの以下のトピックで、展開する関連アーキテクチャの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="dcd8b-106">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="dcd8b-107">Lync Server 2013 でのプライベート IP アドレスと NAT を使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="dcd8b-107">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="dcd8b-108">Lync Server 2013 でのパブリック IP アドレスを使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="dcd8b-108">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="dcd8b-109">Lync Server 2013 での拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="dcd8b-109">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="dcd8b-110">Lync Server 2013 の拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="dcd8b-110">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="dcd8b-111">Lync Server 2013 での拡張統合エッジとロードバランサー機器</span><span class="sxs-lookup"><span data-stu-id="dcd8b-111">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="dcd8b-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dcd8b-112">In This Section</span></span>

  - [<span data-ttu-id="dcd8b-113">Lync Server 2013 でエッジサポートの DNS を構成する</span><span class="sxs-lookup"><span data-stu-id="dcd8b-113">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="dcd8b-114">Lync Server 2013 で拡張エッジトポロジ用のロードバランサー機器を設定する</span><span class="sxs-lookup"><span data-stu-id="dcd8b-114">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="dcd8b-115">Lync Server 2013 で外部ユーザーアクセス用のファイアウォールとポートを構成する</span><span class="sxs-lookup"><span data-stu-id="dcd8b-115">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="dcd8b-116">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="dcd8b-116">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="dcd8b-117">Lync Server 2013 のエッジコンポーネントの証明書を要求する</span><span class="sxs-lookup"><span data-stu-id="dcd8b-117">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

