---
title: 'Lync Server 2013: 高可用性および障害復旧の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7ba7e58f29bb4e54972804fbe338c2e1345e91e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="a7622-102">Lync Server 2013 での高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="a7622-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7622-103">_**トピックの最終更新日:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="a7622-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="a7622-104">Lync server 2010 の場合と同様に、Lync Server 2013 のほとんどのサーバーの役割に関する主な高可用性スキームは、プーリングによるサーバーの冗長性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a7622-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="a7622-105">あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="a7622-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="a7622-106">これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a7622-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="a7622-107">Lync Server 2013 は、サーバーの地理的なた場合地理的を2つのデータセンターに導入して、1つのプールまたはサイトを停止する必要があることを提供することにより、フロントエンドプール用の新しい障害復旧手段を追加します。</span><span class="sxs-lookup"><span data-stu-id="a7622-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="a7622-108">Lync Server 2013 では、バックエンドデータベースの同期 SQL ミラーリングをサポートすることにより、バックエンドサーバーの高可用性も強化されています。</span><span class="sxs-lookup"><span data-stu-id="a7622-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="a7622-109">このセクションでは、これらの主要な高可用性機能と障害復旧機能について説明し、別のサーバーの役割の高可用性と障害復旧に使用できる手順についても説明します。</span><span class="sxs-lookup"><span data-stu-id="a7622-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a7622-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a7622-110">In This Section</span></span>

  - [<span data-ttu-id="a7622-111">Lync Server 2013 のフロントエンドプールの障害復旧</span><span class="sxs-lookup"><span data-stu-id="a7622-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="a7622-112">Lync Server 2013 でのエッジサーバーの障害復旧</span><span class="sxs-lookup"><span data-stu-id="a7622-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="a7622-113">Lync Server 2013 でのエンタープライズ Voip の復元の計画</span><span class="sxs-lookup"><span data-stu-id="a7622-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="a7622-114">Lync Server 2013 での障害復旧のための通話管理機能</span><span class="sxs-lookup"><span data-stu-id="a7622-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="a7622-115">Lync Server 2013 での高可用性および障害復旧用の常設チャットサーバーの構成</span><span class="sxs-lookup"><span data-stu-id="a7622-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="a7622-116">Lync Server 2010 大都市サイト復元</span><span class="sxs-lookup"><span data-stu-id="a7622-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

