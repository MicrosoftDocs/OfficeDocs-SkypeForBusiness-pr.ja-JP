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
ms.openlocfilehash: 87e6e24ea9bf1073411eeb8c930e8e6fb509ae115242b529331aa43a25d5ac11
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329332"
---
# <a name="user-table"></a>ユーザー テーブル
 
User テーブルは、データベースに記録されるセッションに参加したさまざまなユーザーの一覧を格納するサポート テーブルです。このテーブルの各レコードは、1 人のユーザーを表しています。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |整数  <br/> |Primary  <br/> |このユーザーを示す一意の番号です。  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |一意  <br/> |URI 文字列です。  <br/> |
|**URIType** <br/> |整数  <br/> ||1 は不明な URI の種類です。  <br/> 2 はユーザーの URI です。  <br/> 4 は電話会議の URI です。  <br/> 8 は電話の URI です。  <br/> |
|**TenantKey** <br/> |整数  <br/> |外部  <br/> |ユーザーのテナントであり、テナント テーブルから参照されます。  <br/> |
|**LastPoorCallTime** <br/> |日付型  <br/> ||ユーザーが低音質の通話を行った時点を示す最新のタイム スタンプです。  <br/> |
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のみ。  <br/> |
   

