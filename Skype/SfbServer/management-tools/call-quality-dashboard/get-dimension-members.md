---
title: ディメンションのメンバーの取得
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: '概要: ディメンションメンバーの取得操作について説明します。 ディメンションメンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: c457e7f3b42aaeb11c35180bc4c1ae6ee42b914e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274752"
---
# <a name="get-dimension-members"></a>ディメンションのメンバーの取得
 
**概要:** ディメンションメンバーの取得操作について説明します。 ディメンションメンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
ディメンションメンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="get-dimension-members"></a>ディメンションのメンバーの取得

ディメンションメンバーの取得操作特定のディメンションのメンバーの一覧を返します。 また、メンバーリストをフィルター処理して、送金料金を削減することができます。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|投稿  <br/> |https://\<ポータル\>の/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** -なし。
  
 **ヘッダーを要求**する-追加のヘッダーは不要です。
  
 **要求本文**-メンバーが必要とするディメンションの名前が含まれます。 返されるメンバーの最大数として、その横にあるフィルターを指定して、返されるメンバーを制限することもできます。
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。
  
 **応答ヘッダー** -ヘッダーは追加されません。
  
 **応答本文**-以下は、"[開始日] の要求に応じて、JSON のサンプル応答のペイロードを示しています。[Month] "ディメンション。
  
> [!NOTE]
> リストは、リストのごく一部のみを表示します。 
  
```
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
