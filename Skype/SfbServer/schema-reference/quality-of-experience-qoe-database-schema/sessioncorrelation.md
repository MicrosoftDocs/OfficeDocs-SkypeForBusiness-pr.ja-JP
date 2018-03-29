---
title: SessionCorrelation テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation はテーブルをサポートします。 各レコードは、複数のセッションを関連付けるために使用される 1 つの CorrelationID を表します。
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation テーブル
 
SessionCorrelation はテーブルをサポートします。 各レコードは、複数のセッションを関連付けるために使用される 1 つの CorrelationID を表します。 
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**チェックサム** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |この A を識別する一意の番号/V 会議サーバーです。  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |一意  <br/> |関連付けられたセッションが同じ相関関係 ID をが  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |内部でのみ使用します。  <br/> |
   

