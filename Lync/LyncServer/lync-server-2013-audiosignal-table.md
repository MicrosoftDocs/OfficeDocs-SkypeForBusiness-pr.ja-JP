---
title: 'Lync Server 2013: AudioSignal テーブル'
TOCTitle: AudioSignal テーブル
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48271050
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の AudioSignal テーブル

 

_**トピックの最終更新日:** 2015-03-09_

各レコードは、1 つのエンドポイントのオーディオ信号測定指標を表します。通常は、通話ごとに、呼び出し元と呼び出し先に対する 2 つのレコードが作成されます。


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>アナログ後ゲイン制御のオーディオ信号レベルを表します。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>SendSignalLevel を参照。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>アナログ後ゲイン制御のオーディオ ノイズ レベルを表します。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>SendNoiseLevel を参照。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>エコー リターン ロス エンハンスメントの測定指標です。この測定指標の単位は dB です。値が小さいほど、エコーが少ないことを示します。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ラウドスピーカー出力での 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>マイク キャプチャでの 5 分間の平均障害回数です。良好な品質といえるのは、5 分間に 1 回未満です。音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>decimal(9.2)</p></td>
<td><p> </p></td>
<td><p>CPU クロックに対するマイク デバイスのクロック誤差の割合です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>decimal(9.2)</p></td>
<td><p> </p></td>
<td><p>CPU クロックに対するスピーカー デバイスのクロック誤差の割合です。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>decimal(9.2)</p></td>
<td><p> </p></td>
<td><p>CPU クロックに対するスピーカー デバイスのクロック誤差の割合です。</p>
<p>過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>decimal(9.2)</p></td>
<td><p> </p></td>
<td><p>過去 20 秒間の通話での平均スピーカー出力ストリーム タイム スタンプ エラーです (ミリ秒単位)。</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>音声スイッチは、遮断能力が低下した半二重モードです。音声スイッチ エントリの原因は次のとおりです。</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>実際の原因は、これらの個別原因の組み合わせになっている場合があります。ENTER_VS_FORCEORCONVERGENCE はテストを目的として regkey によってのみ有効にできます。</p>
<p>この列のデータ型は、Microsoft Lync Server 2013 で変更されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>エコー イベントの原因です。</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>実際の原因は、これらの個別原因の組み合わせになっている場合があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p> </p></td>
<td><p>マイク キャプチャ ストリームでエコーが検出される時間の割合です。通常、ヘッドセットやハンドセットでは値が小さくなり、スピーカー フォンやスタンドアロンのスピーカーでは値が大きくなります。オンボードのアコーステック エコー キャンセレーションをサポートしているデバイスでの高い値は、エコー リークを示します。その他のデバイスでは、この指標をデバイス品質の評価に使用しないでください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p></p></td>
<td><p>送信ストリームでエコーが検出された時間の割合です。送信ストリームでの高いエコー率は、エコー リークを示しています。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>仲介サーバーでのゲートウェイからの受信信号レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-30 ～ -18 dBoV です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>仲介サーバーでのゲートウェイからの受信ノイズ レベルです。この値は、仲介サーバーに対してのみ適用されます。この測定指標の単位は dBoV です。良好な品質として許容される範囲は、-50 dBoV 未満です。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>仲介サーバー側での自動ゲイン制御 (AGC) です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>通話の最初の最大 30 秒間の着信信号の二重平均 (RMS) です。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>チャンネル 1 の受信信号レベル。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>チャンネル 2 の受信信号レベル。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>チャンネル 1 の受信ノイズ レベル。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>チャンネル 2 の受信ノイズ レベル。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>チャンネル 1 の送信信号レベル。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>チャンネル 2 の送信信号レベル。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>チャンネル 1 の送信ノイズ レベル。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>チャンネル 2 の送信ノイズ レベル。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>

