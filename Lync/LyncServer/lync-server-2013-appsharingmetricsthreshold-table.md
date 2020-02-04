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
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>Lync Server 2013 の AppSharingMetricsThreshold テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-12-08_

AppSharingMetricsThreshold の表には、アプリケーションの共有で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値が含まれています。 これらのしきい値は、アプリケーション共有エクスペリエンスが低品質として分類される必要があるかどうかを判断するために使用されます。

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
<td><p>発信した通話の種類。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>アプリケーション共有に最適な帯域幅の制限。 既定値は100万です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>アプリケーション共有に対して許容可能な帯域幅制限。 既定値は50万です。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>アプリケーション共有の品質を分類するための "損失" タイルの最適な比率。 この値は、閲覧者に届かなかった、共有先のコンテンツのパーセンテージです。 グラフィックスソースまたは ASMCU タイルから共有されているタイルがそれぞれ、共有元のタイルを破棄した場合、コンテンツは破棄 (または損失) されることがあります。 既定値は11パーセントです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>アプリの共有品質を分類するための "損失" タイルの cceptable のパーセンテージ率。 この値は、閲覧者に届かなかった、共有先のコンテンツのパーセンテージです。 グラフィックスソースまたは ASMCU タイルから共有されているタイルがそれぞれ、共有元のタイルを破棄した場合、コンテンツは破棄 (または損失) されることがあります。 既定値は36パーセントです。</p></td>
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
<td><p>float</p></td>
<td></td>
<td><p>この列は、Microsoft Lync Server 2013 では使用されません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>この列は、Microsoft Lync Server 2013 では使用されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>この列は、Microsoft Lync Server 2013 では使用されません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>この列は、Microsoft Lync Server 2013 では使用されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>アプリケーション共有に関連する2つのメディアエンドポイント間の相対的な一方向の遅延の最適値。 これは 1 ホップの遅延の測定です。 既定値は1.0 秒です。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>アプリケーション共有に関連する2つのメディアエンドポイント間の相対的な一方向の遅延の最適値。 これは 1 ホップの遅延の測定です。 既定値は1.75 秒です。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>表示セッションの間の会議サーバーとしての平均 RDP タイル処理の待機時間の最適値。 [待ち時間] は、サーバー (シナリオによっては共有先または MCU) で開始フレームがエンコードされてから、同じ開始フレームが viewer でデコードされるタイミングの差です。</p>
<p>平均値が高いと、表示の際の遅延が大きくなります。 過負荷の会議サーバーでは平均遅延が大きくなる場合があります。 既定値は200ms です。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>表示セッション中の会議サーバーとしての平均 RDP タイル処理待ち時間の値。 [待ち時間] は、サーバー (シナリオによっては共有先または MCU) で開始フレームがエンコードされてから、同じ開始フレームが viewer でデコードされるタイミングの差です。</p>
<p>平均値が高いと、表示の際の遅延が大きくなります。 過負荷の会議サーバーでは平均遅延が大きくなる場合があります。 既定値は200ms です。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

