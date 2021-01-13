---
title: AudioClientEvent テーブル
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
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 各レコードには、オーディオ呼び出しの 1 つのエンドポイントのクライアント イベントが含まれる。 通常、1 つの呼び出しには、呼び出し元用と呼び出し先用の 2 つのレコードがあります。
ms.openlocfilehash: f5211d7f4ec3bc1d366d97def06edd325c448def
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809687"
---
# <a name="audioclientevent-table"></a>AudioClientEvent テーブル
 
各レコードには、オーディオ呼び出しの 1 つのエンドポイントのクライアント イベントが含まれる。 通常、1 つの呼び出しには 2 つのレコードがあります。1 つは呼び出し元用で、もう 1 つは呼び出し先用です。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 発信者のデータ  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |NetworkSendQuality イベントが "Bad" 状態で発生したセッションの割合。  <br/> ジッターやパケット損失の観点から見たネットワーク品質は重大であり、送信される音声の品質に影響を与えます。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |ReceiveSendQuality イベントが "Bad" 状態で発生したセッションの割合。  <br/> ジッターやパケット損失の観点から見たネットワーク品質は重大であり、受信する音声の品質に影響を与えます。  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Delay イベントが "Bad" 状態で発生したセッションの割合。 ネットワーク待機時間は重大であり、対話型通信を防止することでエクスペリエンスに影響を与えます。  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |LowBandwidth イベントが "Bad" 状態で発生したセッションの割合。 使用可能な帯域幅は、許容できる音声エクスペリエンスには不十分です。  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |"Bad" 状態に対して十分な CPU イベントが発生したセッションの割合。 現在のモダリティとアプリケーションを使用して処理する CPU サイクルが不十分です。 これにより、オーディオ チャネルにゆがみが生じる原因です。  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceHalfDuplexAEC イベントが "Bad" 状態で発生したセッションの割合。 エコーを防止するために、システムは半二重に入っています。  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceRenderNotFunctioning イベントが "Bad" 状態で発生したセッションの割合。 セッションに現在使用されているレンダー デバイスが正しく機能していません。 これにより、一方通行のオーディオの問題が発生する可能性があります。  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceCaptureNotFunctioning イベントが "Bad" 状態で発生したセッションの割合。 セッションに現在使用されているキャプチャ デバイスが正しく機能していません。 これにより、一方通行のオーディオの問題が発生する可能性があります。  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceGlitches イベントが "Bad" 状態で発生したセッションの割合。 オーディオのレンダリングに重大な障害が発生し、ゆがみを引き起こしています。 これらの障害は、ドライバーの問題、遅延プロシージャ コール (DPC) のストーマー (ドライバー)、および CPU 使用率の高さによって発生する可能性があります。  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceLowSNR イベントが "Bad" 状態で発生したセッションの割合。 キャプチャ品質が非常に低く、非常にノイズが高い、またはユーザーがマイクから離れすぎて話している。 これにより、ゆがみが生じる可能性があります。  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceLowSpeechLevel イベントが "Bad" 状態で発生したセッションの割合。 ユーザーの音声レベルが低すぎるので、システムはそれ以上音声レベルを上げできません。 これにより、ゆがみの原因となるか、一方通行のオーディオとして認識される可能性があります。  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |DeviceClipping イベントが "Bad" 状態で発生したセッションの割合。  <br/> 近端音声がマイクをクリッピングすると、クリッピングによるゆがみが聞こえます。 近端マイクのクリッピングを回避することが重要です。  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceEchoEvent イベントが "Bad" 状態で発生したセッションの割合。 デバイスまたはセットアップによって、システムが補正する機能を超えるエコーが発生しています。  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceNearEndToEchoRatio イベントが "Bad" 状態で発生したセッションの割合。 ユーザーの音声はキャプチャされるエコーに比べて低すぎるので、ユーザーエクスペリエンスに影響を与えるのは、ユーザーを中断する簡単さが制限されるからです。 スピーカーの音量を小さめ、話し手の近くにマイクを移動します。  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||セッション中に DeviceMultipleEndpoints イベントが "Bad" 状態で発生した回数。 同じセッション内の複数のオーディオ エンドポイントが検出され、システムはレンダー ボリュームを減らすことで問題を引き受けしました。  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |セッション中に DeviceHowlingEvent イベントが "Bad" 状態で発生した回数。 音声フィードバック ループが検出されました (オーディオ パスを共有する複数のエンドポイントによって発生します)。  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||DeviceRenderZeroVolume イベントが "Bad" 状態で発生したセッションの割合。 レンダー デバイスはゼロ ボリュームに設定されています。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||DeviceRenderMute イベントが "Bad" 状態で発生したセッションの割合。 レンダー デバイスがミュートされました。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
   

