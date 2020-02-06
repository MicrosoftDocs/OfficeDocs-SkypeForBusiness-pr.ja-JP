---
title: ユーザー テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: ユーザーテーブルは、サポートテーブルです。 テーブル内の各レコードには、データベース内のレコードが含まれる1人のユーザーに関する情報が含まれています。
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814805"
---
# <a name="users-table"></a>ユーザー テーブル
 
ユーザーテーブルは、サポートテーブルです。 テーブル内の各レコードには、データベース内のレコードが含まれる1人のユーザーに関する情報が含まれています。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Nextupdatupdat** <br/> |datetime  <br/> ||内部使用のタイムスタンプ。  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号です。  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |ユーザー URI。  <br/> |
|**テナント** <br/> |int  <br/> |外部  <br/> |このユーザーのテナント ID。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**UriTypeId** <br/> |int  <br/> |外部  <br/> |このユーザーの URI 型。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
   

