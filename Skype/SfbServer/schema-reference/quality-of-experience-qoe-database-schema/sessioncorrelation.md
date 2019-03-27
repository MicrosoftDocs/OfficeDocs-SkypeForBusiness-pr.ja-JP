---
title: SessionCorrelation テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884664"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation テーブル
 
SessionCorrelation はテーブルをサポートします。 各レコードは、複数のセッションを関連付けるために使用される 1 つの CorrelationID を表します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**チェックサム** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |この A を識別する一意の番号/V 会議サーバーです。  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |一意  <br/> |関連付けられたセッションが同じ相関関係 ID をが  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |内部でのみ使用します。  <br/> |
   

