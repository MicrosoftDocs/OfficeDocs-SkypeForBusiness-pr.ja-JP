---
title: サブアイテムの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '概要: 項目サービスの一部である [サブ項目の取得] 操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 523a6050065680550685337dabfec72c87f30bf7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816766"
---
# <a name="get-sub-items"></a>サブアイテムの取得
 
**概要:** 項目サービスの一部である [サブ項目の取得] 操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
[サブアイテムの取得] 操作は、[リポジトリ API for Call Quality] ダッシュボードのアイテムサービスの一部です。
  
## <a name="get-sub-items"></a>サブアイテムの取得

サブ項目の取得: 特定の項目のサブ項目を返します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>の/QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** -なし。
  
 **ヘッダーを要求**する-追加のヘッダーは不要です。
  
 **要求本文**-なし。
  
 **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。 指定したユーザー ID が見つからない場合は、状態コード 404 (見つかりません) が返されます。
  
 **応答ヘッダー** -ヘッダーは追加されません。
  
 **応答本文**-以下は JSON のサンプル応答ペイロードです。
  
> [!NOTE]
> 項目オブジェクトの配列が返されます。 
  
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

サブ項目操作によって返される Item オブジェクトには、次の3つのフィールドのみが含まれます。 
  
 *itemId* -項目の ID です。
  
 *userId* -このアイテムを所有しているユーザーの id です。
  
 *type* -コンテンツの種類。 このフィールドは、アプリケーションによって設定されます。
  
> [!NOTE]
>  `Content`また`subItems` 、ネットワーク経由で送信されるデータの量を減らすために、フィールドは返信に含まれません。
  

