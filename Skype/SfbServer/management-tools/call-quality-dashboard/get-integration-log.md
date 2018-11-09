---
title: 統合ログを取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '概要: は、統合ログの取得の操作では、品質のダッシュ ボードを呼び出すためのデータ API の一部について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 6408d0a773ee00854f82c4430e4402e79db23fa6
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035561"
---
# <a name="get-integration-log"></a>統合ログを取得します。
 
**の概要:** 統合ログの取得の操作では、品質のダッシュ ボードを呼び出すためのデータ API の一部について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。
  
統合ログの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部
  
## <a name="get-integration-log"></a>統合ログを取得します。

操作が返されます QoE のキューブに含まれるアクティビティを説明するログ エントリの一覧を処理する統合ログを取得します。
  
この操作は既定ではセキュリティ上の理由で無効になります。 無効にすると、空の文字列を返します。 この操作を有効にするには、管理者はデータ API のホストの web アプリケーションの web.config を構成する必要があります。
  

|メソッド|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>/QoEDataService/IntegrationLog  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **リクエストの本文**の [なし] です。
  
 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 **応答本体**のログ エントリの構造の例を次に示します。
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


