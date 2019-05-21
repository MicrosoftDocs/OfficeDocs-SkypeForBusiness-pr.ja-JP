---
title: サーバー テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: サーバーテーブルは、サポートされているテーブルです。 各レコードは1つのサーバーを表します。
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294713"
---
# <a name="server-table"></a>サーバー テーブル
 
サーバーテーブルは、サポートされているテーブルです。 各レコードは1つのサーバーを表します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |サーバーを識別する一意の番号。  <br/> |
|**同一の Dnorip** <br/> |nvarchar(256)  <br/> |位置  <br/> |MAC アドレス文字列。  <br/> |
|**ServerType** <br/> |int  <br/> |外部  <br/> |1: 仲介サーバー  <br/> 2: a/v 会議 Server16394: A/V Edge service32769: ゲートウェイ  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||サーバーが所属するプール。 A/V 会議サーバーにのみ適用されます。  <br/> |
|**Nextupdatupdat** <br/> |datetime  <br/> ||内部使用のみ。  <br/> |
   

