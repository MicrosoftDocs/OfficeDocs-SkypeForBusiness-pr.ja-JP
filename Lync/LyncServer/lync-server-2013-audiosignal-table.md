---
title: 'Lync Server 2013: AudioSignal テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d7dcf9337dceded96679411e575abc888164618
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Lync Server 2013 の AudioSignal テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-12_

各レコードは、1つのエンドポイントの音声信号指標を表します。 通常、それぞれの呼び出しには2つのレコードがあります。1つは発信者用、もう1つは呼び出し先用です。


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>アナログのゲイン制御音声信号レベルを表します。 この測定指標の単位は dBmo です。 許容される品質は 30 dBmo 以上です。 この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>SendSignalLevel を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>アナログのゲインコントロールのオーディオノイズレベルを表します。 この測定指標の単位は dBmo です。 許容される品質は 35 dBmo 未満です。 この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>SendNoiseLevel を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>エコーリターン損失の拡張指標。 この測定指標の単位は dB です。 値が小さいほど、エコーが少ないことを示します。 この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Loudspeaker レンダリングの5分あたりの平均の異常。 良好な品質といえるのは、5 分間に 1 回未満です。 音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>マイクキャプチャに対する5分あたりの平均の異常。 良好な品質といえるのは、5 分間に 1 回未満です。 音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>10進数 (9、2)</p></td>
<td><p> </p></td>
<td><p>CPU クロックに対するマイクデバイスのクロック誤差の割合です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>10進数 (9、2)</p></td>
<td><p> </p></td>
<td><p>CPU クロックに対するスピーカーデバイスのクロック誤差の割合。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>10進数 (9、2)</p></td>
<td><p> </p></td>
<td><p>CPU クロックに対するスピーカーデバイスのクロック誤差の割合。</p>
<p>過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>10進数 (9、2)</p></td>
<td><p> </p></td>
<td><p>過去20秒間の通話の平均スピーカーレンダーストリームタイムスタンプエラー (ミリ秒単位)。</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>音声スイッチは、遮断能力が低下した半二重モードです。 音声スイッチエントリの原因:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>原因として、個々の原因の組み合わせが考えられます。 ENTER_VS_FORCEORCONVERGENCE は、テストの目的でのみ、レジストリキーを使用して有効にすることができます。</p>
<p>この列のデータ型は、Microsoft Lync Server 2013 で変更されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Echo イベントの原因:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>原因として、個々の原因の組み合わせが考えられます。</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td><p> </p></td>
<td><p>マイクキャプチャストリームでエコーが検出された時間の割合。 通常、ヘッドホンまたはハンドセットの値は低く、スピーカーフォンまたはスタンドアロンスピーカーでは高です。 オンボード音響エコーキャンセレーションをサポートするデバイスでは、値が大きいと、エコーリークが発生します。 その他のデバイスでは、この指標を使用してデバイスの品質を評価することはできません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td></td>
<td><p>送信されたストリームでエコーが検出された時間の割合。 送信ストリームでの高いエコー率は、エコー リークを示しています。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ゲートウェイからの仲介サーバーの受信した信号レベル。これは、仲介サーバーにのみ適用されます。 この測定指標の単位は dBoV です。 品質を良くするには、許容範囲は [-30 ~-18] dBoV にする必要があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ゲートウェイからの仲介サーバー上の受信した信号レベル。 この値は、仲介サーバーに対してのみ適用されます。 この測定指標の単位は dBoV です。 良好な品質として許容される範囲は、-50 dBoV 未満です。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>仲介サーバー側での自動ゲイン制御 (AGC)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>浮動小数点数</p></td>
<td><p> </p></td>
<td><p>通話の最初の最大30秒間の着信信号のルート平均二乗 (RMS)。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル1で受信したシグナルレベル。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル2で受信したシグナルレベル。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル1で受信したノイズレベル。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル2で受信したノイズレベル。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル1で送信されたシグナルレベル。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル2で送信されたシグナルレベル。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル1で送信されたノイズレベル。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル2で送信されたノイズレベル。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

