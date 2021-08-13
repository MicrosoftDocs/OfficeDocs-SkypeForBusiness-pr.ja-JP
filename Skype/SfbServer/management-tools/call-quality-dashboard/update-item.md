---
title: アイテムを更新する
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: '概要: アイテム サービスの一部であるアイテムの更新操作について学習します。 Item Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: ad615e5b6c6187a51293e86bcf3b1e2ee20c820f8c8c7a48b013d95befd03d87
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340803"
---
# <a name="update-item"></a>アイテムを更新する
 
**概要:** アイテム サービスの一部であるアイテムの更新操作について学習します。 Item Service は、呼び出し品質ダッシュボードのリポジトリ API の一部です。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
アイテムの更新操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。
  
## <a name="update-item"></a>アイテムを更新する

[アイテムの更新] は、リポジトリ内の特定のアイテムを更新します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** -Content-Type: application/json。
  
 **要求本文** - JSON。
  
サンプル要求ペイロード:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *コンテンツ*  既存のサブアイテムの新しいコンテンツとして格納される JSON 形式のデータ。 技術的には、リポジトリには任意のスキーマのコンテンツを格納できますが、通話品質ダッシュボードで使用する場合は、レポートまたはクエリのいずれかである必要があります。 *type*  通話品質ダッシュボードには常に "application/json" を指定します。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 204 (コンテンツなし) が返されます。 指定したアイテム ID が見つからない場合は、状態コード 404 (Not Found) が返されます。
  
> [!IMPORTANT]
> "コンテンツなし" はエラー状態ではありません。 これは、応答が本文内の何も返しなかったことを意味します (これに対し、200 OK は Body のコンテンツを返します)。 これは、アイテムが正常に更新されたことを示します。 
  
 **応答ヘッダー** - なし。
  
 **応答本文** - なし。
  

