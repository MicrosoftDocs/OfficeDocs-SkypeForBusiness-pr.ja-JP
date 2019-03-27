---
title: Pool テーブル
ms.reviewer: ''
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
ms.openlocfilehash: ae8695316bdea6ba858bf9a4d334dc6075b99d50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874019"
---
# <a name="pool-table"></a>Pool テーブル
 
プール テーブルは、さまざまなフロント エンド プールに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのプールを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |このプールを識別する一意の番号です。  <br/> |
|**大文字と小文字** <br/> |nvarchar(256)  <br/> |一意  <br/> |プールの FQDN です。  <br/> |
   

