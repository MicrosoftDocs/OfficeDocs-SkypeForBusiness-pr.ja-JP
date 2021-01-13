---
title: Users テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Users テーブルはサポート テーブルです。 テーブル内の各レコードには、呼び出しに関係する 1 人のユーザーまたはデータベース内のレコードを持つセッションに関する情報が格納されます。
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831617"
---
# <a name="users-table"></a>Users テーブル
 
Users テーブルはサポート テーブルです。 テーブル内の各レコードには、呼び出しに関係する 1 人のユーザーまたはデータベース内のレコードを持つセッションに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のタイム スタンプ。  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号。  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |ユーザーの URI。  <br/> |
|**TenantId** <br/> |int  <br/> |外部  <br/> |このユーザーのテナント ID。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**UriTypeId** <br/> |int  <br/> |外部  <br/> |このユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
   

