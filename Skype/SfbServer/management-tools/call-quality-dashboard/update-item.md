---
title: アイテムの更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: '概要: 項目サービスの一部である、項目の更新操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: aa46be0babf5998fcf2fabea797cb7a769914f8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274535"
---
# <a name="update-item"></a>アイテムの更新
 
**概要:** 項目サービスの一部である、項目の更新操作について説明します。 項目サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
アイテムの更新操作は、[リポジトリ API for Call Quality] ダッシュボードのアイテムサービスの一部です。
  
## <a name="update-item"></a>アイテムの更新

更新アイテムによって、リポジトリ内の特定のアイテムが更新されます。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|言う  <br/> |https://\<ポータル\>の/QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** -なし。
  
 **要求ヘッダー** -Content-Type: application/json。
  
 **要求本文**-JSON。
  
要求ペイロードの例:
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *コンテンツ* 既存のサブ項目の新しいコンテンツとして保存される JSON 形式のデータ。 技術的には、リポジトリには任意のスキーマのコンテンツを保存できますが、通話品質ダッシュボードに使用する場合は、レポートまたはクエリのいずれかにする必要があります。 *入力* 通話品質ダッシュボードの場合は、常に "application/json" を指定します。
  
 **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード**-正常に動作している操作は、状態コード 204 (コンテンツなし) を返します。 指定した項目 ID が見つからない場合は、状態コード 404 (見つからない) が返されます。
  
> [!IMPORTANT]
> "コンテンツなし" はエラー状態ではありません。 これは、応答が本文に何も返されなかったことを意味します (これは、200 OK は本文の内容を返します)。 項目が正常に更新されたことを示します。 
  
 **応答ヘッダー** -なし。
  
 **応答本文**-なし。
  

