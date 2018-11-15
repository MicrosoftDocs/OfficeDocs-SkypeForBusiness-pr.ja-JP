---
title: サブ項目を取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '概要: は、項目のサービスの一部では、サブ項目の取得操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 648f514ff03361673962052445d25076437057b9
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531075"
---
# <a name="get-sub-items"></a>サブ項目を取得します。
 
**の概要:** 品目サービスの一部では、サブ項目の取得操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。
  
サブ項目の取得操作は、リポジトリ api の呼び出し品質のダッシュ ボードの項目のサービスの一部です。
  
## <a name="get-sub-items"></a>サブ項目を取得します。

サブ項目を返します。 特定の項目のサブ項目を取得します。
  

|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>/QoERepositoryService/リポジトリ/アイテム/{itemId} subitem/  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **リクエストの本文**の [なし] です。
  
 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。 特定のユーザ ID が見つからない場合は、ステータス コード 404 (見つかりません) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 **応答本体**の JSON のサンプル応答の内容を次に示します。
  
> [!NOTE]
> アイテム オブジェクトの配列が返されます。 
  
```
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

サブ項目の操作によって返される項目のオブジェクトには、次の 3 つのフィールドのみ含まれています。 
  
 *アイテム Id*の項目の ID です。
  
 *ユーザー Id* - このアイテムを所有するユーザーの ID。
  
 *型*のコンテンツの種類です。 このフィールドは、アプリケーションによって設定されます。
  
> [!NOTE]
>  `Content``subItems`フィールドは、応答をネットワーク経由で送信されるデータの量を減らすには含まれません。
  

