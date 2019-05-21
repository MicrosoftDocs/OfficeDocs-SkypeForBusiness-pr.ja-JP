---
title: ユーザーの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '概要: ユーザーサービスの一部であるユーザーの取得操作について説明します。 ユーザーサービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 6c38bb2db2bef1a21dfc5c4791de7a163c57ff5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274598"
---
# <a name="get-user"></a>ユーザーの取得
 
**概要:** ユーザーサービスの一部であるユーザーの取得操作について説明します。 ユーザーサービスは、通話品質ダッシュボードのリポジトリ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
ユーザーの取得操作は、ユーザーサービスの一部であり、通話品質ダッシュボードのリポジトリ API に含まれています。
  
## <a name="get-user"></a>ユーザーの取得

ユーザー Get は、リポジトリからユーザーレコードを返します。
  
|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|取得  <br/> |https://\<ポータル\>の/QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** -なし。
  
 **ヘッダーを要求**する-追加のヘッダーは不要です。
  
 **要求本文**-なし。
  
 **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。 指定したユーザー ID が見つからない場合は、状態コード 404 (見つかりません) が返されます。
  
 **応答ヘッダー** -ヘッダーは追加されません。
  
 **応答本文**-以下は JSON のサンプル応答ペイロードです。
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId* -ユーザーの id です。
  
 *ログイン*情報-通常ユーザーの外部ユーザー id。 ユーザーの認証に Windows 認証が使用されている場合は、ユーザーの FQDN である可能性があります。
  
 *defaultItemId* -このユーザーの既定のアイテムの ID です。 既定のアイテムは、ユーザーに関連付けられている最上位のアイテムです。 このユーザーが所有する他のすべてのアイテムは、既定のアイテムから移動することができます。
  
> [!NOTE]
> 項目の`defaultItemId`操作を取得する値を指定して、既定の項目の詳細を取得します。
  

