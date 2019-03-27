---
title: AudioSignal テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 各レコードは、1 つのエンドポイントのオーディオ信号の測定値を表します。 通常、各呼び出しには、2 つのレコードが含まれています、1 に対して、呼び出し元、呼び出し先の 1 つは、です。
ms.openlocfilehash: 7a064f13b6f34f61dcfb72169a4b1620cd81b01f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895119"
---
# <a name="audiosignal-table"></a>AudioSignal テーブル
 
各レコードは、1 つのエンドポイントのオーディオ信号の測定値を表します。 通常、各呼び出しには、2 つのレコードが含まれています、1 に対して、呼び出し元、呼び出し先の 1 つは、です。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 呼び出し元のデータ  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |ゲイン制御の後のアナログ オーディオ信号のレベルを表します。 この指標の単位は、dBmo です。 許容可能な品質には、30 台以上の dBmo をする必要があります。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |SendSignalLevel を参照してください。  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |ゲイン制御の後のアナログ オーディオのノイズのレベルを表します。 この指標の単位は、dBmo です。 許容可能な品質には、35 未満の dBmo をする必要があります。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |SendNoiseLevel を参照してください。  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |エコーを返すが失われる拡張機能の指標です。 この指標の単位は、dB です。 低い値では、以下のエコーを表します。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |ラウド スピーカーのレンダリングに 5 分ごとの平均故障します。 高品質は、5 分ごとに 1 つより小さいするこの必要があります。 A によって報告されていないと、音声ビデオ会議サーバー、仲介サーバー、または IP 電話です。  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |マイクのキャプチャ用の 5 分間あたりの平均故障。 高品質のこの必要があります 5 分ごとに 1 回未満です。 A によって報告されていないと、音声ビデオ会議サーバー、仲介サーバー、または IP 電話です。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |マイク デバイスの時計のズレ、CPU のクロックを基準にしています。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |スピーカー デバイスの時計のズレ、CPU のクロックを基準にしています。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |スピーカー デバイスの時計のズレ、CPU のクロックを基準にしています。  <br/> マイク キャプチャ ストリーム タイム スタンプ エラー、ミリ秒単位での呼び出しの最後の 20 秒間の平均します。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |平均のスピーカーでは、呼び出しの最後の 20 秒間 (ミリ秒単位) のストリーム タイム スタンプ エラーをレンダリングします。  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |ボイス スイッチは、中断を削減できると半二重モードです。 声の原因は、エントリを切り替えます。  <br/> ENTER_VS_BADTS 0X01  <br/> ENTER_VS_ECHO 0X02  <br/> ENTER_VS_FORCEORCONVERGENCE 0X04  <br/> ENTER_VS_DNLP 0X08  <br/> 原因は、これらの個々 の原因の組み合わせです。 ENTER_VS_FORCEORCONVERGENCE は、レジストリ キーはテスト目的でのみ有効にすることができます。  <br/> Microsoft Lync Server 2013 では、この列のデータ型が変更されました。  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |エコー イベントの原因。  <br/> ECHO_EVENT_BAD_TIMESTAMP 0X01  <br/> ECHO_EVENT_POSTAEC_ECHO 0X02  <br/> ECHO_EVENT_ANLP 0X04  <br/> ECHO_EVENT_DNLP 0X08  <br/> ECHO_EVENT_MIC_CLIPPING 0X10  <br/> ECHO_EVENT_BAD_STATE 0X20  <br/> 原因は、これらの個々 の原因の組み合わせです。  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |エコーがマイク キャプチャ ストリームで検出された場合の時間の割合。 通常、値は、ヘッドセットやハンドセット、低以上スピーカー フォンまたはスタンドアロンのスピーカー。 内蔵型のアコースティック エコー キャンセレーションをサポートしているデバイスでは、高の値は、エコーのリークを示します。 その他のデバイスでは、この指標がないデバイスの品質を評価するために使用してください。  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||エコーが検出された場合の時間の割合は、ストリームを送信します。 高エコーのパーセンテージでは、エコー リークを示す値をストリームに送信します。  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |ゲートウェイから仲介サーバー上の信号レベルを受信しました。これは、仲介サーバーにのみ適用されます。 DBoV は、この測定の単位です。 高品質、適正範囲をする必要があります [-18 に-30] dBoV です。  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |ゲートウェイから仲介サーバーで受信した信号レベルです。 これは、仲介サーバーにのみ適用されます。 DBoV は、この測定の単位です。 高品質は、許容範囲はより小さい-50 dBoV をする必要があります。  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |自動では、仲介サーバー側のコントロール (AGC) を取得します。  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |平均平方根 (RMS) の呼び出しの最初の 30 秒までの入力信号の。  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||チャネル 1 の受信時の信号レベルです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||2 チャンネルの受信時の信号レベルです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||チャネル 1 の受信時のノイズ レベルです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||2 チャンネルの受信時のノイズ レベルです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||信号レベル 1 のチャネルで送信されるとします。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||信号レベル 2 のチャネルで送信されるとします。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||ノイズのレベル 1 のチャネルで送信されるとします。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||ノイズのレベル 2 のチャネルで送信されるとします。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||再生用のスピーカーに送信する信号の dBFS のレベルです。 ゲインの調整が受信した信号に加えられたすべてのアカウントです。 <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||DBFS の再生用のスピーカーに送信する信号のノイズのコンテンツのレベルします。 <br/> |

