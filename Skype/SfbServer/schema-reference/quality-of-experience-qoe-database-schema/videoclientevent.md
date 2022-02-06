---
title: VideoClientEvent テーブル
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 各レコードには、ビデオ通話で 1 つのエンドポイントのクライアント イベントが含まれる。 通常、1 つの呼び出しには、呼び出し元用と呼び出し先用の 2 つのレコードがあります。
---

# <a name="videoclientevent-table"></a>VideoClientEvent テーブル
 
各レコードには、ビデオ通話で 1 つのエンドポイントのクライアント イベントが含まれる。 通常、1 つの呼び出しには、呼び出し元用と呼び出し先用の 2 つのレコードがあります。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |ビット  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 発信者のデータ  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |LowBandwidth イベントが 'Bad' 状態で発生したセッションの割合。 使用可能な帯域幅は、許容可能な音声エクスペリエンスでは不十分です。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |ReceiveSendQuality イベントが "Bad" 状態で発生したセッションの割合。  <br/> ジッターまたはパケット損失に関するネットワーク品質は重大であり、受信されるオーディオの品質に影響を与えます。  <br/> |
   

