---
title: User テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: ユーザー テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 人のユーザーを表します。
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a>User テーブル
 
ユーザー テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 人のユーザーを表します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ユーザー キー** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号です。  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |一意  <br/> |URI 文字列です。  <br/> |
|**URIType** <br/> |int  <br/> ||1 は、URI の種類が不明です。  <br/> 2 は、ユーザーの URI です。  <br/> 4 は、会議の URI です。  <br/> 8 は、電話の URI です。  <br/> |
|**TenantKey** <br/> |int  <br/> |外部  <br/> |テナントのテーブルから参照されているユーザーのテナントです。  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||最新タイムスタンプが低いオーディオ呼び出しをユーザーがいたとします。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||内部でのみ使用します。  <br/> |
   

