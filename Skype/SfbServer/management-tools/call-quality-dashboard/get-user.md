---
title: ユーザーの取得
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '概要: ユーザー サービスの一部であるユーザーの取得操作について学習します。 User Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: adcb832d03d97eee978e3eb4c0f9027bd44ac7ce
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768675"
---
# <a name="get-user"></a>ユーザーの取得
 
**概要:** ユーザー サービスの一部であるユーザーの取得操作について学習します。 User Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
ユーザーの取得操作は、呼び出し品質ダッシュボードのリポジトリ API のユーザー サービスの一部です。
  
## <a name="get-user"></a>ユーザーの取得

Get User はリポジトリからユーザー レコードを返します。
  
|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。 指定したユーザー ID が見つからない場合は、状態コード 404 (Not Found) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - JSON の応答ペイロードの例を以下に示します。
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  - ユーザーの ID。
  
 *loginName*  - 通常のユーザーの外部ユーザー ID。 ユーザー Windows認証に認証が使用されている場合、これはユーザーの FQDN である可能性があります。
  
 *defaultItemId*  - このユーザーの既定のアイテムの ID。 既定のアイテムは、ユーザーに関連付けられている最も高いアイテムです。 このユーザーが所有する他のすべてのアイテムは、既定のアイテムから移動できます。
  
> [!NOTE]
> 既定の  `defaultItemId` アイテムの詳細を取得するには、[アイテムの取得] 操作に値を指定します。
  

