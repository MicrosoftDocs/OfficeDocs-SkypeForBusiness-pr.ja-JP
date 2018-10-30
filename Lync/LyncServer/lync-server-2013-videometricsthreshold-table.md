---
title: VideoMetricsThreshold テーブル
TOCTitle: VideoMetricsThreshold テーブル
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48271595
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VideoMetricsThreshold テーブル

 

_**トピックの最終更新日:** 2015-03-09_

VideoMetricsThreshold テーブルには、ビデオ通話で使用される QoE 指標の最適な値および許容可能な値が含まれています。


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
<td><p>主/プライマリ</p></td>
<td><p>発信された通話の種類</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLROptimal</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>既定値は 0.05 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPostFECPLRAcceptable</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>既定値は 0.10 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>既定値は 5.0 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>既定値は 10.0 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverageOptimal</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p></p></td>
<td><p>既定値は 12.0000 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvFramerateAverageAcceptable</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p></p></td>
<td><p>既定値は 7.0000 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercentOptimal</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>既定値は 5.0 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowFrameRateCallPercentAcceptable</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>既定値は 10.0 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowResolutionCallPercentOptimal</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>既定値は 5.0 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercentAcceptable</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>既定値は 10.0 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRateOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>既定値は 0.05 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPacketLossRateAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>既定値は 0.10 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFrameRateAvgOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>既定値は 12 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameRateAvgAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>既定値は 7 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>DynamicCapabilityPercentOptimal</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>既定値は 5.00 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercentAcceptable</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>既定値は 10.00 です。</p></td>
</tr>
</tbody>
</table>

