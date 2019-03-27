---
title: AudioClientEvent テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 各レコードには、オーディオの呼び出しで 1 つのエンドポイントのクライアント イベントが含まれています。 通常、1 回の呼び出しでは、2 つのレコード用の呼び出し元と呼び出し先の 1 つがあります。
ms.openlocfilehash: 307406446d71adf462cdc8a0345aa823129a8f99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895056"
---
# <a name="audioclientevent-table"></a>AudioClientEvent テーブル
 
各レコードには、オーディオの呼び出しで 1 つのエンドポイントのクライアント イベントが含まれています。 通常、1 回の呼び出しでは、2 つのレコード用の呼び出し元と呼び出し先の 1 つがあります。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 呼び出し元のデータ  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、NetworkSendQuality イベントが発生したセッションの割合です。  <br/> ジッターやパケット損失の点でネットワーク品質は重大な送信されているオーディオの品質に影響を与えるとします。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、ReceiveSendQuality イベントが発生したセッションの割合です。  <br/> ジッターまたはパケット損失の点でネットワークの品質は、重大な受信されているオーディオの品質に影響を与えるとします。  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'不良' 状態の遅延イベントが発生したセッションの割合です。 ネットワークの遅延が深刻な対話型の通信を防止することで操作性に影響を与えず、  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、LowBandwidth イベントが発生したセッションの割合です。 使用可能な帯域幅は、許容可能な音声操作のための十分ではありません。  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態に十分な CPU のイベントが発生したセッションの割合です。 現在の形式と使用中のアプリケーションの処理の不足のための CPU サイクルがあります。 オーディオ チャンネルを示すゆがみが発生します。  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、DeviceHalfDuplexAEC イベントが発生したセッションの割合です。 エコーを防止するためにシステムは半二重を入力します。  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、DeviceRenderNotFunctioning イベントが発生したセッションの割合です。 セッションで現在使用されているレンダリング デバイスが正しく機能していません。 これにより、一方向のオーディオの問題が発生することができます。  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、DeviceCaptureNotFunctioning イベントが発生したセッションの割合です。 セッションで現在使用されているキャプチャ デバイスが正しく機能していません。 これにより、一方向のオーディオの問題が発生することができます。  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、DeviceGlitches イベントが発生したセッションの割合です。 ゆがみの原因となっているオーディオのレンダリングでは、重大な問題があります。 ドライバーの問題、遅延プロシージャ呼び出し (DPC) 嵐 (ドライバー)、CPU 使用率が高く、これらの問題が起こります。  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、DeviceLowSNR イベントが発生したセッションの割合です。 キャプチャの品質は、非常に悪くなるか、非常に騒々しいか、ユーザーがマイクから遠すぎる話です。 ゆがみになります。  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、DeviceLowSpeechLevel イベントが発生したセッションの割合です。 ユーザーの音声レベルが低すぎると、システムことはできないこと、さらに増えています。 これは、ゆがみが発生することができますか、または一方向のオーディオとして認識します。  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、DeviceClipping イベントが発生したセッションの割合です。  <br/> 終了近くにある音声は、マイクをクリップ、遠端側はクリッピングのためのゆがみを聞くことです。 終了近くにあるマイクのクリッピングを避けることが重要です。  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、DeviceEchoEvent イベントが発生したセッションの割合です。 デバイスまたはセットアップのエコーを補正するためにシステムの機能以外では原因となっています。  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |'正しくない' の状態には、DeviceNearEndToEchoRatio イベントが発生したセッションの割合です。 ユーザーの音声が小さすぎると比較してユーザーを中断することが簡単な方法が制限されるため、ユーザー エクスペリエンスに影響を与えるキャプチャされているエコーします。 スピーカーの音量を減らす、話者にマイクを近くに移動します。  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||'正しくない' の状態は、DeviceMultipleEndpoints イベントが発生したセッション中に時間の数です。 検出された同一セッション内の複数のオーディオ エンドポイントとシステムが報酬を受け取るレンダリングのボリュームを減らすことによって。  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |'正しくない' の状態は、DeviceHowlingEvent イベントが発生したセッション中に時間の数です。 音声フィードバックのループが検出されました (オーディオ パスを共有する複数のエンドポイントによって発生) します。  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||なるは、DeviceRenderZeroVolume イベントが発生したセッションの割合、「不正な ' の状態です。 レンダリング デバイスは、ボリュームがゼロに設定されました。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||なるは、DeviceRenderMute イベントが発生したセッションの割合、「不正な ' の状態です。 レンダリング デバイスがミュートになっています。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

