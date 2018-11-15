---
title: ユーザー設定を取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: '概要: は、ユーザー設定のサービスの一部では、ユーザー設定の取得操作について説明します。 ユーザー設定のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 9547479b95a8b321a9aa2f92c7cfcb2e88edf4bb
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532900"
---
# <a name="get-user-settings"></a>ユーザー設定を取得します。
 
**の概要:** ユーザー設定のサービスの一部では、ユーザー設定の取得操作について説明します。 ユーザー設定のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。
  
ユーザー設定の取得操作は、ユーザーの設定でのサービス品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。
  
## <a name="get-user-settings"></a>ユーザー設定を取得します。

ユーザー設定を取得、指定したユーザー設定の一覧を返します。
  

|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>/QoERepositoryService/リポジトリとユーザー/{ユーザー Id} の設定/  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**
  
- *効果的な*- 省略可能です。 このパラメーターでは、特別なユーザー ID の既定値を使用する場合にのみ適用されます。 それ以外の場合、無視されます。 `True`効果的なユーザーの設定を取得および`false`ユーザーの設定 (既定値) だけを返します。
    
  **要求ヘッダー**の追加のヘッダーではありません。
  
  **リクエストの本文**の [なし] です。
  
  **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
  **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。
  
  **応答ヘッダー**の追加のヘッダーではありません。
  
  **応答本体**の JSON のサンプル応答の内容を次に示します。
  
```
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```