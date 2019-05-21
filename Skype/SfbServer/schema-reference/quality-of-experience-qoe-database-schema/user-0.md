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
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: ユーザーテーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1人のユーザーを表します。
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294615"
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
   

