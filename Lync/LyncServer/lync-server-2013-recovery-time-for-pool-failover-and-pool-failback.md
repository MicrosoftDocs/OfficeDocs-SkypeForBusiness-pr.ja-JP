---
title: Lync Server 2013 のプールフェールオーバーおよびプールフェールバックの回復時間
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb165fa762b23bd271dde56c0846ccb18adfbf7f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="15841-102">Lync Server 2013 でのプールのフェールオーバーおよびプールのフェールバックの復旧時間</span><span class="sxs-lookup"><span data-stu-id="15841-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15841-103">_**トピックの最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="15841-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="15841-p101">プールのフェールオーバーおよびフェールバックで、エンジニアリング上想定される復旧時間目標 (RTO) は 30 分です。これは、管理者が障害の発生を認知してフェールオーバー手順を開始してから、フェールオーバーが発生するまでに必要な時間です。管理者が状況を評価して意思決定を行う時間は含まれていません。また、フェールオーバーの完了後にユーザーが再度サインインするまでの時間も含まれていません。</span><span class="sxs-lookup"><span data-stu-id="15841-p101">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes. This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures. It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="15841-107">プールのフェールオーバーおよびフェールバックで、エンジニアリング上想定される復旧時点目標 (RPO) は 30 分です。</span><span class="sxs-lookup"><span data-stu-id="15841-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="15841-108">これは、障害が発生したときに、バックアップ サービスのレプリケーション待機時間に起因してデータが消失する可能性がある時間を表すものです。</span><span class="sxs-lookup"><span data-stu-id="15841-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="15841-109">たとえば、プールが 10:00 A.M. になり、RPO が30分になると、データは 9:30 A.M. からに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="15841-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="15841-110">および10:00 は、バックアッププールにレプリケートされていない可能性があり、失われます。</span><span class="sxs-lookup"><span data-stu-id="15841-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="15841-111">このドキュメントに示す RTO と RPO の数値はすべて、待ち時間の少ない高速接続で 2 つのサイトが結ばれている同じ地域内に 2 つのデータ センターが設置されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="15841-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="15841-112">これらの番号は、データレプリケーションのバックログがない、事前に定義されたユーザーモデルに対して、4万の同時アクティブユーザーと Lync が有効になっている20万ユーザーが使用するプールに対して測定されます。</span><span class="sxs-lookup"><span data-stu-id="15841-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="15841-113">これらの数値は、パフォーマンス テストおよび検証に基づいて変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="15841-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

