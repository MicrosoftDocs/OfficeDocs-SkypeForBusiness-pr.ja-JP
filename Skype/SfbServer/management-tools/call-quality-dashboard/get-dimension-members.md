---
title: ディメンション メンバーを取得します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: '概要: は、ディメンション メンバーを取得する操作について説明します。 ディメンション メンバーの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: e15f63d5ad52c9fbc52d692fd5bbb0480a41a50a
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569279"
---
# <a name="get-dimension-members"></a>ディメンション メンバーを取得します。
 
**の概要:** ディメンション メンバーを取得する操作について説明します。 ディメンション メンバーの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。
  
ディメンション メンバーの取得操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。
  
## <a name="get-dimension-members"></a>ディメンション メンバーを取得します。

ディメンション メンバーの取得操作は、特定のディメンションのメンバーの一覧を返します。 また、メンバーの一覧をフィルター処理し、ワイヤ転送コストを削減するのには、サブセットを取得する機能を提供します。
  

|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|投稿  <br/> |https://\<ポータル\>/QoEDataService/DimensionMembers  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **要求の本文**にするメンバーのディメンションの名前が含まれています。 メンバーの最大数が返されるの横にあるを指定することもいくつか返されるメンバーを制限するフィルタ リングします。
  
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

 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 以下は、JSON 内の「[開始日] 要求へ応答サンプル応答内容を**応答本文**:。[月]"分析コード。
  
> [!NOTE]
> 一覧を表示しているリストの一部です。 
  
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