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
ms.openlocfilehash: a74c8e35af346d82c695f738a8db46bc328d691b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="16089-102">Lync Server 2013 の VideoClientEvent テーブル</span><span class="sxs-lookup"><span data-stu-id="16089-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16089-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="16089-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="16089-104">各レコードには、ビデオ通話の1つのエンドポイントのクライアントイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="16089-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="16089-105">通常、1つの呼び出しには2つのレコードがあり、1つは呼び出し元用、もう1つは呼び出し先用です。</span><span class="sxs-lookup"><span data-stu-id="16089-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16089-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="16089-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="16089-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="16089-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="16089-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="16089-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="16089-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="16089-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16089-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="16089-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="16089-111">日付型</span><span class="sxs-lookup"><span data-stu-id="16089-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="16089-112">Primary</span><span class="sxs-lookup"><span data-stu-id="16089-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="16089-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="16089-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16089-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="16089-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="16089-115">int</span><span class="sxs-lookup"><span data-stu-id="16089-115">int</span></span></p></td>
<td><p><span data-ttu-id="16089-116">Primary</span><span class="sxs-lookup"><span data-stu-id="16089-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="16089-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="16089-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16089-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="16089-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="16089-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="16089-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="16089-120">Primary</span><span class="sxs-lookup"><span data-stu-id="16089-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="16089-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="16089-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16089-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="16089-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="16089-123">若干</span><span class="sxs-lookup"><span data-stu-id="16089-123">bit</span></span></p></td>
<td><p><span data-ttu-id="16089-124">Primary</span><span class="sxs-lookup"><span data-stu-id="16089-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="16089-125">0: 呼び出し先のデータ</span><span class="sxs-lookup"><span data-stu-id="16089-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="16089-126">1: 発信者のデータ</span><span class="sxs-lookup"><span data-stu-id="16089-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16089-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="16089-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="16089-128">[セッションの割合] LowBandwidth 幅イベントは、' Bad ' 状態に対して起動されました。</span><span class="sxs-lookup"><span data-stu-id="16089-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="16089-129">使用可能な音声環境に十分な帯域幅がありません。</span><span class="sxs-lookup"><span data-stu-id="16089-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16089-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="16089-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="16089-131">対して receivesendquality イベントが ' Bad ' 状態に対して起動されたセッションの割合。</span><span class="sxs-lookup"><span data-stu-id="16089-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="16089-132">ジッターまたはパケット損失の面でネットワーク品質が厳しく、受信する音声の品質に影響します。</span><span class="sxs-lookup"><span data-stu-id="16089-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

