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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: サーバーテーブルは、サポートされているテーブルです。 各レコードは1つのサーバーを表します。
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806135"
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
   

