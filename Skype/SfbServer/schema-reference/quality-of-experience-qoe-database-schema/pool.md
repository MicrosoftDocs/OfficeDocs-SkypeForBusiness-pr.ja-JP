---
title: プール テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool テーブルは、さまざまなフロントエンド プールに関する情報を格納するサポート テーブルです。このテーブル内の各レコードは、1 つのプールを表しています。
ms.openlocfilehash: 501c35c6e3a8ded5d1a9c7cfab58395d91d0e653
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740263"
---
# <a name="pool-table"></a>プール テーブル
 
Pool テーブルは、さまざまなフロントエンド プールに関する情報を格納するサポート テーブルです。このテーブル内の各レコードは、1 つのプールを表しています。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |このプールを示す一意の番号です。  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |一意  <br/> |プールの FQDN です。  <br/> |
   

