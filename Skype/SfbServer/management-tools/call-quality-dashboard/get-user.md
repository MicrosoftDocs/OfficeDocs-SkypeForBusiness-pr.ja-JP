---
title: ユーザーの取得
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '概要: ユーザー サービスの一部であるユーザーの取得操作について学習します。 ユーザー サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832417"
---
# <a name="get-user"></a>ユーザーの取得
 
**概要:** ユーザー サービスの一部であるユーザーの取得操作について学習します。 ユーザー サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
ユーザーの取得操作は、通話品質ダッシュボードのリポジトリ API のユーザー サービスの一部です。
  
## <a name="get-user"></a>ユーザーの取得

Get User はリポジトリからユーザー レコードを返します。
  
|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。 指定されたユーザー ID が見つからない場合は、状態コード 404 (Not Found) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - JSON の応答ペイロードのサンプルを次に示します。
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  - ユーザーの ID。
  
 *loginName*  - 通常のユーザーの外部ユーザー ID。 Windows 認証を使用してユーザーを認証する場合、これはユーザーの FQDN である可能性があります。
  
 *defaultItemId*  - このユーザーの既定のアイテムの ID。 既定のアイテムは、ユーザーに関連付けられている最も上位のアイテムです。 このユーザーが所有する他のすべてのアイテムは、既定のアイテムから移動できます。
  
> [!NOTE]
> 既定の  `defaultItemId` アイテムの詳細を取得するアイテムの取得操作の値を指定します。
  

