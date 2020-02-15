---
title: 'Lync Server 2013: AudioClientEvent テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53f43bdae2fd134e851c93be958aa671657489e1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Lync Server 2013 の AudioClientEvent テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-17_

各レコードには、音声通話の1つのエンドポイントのクライアントイベントが含まれています。 通常、1つの呼び出しには2つのレコードがあり、1つは呼び出し元用、もう1つは呼び出し先用です。


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
<td><p>日付型</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>若干</p></td>
<td><p>Primary</p></td>
<td><p>0: 呼び出し先のデータ</p>
<p>1: 発信者のデータ</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>' Bad ' 状態に対して NetworkSendQuality イベントが発生したセッションの割合。</p>
<p>ジッターまたはパケット損失の面でネットワーク品質が深刻で、送信される音声の品質に影響します。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>対して receivesendquality イベントが ' Bad ' 状態に対して起動されたセッションの割合。</p>
<p>ジッターまたはパケット損失の面でネットワーク品質が厳しく、受信する音声の品質に影響します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Networkdelayeventrev</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>' Bad ' 状態で遅延イベントが発生したセッションの割合。 ネットワークの遅延が深刻で、対話的なコミュニケーションを妨げることによって、操作が影響を受ける</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>[セッションの割合] LowBandwidth 幅イベントは、' Bad ' 状態に対して起動されました。 使用可能な音声環境に十分な帯域幅がありません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>' Bad ' 状態に対して、CPU の不足イベントが発生したセッションの割合。 現在使用されているモダリティおよびアプリケーションとの処理に CPU サイクルが不足しています。 これにより、オーディオチャネルとのゆがみが発生します。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>DeviceHalfDuplexAEC イベントが ' Bad ' 状態に対して起動されたセッションの割合。 エコーを防ぐために、システムは半二重入力します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Devicerendernotfunctioningeventrev</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>' Bad ' 状態に対して DeviceRenderNotFunctioning イベントが発生したセッションの割合。 セッションで現在使用されているレンダーデバイスが正しく機能していません。 これにより、1ウェイの音声の問題が発生する可能性があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>Devicecapturenotfunctioningeventrev</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>' Bad ' 状態に対して DeviceCaptureNotFunctioning イベントが発生したセッションの割合。 セッションで現在使用されているキャプチャデバイスが正しく機能していません。 これにより、1ウェイの音声の問題が発生する可能性があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>' Bad ' 状態で DeviceGlitches イベントが発生したセッションの割合。 ひずみが発生している音声のレンダリングに重大な問題があります。 これらの問題は、ドライバーの問題、遅延プロシージャ呼び出し (DPC) ストーム (ドライバー)、CPU 使用率が高いことが原因で発生することがあります。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>' Bad ' 状態に対して DeviceLowSNR イベントが発生したセッションの割合。 キャプチャ品質が非常に低い。雑音が多いか、ユーザーがマイクから離れすぎている。 これにより、ゆがみが発生します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>DeviceLowSpeechLevel イベントが ' Bad ' 状態に対して起動されたセッションの割合。 ユーザーの音声レベルが低すぎるため、システムがこれ以上の機能を向上させることはできません。 これにより、ゆがみが一通行の音声として認識されることがあります。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>対して deviceclipping イベントが ' Bad ' 状態に対して起動されたセッションの割合。</p>
<p>ニアエンド音声によってマイクがクリップされると、遠方でクリッピングが発生することがあります。 ニアエンドマイクのクリッピングを回避することが重要です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>Deviceechoevent が生じイベントが ' Bad ' 状態に対して起動されたセッションの割合。 デバイスまたはセットアップによって、システムの機能を超えるエコーが発生しています。</p></td>
</tr>
<tr class="even">
<td><p><strong>Devicenん endtoo/exceloeventrev</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>' Bad ' 状態に対して、Devicen/Endto///のイベントが発生したセッションの割合。 ユーザーの音声が小さすぎる場合は、キャプチャしたエコーと比較して、ユーザーが簡単に中断できることを制限するため、ユーザーの操作に影響を及ぼします。 スピーカー音量を下げるには、マイクをトーカーの近くに動かします。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>セッション中の DeviceMultipleEndpoints イベントが ' Bad ' 状態に対して起動された回数。 同じセッションで複数のオーディオエンドポイントが検出され、描画ボリュームが減少することにより、システムが補償しています。</p></td>
</tr>
<tr class="even">
<td><p><strong>Devicecount/Eventcount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>セッション中に発生した回数。 ' Bad ' 状態で Deviceの状態イベントイベントが発生しました。 検出された音声フィードバックループ (複数のエンドポイントがオーディオパスを共有したことが原因)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Devicerenderゼロの volumeeventr</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td></td>
<td><p>"Bad" 状態になっているために、Devicerenderゼロボリュームイベントが発生したセッションの割合。 レンダーデバイスがボリューム0に設定されています。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio スペック)</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td></td>
<td><p>"Bad" 状態であるために、DeviceRenderMute イベントが発生したセッションの割合。 レンダーデバイスがミュートされました。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

