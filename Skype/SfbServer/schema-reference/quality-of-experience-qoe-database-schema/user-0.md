---
title: User テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: ユーザー テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 人のユーザーを表します。
ms.openlocfilehash: 426d272a5c8bee2fd37511edc62bcb3e1a0c533e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907039"
---
# <a name="user-table"></a>User テーブル
 
ユーザー テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 人のユーザーを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ユーザー キー** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号です。  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |一意  <br/> |URI 文字列です。  <br/> |
|**URIType** <br/> |int  <br/> ||1 は、URI の種類が不明です。  <br/> 2 は、ユーザーの URI です。  <br/> 4 は、会議の URI です。  <br/> 8 は、電話の URI です。  <br/> |
|**TenantKey** <br/> |int  <br/> |外部  <br/> |テナントのテーブルから参照されているユーザーのテナントです。  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||最新タイムスタンプが低いオーディオ呼び出しをユーザーがいたとします。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||内部でのみ使用します。  <br/> |
   

