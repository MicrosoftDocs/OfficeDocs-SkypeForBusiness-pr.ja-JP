---
title: ユーザーの取得
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: '概要: ユーザー サービスの一部であるユーザーの取得操作について学習します。 User Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: 9efb2e10a4197a2ad323ce521617c3ce8c1600eb490077ffcf122d4d4628cdd8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331249"
---
# <a name="get-users"></a>ユーザーの取得
 
**概要:** ユーザー サービスの一部であるユーザーの取得操作について学習します。 User Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
ユーザーの取得操作は、呼び出し品質ダッシュボードのリポジトリ API のユーザー サービスの一部です。
  
## <a name="get-users"></a>ユーザーの取得

Get Users は、リポジトリ内のユーザーのリストを返します。
  
|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - JSON の応答ペイロードの例を以下に示します。
  
> [!NOTE]
> User オブジェクトの配列が返されます。 User オブジェクトの詳細については、「Get User」を参照してください。 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


