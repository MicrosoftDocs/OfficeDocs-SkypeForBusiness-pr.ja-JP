---
title: サブアイテムの取得
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '概要: アイテム サービスの一部Sub-Items取得操作について学習します。 Item Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: 3d17ab46ece202ea36dce45b6266a1cd3de74928
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774647"
---
# <a name="get-sub-items"></a>サブアイテムの取得
 
**概要:** アイテム サービスの一部Sub-Items、Get Sub-Items操作について学習します。 Item Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
Get Sub-Items操作は、呼び出し品質ダッシュボードのリポジトリ API の Item Service の一部です。
  
## <a name="get-sub-items"></a>サブアイテムの取得

Get Sub-Itemsアイテムのサブアイテムを返します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。 指定したユーザー ID が見つからない場合は、状態コード 404 (Not Found) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - JSON の応答ペイロードの例を以下に示します。
  
> [!NOTE]
> Item オブジェクトの配列が返されます。 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

この操作によって返される Item Sub-Itemsには、次の 3 つのフィールドだけが含まれます。 
  
 *itemId*  - アイテムの ID。
  
 *userId*  - このアイテムを所有するユーザーの ID。
  
 *type*  - コンテンツの種類。 このフィールドは、アプリケーションによって設定されます。
  
> [!NOTE]
>  `Content` ネットワーク `subItems` 経由で送信されるデータ量を減らす応答にはフィールドは含まれません。
  

