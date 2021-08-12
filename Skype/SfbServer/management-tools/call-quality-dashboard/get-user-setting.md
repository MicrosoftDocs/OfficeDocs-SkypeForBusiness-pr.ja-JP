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
description: '概要: User 設定 サービスの一部であるユーザー設定の取得操作について設定します。 User 設定サービスは、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: 5ea18a5ae5307bbf392796f95f7dcce8393371bdb8ddcfc192cb32d819494aa3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298157"
---
# <a name="get-user-setting"></a>ユーザー設定の取得
 
**概要:** User 設定 サービスの一部であるユーザー設定の取得操作について設定します。 User 設定サービスは、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
ユーザー設定の取得操作は、呼び出し品質ダッシュボード設定リポジトリ API の User 設定 サービスの一部です。
  
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
  
 **応答本文** - JSON の応答ペイロードの例を以下に示します。
  
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
  

