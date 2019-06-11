---
title: 'Lync Server 2013: VideoMetricsThreshold テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c15910f6478f3df12bf906f04aee82c89a822de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a>Lync Server 2013 の VideoMetricsThreshold テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

VideoMetricsThreshold テーブルには、ビデオ通話で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値が含まれています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>発信した通話の種類。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLROptimal</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>既定値は0.05 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPostFECPLRAcceptable</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>既定値は0.10 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>既定値は5.0 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>既定値は10.0 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverageOptimal</strong></p></td>
<td><p>10進数 (9, 4)</p></td>
<td></td>
<td><p>既定値は12.0000 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvFramerateAverageAcceptable</strong></p></td>
<td><p>10進数 (9, 4)</p></td>
<td></td>
<td><p>既定値は7.0000 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercentOptimal</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>既定値は5.0 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowFrameRateCallPercentAcceptable</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>既定値は 10.0/</p></td>
</tr>
<tr class="even">
<td><p><strong>LowResolutionCallPercentOptimal</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>既定値は5.0 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercentAcceptable</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>既定値は10.0 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRateOptimal</strong></p></td>
<td><p>@</p></td>
<td></td>
<td><p>既定値は0.05 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPacketLossRateAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>既定値は0.10 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFrameRateAvgOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>既定値は12です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameRateAvgAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>既定値は7です。</p></td>
</tr>
<tr class="even">
<td><p><strong>DynamicCapabilityPercentOptimal</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>既定値は5.00 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercentAcceptable</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>既定値は10.00 です。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

