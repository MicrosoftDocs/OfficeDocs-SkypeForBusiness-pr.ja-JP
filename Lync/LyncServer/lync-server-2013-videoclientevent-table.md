---
title: 'Lync Server 2013: VideoClientEvent テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ff9e19288aaaa09b8c72f857f3cfcf4e5331dd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="71e55-102">Lync Server 2013 の VideoClientEvent テーブル</span><span class="sxs-lookup"><span data-stu-id="71e55-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71e55-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="71e55-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="71e55-104">各レコードには、ビデオ通話での1つのエンドポイントのクライアントイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="71e55-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="71e55-105">通常、1つの通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="71e55-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71e55-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="71e55-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="71e55-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="71e55-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="71e55-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="71e55-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="71e55-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="71e55-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71e55-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="71e55-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71e55-111">datetime</span><span class="sxs-lookup"><span data-stu-id="71e55-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="71e55-112">Primary</span><span class="sxs-lookup"><span data-stu-id="71e55-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="71e55-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="71e55-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71e55-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="71e55-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="71e55-115">int</span><span class="sxs-lookup"><span data-stu-id="71e55-115">int</span></span></p></td>
<td><p><span data-ttu-id="71e55-116">Primary</span><span class="sxs-lookup"><span data-stu-id="71e55-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="71e55-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="71e55-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71e55-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="71e55-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="71e55-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="71e55-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71e55-120">Primary</span><span class="sxs-lookup"><span data-stu-id="71e55-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="71e55-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</span><span class="sxs-lookup"><span data-stu-id="71e55-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71e55-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="71e55-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="71e55-123">bit</span><span class="sxs-lookup"><span data-stu-id="71e55-123">bit</span></span></p></td>
<td><p><span data-ttu-id="71e55-124">Primary</span><span class="sxs-lookup"><span data-stu-id="71e55-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="71e55-125">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="71e55-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="71e55-126">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="71e55-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71e55-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="71e55-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71e55-128">セッションのパーセンテージ低帯域幅イベントが ' Bad ' 状態に対して発生しました。</span><span class="sxs-lookup"><span data-stu-id="71e55-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="71e55-129">利用可能な音声エクスペリエンスを実現するには、利用可能な帯域幅が不足しています。</span><span class="sxs-lookup"><span data-stu-id="71e55-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71e55-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="71e55-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71e55-131">セッションのパーセンテージ ReceiveSendQuality イベントが ' Bad ' 状態で発生しました。</span><span class="sxs-lookup"><span data-stu-id="71e55-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="71e55-132">ネットワーク品質は、ジッタまたはパケット損失の観点では深刻であり、受信中のオーディオの品質に影響します。</span><span class="sxs-lookup"><span data-stu-id="71e55-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

