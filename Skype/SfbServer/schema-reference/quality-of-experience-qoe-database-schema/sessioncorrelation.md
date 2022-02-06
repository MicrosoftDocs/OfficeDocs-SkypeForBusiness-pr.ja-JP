---
title: SessionCorrelation テーブル
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation テーブルは、サポート テーブルです。 各レコードは、複数のセッションを関連付けるのに使用される 1 つの CorrelationID を表します。
---

# <a name="sessioncorrelation-table"></a>SessionCorrelation テーブル
 
SessionCorrelation テーブルは、サポート テーブルです。 各レコードは、複数のセッションを関連付けるのに使用される 1 つの CorrelationID を表します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**チェックサム** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |この音声ビデオ会議サーバーを識別する一意の番号。  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |一意  <br/> |相互に関連付けるセッションの相関 ID は同じです。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> | <br/> |内部使用のみ。  <br/> |
   

