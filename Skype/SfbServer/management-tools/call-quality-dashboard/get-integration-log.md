---
title: 統合ログの取得
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '概要: 呼び出し品質ダッシュボードのデータ API の一部である統合ログの取得操作について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: b82ecffd5b39df6e149787ec7b3265f3e8176376
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388075"
---
# <a name="get-integration-log"></a>統合ログの取得
 
**概要:** 呼び出し品質ダッシュボードのデータ API の一部である統合ログの取得操作について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
統合ログの取得操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="get-integration-log"></a>統合ログの取得

統合ログの取得操作は、QoE キューブ処理のアクティビティを説明するログ エントリの一覧を返します。
  
この操作は、セキュリティ上の理由から既定で無効になっています。 無効にすると、空の文字列が返されます。 この操作を有効にするには、管理者が Data API のホスト web アプリケーションweb.configを構成する必要があります。
  

|メソッド|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - ログ エントリの構造の例を以下に示します。
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


