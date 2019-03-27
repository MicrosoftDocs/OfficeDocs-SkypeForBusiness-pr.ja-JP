---
title: ユーザー設定の取得
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '概要: は、ユーザー設定のサービスの一部では、ユーザー設定の取得操作について説明します。 ユーザー設定のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 003850ed4e6f1e49fc0e8bafe8dfa7d828cae63f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889001"
---
# <a name="get-user-setting"></a>ユーザー設定の取得
 
**の概要:** ユーザー設定のサービスの一部では、ユーザー設定の取得操作について説明します。 ユーザー設定のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。
  
ユーザー設定の取得操作は、ユーザーの設定でのサービス品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。
  
## <a name="get-user-setting"></a>ユーザー設定の取得

ユーザーの設定を返します。 1 つのユーザー設定を取得します。
  

|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>/QoERepositoryService/リポジトリとユーザー/{ユーザー Id}/setting/{キー}  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **リクエストの本文**の [なし] です。
  
 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 **応答本体**の JSON のサンプル応答の内容を次に示します。
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *ユーザー Id*がユーザーの ID。
  
 *キー*の設定のキーです。
  
 *値*の設定の値です。
  

