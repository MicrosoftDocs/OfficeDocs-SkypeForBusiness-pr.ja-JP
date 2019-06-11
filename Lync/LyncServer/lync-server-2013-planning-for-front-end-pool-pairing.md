---
title: 'Lync Server 2013: フロント エンド プールのペアリングの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0445a6d952ba7311b8f6b5435c16d9e91de587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="5c08f-102">Lync Server 2013 でのフロント エンド プールのペアリングの計画</span><span class="sxs-lookup"><span data-stu-id="5c08f-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c08f-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5c08f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5c08f-104">Lync Server 2013 で最高の障害回復機能を使用するには、地理的に分散した2つのサイトにフロントエンドプールのペアを展開します。</span><span class="sxs-lookup"><span data-stu-id="5c08f-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="5c08f-105">各サイトには、他のサイトで対応するフロントエンドプールとペアリングされたフロントエンドプールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5c08f-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="5c08f-106">両方のサイトがアクティブになり、Lync Server バックアップサービスはリアルタイムのデータレプリケーションを提供して、プールの同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="5c08f-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="5c08f-107">バックアップサービスは、Lync Server 2013 の新機能であり、障害回復ソリューションをサポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="5c08f-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="5c08f-108">プールを別のフロントエンドプールとペアリングすると、フロントエンドプールにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5c08f-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="5c08f-109">1つのサイトのプールで障害が発生した場合は、そのプールのユーザーを他のサイトのプールにフェイルオーバーすることができます。これにより、両方のプールのすべてのユーザーにサービスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5c08f-109">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="5c08f-110">容量の計画を立てるために、各プールは、障害が発生した場合に両方のプールのすべてのユーザーの作業負荷を処理するように設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c08f-110">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5c08f-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="5c08f-111">In This Section</span></span>

  - [<span data-ttu-id="5c08f-112">サポートされているプールペアリングオプションと Lync Server 2013 のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="5c08f-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="5c08f-113">Lync Server 2013 のバックアップ レジストラー関係</span><span class="sxs-lookup"><span data-stu-id="5c08f-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="5c08f-114">Lync Server 2013 のプールのフェールオーバーおよびフェールバックの復旧時間</span><span class="sxs-lookup"><span data-stu-id="5c08f-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="5c08f-115">Lync Server 2013 の中央管理ストアのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="5c08f-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="5c08f-116">Lync Server 2013 でのフロントエンド プールのペアリング データのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="5c08f-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

