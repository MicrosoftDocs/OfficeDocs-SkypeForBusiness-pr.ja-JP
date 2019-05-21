---
title: VideoClientEvent テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 各レコードには、ビデオ通話での1つのエンドポイントのクライアントイベントが含まれています。 通常、1つの通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294555"
---
# <a name="videoclientevent-table"></a>VideoClientEvent テーブル
 
各レコードには、ビデオ通話での1つのエンドポイントのクライアントイベントが含まれています。 通常、1つの通話には2つのレコードがあります。1つは呼び出し元用、もう1つは呼び出し先用です。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 呼び出し先のデータ  <br/> 1: 発信者のデータ  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |セッションのパーセンテージ低帯域幅イベントが ' Bad ' 状態に対して発生しました。 利用可能な音声エクスペリエンスを実現するには、利用可能な帯域幅が不足しています。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |セッションのパーセンテージ ReceiveSendQuality イベントが ' Bad ' 状態で発生しました。  <br/> ネットワーク品質は、ジッタまたはパケット損失の観点では深刻であり、受信中のオーディオの品質に影響します。  <br/> |
   

