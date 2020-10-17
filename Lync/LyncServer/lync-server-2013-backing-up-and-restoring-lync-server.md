---
title: 'Lync Server 2013: Lync Server のバックアップと復元'
description: 'Lync Server 2013: Lync Server のバックアップと復元。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1a7024b2264fb895d1562a6da0775f9397644b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543783"
---
# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="36520-103">Lync Server 2013 のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="36520-103">Backing up and restoring Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36520-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="36520-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="36520-105">このセクションでは、Lync Server 2013 データをバックアップするためのベストプラクティスと、障害が発生した場合に復元するためのベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="36520-105">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="36520-106">これらのベストプラクティスは、次の状況に適用されます。</span><span class="sxs-lookup"><span data-stu-id="36520-106">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="36520-107">すべての種類の Lync Server プール (フロントエンドサーバー、エッジサーバー、仲介サーバー、常設チャットサーバー、またはディレクター)、またはこれらのプールのいずれかの個々のサーバー。</span><span class="sxs-lookup"><span data-stu-id="36520-107">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="36520-108">中央管理サーバー</span><span class="sxs-lookup"><span data-stu-id="36520-108">The Central Management Server</span></span>

  - <span data-ttu-id="36520-109">Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="36520-109">A Standard Edition server</span></span>

  - <span data-ttu-id="36520-110">Enterprise Edition バックエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="36520-110">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="36520-111">ファイルストア</span><span class="sxs-lookup"><span data-stu-id="36520-111">A File Store</span></span>

  - <span data-ttu-id="36520-112">アーカイブデータベース、監視データベース、または常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="36520-112">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="36520-113">このセクションには、サイト全体の復元、またはスタンバイサイトの開発に関する情報は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="36520-113">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="36520-114">ペアのフロントエンドプールを使用する障害復旧ソリューションの開発の詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36520-114">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="36520-115">これは、障害復旧の計画に推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="36520-115">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="36520-116">ペアになったフロントエンドプールを展開した場合、これらのプールのいずれかが失敗して回復不能になった場合は、そのプールから新しい完全修飾ドメイン名 (FQDN) を使用して、このプールを復元できます。</span><span class="sxs-lookup"><span data-stu-id="36520-116">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="36520-117">この回復を実行する手順の詳細については、「 [Lync Server 2013 でプールをフェールオーバー](lync-server-2013-failing-over-a-pool.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36520-117">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="36520-118">さらに、フロントエンドペアに含まれていた、障害が発生した回復不能なプールを再作成する必要がある場合は、「 [Lync Server 2013 で ABC フロントエンドプールのフェールオーバーを実行](lync-server-2013-performing-an-abc-front-end-pool-failover.md)する」の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="36520-118">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="36520-119">このドキュメントで説明する方法論には、計画フェーズでの特別な考慮事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36520-119">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="36520-120">詳細については、「 [Lync Server 2013 のバックアップと復元の計画](lync-server-2013-establishing-a-backup-and-restoration-plan.md)を立てる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36520-120">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36520-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="36520-121">In This Section</span></span>

  - [<span data-ttu-id="36520-122">Lync Server 2013 のバックアップと復元の準備</span><span class="sxs-lookup"><span data-stu-id="36520-122">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="36520-123">Lync Server 2013 でのデータと設定のバックアップ</span><span class="sxs-lookup"><span data-stu-id="36520-123">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="36520-124">Lync Server 2013 でのデータと設定の復元</span><span class="sxs-lookup"><span data-stu-id="36520-124">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="36520-125">Lync Server 2013 のバックアップと復元のワークシート</span><span class="sxs-lookup"><span data-stu-id="36520-125">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

