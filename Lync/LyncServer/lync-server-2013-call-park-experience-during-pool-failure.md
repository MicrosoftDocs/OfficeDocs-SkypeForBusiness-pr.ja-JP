---
title: 'Lync Server 2013: プール障害時のコール パーク エクスペリエンス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="81f4f-102">プール障害時の Lync Server 2013 のコール パーク エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="81f4f-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81f4f-103">_**最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="81f4f-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="81f4f-104">予期しないインシデントが原因で、フロントエンドプールが利用できなくなった場合、保留になっているがまだ取得されていない呼び出しは切断されます。</span><span class="sxs-lookup"><span data-stu-id="81f4f-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="81f4f-105">バックアッププールへのフェールオーバー中は、ユーザーはバックアッププールにリダイレクトされ、回復性モードになります。</span><span class="sxs-lookup"><span data-stu-id="81f4f-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="81f4f-106">回復可能モードでは、ユーザーは電話をパークすることはできませんが、通話を保留にして転送することができます。</span><span class="sxs-lookup"><span data-stu-id="81f4f-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="81f4f-107">フェールオーバーが完了すると、通常どおりに通話を保留したり、取得したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="81f4f-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="81f4f-108">フェールバック中は、回復性モードが終了するまで、ユーザーは通話をパークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="81f4f-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="81f4f-109">障害回復中に、フェールオーバープロセスの一環としてバックアッププールにリダイレクトされたユーザーは、バックアッププールに展開されているコールパークアプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="81f4f-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="81f4f-110">そのため、バックアッププールにリダイレクトされたユーザーは、バックアッププール内のコールパークアプリケーション用に構成されているコールパーク設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="81f4f-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="81f4f-111">次の表は、障害回復のフェーズを通して、コールパークのエクスペリエンスをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="81f4f-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="81f4f-112">障害回復中のユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="81f4f-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81f4f-113">通話の状態</span><span class="sxs-lookup"><span data-stu-id="81f4f-113">Call state</span></span></th>
<th><span data-ttu-id="81f4f-114">障害が発生した場合</span><span class="sxs-lookup"><span data-stu-id="81f4f-114">When outage occurs</span></span></th>
<th><span data-ttu-id="81f4f-115">フェールオーバー中</span><span class="sxs-lookup"><span data-stu-id="81f4f-115">During failover</span></span></th>
<th><span data-ttu-id="81f4f-116">フェールバック時</span><span class="sxs-lookup"><span data-stu-id="81f4f-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81f4f-117">まだ保留中の通話はありません</span><span class="sxs-lookup"><span data-stu-id="81f4f-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="81f4f-118">通話は接続されたままですが、保留にできません。</span><span class="sxs-lookup"><span data-stu-id="81f4f-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="81f4f-119">フェールオーバー中に、ユーザーが回復可能モードになっている間は、通話を保留にすることはできませんが、保留にして転送することはできます。</span><span class="sxs-lookup"><span data-stu-id="81f4f-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="81f4f-120">フェールオーバーが完了したら、通話を保留および取得することができます。</span><span class="sxs-lookup"><span data-stu-id="81f4f-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="81f4f-121">フェールバック中に、ユーザーが回復可能モードになっている間は、通話を保留にすることはできませんが、保留にして転送することはできます。</span><span class="sxs-lookup"><span data-stu-id="81f4f-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="81f4f-122">フェールバックが完了すると、通話を保留および取得することができます。</span><span class="sxs-lookup"><span data-stu-id="81f4f-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81f4f-123">保留中の通話はまだ取得されていません</span><span class="sxs-lookup"><span data-stu-id="81f4f-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="81f4f-124">通話が切断されました。</span><span class="sxs-lookup"><span data-stu-id="81f4f-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="81f4f-125">この状態では、通話はありません。</span><span class="sxs-lookup"><span data-stu-id="81f4f-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="81f4f-126">通話は保留中のままになります。</span><span class="sxs-lookup"><span data-stu-id="81f4f-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81f4f-127">既に取得された保留中の通話</span><span class="sxs-lookup"><span data-stu-id="81f4f-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="81f4f-128">通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="81f4f-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="81f4f-129">通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="81f4f-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="81f4f-130">通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="81f4f-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

