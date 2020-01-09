---
title: アイテムの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: '概要: 項目サービスの一部である、"項目の取得" 操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 208ad3d1852ab58b7fcd0d01eeb440097328f733
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992674"
---
# <a name="get-item"></a>アイテムの取得
 
**概要:** 項目サービスの一部である、"項目の取得" 操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
"項目の取得" 操作は、[リポジトリ API for Call Quality] ダッシュボードのアイテムサービスの一部です。
  
## <a name="get-item"></a>アイテムの取得

項目を取得すると、リポジトリ内の特定の項目が返されます。
  
|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>の/QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** -なし。
  
 **ヘッダーを要求**する-追加のヘッダーは不要です。
  
 **要求本文**-なし。
  
 **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。 指定した項目 ID が見つからない場合は、状態コード 404 (見つからない) が返されます。
  
 **応答ヘッダー** -ヘッダーは追加されません。
  
 **応答本文**-以下は JSON のサンプル応答ペイロードです。
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId* -項目の ID です。
  
 *userId* -このアイテムを所有しているユーザーの id です。
  
 *コンテンツ*-アプリケーション固有のコンテンツ。
  
 *type* -コンテンツの種類。 このフィールドは、アプリケーションによって設定されます。
  
 *Subitemids* -サブ項目の id (存在する場合)。 これは、通話を保存するサブ項目取得操作のショートサーキットです。 アプリケーションでは、Get サブ項目操作を使って同じ情報を取得することもできます。
  

