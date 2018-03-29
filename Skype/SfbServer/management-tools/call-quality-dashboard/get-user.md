---
title: ユーザーを取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '概要: は、ユーザー サービスの一部を取得するユーザーの操作について説明します。 ユーザー サービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: e3863819ea15a1039a3a02b1a35cfc7326af7e1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="get-user"></a>ユーザーを取得します。
 
**の概要:**ユーザー サービスの一部を取得するユーザーの操作について説明します。 ユーザー サービスは、品質のダッシュ ボードを呼び出すためのリポジトリ API の一部です。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。
  
ユーザーの取得操作は、リポジトリ api の呼び出し品質のダッシュ ボードのユーザー ・ サービスの一部です。
  
## <a name="get-user"></a>ユーザーを取得します。

リポジトリからユーザを返します。 ユーザー レコードを取得します。
  
|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>/QoERepositoryService/リポジトリとユーザー/{ユーザー Id}  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **リクエストの本文**の [なし] です。
  
 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。 特定のユーザ ID が見つからない場合は、ステータス コード 404 (見つかりません) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 **応答本体**の JSON のサンプル応答の内容を次に示します。
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}

```

 *ユーザー Id*がユーザーの ID。
  
 *loginName* - 通常のユーザーの外部ユーザー id です。 ユーザーの認証に Windows 認証を使用する場合、この可能性がありますユーザーの FQDN です。
  
 *defaultItemId* - このユーザーの既定の項目の ID です。 既定の項目は、ユーザーに関連付けられている最上位のアイテムです。 このユーザーが所有する他のすべての項目は、既定アイテムから移動できます。
  
> [!NOTE]
> 装置、`defaultItemId`の値を既定の項目の詳細を取得する項目の取得操作。
  

