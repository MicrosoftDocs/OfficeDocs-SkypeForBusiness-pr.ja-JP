---
title: キャッシュのクリア
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '概要: 通話品質ダッシュボードのデータ API の一部であるキャッシュのクリア操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806417"
---
# <a name="clear-cache"></a>キャッシュのクリア
 
**概要:** 通話品質ダッシュボードのデータ API の一部であるキャッシュのクリア操作について説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
キャッシュのクリア操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="clear-cache"></a>キャッシュのクリア

キャッシュをクリア操作すると、クエリとデータのサーバー上のキャッシュが削除されます。 これによりキャッシュがリセットされ、後で新しい要求の QoE キューブから新しいデータが取得されます。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** - なし。
  
 **要求ヘッダー** - 追加のヘッダーはありません。
  
 **要求本文** - なし。
  
 **応答** - 応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード** - 正常な操作では、状態コード 200 (OK) が返されます。
  
 **応答ヘッダー** - 追加のヘッダーはありません。
  
 **応答本文** - なし。
  

