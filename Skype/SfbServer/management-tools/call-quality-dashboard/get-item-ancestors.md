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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: '概要: アイテム サービスの一部であるアイテムの先祖の取得操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832577"
---
# <a name="get-item-ancestors"></a>アイテムの親の取得
 
**概要:** アイテム サービスの一部であるアイテムの先祖の取得操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
アイテムの先祖の取得操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。
  
## <a name="get-item-ancestors"></a>アイテムの親の取得

アイテムの先祖を取得すると、リポジトリから特定のアイテムの先祖が返されます。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。 指定されたユーザー ID が見つからない場合は、状態コード 404 (Not Found) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - JSON の応答ペイロードのサンプルを次に示します。
  
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
  
 *Item2*  - 深度はアイテムからの距離です。 0 は直接の親です。
  
 *Item3*  - アイテムのタイトル。
  

