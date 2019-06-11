---
title: 'Lync Server 2013: AudioClientEvent テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489777458838d5e77df1f8c82ed6ab8b6c295832
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Lync Server 2013 の AudioClientEvent テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-17_

各レコードには、音声通話中の1つのエンドポイントのクライアントイベントが含まれています。 通常、1つの通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primary</p></td>
<td><p>0: 呼び出し先のデータ</p>
<p>1: 発信者のデータ</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ NetworkSendQuality イベントが ' Bad ' 状態に対して発生しました。</p>
<p>ネットワーク品質は、ジッタまたはパケット損失の観点から、送信された音声の品質に重大な影響を与えることがあります。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ ReceiveSendQuality イベントが ' Bad ' 状態で発生しました。</p>
<p>ネットワーク品質は、ジッタまたはパケット損失の観点から、受信中のオーディオの品質に深刻な影響を与えることができます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio スペック</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ "Bad" 状態に対して Delay イベントが発生しました。 ネットワーク待ち時間が重大であり、対話的なコミュニケーションを防ぐことで、エクスペリエンスに影響を与える</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ低帯域幅イベントが ' Bad ' 状態に対して発生しました。 利用可能な音声エクスペリエンスを実現するには、利用可能な帯域幅が不足しています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションの割合。不適切な CPU イベントが ' Bad ' 状態に対して発生しました。 現在使用中のモダリティとアプリケーションで処理するための CPU サイクルが十分にありません。 これにより、オーディオチャンネルでひずみが発生します。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ DeviceHalfDuplexAEC イベントが ' Bad ' 状態で発生しました。 エコーを防ぐために、システムは半二重モードに設定されています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションの割合 DeviceRenderNotFunctioning イベントが ' Bad ' 状態に対して発生しました。 現在セッションで使用されているレンダーデバイスが正常に機能していません。 これにより、1方向の音声の問題が発生する可能性があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio 使い方</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ DeviceCaptureNotFunctioning イベントが ' Bad ' 状態に対して発生しました。 現在セッションで使用されているキャプチャデバイスが正常に機能していません。 これにより、1方向の音声の問題が発生する可能性があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションの割合 DeviceGlitches イベントが ' Bad ' 状態で発生しました。 オーディオのレンダリングで、ひずみの原因となる重大な問題が発生します。 これらのエラーは、ドライバーの問題、遅延プロシージャ呼び出し (DPC) ストーム (ドライバー)、および CPU 使用率が高くなることが原因で発生する可能性があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ DeviceLowSNR イベントが ' Bad ' 状態に対して発生しました。 キャプチャ品質は非常に低い。雑音が多いか、ユーザがマイクから離れすぎている。 これにより、ひずみが発生します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ DeviceLowSpeechLevel イベントが ' Bad ' 状態で発生しました。 ユーザーの音声レベルが低すぎて、システムがそれ以上の機能を向上させることができない。 これにより、ひずみが発生したり、一方向のオーディオとして認識されるようになります。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ DeviceClipping イベントが ' Bad ' 状態で発生しました。</p>
<p>ニアエンドの音声によってマイクがクリップされる場合は、クリッピングによるひずみが発生します。 ニアエンドマイクのクリッピングを回避することが重要です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ DeviceEchoEvent イベントが ' Bad ' 状態で発生しました。 デバイスまたはセットアップが原因で、システムの補正機能を超えたエコーが発生しています。</p></td>
</tr>
<tr class="even">
<td><p><strong>デバイスの Devicorています。</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>セッションのパーセンテージ Devicenなイベントが ' Bad ' 状態で発生しました。 ユーザーの音声が、ユーザーの中断を簡単にすることができるようになるため、キャプチャされたエコーと比較して、ユーザーエクスペリエンスに影響を与えることができます。 スピーカーの音量を下げて、マイクをトーカーに近づける。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>セッション中に ' Bad ' 状態に対して DeviceMultipleEndpoints イベントが発生した回数。 同じセッション内の複数のオーディオエンドポイントが検出され、レンダーボリュームが減ることで、システムが補正しています。</p></td>
</tr>
<tr class="even">
<td><p><strong>Deviceskのイベントカウント</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>セッション中に、' Bad ' 状態に対して Deviceなイベントイベントが発生した回数。 音声フィードバックループが検出されました (複数のエンドポイントでのオーディオパスの共有によって発生)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Devicerendervolumevolumeeventr</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>セッションのパーセンテージ Devicerenderゼロボリュームイベントが "Bad" 状態になったときに発生しました。 レンダーデバイスがボリューム0に設定されています。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>Devicerendermuteeventr</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>セッションのパーセンテージ DeviceRenderMute イベントが "Bad" 状態になったときに発生しました。 レンダーデバイスがミュートにされました。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

