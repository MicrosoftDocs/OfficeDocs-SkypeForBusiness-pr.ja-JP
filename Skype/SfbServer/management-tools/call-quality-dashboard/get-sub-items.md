---
title: サブアイテムの取得
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '概要: Item Service の一部Sub-Items取得操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832507"
---
# <a name="get-sub-items"></a>サブアイテムの取得
 
**概要:** Item Service の一Sub-Items取得操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
Get Sub-Items操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。
  
## <a name="get-sub-items"></a>サブアイテムの取得

取得Sub-Itemsアイテムのサブアイテムを返します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。 指定されたユーザー ID が見つからない場合は、状態コード 404 (Not Found) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - JSON の応答ペイロードのサンプルを次に示します。
  
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
  
 *type:*  コンテンツの種類を指定します。 このフィールドは、アプリケーションによって設定されます。
  
> [!NOTE]
>  `Content` およびフィールドは、ネットワーク経由で送信されるデータの量を減らすために `subItems` 応答に含まれません。
  

