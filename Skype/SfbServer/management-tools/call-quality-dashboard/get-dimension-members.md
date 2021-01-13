---
title: ディメンションのメンバーの取得
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
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: '概要: ディメンション メンバーの取得操作について学習します。 ディメンション メンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832637"
---
# <a name="get-dimension-members"></a>ディメンションのメンバーの取得
 
**概要:** ディメンション メンバーの取得操作について学習します。 ディメンション メンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
ディメンション メンバーの取得操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="get-dimension-members"></a>ディメンションのメンバーの取得

ディメンション メンバーの取得操作は、特定のディメンションのメンバーの一覧を返します。 また、メンバー リストをフィルター処理してサブセットを取得し、電信送金コストを削減する機能も提供します。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - メンバーが必要なディメンションの名前が含まれる。 また、返されるメンバーの数も上限です。また、返されるメンバーを制限するフィルターを指定できます。
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - "[StartDate]" の要求に対する応答として JSON のサンプル応答ペイロードを次に示します。[Month]" ディメンション。
  
> [!NOTE]
> リストには、一覧の一部しか表示されません。 
  
```json
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
