---
title: ユーザー テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: ユーザーはテーブルをサポートします。 テーブル内の各レコードでは、呼び出しまたはデータベースのレコードが存在するセッションに関連する 1 つのユーザーに関する情報を格納します。
ms.openlocfilehash: 3929ba33737c107ee60ec1e31beebb1addbb2e3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212741"
---
# <a name="users-table"></a>ユーザー テーブル
 
ユーザーはテーブルをサポートします。 テーブル内の各レコードでは、呼び出しまたはデータベースのレコードが存在するセッションに関連する 1 つのユーザーに関する情報を格納します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||内部で使用するタイム ・ スタンプ。  <br/> |
|**ユーザー Id** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号です。  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |ユーザー URI です。  <br/> |
|**TenantId** <br/> |int  <br/> |外部  <br/> |このユーザーのテナント id。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**UriTypeId** <br/> |int  <br/> |外部  <br/> |このユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
   

