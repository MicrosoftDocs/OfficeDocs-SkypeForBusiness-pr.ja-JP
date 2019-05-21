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
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: プールテーブルは、さまざまなフロントエンドプールに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのプールを表します。
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294804"
---
# <a name="pool-table"></a>Pool テーブル
 
プールテーブルは、さまざまなフロントエンドプールに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのプールを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |このプールを識別する一意の番号。  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |一意  <br/> |プールの FQDN。  <br/> |
   

