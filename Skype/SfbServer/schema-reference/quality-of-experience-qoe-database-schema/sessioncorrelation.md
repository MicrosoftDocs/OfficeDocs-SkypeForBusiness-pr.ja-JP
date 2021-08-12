---
title: SessionCorrelation テーブル
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation テーブルは、サポート テーブルです。 各レコードは、複数のセッションを関連付けるのに使用される 1 つの CorrelationID を表します。
ms.openlocfilehash: 2029d78a0a083bcf8817b3a819cd28e74824995d79575036ecafd85998bd5218
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314423"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation テーブル
 
SessionCorrelation テーブルは、サポート テーブルです。 各レコードは、複数のセッションを関連付けるのに使用される 1 つの CorrelationID を表します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**チェックサム** <br/> |整数  <br/> |||
|**CorrelationKey** <br/> |整数  <br/> |Primary  <br/> |この音声ビデオ会議サーバーを識別する一意の番号。  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |一意  <br/> |相互に関連付けるセッションの相関 ID は同じです。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> | <br/> |内部使用のみ。  <br/> |
   

