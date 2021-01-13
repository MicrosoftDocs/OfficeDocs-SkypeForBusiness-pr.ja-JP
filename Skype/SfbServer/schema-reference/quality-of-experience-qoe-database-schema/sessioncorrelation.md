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
description: SessionCorrelation テーブルはサポート テーブルです。 各レコードは、複数のセッションを関連付けるのに使用される 1 つの CorrelationID を表します。
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802657"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation テーブル
 
SessionCorrelation テーブルはサポート テーブルです。 各レコードは、複数のセッションを関連付けるのに使用される 1 つの CorrelationID を表します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**チェックサム** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |この音声ビデオ会議サーバーを識別する一意の番号。  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |一意  <br/> |関連付けされているセッションの関連付け ID は同じになります。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> | <br/> |内部使用のみ。  <br/> |
   

