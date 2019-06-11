---
title: 'Lync Server 2013: AudioSignal テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6605a25191906660bbad11908f754a81360c893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Lync Server 2013 の AudioSignal テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-12_

各レコードは、1つのエンドポイントの音声シグナルメトリックを表します。 通常、各通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>アナログ高のゲイン制御オーディオ信号レベルを表します。 このメトリックの単位は dBmo です。 許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>「SendSignalLevel」をご覧ください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>アナログのゲイン制御オーディオノイズレベルを表します。 このメトリックの単位は dBmo です。 許容される品質には、35 dBmo よりも小さい値を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>「SendNoiseLevel」をご覧ください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>エコーリターンロスの拡張メトリック。 このメトリックの単位は dB です。 小さい値は、エコーが少なくなります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>スピーカーレンダリングに対する5分あたりの平均エラー。 品質を向上させるには、5分未満でなければなりません。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>マイクをキャプチャするための5分あたりの平均エラー。 品質を向上させるには、5分未満の値を指定する必要があります。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p> </p></td>
<td><p>CPU クロックを基準としたマイクデバイスクロックドリフトレート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p> </p></td>
<td><p>CPU クロックを基準としたスピーカーデバイスクロックドリフトレート。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p> </p></td>
<td><p>CPU クロックを基準としたスピーカーデバイスクロックドリフトレート。</p>
<p>平均マイクキャプチャストリームタイムスタンプエラー (ミリ秒単位)、通話の最後の20秒。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p> </p></td>
<td><p>通話の最後の20秒間の平均スピーカーレンダーストリームタイムスタンプエラー (ミリ秒単位)。</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses 原因</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>音声スイッチは半二重モードで、中断機能が低減されます。 音声スイッチの入力の原因:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>原因として、このような個々の原因が考えられます。 ENTER_VS_FORCEORCONVERGENCE は、テスト目的でのみ、regkey で有効にすることができます。</p>
<p>この列のデータ型は、Microsoft Lync Server 2013 で変更されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>エコーイベントの原因:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>原因として、このような個々の原因が考えられます。</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p> </p></td>
<td><p>マイクのキャプチャストリームでエコーが検出された時間の割合。 一般的に、ヘッドセットまたはハンドセットの値は低く、スピーカーフォンやスタンドアロンスピーカーでは高くなります。 オンボード音響エコーキャンセルをサポートしているデバイスでは、高値を指定するとエコーリークが発生します。 その他のデバイスでは、デバイスの品質を評価するためにこのメトリックを使用しないようにする必要があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>送信ストリームでエコーが検出された時間のパーセンテージ。 送信ストリームでのエコー率が高いと、エコーが発生したことを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ゲートウェイからの仲介サーバー上の受信したシグナルレベル。これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲は [-30 ~-18] の dBoV にする必要があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ゲートウェイからの仲介サーバーで受信したシグナルレベル。 これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲として 50 dBoV 未満の値を指定する必要があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>仲介サーバー側の自動ゲイン制御 (AGC)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>通話の最初の30秒以内の着信シグナルのルート平均平方根 (RMS)。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル1で受信したシグナルレベル。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル2で受信したシグナルレベル。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル1で受信したノイズレベル。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル2で受信したノイズレベル。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル1で送信されたシグナルレベル。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル2で送信されたシグナルレベル。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャネル1で送信されたノイズレベル。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>チャンネル2に送信されたノイズレベル。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

