---
title: Pool テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: プールテーブルは、さまざまなフロントエンドプールに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのプールを表します。
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807405"
---
# <a name="pool-table"></a>Pool テーブル
 
プールテーブルは、さまざまなフロントエンドプールに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのプールを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |このプールを識別する一意の番号。  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |一意  <br/> |プールの FQDN。  <br/> |
   

