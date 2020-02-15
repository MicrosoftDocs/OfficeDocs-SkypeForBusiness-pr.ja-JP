---
title: 'Lync Server 2013: フロントエンドプールのペアリングの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4daeb3ea88570afaf9fc90c0e252466be67ed192
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="6b1c8-102">Lync Server 2013 でのフロントエンドプールのペアリングの計画</span><span class="sxs-lookup"><span data-stu-id="6b1c8-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b1c8-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6b1c8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6b1c8-104">Lync Server 2013 で最高の障害復旧機能を使用するには、2つの地理的に分散したサイト間でフロントエンドプールのペアを展開します。</span><span class="sxs-lookup"><span data-stu-id="6b1c8-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="6b1c8-105">各サイトのフロントエンド プールは、他のサイトの対応するフロントエンド プールとペアになっています。</span><span class="sxs-lookup"><span data-stu-id="6b1c8-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="6b1c8-106">両方のサイトがアクティブであり、Lync Server バックアップサービスは、プールの同期を維持するためのリアルタイムデータレプリケーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="6b1c8-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="6b1c8-107">バックアップサービスは、Lync Server 2013 の新機能で、障害復旧ソリューションをサポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="6b1c8-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="6b1c8-108">プールを別のフロントエンド プールとペアにすると、バックアップ サービスがフロントエンド プールにインストールされます</span><span class="sxs-lookup"><span data-stu-id="6b1c8-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="6b1c8-p102">一方のサイトのプールで障害が発生した場合は、そのプールから他のサイトのプールにユーザーをフェールオーバーでき、それ以降はそのサイトが両方のプールのすべてのユーザーに対応します。容量計画では、障害発生時に両方のプールの全ユーザーのワークロードを処理するように各プールを設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b1c8-p102">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools. For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6b1c8-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6b1c8-111">In This Section</span></span>

  - [<span data-ttu-id="6b1c8-112">Lync Server 2013 でサポートされているプールのペアのオプションとベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="6b1c8-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="6b1c8-113">Lync Server 2013 のバックアップレジストラーの関係</span><span class="sxs-lookup"><span data-stu-id="6b1c8-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="6b1c8-114">Lync Server 2013 でのプールのフェールオーバーおよびプールのフェールバックの復旧時間</span><span class="sxs-lookup"><span data-stu-id="6b1c8-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="6b1c8-115">Lync Server 2013 での中央管理ストアのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="6b1c8-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="6b1c8-116">Lync Server 2013 でのフロントエンドプールのペアリングデータのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="6b1c8-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

