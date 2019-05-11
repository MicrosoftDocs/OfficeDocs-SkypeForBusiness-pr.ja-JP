---
title: アイテムの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: '概要: は、項目のサービスの一部の項目の取得操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: fe8d4f9a64e0855c90ee9f2accb67424ac3edb9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926123"
---
# <a name="get-items"></a>アイテムの取得
 
**の概要:** 品目サービスの一部の項目の取得操作について説明します。 項目のサービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。
  
項目の取得操作は、リポジトリ api の呼び出し品質のダッシュ ボードの項目のサービスの一部です。
  
## <a name="get-items"></a>アイテムの取得

リポジトリ内のアイテムを返します。 すべてのアイテムを取得します。
  
|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>/QoERepositoryService/repository/item  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **リクエストの本文**の [なし] です。
  
 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 **応答本体**の JSON のサンプル応答の内容を次に示します。
  
> [!NOTE]
> アイテム オブジェクトの配列が返されます。 詳細については、Item オブジェクトは、アイテムの取得を参照してください。 
  
```
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
