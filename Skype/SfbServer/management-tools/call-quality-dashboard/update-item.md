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
description: '概要: アイテム サービスの一部であるアイテムの更新操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803087"
---
# <a name="update-item"></a>アイテムを更新する
 
**概要:** アイテム サービスの一部であるアイテムの更新操作について学習します。 アイテム サービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
アイテムの更新操作は、呼び出し品質ダッシュボードのリポジトリ API のアイテム サービスの一部です。
  
## <a name="update-item"></a>アイテムを更新する

アイテムを更新すると、リポジトリ内の特定のアイテムが更新されます。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** -Content-Type: application/json。
  
 **要求本文** - JSON。
  
要求ペイロードの例:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *content*  既存のサブアイテムの新しいコンテンツとして格納される JSON 形式のデータ。 技術的には、リポジトリは任意のスキーマのコンテンツを格納できますが、通話品質ダッシュボードで使用する場合は、レポートまたはクエリである必要があります。 *type*  通話品質ダッシュボードには、常に "application/json" を指定します。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 204 (コンテンツなし) が返されます。 指定されたアイテム ID が見つからない場合は、状態コード 404 (Not Found) が返されます。
  
> [!IMPORTANT]
> "コンテンツなし" はエラー状態ではありません。 これは、応答が本文に何も返しなかったことを意味します (対照的に、200 OK は本文のコンテンツを返します)。 アイテムが正常に更新されたことを示します。 
  
 **応答ヘッダー** - なし。
  
 **応答本文** - なし。
  

