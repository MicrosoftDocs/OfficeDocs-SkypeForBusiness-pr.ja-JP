---
title: AppSharingMetricsThreshold テーブル
TOCTitle: AppSharingMetricsThreshold テーブル
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48272555
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# AppSharingMetricsThreshold テーブル

 

_**トピックの最終更新日:** 2015-12-08_

AppSharingMetricsThreshold テーブルには、アプリケーション共有で使用される QoE (Quality of Experience) 指標の最適な値と許容される値が含まれます。これらのしきい値は、アプリケーション共有のエクスペリエンスを不良として分類する必要があるかどうかを判断するために使用されます。

このテーブルは、Microsoft Lync Server 2013 で導入されました。


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
<td><p>行われた通話の種類です。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>アプリケーション共有の最善の帯域幅制限です。既定値は 1000000 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>アプリケーション共有の許容される帯域幅制限です。既定値は 500000 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p></p></td>
<td><p>アプリケーション共有の品質の分類のために &quot;スポイルされた&quot; タイルの最善の割合です。この値は、ビューアーに到達しなかった共有者からのコンテンツのパーセンテージです。コンテンツは、共有者がグラフィックス ソースからタイルを破棄すると、または ASMCU タイルが共有者からタイルを破棄すると、破棄される (スポイルされる) 可能性があります。既定値は 11 パーセントです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p></p></td>
<td><p>アプリケーション共有の品質の分類のために &quot;スポイルされた&quot; タイルの許容される割合です。この値は、ビューアーに到達しなかった共有者からのコンテンツのパーセンテージです。コンテンツは、共有者がグラフィックス ソースからタイルを破棄すると、または ASMCU タイルが共有者からタイルを破棄すると、破棄される (スポイルされる) 可能性があります。既定値は 36 パーセントです。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>この列は Microsoft Lync Server 2013 では使用されていません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>この列は Microsoft Lync Server 2013 では使用されていません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>この列は Microsoft Lync Server 2013 では使用されていません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>この列は Microsoft Lync Server 2013 では使用されていません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>この列は Microsoft Lync Server 2013 では使用されていません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>この列は Microsoft Lync Server 2013 では使用されていません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>アプリケーション共有に関係する 2 つのメディア エンドポイント間の相対的な一方向遅延の最善の値です。これは単一ホップ遅延の測定値です。既定値は 1.0 秒です。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>アプリケーション共有に関係する 2 つのメディア エンドポイント間の相対的な一方向遅延の許容される値です。これは単一ホップ遅延の測定値です。既定値は 1.75 秒です。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>表示セッション中の AS 会議サーバーでの RDP タイル処理の最善の平均遅延です。ネットワーク遅延はこの指標の対象外です。</p>
<p>高い平均値は、表示エクスペリエンスでの長い遅延を反映します。高い負荷がかかっている会議サーバーでは、平均遅延が高くなる場合があります。既定値は 200 ミリ秒です。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>表示セッション中の AS 会議サーバーでの RDP タイル処理の平均遅延の許容される値です。ネットワーク遅延はこの指標の対象外です。</p>
<p>高い平均値は、表示エクスペリエンスでの長い遅延を反映します。高い負荷がかかっている会議サーバーでは、平均遅延が高くなる場合があります。既定値は 200 ミリ秒です。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>

