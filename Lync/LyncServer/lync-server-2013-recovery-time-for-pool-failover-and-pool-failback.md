---
title: 'Lync Server 2013: プールのフェールオーバーおよびフェールバックの復旧時間'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a746eb96de7b1e22291cf7a147851b313469bed5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="bda22-102">Lync Server 2013 のプールのフェールオーバーおよびフェールバックの復旧時間</span><span class="sxs-lookup"><span data-stu-id="bda22-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bda22-103">_**最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="bda22-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="bda22-104">プールのフェールオーバーとプールのフェールバックの場合、復旧時間の目標 (RTO) のエンジニアリングターゲットは30分です。</span><span class="sxs-lookup"><span data-stu-id="bda22-104">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes.</span></span> <span data-ttu-id="bda22-105">これは、管理者が障害が発生し、フェールオーバー手順が開始された後に、フェールオーバーが発生するために必要な時間です。</span><span class="sxs-lookup"><span data-stu-id="bda22-105">This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures.</span></span> <span data-ttu-id="bda22-106">管理者が状況を評価して意思決定を行う時間は含まれません。また、フェールオーバーの完了後にユーザーがもう一度サインインする時間も含まれません。</span><span class="sxs-lookup"><span data-stu-id="bda22-106">It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="bda22-107">プールのフェールオーバーとプールのフェールバックの場合、RPO (目標復旧時点) のエンジニアリングターゲットは30分です。</span><span class="sxs-lookup"><span data-stu-id="bda22-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="bda22-108">これは、障害が発生したときに、バックアップ サービスのレプリケーション待機時間に起因してデータが消失する可能性がある時間を表すものです。</span><span class="sxs-lookup"><span data-stu-id="bda22-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="bda22-109">たとえば、プールが午前10:00 時に停止し、RPO が30分の場合は、9:30 A.M. までにプールに書き込まれたデータ</span><span class="sxs-lookup"><span data-stu-id="bda22-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="bda22-110">また、10:00 はバックアッププールにレプリケートされておらず、失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bda22-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="bda22-111">このドキュメントに示す RTO と RPO の数値はすべて、待ち時間の少ない高速接続で 2 つのサイトが結ばれている同じ地域内に 2 つのデータ センターが設置されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="bda22-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="bda22-112">どちらの数値も、データ レプリケーションにバックログがない事前定義済みのユーザー モデルに対して、同時アクティブ ユーザーが 40,000 人と Lync に対して有効になっているユーザーが 200,000 人存在するプールを対象として測定を行った結果です。</span><span class="sxs-lookup"><span data-stu-id="bda22-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="bda22-113">これらの数値は、パフォーマンス テストおよび検証に基づいて変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bda22-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

