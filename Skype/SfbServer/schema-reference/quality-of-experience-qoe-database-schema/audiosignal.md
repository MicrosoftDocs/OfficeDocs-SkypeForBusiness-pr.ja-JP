---
title: AudioSignal テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 各レコードは、1 つのエンドポイントのオーディオ信号メトリックを表します。 通常、各呼び出しには 2 つのレコードが含まれます。1 つは発信者用で、1 つは呼び出し先用です。
ms.openlocfilehash: 36ece4a9481400c3fae9e248d00cc59f3ec161b21aa03d8e824fc4d21931d04f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309206"
---
# <a name="audiosignal-table"></a>AudioSignal テーブル
 
各レコードは、1 つのエンドポイントのオーディオ信号メトリックを表します。 通常、各呼び出しには 2 つのレコードが含まれます。1 つは発信者用で、1 つは呼び出し先用です。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |整数  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |ビット  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 発信者のデータ  <br/> |
|**SendSignalLevel** <br/> |整数  <br/> | <br/> |アナログ後ゲインコントロールのオーディオ信号レベルを表します。 この測定指標の単位は dBmo です。 許容される品質は 30 dBmo 以上です。 この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|**RecvSignalLevel** <br/> |整数  <br/> | <br/> |「SendSignalLevel」を参照してください。  <br/> |
|**SendNoiseLevel** <br/> |整数  <br/> | <br/> |アナログゲイン制御後のオーディオ ノイズ レベルを表します。 この測定指標の単位は dBmo です。 許容される品質は 35 dBmo 未満です。 この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|**RecvNoiseLevel** <br/> |整数  <br/> | <br/> |「SendNoiseLevel」を参照してください。  <br/> |
|**EchoReturn** <br/> |整数  <br/> | <br/> |Echo Return Loss Enhancement メトリック。 この測定指標の単位は dB です。 値が小さいほど、エコーが少ないことを示します。 この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |整数  <br/> | <br/> |ラウドスピーカー レンダリングの 5 分あたりの平均グリッチ。 良好な品質といえるのは、5 分間に 1 回未満です。 音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。  <br/> |
|**AudioMicGlitchRate** <br/> |整数  <br/> | <br/> |マイク キャプチャの 5 分あたりの平均グリッチ。 良好な品質といえるのは、5 分間に 1 回未満です。 音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |CPU クロックに対するマイク デバイスのクロックドリフトレート。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |スピーカー デバイスのクロック ドリフトレート (CPU クロックに対する)。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |スピーカー デバイスのクロック ドリフトレート (CPU クロックに対する)。  <br/> 過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |通話の最後の 20 秒の平均スピーカー レンダリング ストリーム タイムスタンプ エラー (ミリ秒単位)。  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |音声スイッチは、遮断能力が低下した半二重モードです。 音声切り替えエントリの原因:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> 原因は、個々の原因の組み合わせである可能性があります。 ENTER_VS_FORCEORCONVERGENCEは、テスト目的で regkey によってのみ有効にできます。  <br/> この列のデータ型は、Microsoft Lync Server 2013 で変更されました。  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |エコー イベントの原因:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> 原因は、個々の原因の組み合わせである可能性があります。  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |マイク キャプチャ ストリームでエコーが検出された時間の割合。 通常、ヘッドセットやハンドセットの値は低く、スピーカー電話やスタンドアロン スピーカーの場合は高くなります。 ボード上の音響エコーキャンセルをサポートするデバイスの場合、高い値はエコー リークを示します。 他のデバイスでは、この指標を使用してデバイスの品質を評価する必要があります。  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||送信ストリームでエコーが検出された時間の割合。 送信ストリームでの高いエコー率は、エコー リークを示しています。  <br/> |
|**RxAGCSignalLevel** <br/> |整数  <br/> | <br/> |ゲートウェイから仲介サーバーで受信した信号レベル。これは仲介サーバーにのみ適用されます。 この測定指標の単位は dBoV です。 良好な品質を得る場合、許容範囲は [-30 ~ -18] dBoV である必要があります。  <br/> |
|**RxAGCNoiseLevel** <br/> |整数  <br/> | <br/> |ゲートウェイから仲介サーバーで受信した信号レベル。 この値は、仲介サーバーに対してのみ適用されます。 この測定指標の単位は dBoV です。 良好な品質として許容される範囲は、-50 dBoV 未満です。  <br/> |
|**RxAvgAGCGain** <br/> |整数  <br/> | <br/> |仲介サーバー側の自動ゲイン制御 (AGC)。  <br/> |
|**InitialSignalLevelRMS** <br/> |浮動小数点数  <br/> | <br/> |呼び出しの最初の 30 秒までの着信信号の平均平方根 (RMS)。  <br/> |
|**RecvSignalLevelCh1** <br/> |整数  <br/> ||チャネル 1 で受信した信号レベル。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvSignalLevelCh2** <br/> |整数  <br/> ||チャネル 2 で受信した信号レベル。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvNoiseLevelCh1** <br/> |整数  <br/> ||チャネル 1 で受信したノイズ レベル。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvNoiseLevelCh2** <br/> |整数  <br/> ||チャネル 2 で受信したノイズ レベル。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendSignalLevelCh1** <br/> |整数  <br/> ||チャネル 1 で送信されるシグナル レベル。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendSignalLevelCh2** <br/> |整数  <br/> ||チャネル 2 で送信されるシグナル レベル。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendNoiseLevelCh1** <br/> |整数  <br/> ||チャネル 1 で送信されるノイズ レベル。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendNoiseLevelCh2** <br/> |整数  <br/> ||チャネル 2 で送信されるノイズ レベル。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RenderLoopbackSignalLevel** <br/> |整数  <br/> ||再生のために拡声器に送信される信号の dBFS のレベル。 受信信号に対して行われたゲイン調整をアカウントに設定します。 <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |   
|**RenderNoiseLevel** <br/> |整数  <br/> ||再生のために拡声器に送信される信号内のノイズ コンテンツの dBFS のレベル <br/> |

