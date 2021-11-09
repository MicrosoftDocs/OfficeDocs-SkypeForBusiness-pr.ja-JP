---
title: キャッシュのクリア
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '概要: 呼び出し品質ダッシュボードのデータ API の一部であるキャッシュのクリア操作について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: de956a3541416100cf7877b46340f2eccb38b3ea
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843820"
---
# <a name="clear-cache"></a>キャッシュのクリア
 
**概要:** 呼び出し品質ダッシュボードのデータ API の一部であるキャッシュのクリア操作について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。
  
キャッシュのクリア操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="clear-cache"></a>キャッシュのクリア

[キャッシュのクリア] 操作を実行すると、クエリとデータのサーバー上のキャッシュが削除されます。 これにより、キャッシュがリセットされ、新しい要求に対して QoE キューブから新しいデータが取得されます。
  

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
  

