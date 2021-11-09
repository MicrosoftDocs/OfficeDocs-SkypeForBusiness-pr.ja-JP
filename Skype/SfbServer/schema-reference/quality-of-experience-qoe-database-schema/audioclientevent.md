---
title: AudioClientEvent テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 各レコードには、オーディオ通話で 1 つのエンドポイントのクライアント イベントが含まれる。 通常、1 つの呼び出しには、呼び出し元用と呼び出し先用の 2 つのレコードがあります。
ms.openlocfilehash: e51146211567af3abfe68fdc415814d433e84884
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843650"
---
# <a name="audioclientevent-table"></a>AudioClientEvent テーブル
 
各レコードには、オーディオ通話で 1 つのエンドポイントのクライアント イベントが含まれる。 通常、1 つの呼び出しには、呼び出し元用と呼び出し先用の 2 つのレコードがあります。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |ビット  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 発信者のデータ  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |NetworkSendQuality イベントが "Bad" 状態で発生したセッションの割合。  <br/> ジッターやパケット損失に関するネットワーク品質は重大であり、送信されるオーディオの品質に影響を与えます。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |ReceiveSendQuality イベントが "Bad" 状態で発生したセッションの割合。  <br/> ジッターやパケット損失に関するネットワーク品質は重大であり、受信されるオーディオの品質に影響を与えます。  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |遅延イベントが 'Bad' 状態で発生したセッションの割合。 ネットワークの待ち時間は重大であり、対話的な通信を防止することでエクスペリエンスに影響を与えます  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |LowBandwidth イベントが 'Bad' 状態で発生したセッションの割合。 使用可能な帯域幅は、許容可能な音声エクスペリエンスでは不十分です。  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |不十分な CPU イベントが 'Bad' 状態に対して発生したセッションの割合。 現在のモダリティと使用されているアプリケーションで処理する CPU サイクルが不十分です。 これにより、オーディオ チャネルの歪みが発生します。  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceHalfDuplexAEC イベントが "Bad" 状態で発生したセッションの割合。 エコーを防止するために、システムは半二重に入っています。  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceRenderNotFunctioning イベントが 'Bad' 状態で発生したセッションの割合。 セッションに現在使用されているレンダー デバイスが正しく機能していません。 これにより、一方通行のオーディオの問題が発生する可能性があります。  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceCaptureNotFunctioning イベントが 'Bad' 状態で発生したセッションの割合。 セッションに現在使用されているキャプチャ デバイスが正しく機能していません。 これにより、一方通行のオーディオの問題が発生する可能性があります。  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceGlitches イベントが "Bad" 状態で発生したセッションの割合。 オーディオのレンダリングに重大な不具合が発生し、歪みが発生しています。 これらの不具合は、ドライバーの問題、遅延プロシージャ呼び出し (DPC) ストーム (ドライバー)、CPU 使用率の高さによって発生する可能性があります。  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceLowSNR イベントが "Bad" 状態で発生したセッションの割合。 キャプチャの品質は非常に低く、非常にノイズが多いか、ユーザーがマイクから離れすぎて話しています。 これにより、歪みが発生します。  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceLowSpeechLevel イベントが "Bad" 状態で発生したセッションの割合。 ユーザーの音声レベルが低すぎると、システムはそれ以上増加できません。 これは、歪みの原因となるか、一方通行オーディオとして認識される可能性があります。  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |DeviceClipping イベントが "Bad" 状態で発生したセッションの割合。  <br/> 近端の音声がマイクをクリップすると、クリッピングによる歪みが聞こえます。 近端マイクのクリッピングを回避することが重要です。  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceEchoEvent イベントが "Bad" 状態で発生したセッションの割合。 デバイスまたはセットアップによって、システムの補正機能を超えたエコーが発生しています。  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceNearEndToEchoRatio イベントが 'Bad' 状態で発生したセッションの割合。 ユーザーの音声はキャプチャされるエコーと比較して低すぎます。これは、ユーザーエクスペリエンスに影響を与えるので、ユーザーを中断する方法が制限されます。 スピーカーの音量を小さめ、マイクを話し手の近くに移動します。  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||セッション中に DeviceMultipleEndpoints イベントが "Bad" 状態で発生した回数。 同じセッション内の複数のオーディオ エンドポイントが検出され、システムはレンダリングボリュームを減らすことで補正されています。  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |セッション中に DeviceHowlingEvent イベントが "Bad" 状態で発生した回数。 オーディオ フィードバック ループが検出されました (オーディオ パスを共有する複数のエンドポイントが原因)。  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||DeviceRenderZeroVolume イベントが "Bad" 状態で発生したセッションの割合。 レンダー デバイスは、ボリュームが 0 に設定されています。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||DeviceRenderMute イベントが "Bad" 状態で発生したセッションの割合。 レンダー デバイスがミュートされました。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

