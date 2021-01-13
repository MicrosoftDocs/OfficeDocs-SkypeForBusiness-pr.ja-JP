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
description: 各レコードは、1 つのエンドポイントのオーディオ信号メトリックを表します。 通常、各呼び出しには 2 つのレコードがあります。1 つは呼び出し元用で、もう 1 つは呼び出し先用です。
ms.openlocfilehash: ab918941357b85c6bcb25dcbaeb93a7be9c55f2d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809657"
---
# <a name="audiosignal-table"></a>AudioSignal テーブル
 
各レコードは、1 つのエンドポイントのオーディオ信号メトリックを表します。 通常、各呼び出しには 2 つのレコードがあります。1 つは呼び出し元用で、もう 1 つは呼び出し先用です。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 発信者のデータ  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |アナログ後ゲイン制御オーディオ信号レベルを表します。 この測定指標の単位は dBmo です。 許容される品質は 30 dBmo 以上です。 この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |「SendSignalLevel」を参照してください。  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |アナログ後ゲイン制御のオーディオ ノイズ レベルを表します。 この測定指標の単位は dBmo です。 許容される品質は 35 dBmo 未満です。 この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |「SendNoiseLevel」を参照してください。  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Echo Return Loss Enhancement 指標。 この測定指標の単位は dB です。 値が小さいほど、エコーが少ないことを示します。 この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |ラウドスピーカーのレンダリングに対する 5 分間の平均不具合。 良好な品質といえるのは、5 分間に 1 回未満です。 音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |マイク キャプチャの 5 分間の平均不具合。 良好な品質といえるのは、5 分間に 1 回未満です。 音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |CPU クロックに対するマイク デバイスのクロック の周波数の流れ速度。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |CPU クロックに対するスピーカー デバイスのクロック の周波数の流れ速度。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |CPU クロックに対するスピーカー デバイスのクロック の周波数の流れ速度。  <br/> 過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |通話の最後の 20 秒間の平均スピーカー レンダリング ストリーム タイム スタンプ エラー (ミリ秒単位)。  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |音声スイッチは、遮断能力が低下した半二重モードです。 音声切り替えエントリの原因:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> 原因は、これらの個々の原因の組み合わせである可能性があります。 ENTER_VS_FORCEORCONVERGENCEは、テスト目的のレジストリ キーでのみ有効にできます。  <br/> この列のデータ型は、Microsoft Lync Server 2013 で変更されました。  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |エコー イベントの原因:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> 原因は、これらの個々の原因の組み合わせである可能性があります。  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |マイク キャプチャ ストリームでエコーが検出された時間の割合。 通常、ヘッドセットやハンドセットの値は低く、スピーカーフォンやスタンドアロンスピーカーの場合は高くなります。 ボード上のアコースティック エコー キャンセルをサポートするデバイスの場合、高い値はエコー リークを示します。 その他のデバイスでは、この指標を使用してデバイスの品質を評価する必要があります。  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||送信ストリームでエコーが検出された時間の割合。 送信ストリームでの高いエコー率は、エコー リークを示しています。  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |ゲートウェイからの仲介サーバーでの受信信号レベルこれは仲介サーバーにのみ適用されます。 この測定指標の単位は dBoV です。 良好な品質を得る場合、許容される範囲は dBoV [-30 ~ -18] である必要があります。  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |ゲートウェイからの仲介サーバーでの受信信号レベル。 この値は、仲介サーバーに対してのみ適用されます。 この測定指標の単位は dBoV です。 良好な品質として許容される範囲は、-50 dBoV 未満です。  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |仲介サーバー側の自動ゲイン制御 (AGC)。  <br/> |
|**InitialSignalLevelRMS** <br/> |浮動小数点数  <br/> | <br/> |呼び出しの最初の 30 秒までの着信信号のルート平均平方根 (RMS)。  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||チャネル 1 で受信した信号レベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||チャネル 2 で受信した信号レベル。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||チャネル 1 で受信したノイズ レベル。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||チャネル 2 で受信したノイズ レベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||チャネル 1 で送信される信号レベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||チャネル 2 で送信される信号レベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||チャネル 1 で送信されるノイズ レベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||チャネル 2 で送信されるノイズ レベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||再生用のスピーカーに送信される信号の dBFS レベル。 受信信号に加えるゲイン調整を行います。 <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||再生のためにスピーカーに送信される信号のノイズ コンテンツの dBFS レベル <br/> |

