---
title: Pool テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: プール テーブルは、さまざまなフロント エンド プールに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのプールを表します。
ms.openlocfilehash: 8ce54d4b0a20fa405f34bb14b3eecb9ad395884e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="pool-table"></a>Pool テーブル
 
プール テーブルは、さまざまなフロント エンド プールに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのプールを表します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |このプールを識別する一意の番号です。  <br/> |
|**大文字と小文字** <br/> |nvarchar(256)  <br/> |一意  <br/> |プールの FQDN です。  <br/> |
   

