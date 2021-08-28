---
title: ユーザー テーブル
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
ms.localizationpriority: medium
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Users テーブルはサポート テーブルです。 テーブル内の各レコードには、データベース内のレコードを持つ呼び出しまたはセッションに関係する 1 人のユーザーに関する情報が格納されます。
ms.openlocfilehash: b2f7dad297a085d3fb5b8dc77c86feb07b094e7e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598631"
---
# <a name="users-table"></a>ユーザー テーブル
 
Users テーブルはサポート テーブルです。 テーブル内の各レコードには、データベース内のレコードを持つ呼び出しまたはセッションに関係する 1 人のユーザーに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |日付型  <br/> ||内部使用のタイム スタンプ。  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号。  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |ユーザーの URI。  <br/> |
|**TenantId** <br/> |int  <br/> |外部  <br/> |このユーザーのテナント ID。 詳細については [、「Tenants」テーブル](tenants.md) を参照してください。 <br/> |
|**UriTypeId** <br/> |int  <br/> |外部  <br/> |このユーザーの URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
   

