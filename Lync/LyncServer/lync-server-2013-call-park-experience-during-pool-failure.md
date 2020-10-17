---
title: 'Lync Server 2013: プール障害時のコールパーク環境'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 605900501a141c053459c690292b1e0a10c8abbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508254"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="8a360-102">プール障害発生時の Lync Server 2013 でのコールパークの動作</span><span class="sxs-lookup"><span data-stu-id="8a360-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a360-103">_**トピックの最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="8a360-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="8a360-104">予期しないインシデントが発生したためにフロントエンドプールが使用できなくなった場合、保留されたがまだ取得されていない呼び出しは切断されます。</span><span class="sxs-lookup"><span data-stu-id="8a360-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="8a360-105">バックアッププールへのフェールオーバー中、ユーザーはバックアッププールにリダイレクトされ、復元モードになります。</span><span class="sxs-lookup"><span data-stu-id="8a360-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="8a360-106">復元モードでは、ユーザーは通話をパークできませんが、通話を保留にして転送することができます。</span><span class="sxs-lookup"><span data-stu-id="8a360-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="8a360-107">フェールオーバーが完了すると、通常どおりに通話を保留して取得することができます。</span><span class="sxs-lookup"><span data-stu-id="8a360-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="8a360-108">フェールバック時に、ユーザーは復元モードが解除されるまで通話をパークできません。</span><span class="sxs-lookup"><span data-stu-id="8a360-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="8a360-109">障害復旧時に、フェールオーバープロセスの一環としてバックアッププールにリダイレクトされたユーザーは、バックアッププールに展開されているコールパークアプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a360-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="8a360-110">そのため、バックアッププールにリダイレクトされたユーザーは、バックアッププールのコールパークアプリケーションに対して構成されているコールパーク設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a360-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="8a360-111">次の表では、障害復旧のフェーズを通じてコールパークの使用状況を要約しています。</span><span class="sxs-lookup"><span data-stu-id="8a360-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="8a360-112">障害復旧時のユーザーの利便性</span><span class="sxs-lookup"><span data-stu-id="8a360-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a360-113">呼び出しの状態</span><span class="sxs-lookup"><span data-stu-id="8a360-113">Call state</span></span></th>
<th><span data-ttu-id="8a360-114">停止が発生した場合</span><span class="sxs-lookup"><span data-stu-id="8a360-114">When outage occurs</span></span></th>
<th><span data-ttu-id="8a360-115">フェールオーバー中</span><span class="sxs-lookup"><span data-stu-id="8a360-115">During failover</span></span></th>
<th><span data-ttu-id="8a360-116">フェールバック中</span><span class="sxs-lookup"><span data-stu-id="8a360-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a360-117">通話はまだパークされていません</span><span class="sxs-lookup"><span data-stu-id="8a360-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="8a360-118">通話は接続されたままですが、パークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8a360-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8a360-119">フェールオーバー中は、ユーザーが復元モードの間は通話をパークすることはできませんが、通話を保留および転送することはできます。</span><span class="sxs-lookup"><span data-stu-id="8a360-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="8a360-120">フェールオーバーが完了すると、通話をパークおよび取得できます。</span><span class="sxs-lookup"><span data-stu-id="8a360-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="8a360-121">フェールバック時に、ユーザーが復元モードの間は通話を保留することはできませんが、保留にして転送することはできます。</span><span class="sxs-lookup"><span data-stu-id="8a360-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="8a360-122">フェールバックが完了すると、通話をパークおよび取得できます。</span><span class="sxs-lookup"><span data-stu-id="8a360-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a360-123">コールパーク (まだ取得されていない)</span><span class="sxs-lookup"><span data-stu-id="8a360-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="8a360-124">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="8a360-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="8a360-125">この状態の通話はありません。</span><span class="sxs-lookup"><span data-stu-id="8a360-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="8a360-126">通話は保留中のままになります。</span><span class="sxs-lookup"><span data-stu-id="8a360-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a360-127">既に取得された保留中の通話</span><span class="sxs-lookup"><span data-stu-id="8a360-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="8a360-128">通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="8a360-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="8a360-129">通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="8a360-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="8a360-130">通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="8a360-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

