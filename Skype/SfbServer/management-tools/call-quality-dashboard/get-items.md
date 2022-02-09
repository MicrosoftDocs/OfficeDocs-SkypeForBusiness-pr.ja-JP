---
title: アイテムの取得
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: '概要: アイテム サービスの一部であるアイテムの取得操作について学習します。 Item Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: a28f495dbe76750e70633c5d0f07f5c23576485c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416540"
---
# <a name="get-items"></a>アイテムの取得
 
**概要:** アイテム サービスの一部であるアイテムの取得操作について学習します。 Item Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
[アイテムの取得] 操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。
  
## <a name="get-items"></a>アイテムの取得

Get Items は、リポジトリ内のすべてのアイテムを返します。
  
|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoERepositoryService/repository/item  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - JSON の応答ペイロードの例を以下に示します。
  
> [!NOTE]
> Item オブジェクトの配列が返されます。 Item オブジェクトの詳細については、「Get Item」を参照してください。 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
