---
title: User テーブル
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
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: ユーザーテーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1人のユーザーを表します。
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805095"
---
# <a name="user-table"></a>User テーブル
 
ユーザーテーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1人のユーザーを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号です。  <br/> |
|**URI** <br/> |nvarchar (450)  <br/> |一意  <br/> |URI 文字列。  <br/> |
|**URIType** <br/> |int  <br/> ||1の URI の型が不明です。  <br/> 2はユーザー URI です。  <br/> 4は会議の URI です。  <br/> 8は電話の URI です。  <br/> |
|**TenantKey** <br/> |int  <br/> |外部  <br/> |テナントテーブルから参照されたユーザーのテナント。  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||ユーザーが低品質の音声通話を行ったときの最新のタイムスタンプ。  <br/> |
|**Nextupdatupdat** <br/> |datetime  <br/> ||内部使用のみ。  <br/> |
   

