---
title: 'Lync Server 2013: AudioClientEvent テーブル'
TOCTitle: AudioClientEvent テーブル
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48274167
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の AudioClientEvent テーブル

 

_**トピックの最終更新日:** 2015-03-09_

各レコードには、音声通話の 1 つのエンドポイントのクライアント イベントが格納されます。通常、1 件の通話に対して、発信者と呼び出し先の 2 つのレコードが存在します。


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
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>主/プライマリ</p></td>
<td><p>0: 呼び出し先のデータ</p>
<p>1: 呼び出し元のデータ</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して NetworkSendQuality イベントが発生したセッションの割合。</p>
<p>ジッターまたはパケット損失の面でネットワーク品質が厳しく、送信する音声の品質に影響します。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して ReceiveSendQuality イベントが発生したセッションの割合。</p>
<p>ジッターまたはパケット損失の面でネットワーク品質が厳しく、受信する音声の品質に影響します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して Delay イベントが発生したセッションの割合。ネットワーク待ち時間が厳しく、インタラクティブな通信が阻害されてエクスペリエンスに影響します。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して LowBandwidth イベントが発生したセッションの割合。帯域幅が不足しているために、満足のいく状態で音声を利用できません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して CPU 不足のイベントが発生したセッションの割合。現在のモダリティおよび使用中のアプリケーションを処理する CPU サイクルが不足しています。これは音声チャネルのひずみの原因になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して DeviceHalfDuplexAEC イベントが発生したセッションの割合。エコーを防ぐために、システムは半二重モードに入ります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して DeviceRenderNotFunctioning イベントが発生したセッションの割合。セッションで現在使用中のレンダー デバイスが正しく動作していません。一方向の音声の問題が発生する可能性があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して DeviceCaptureNotFunctioning イベントが発生したセッションの割合。セッションで現在使用中のキャプチャ デバイスが正しく動作していません。一方向の音声の問題が発生する可能性があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して DeviceGlitches イベントが発生したセッションの割合。音声のレンダリングに重大な異常があり、ひずみが発生しています。このような異常の原因となり得るのは、ドライバーの問題、遅延プロシージャ呼び出し (DPC) のストーム (ドライバー)、および高い CPU 使用率です。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して DeviceLowSNR イベントが発生したセッションの割合。キャプチャの品質が非常に低く、ノイズが非常に多いか、ユーザーがマイクから遠すぎる位置で話しているかのどちらかです。これはひずみの原因になります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して DeviceLowSpeechLevel イベントが発生したセッションの割合。ユーザーのスピーチ レベルが低すぎて、システムでこれ以上引き上げることができません。これはひずみの原因となるか、または一方向の音声として認識されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して DeviceClipping イベントが発生したセッションの割合。</p>
<p>近端のスピーチでマイクのクリッピングが生じると、遠端でクリッピングによるゆがみが発生します。近端のマイクのクリッピングを回避することが重要です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して DeviceEchoEvent イベントが発生したセッションの割合。デバイスまたはセットアップにより、システムの補正能力を超えるエコーが発生しています。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>'無効' な状態に対して DeviceNearEndToEchoRatio イベントが発生したセッションの割合。ユーザーのスピーチが、キャプチャされているエコーに比べて低すぎると、ユーザーへの割り込みのしやすさが制限され、ユーザーのエクスペリエンスに影響します。スピーカーのボリュームを下げ、マイクを発話者に近付けます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>セッション中に '無効' な状態に対して DeviceMultipleEndpoints イベントが発生した回数。同じセッション内で複数の音声エンドポイントが検出され、システムはレンダー ボリュームを落とすことにより補正しました。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>セッション中に '無効' な状態に対して DeviceHowlingEvent イベントが発生した回数。オーディオ フィードバック ループが検出されました (複数のエンドポイントによるオーディオ パスの共有が原因)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p></p></td>
<td><p>'無効' な状態に対して DeviceRenderZeroVolume イベントが発生したセッションの割合。レンダー デバイスはゼロ ボリュームに設定されました。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p></p></td>
<td><p>'無効' な状態に対して DeviceRenderZeroVolume イベントが発生したセッションの割合。レンダー デバイスはミュートに設定されました。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>

