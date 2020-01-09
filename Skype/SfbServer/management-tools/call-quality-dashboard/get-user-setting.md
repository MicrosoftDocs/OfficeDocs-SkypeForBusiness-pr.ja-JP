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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '概要: ユーザー設定サービスの一部である [ユーザー設定の取得] 操作について説明します。 ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 168e61aaebb47cb087e77cbd18e3e6edfd987227
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992644"
---
# <a name="get-user-setting"></a>ユーザー設定の取得
 
**概要:** ユーザー設定サービスの一部である [ユーザー設定の取得] 操作について説明します。 ユーザー設定サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
"ユーザー設定の取得" 操作は、[リポジトリ API for Call Quality] ダッシュボードのユーザー設定サービスに含まれています。
  
## <a name="get-user-setting"></a>ユーザー設定の取得

Get User Setting は、単一のユーザー設定を返します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>の/QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** -なし。
  
 **ヘッダーを要求**する-追加のヘッダーは不要です。
  
 **要求本文**-なし。
  
 **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。
  
 **応答ヘッダー** -ヘッダーは追加されません。
  
 **応答本文**-以下は JSON のサンプル応答ペイロードです。
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId* -ユーザーの id です。
  
 設定*のキーキー* 。
  
 *値*-設定の値。
  

