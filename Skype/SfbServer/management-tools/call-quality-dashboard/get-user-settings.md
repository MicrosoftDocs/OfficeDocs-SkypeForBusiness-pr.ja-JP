---
title: ユーザー設定の取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: '概要: ユーザー設定サービスの一部である [ユーザー設定の取得] 操作について説明します。 ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 42934496b8b65132a67d4012d81d7b8997859726
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992634"
---
# <a name="get-user-settings"></a>ユーザー設定の取得
 
**概要:** ユーザー設定サービスの一部である [ユーザー設定の取得] 操作について説明します。 ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
[ユーザー設定の取得] 操作は、[リポジトリ API for Call Quality] ダッシュボードのユーザー設定サービスに含まれています。
  
## <a name="get-user-settings"></a>ユーザー設定の取得

ユーザー設定の取得指定したユーザーの設定のリストを返します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>の/QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター**
  
- *有効*-省略可能。 このパラメーターは、特別なユーザー ID の既定値が使用されている場合にのみ適用されます。 それ以外の場合は、無視されます。 `True`有効なユーザー設定を`false`返し、ユーザー設定 (既定値) のみを返します。
    
  **ヘッダーを要求**する-追加のヘッダーは不要です。
  
  **要求本文**-なし。
  
  **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
  **状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。
  
  **応答ヘッダー** -ヘッダーは追加されません。
  
  **応答本文**-以下は JSON のサンプル応答ペイロードです。
  
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
