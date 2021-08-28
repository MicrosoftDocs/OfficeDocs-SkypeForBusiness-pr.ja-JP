---
title: アイテムの親の取得
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: '概要: アイテム サービスの一部であるアイテムの先祖の取得操作について学習します。 Item Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: f6977d1519b487003460e8d4eb5300fe4d98e84f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633621"
---
# <a name="get-item-ancestors"></a>アイテムの親の取得
 
**概要:** アイテム サービスの一部であるアイテムの先祖の取得操作について学習します。 Item Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
[アイテムの先祖の取得] 操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。
  
## <a name="get-item-ancestors"></a>アイテムの親の取得

Get Item Ancestors は、リポジトリから特定のアイテムの先祖を返します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。 指定したユーザー ID が見つからない場合は、状態コード 404 (Not Found) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - JSON の応答ペイロードの例を以下に示します。
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1*  - アイテムの ID。
  
 *Item2*  - 深度はアイテムからの距離です。 0 は即座の親です。
  
 *Item3*  - アイテムのタイトル。
  

