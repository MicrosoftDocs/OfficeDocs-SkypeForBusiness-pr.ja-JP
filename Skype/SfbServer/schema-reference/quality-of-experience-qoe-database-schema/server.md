---
title: サーバー テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: サーバー テーブルは補助的なテーブルです。個々のレコードが 1 つのサーバーを表します。
ms.openlocfilehash: c061176c7a3dbb30fbbe696241fccd54db8dc9b2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834925"
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
   

