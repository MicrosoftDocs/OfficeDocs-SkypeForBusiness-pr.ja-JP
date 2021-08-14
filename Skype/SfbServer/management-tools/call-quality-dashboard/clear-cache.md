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
description: '概要: 呼び出し品質ダッシュボードのデータ API の一部であるキャッシュのクリア操作について説明します。 品質ダッシュボードの呼び出しは、ユーザーのSkype for Business Server。'
ms.openlocfilehash: b6767302256d8d448141b9aab5ddeda6c80935173c8381747ae9d91e425d833f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351407"
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
  

