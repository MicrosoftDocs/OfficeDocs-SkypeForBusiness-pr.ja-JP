---
title: AudioClientEvent テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 各レコードには、音声通話中の1つのエンドポイントのクライアントイベントが含まれています。 通常、1つの通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。
ms.openlocfilehash: 713804875f9cd2a1fc37a2255697c4ffda47a3c5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811085"
---
# <a name="audioclientevent-table"></a>AudioClientEvent テーブル
 
各レコードには、音声通話中の1つのエンドポイントのクライアントイベントが含まれています。 通常、1つの通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 発信者のデータ  <br/> |
|**NetworkSendQualityEventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ NetworkSendQuality イベントが ' Bad ' 状態に対して発生しました。  <br/> ネットワーク品質は、ジッタまたはパケット損失の観点から、送信された音声の品質に重大な影響を与えることがあります。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ ReceiveSendQuality イベントが ' Bad ' 状態で発生しました。  <br/> ネットワーク品質は、ジッタまたはパケット損失の観点から、受信中のオーディオの品質に深刻な影響を与えることができます。  <br/> |
|**NetworkDelayEventRatio スペック** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ "Bad" 状態に対して Delay イベントが発生しました。 ネットワーク待ち時間が重大であり、対話的なコミュニケーションを防ぐことで、エクスペリエンスに影響を与える  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ低帯域幅イベントが ' Bad ' 状態に対して発生しました。 利用可能な音声エクスペリエンスを実現するには、利用可能な帯域幅が不足しています。  <br/> |
|**CPUInsufficientEventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションの割合。不適切な CPU イベントが ' Bad ' 状態に対して発生しました。 現在使用中のモダリティとアプリケーションで処理するための CPU サイクルが十分にありません。 これにより、オーディオチャンネルでひずみが発生します。  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ DeviceHalfDuplexAEC イベントが ' Bad ' 状態で発生しました。 エコーを防ぐために、システムは半二重モードに設定されています。  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションの割合 DeviceRenderNotFunctioning イベントが ' Bad ' 状態に対して発生しました。 現在セッションで使用されているレンダーデバイスが正常に機能していません。 これにより、1方向の音声の問題が発生する可能性があります。  <br/> |
|**DeviceCaptureNotFunctioningEventRatio 使い方** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ DeviceCaptureNotFunctioning イベントが ' Bad ' 状態に対して発生しました。 現在セッションで使用されているキャプチャデバイスが正常に機能していません。 これにより、1方向の音声の問題が発生する可能性があります。  <br/> |
|**DeviceGlitchesEventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションの割合 DeviceGlitches イベントが ' Bad ' 状態で発生しました。 オーディオのレンダリングで、ひずみの原因となる重大な問題が発生します。 これらのエラーは、ドライバーの問題、遅延プロシージャ呼び出し (DPC) ストーム (ドライバー)、および CPU 使用率が高くなることが原因で発生する可能性があります。  <br/> |
|**DeviceLowSNREventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ DeviceLowSNR イベントが ' Bad ' 状態に対して発生しました。 キャプチャ品質は非常に低い。雑音が多いか、ユーザがマイクから離れすぎている。 これにより、ひずみが発生します。  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ DeviceLowSpeechLevel イベントが ' Bad ' 状態で発生しました。 ユーザーの音声レベルが低すぎて、システムがそれ以上の機能を向上させることができない。 これにより、ひずみが発生したり、一方向のオーディオとして認識されるようになります。  <br/> |
|**DeviceClippingEventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ DeviceClipping イベントが ' Bad ' 状態で発生しました。  <br/> ニアエンドの音声によってマイクがクリップされる場合は、クリッピングによるひずみが発生します。 ニアエンドマイクのクリッピングを回避することが重要です。  <br/> |
|**DeviceEchoEventRatio** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ DeviceEchoEvent イベントが ' Bad ' 状態で発生しました。 デバイスまたはセットアップが原因で、システムの補正機能を超えたエコーが発生しています。  <br/> |
|**デバイスの Devicorています。** <br/> |10進数 (5, 2)  <br/> | <br/> |セッションのパーセンテージ Devicenなイベントが ' Bad ' 状態で発生しました。 ユーザーの音声が、ユーザーの中断を簡単にすることができるようになるため、キャプチャされたエコーと比較して、ユーザーエクスペリエンスに影響を与えることができます。 スピーカーの音量を下げて、マイクをトーカーに近づける。  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||セッション中に ' Bad ' 状態に対して DeviceMultipleEndpoints イベントが発生した回数。 同じセッション内の複数のオーディオエンドポイントが検出され、レンダーボリュームが減ることで、システムが補正しています。  <br/> |
|**Deviceskのイベントカウント** <br/> |int  <br/> | <br/> |セッション中に、' Bad ' 状態に対して Deviceなイベントイベントが発生した回数。 音声フィードバックループが検出されました (複数のエンドポイントでのオーディオパスの共有によって発生)。  <br/> |
|**Devicerendervolumevolumeeventr** <br/> |10進数 (5, 2)  <br/> ||セッションのパーセンテージ Devicerenderゼロボリュームイベントが "Bad" 状態になったときに発生しました。 レンダーデバイスがボリューム0に設定されています。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**Devicerendermuteeventr** <br/> |10進数 (5, 2)  <br/> ||セッションのパーセンテージ DeviceRenderMute イベントが "Bad" 状態になったときに発生しました。 レンダーデバイスがミュートにされました。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
   

