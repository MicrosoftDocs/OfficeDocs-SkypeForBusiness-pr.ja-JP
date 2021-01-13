---
title: ユーザー テーブル
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
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: User テーブルは、データベースに記録されるセッションに参加したさまざまなユーザーの一覧を格納するサポート テーブルです。このテーブルの各レコードは、1 人のユーザーを表しています。
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800077"
---
# <a name="user-table"></a>ユーザー テーブル
 
User テーブルは、データベースに記録されるセッションに参加したさまざまなユーザーの一覧を格納するサポート テーブルです。このテーブルの各レコードは、1 人のユーザーを表しています。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |このユーザーを示す一意の番号です。  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |一意  <br/> |URI 文字列です。  <br/> |
|**URIType** <br/> |int  <br/> ||1 は不明な URI の種類です。  <br/> 2 はユーザーの URI です。  <br/> 4 は電話会議の URI です。  <br/> 8 は電話の URI です。  <br/> |
|**TenantKey** <br/> |int  <br/> |外部  <br/> |ユーザーのテナントであり、テナント テーブルから参照されます。  <br/> |
|**LastPoorCallTime** <br/> |日付型  <br/> ||ユーザーが低音質の通話を行った時点を示す最新のタイム スタンプです。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のみ。  <br/> |
   

