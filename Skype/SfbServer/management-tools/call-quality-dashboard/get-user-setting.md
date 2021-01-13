---
title: ユーザー設定の取得
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '概要: User Settings Service の一部であるユーザー設定の取得操作について学習します。 ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832487"
---
# <a name="get-user-setting"></a>ユーザー設定の取得
 
**概要:** User Settings Service の一部であるユーザー設定の取得操作について学習します。 ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
ユーザー設定の取得操作は、通話品質ダッシュボードのリポジトリ API のユーザー設定サービスの一部です。
  
## <a name="get-user-setting"></a>ユーザー設定の取得

ユーザー設定を取得すると、1 つのユーザー設定が返されます。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - JSON の応答ペイロードのサンプルを次に示します。
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  - ユーザーの ID。
  
 *key*  - 設定のキー。
  
 *value*  - 設定の値。
  

