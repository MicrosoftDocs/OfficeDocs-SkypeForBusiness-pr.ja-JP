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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: '概要: User 設定 サービスの一部である Get User 設定します。 User 設定サービスは、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: b541cacf3c777ca5991640f3bff05265cf6eeeb5c88f59f9731d46318247c171
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298147"
---
# <a name="get-user-settings"></a>ユーザー設定の取得
 
**概要:** User 設定 サービスの一部である Get User 設定操作について設定します。 User 設定サービスは、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
Get User 設定操作は、呼び出し品質ダッシュボード設定リポジトリ API の User 設定 サービスの一部です。
  
## <a name="get-user-settings"></a>ユーザー設定の取得

Get User 設定指定したユーザーの設定の一覧を返します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター**
  
- *effective*  - 省略可能です。 このパラメーターは、特別なユーザー ID の既定値が使用されている場合にのみ適用されます。 それ以外の場合は無視されます。 `True` 有効なユーザー設定を返し `false` 、ユーザー設定 (既定) を返します。
    
  **要求ヘッダー** - 追加のヘッダーはありません。
  
  **要求本文** - なし。
  
  **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
  **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。
  
  **応答ヘッダー** - 追加のヘッダーはありません。
  
  **応答本文** - JSON の応答ペイロードの例を以下に示します。
  
```json
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
