---
title: 項目を取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: '概要: は、項目のサービスの一部の項目の取得操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: 29811f7f760644d257a2600dea08e54e1a53421b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569153"
---
# <a name="get-item"></a>項目を取得します。
 
**の概要:** 項目のサービスの一部の項目の取得操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。
  
項目の取得操作は、リポジトリ api の呼び出し品質のダッシュ ボードの項目のサービスの一部です。
  
## <a name="get-item"></a>項目を取得します。

リポジトリ内のアイテムを返します。 特定の項目を取得します。
  
|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>/QoERepositoryService/リポジトリ/アイテム/{アイテム Id}  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **リクエストの本文**の [なし] です。
  
 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。 指定した項目の ID が見つからない場合は、ステータス コード 404 (見つかりません) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 **応答本体**の JSON のサンプル応答の内容を次に示します。
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *アイテム Id*の項目の ID です。
  
 *ユーザー Id* - このアイテムを所有するユーザーの ID。
  
 *コンテンツ*・ アプリケーションに固有のコンテンツです。
  
 *型*のコンテンツの種類です。 このフィールドは、アプリケーションによって設定されます。
  
 *subItemIds* - の場合は、すべてのサブ項目の Id です。 呼び出しを保存するのには、サブ項目の取得操作の short-circuit です。 アプリケーションは、サブ項目の取得操作を使用して同じ情報を取得またはことができます。
  

