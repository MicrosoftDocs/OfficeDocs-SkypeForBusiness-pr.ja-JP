---
title: 境界ネットワークへのサーバーのインストールの準備
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
ms.openlocfilehash: a28fc1e77a98e2a6123537ec5c062dca5d0c6ffb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="6d08c-102">Lync Server 2013 の境界ネットワークへのサーバーのインストールの準備</span><span class="sxs-lookup"><span data-stu-id="6d08c-102">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d08c-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6d08c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6d08c-104">エッジサーバーコンポーネントを設定する前に、セットアップしているコンピューターがシステム要件を満たしていることを確認し、エッジサーバーコンポーネントの展開に必要なその他の前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d08c-104">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="6d08c-105">作業を開始する前に、展開する参照アーキテクチャの計画ドキュメントで、次のトピックの詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6d08c-105">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="6d08c-106">Lync Server 2013 におけるプライベート IP アドレスと NAT を用いた単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="6d08c-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="6d08c-107">Lync Server 2013 のパブリック IP アドレスを使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="6d08c-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="6d08c-108">Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="6d08c-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="6d08c-109">Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="6d08c-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="6d08c-110">Lync Server 2013 のハードウェア ロード バランサーによる拡張統合エッジ</span><span class="sxs-lookup"><span data-stu-id="6d08c-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="6d08c-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="6d08c-111">In This Section</span></span>

  - [<span data-ttu-id="6d08c-112">Lync Server 2013 でのエッジ サポートの DNS の構成</span><span class="sxs-lookup"><span data-stu-id="6d08c-112">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="6d08c-113">Lync Server 2013 で拡張エッジ トポロジ用のロード バランサー機器を設定する</span><span class="sxs-lookup"><span data-stu-id="6d08c-113">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="6d08c-114">Lync Server 2013 での外部ユーザー アクセス用のファイアウォールとポートの構成</span><span class="sxs-lookup"><span data-stu-id="6d08c-114">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="6d08c-115">Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="6d08c-115">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="6d08c-116">Lync Server 2013 でエッジ コンポーネントの証明書を要求する</span><span class="sxs-lookup"><span data-stu-id="6d08c-116">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

