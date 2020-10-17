---
title: 'Lync Server 2013: VideoClientEvent テーブル'
description: 'Lync Server 2013: VideoClientEvent テーブル。'
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
ms.openlocfilehash: ae73ac2548e838241febe60a2d31f80983b01de5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568493"
---
# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="e68db-103">Lync Server 2013 の VideoClientEvent テーブル</span><span class="sxs-lookup"><span data-stu-id="e68db-103">VideoClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e68db-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e68db-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e68db-105">各レコードには、ビデオ通話の1つのエンドポイントのクライアントイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e68db-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="e68db-106">通常、1つの呼び出しには2つのレコードがあり、1つは呼び出し元用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="e68db-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e68db-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="e68db-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e68db-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="e68db-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e68db-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="e68db-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e68db-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="e68db-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e68db-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e68db-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e68db-112">日付型</span><span class="sxs-lookup"><span data-stu-id="e68db-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e68db-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e68db-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e68db-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e68db-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e68db-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e68db-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e68db-116">int</span><span class="sxs-lookup"><span data-stu-id="e68db-116">int</span></span></p></td>
<td><p><span data-ttu-id="e68db-117">Primary</span><span class="sxs-lookup"><span data-stu-id="e68db-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="e68db-118"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e68db-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e68db-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e68db-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e68db-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="e68db-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e68db-121">Primary</span><span class="sxs-lookup"><span data-stu-id="e68db-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="e68db-122"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="e68db-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e68db-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="e68db-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="e68db-124">若干</span><span class="sxs-lookup"><span data-stu-id="e68db-124">bit</span></span></p></td>
<td><p><span data-ttu-id="e68db-125">Primary</span><span class="sxs-lookup"><span data-stu-id="e68db-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="e68db-126">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="e68db-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="e68db-127">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="e68db-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e68db-128"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e68db-128"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e68db-129">[セッションの割合] LowBandwidth 幅イベントは、' Bad ' 状態に対して起動されました。</span><span class="sxs-lookup"><span data-stu-id="e68db-129">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e68db-130">使用可能な音声環境に十分な帯域幅がありません。</span><span class="sxs-lookup"><span data-stu-id="e68db-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e68db-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e68db-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e68db-132">対して receivesendquality イベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="e68db-132">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="e68db-133">ジッターまたはパケット損失の面でネットワーク品質が厳しく、受信する音声の品質に影響します。</span><span class="sxs-lookup"><span data-stu-id="e68db-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

