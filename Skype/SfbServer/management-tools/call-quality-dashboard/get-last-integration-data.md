---
title: 直近の統合データの取得
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: '概要: 通話品質ダッシュボードのデータ API の一部である、最後の統合データの取得操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: c40041e41e04d2bdc62a9eb9fa1eb699697a5b3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832517"
---
# <a name="get-last-integration-data"></a>直近の統合データの取得
 
**概要:** 呼び出し品質ダッシュボードのデータ API の一部である、最後の統合データの取得操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
最後の統合データの取得操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="get-last-integration-data"></a>直近の統合データの取得

[最後の統合データの取得] 操作では、アーカイブとキューブ処理の最後の 5 つの成功/失敗のリストが返されます。
  
この機能は既定で無効になっています。データ API を構成して有効にする必要があります。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog/Status  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - 以下にログの状態のサンプルを示します。
  
```json
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
