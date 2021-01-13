---
title: 統合ログの取得
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '概要: 通話品質ダッシュボードのデータ API の一部である統合ログの取得操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832597"
---
# <a name="get-integration-log"></a>統合ログの取得
 
**概要:** 通話品質ダッシュボードのデータ API の一部である統合ログの取得操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
統合ログの取得操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="get-integration-log"></a>統合ログの取得

統合ログの取得操作は、QoE キューブ処理のアクティビティを記述するログ エントリのリストを返します。
  
セキュリティ上の理由により、この操作は既定で無効になっています。 無効にすると、空の文字列が返されます。 この操作を有効にするには、管理者は、データ API のweb.config Web アプリケーションのアプリケーションを構成する必要があります。
  

|メソッド|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - ログ エントリのサンプル構造を次に示します。
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


