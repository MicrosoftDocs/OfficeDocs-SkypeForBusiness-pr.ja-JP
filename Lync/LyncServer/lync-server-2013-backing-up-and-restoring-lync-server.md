---
title: 'Lync Server 2013: Lync Server のバックアップと復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0cf9f9baabd095e54373c31acd4f4522974a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="d207d-102">Lync Server 2013 のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="d207d-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d207d-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d207d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d207d-104">このセクションでは、Lync Server 2013 データをバックアップするためのベストプラクティスと、エラーが発生した場合に復元するためのベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d207d-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="d207d-105">このベストプラクティスは、次のような場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d207d-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="d207d-106">任意の種類の Lync Server プール全体 (フロントエンドサーバー、エッジサーバー、仲介サーバー、常設チャットサーバー、またはディレクター)、またはこれらのいずれかのプールの個々のサーバー。</span><span class="sxs-lookup"><span data-stu-id="d207d-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="d207d-107">中央管理サーバー</span><span class="sxs-lookup"><span data-stu-id="d207d-107">The Central Management Server</span></span>

  - <span data-ttu-id="d207d-108">Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="d207d-108">A Standard Edition server</span></span>

  - <span data-ttu-id="d207d-109">Enterprise Edition バックエンドサーバー</span><span class="sxs-lookup"><span data-stu-id="d207d-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="d207d-110">ファイルストア</span><span class="sxs-lookup"><span data-stu-id="d207d-110">A File Store</span></span>

  - <span data-ttu-id="d207d-111">アーカイブデータベース、監視データベース、または常設チャットデータベース</span><span class="sxs-lookup"><span data-stu-id="d207d-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="d207d-112">このセクションには、サイト全体の復元、またはスタンバイサイトの開発に関する情報は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d207d-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="d207d-113">ペアリングされたフロントエンドプールでの障害回復ソリューションの開発について詳しくは、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d207d-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="d207d-114">これは、障害回復を計画するための推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="d207d-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="d207d-115">ペアリングされたフロントエンドプールを展開している場合、これらのプールのいずれかが失敗して回復不能になった場合は、そのペアのプールから新しい完全修飾ドメイン名 (FQDN) を使用して、このプールを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="d207d-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="d207d-116">この回復を実行する手順の詳細については、「 [Lync Server 2013 でのプールのフェールオーバー](lync-server-2013-failing-over-a-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d207d-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="d207d-117">さらに、フロントエンドペアの一部であった失敗した回復可能なプールを後で再作成する必要がある場合は、「 [Lync Server 2013 で ABC フロントエンドプールフェールオーバーを実行](lync-server-2013-performing-an-abc-front-end-pool-failover.md)する」の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d207d-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="d207d-118">このドキュメントで説明する方法には、計画フェーズでの特別な考慮事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d207d-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="d207d-119">詳細については、「 [Lync Server 2013 のバックアップと復元計画を立てる](lync-server-2013-establishing-a-backup-and-restoration-plan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d207d-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d207d-120">このセクション中</span><span class="sxs-lookup"><span data-stu-id="d207d-120">In This Section</span></span>

  - [<span data-ttu-id="d207d-121">Lync Server 2013 のバックアップと復元の準備</span><span class="sxs-lookup"><span data-stu-id="d207d-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="d207d-122">Lync Server 2013 でのデータと設定のバックアップ</span><span class="sxs-lookup"><span data-stu-id="d207d-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="d207d-123">Lync Server 2013 でのデータと設定の復元</span><span class="sxs-lookup"><span data-stu-id="d207d-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="d207d-124">Lync Server 2013 のバックアップと復元ワークシート</span><span class="sxs-lookup"><span data-stu-id="d207d-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

