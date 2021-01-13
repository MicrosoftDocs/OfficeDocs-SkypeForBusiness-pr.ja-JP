---
title: VideoClientEvent テーブル
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 各レコードには、ビデオ通話の 1 つのエンドポイントのクライアント イベントが含まれる。 通常、1 つの呼び出しには 2 つのレコードがあります。1 つは呼び出し元用で、もう 1 つは呼び出し先用です。
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821397"
---
# <a name="videoclientevent-table"></a>VideoClientEvent テーブル
 
各レコードには、ビデオ通話の 1 つのエンドポイントのクライアント イベントが含まれる。 通常、1 つの呼び出しには、呼び出し元用と呼び出し先用の 2 つのレコードがあります。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 発信者のデータ  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |LowBandwidth イベントが "Bad" 状態で発生したセッションの割合。 使用可能な帯域幅は、許容できる音声エクスペリエンスには不十分です。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |ReceiveSendQuality イベントが "Bad" 状態で発生したセッションの割合。  <br/> ジッターまたはパケット損失の観点から見たネットワーク品質は重大であり、受信する音声の品質に影響します。  <br/> |
   

