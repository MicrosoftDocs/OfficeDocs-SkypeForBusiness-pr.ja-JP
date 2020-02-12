---
title: 統合ログの取得
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '概要: 通話品質ダッシュボードのデータ API の一部である、統合ログの取得操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: e1d790f4723eaaf716482143f08c78624db47433
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888806"
---
# <a name="get-integration-log"></a>統合ログの取得
 
**概要:** 通話品質ダッシュボードのデータ API の一部である、統合ログの取得操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
"統合ログの取得" 操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="get-integration-log"></a>統合ログの取得

統合ログの取得操作 QoE キューブ処理のアクティビティを説明するログエントリの一覧を返します。
  
この操作は、セキュリティ上の理由で既定では無効になっています。 無効にすると、空の文字列が返されます。 この操作を有効にするには、管理者が Data API のホスト web アプリケーション用に web.config を構成する必要があります。
  

|メソッド|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>の/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** -なし。
  
 **ヘッダーを要求**する-追加のヘッダーは不要です。
  
 **要求本文**-なし。
  
 **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。
  
 **応答ヘッダー** -ヘッダーは追加されません。
  
 **応答本文**-以下に、ログエントリのサンプル構造を示します。
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


