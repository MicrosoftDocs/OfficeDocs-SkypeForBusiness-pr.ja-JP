---
title: サーバー テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: サーバーはテーブルをサポートします。 各レコードは、1 つのサーバーを表します。
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a>サーバー テーブル
 
サーバーはテーブルをサポートします。 各レコードは、1 つのサーバーを表します。 
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |サーバーを識別する一意の番号です。  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |インデックス  <br/> |MAC アドレスの文字列です。  <br/> |
|**ServerType** <br/> |int  <br/> |外部  <br/> |1: 仲介サーバー  <br/> 2: A/V 会議 Server16394: A/V エッジの service32769: ゲートウェイ  <br/> |
|**大文字と小文字** <br/> |nvarchar(512)  <br/> ||サーバーが所属するプールです。 のみに適用可能、A/V 会議サーバーです。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||内部でのみ使用します。  <br/> |
   

