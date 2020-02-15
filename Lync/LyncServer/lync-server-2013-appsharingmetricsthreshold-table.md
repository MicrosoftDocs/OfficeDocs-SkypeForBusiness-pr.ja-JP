---
title: 'Lync Server 2013: AppSharingMetricsThreshold テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89260bb2e854087ec1167ff0fd8039c58ac99300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>Lync Server 2013 の AppSharingMetricsThreshold テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-12-08_

AppSharingMetricsThreshold テーブルには、アプリケーション共有で使用される QoE (Quality of Experience) 指標の最適な値と許容される値が含まれます。これらのしきい値は、アプリケーション共有のエクスペリエンスを不良として分類する必要があるかどうかを判断するために使用されます。

この表は、Microsoft Lync Server 2013 で導入されました。


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
<td><p>行われた通話の種類です。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>アプリケーション共有の最善の帯域幅制限です。既定値は 1000000 です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>アプリケーション共有の許容される帯域幅制限です。既定値は 500000 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td></td>
<td><p>アプリケーション共有の品質の分類のために "スポイルされた" タイルの最善の割合です。この値は、ビューアーに到達しなかった共有者からのコンテンツのパーセンテージです。コンテンツは、共有者がグラフィックス ソースからタイルを破棄すると、または ASMCU タイルが共有者からタイルを破棄すると、破棄される (スポイルされる) 可能性があります。既定値は 11 パーセントです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td></td>
<td><p>アプリケーション共有の品質の分類のために "スポイルされた" タイルの許容される割合です。この値は、ビューアーに到達しなかった共有者からのコンテンツのパーセンテージです。コンテンツは、共有者がグラフィックス ソースからタイルを破棄すると、または ASMCU タイルが共有者からタイルを破棄すると、破棄される (スポイルされる) 可能性があります。既定値は 36 パーセントです。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>この列は、Microsoft Lync Server 2013 では使用されません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>この列は、Microsoft Lync Server 2013 では使用されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>この列は、Microsoft Lync Server 2013 では使用されません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>この列は、Microsoft Lync Server 2013 では使用されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>この列は、Microsoft Lync Server 2013 では使用されません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>この列は、Microsoft Lync Server 2013 では使用されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>アプリケーション共有に関係する 2 つのメディア エンドポイント間の相対的な一方向遅延の最善の値です。これは単一ホップ遅延の測定値です。既定値は 1.0 秒です。</p>
<p>このコラムは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>アプリケーション共有に関係する 2 つのメディア エンドポイント間の相対的な一方向遅延の許容される値です。これは単一ホップ遅延の測定値です。既定値は 1.75 秒です。</p>
<p>このコラムは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>表示セッション中の AS 会議サーバーでの RDP タイル処理の最善の平均遅延です。 Latency は、サーバー (シナリオによっては、共有先または MCU) で開始フレームがエンコードされてから、同じ開始フレームが閲覧者にデコードされるまでの時間差です。</p>
<p>高い平均値は、表示エクスペリエンスでの長い遅延を反映します。高い負荷がかかっている会議サーバーでは、平均遅延が高くなる場合があります。既定値は 200 ミリ秒です。</p>
<p>このコラムは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>表示セッション中の AS 会議サーバーでの RDP タイル処理の平均遅延の許容される値です。 Latency は、サーバー (シナリオによっては、共有先または MCU) で開始フレームがエンコードされてから、同じ開始フレームが閲覧者にデコードされるまでの時間差です。</p>
<p>高い平均値は、表示エクスペリエンスでの長い遅延を反映します。高い負荷がかかっている会議サーバーでは、平均遅延が高くなる場合があります。既定値は 200 ミリ秒です。</p>
<p>このコラムは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

