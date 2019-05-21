---
title: AudioSignal テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 各レコードは、1つのエンドポイントの音声シグナルメトリックを表します。 通常、各通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。
ms.openlocfilehash: f8d617e96fe3427493bcb9e4cc70008fedae72e7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295077"
---
# <a name="audiosignal-table"></a>AudioSignal テーブル
 
各レコードは、1つのエンドポイントの音声シグナルメトリックを表します。 通常、各通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 発信者のデータ  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |アナログ高のゲイン制御オーディオ信号レベルを表します。 このメトリックの単位は dBmo です。 許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |「SendSignalLevel」をご覧ください。  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |アナログのゲイン制御オーディオノイズレベルを表します。 このメトリックの単位は dBmo です。 許容される品質には、35 dBmo よりも小さい値を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |「SendNoiseLevel」をご覧ください。  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |エコーリターンロスの拡張メトリック。 このメトリックの単位は dB です。 小さい値は、エコーが少なくなります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |スピーカーレンダリングに対する5分あたりの平均エラー。 品質を向上させるには、5分未満でなければなりません。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |マイクをキャプチャするための5分あたりの平均エラー。 品質を向上させるには、5分未満の値を指定する必要があります。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |10進数 (9, 2)  <br/> | <br/> |CPU クロックを基準としたマイクデバイスクロックドリフトレート。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |10進数 (9, 2)  <br/> | <br/> |CPU クロックを基準としたスピーカーデバイスクロックドリフトレート。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |10進数 (9, 2)  <br/> | <br/> |CPU クロックを基準としたスピーカーデバイスクロックドリフトレート。  <br/> 平均マイクキャプチャストリームタイムスタンプエラー (ミリ秒単位)、通話の最後の20秒。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |10進数 (9, 2)  <br/> | <br/> |通話の最後の20秒間の平均スピーカーレンダーストリームタイムスタンプエラー (ミリ秒単位)。  <br/> |
|**VsEntryCauses 原因** <br/> |smallint  <br/> | <br/> |音声スイッチは半二重モードで、中断機能が低減されます。 音声スイッチの入力の原因:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> 原因として、このような個々の原因が考えられます。 ENTER_VS_FORCEORCONVERGENCE は、テスト目的でのみ、regkey で有効にすることができます。  <br/> この列のデータ型は、Microsoft Lync Server 2013 で変更されました。  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |エコーイベントの原因:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> 原因として、このような個々の原因が考えられます。  <br/> |
|**EchoPercentMicIn** <br/> |10進数 (5, 2)  <br/> | <br/> |マイクのキャプチャストリームでエコーが検出された時間の割合。 一般的に、ヘッドセットまたはハンドセットの値は低く、スピーカーフォンやスタンドアロンスピーカーでは高くなります。 オンボード音響エコーキャンセルをサポートしているデバイスでは、高値を指定するとエコーリークが発生します。 その他のデバイスでは、デバイスの品質を評価するためにこのメトリックを使用しないようにする必要があります。  <br/> |
|**EchoPercentSend** <br/> |10進数 (5, 2)  <br/> ||送信ストリームでエコーが検出された時間のパーセンテージ。 送信ストリームでのエコー率が高いと、エコーが発生したことを示します。  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |ゲートウェイからの仲介サーバー上の受信したシグナルレベル。これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲は [-30 ~-18] の dBoV にする必要があります。  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |ゲートウェイからの仲介サーバーで受信したシグナルレベル。 これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲として 50 dBoV 未満の値を指定する必要があります。  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |仲介サーバー側の自動ゲイン制御 (AGC)。  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |通話の最初の30秒以内の着信シグナルのルート平均平方根 (RMS)。  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||チャネル1で受信したシグナルレベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||チャネル2で受信したシグナルレベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||チャネル1で受信したノイズレベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||チャネル2で受信したノイズレベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||チャネル1で送信されたシグナルレベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||チャネル2で送信されたシグナルレベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||チャネル1で送信されたノイズレベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||チャンネル2に送信されたノイズレベル。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||再生のためにスピーカーに送信されたシグナルの dBFS レベル。 受信した信号に対するゲイン調整用のアカウント。 <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||再生のためにスピーカーに送信されるシグナル内のノイズコンテンツの dBFS レベル <br/> |

