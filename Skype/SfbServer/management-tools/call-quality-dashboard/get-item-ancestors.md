---
title: アイテムの親を取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: '概要: は、項目のサービスの一部では、アイテムの先祖を取得する操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: 60d77ff1fd14a994d55a42516cd686891a56595f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569202"
---
# <a name="get-item-ancestors"></a>アイテムの親を取得します。
 
**の概要:** 項目のサービスの一部では、アイテムの先祖を取得する操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。
  
アイテムの先祖を取得する操作は、リポジトリ api の呼び出し品質のダッシュ ボードの項目のサービスの一部です。
  
## <a name="get-item-ancestors"></a>アイテムの親を取得します。

Get アイテムの先祖は、リポジトリから特定のアイテムの親を返します。
  

|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>/QoERepositoryService/リポジトリ/itemAncestors/{アイテム Id}  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **リクエストの本文**の [なし] です。
  
 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。 特定のユーザ ID が見つからない場合は、ステータス コード 404 (見つかりません) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 **応答本体**の JSON のサンプル応答の内容を次に示します。
  
```
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

 *項目 1*項目の ID です。
  
 *項目 2*の深さは、項目からの距離です。 0 は、直接の親です。
  
 *項目 3* - アイテムのタイトル。
  

