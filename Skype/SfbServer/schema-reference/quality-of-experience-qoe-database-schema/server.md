---
title: サーバー テーブル
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: サーバー テーブルは補助的なテーブルです。 個々のレコードが 1 つのサーバーを表します。
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802707"
---
# <a name="server-table"></a>サーバー テーブル
 
サーバー テーブルは補助的なテーブルです。個々のレコードが 1 つのサーバーを表します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |サーバーを識別する一意の番号。  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |MAC アドレス文字列。  <br/> |
|**ServerType** <br/> |int  <br/> |外部  <br/> |1: 仲介サーバー  <br/> 2: 音声ビデオ会議サーバー16394: 音声ビデオ エッジ サービス 32769: ゲートウェイ  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||サーバーが所属するプール。音声ビデオ会議サーバーにのみ適用されます。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のみ。  <br/> |
   

