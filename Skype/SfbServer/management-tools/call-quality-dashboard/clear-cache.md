---
title: キャッシュのクリア
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '概要: 通話品質ダッシュボードのデータ API の一部である、消去キャッシュ操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274836"
---
# <a name="clear-cache"></a>キャッシュのクリア
 
**概要:** 通話品質ダッシュボードのデータ API の一部である、キャッシュのクリア操作について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。
  
キャッシュのクリア操作は、通話品質ダッシュボードのデータ API の一部です。
  
## <a name="clear-cache"></a>キャッシュのクリア

[キャッシュの消去] 操作は、クエリとデータのためにサーバー上のキャッシュを削除します。 これによりキャッシュがリセットされ、新しい要求があった場合は QoE キューブから最新のデータが取得されます。
  

|**メソッド**|**要求 URI**|**HTTP バージョン**|
|:-----|:-----|:-----|
|投稿  <br/> |https://\<ポータル\>の/QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI パラメーター** -なし。
  
 **ヘッダーを要求**する-追加のヘッダーは不要です。
  
 **要求本文**-なし。
  
 **応答**-応答には、HTTP 状態コードと応答ヘッダーのセットが含まれます。
  
 **状態コード**-正常に動作している操作は、状態コード 200 (OK) を返します。
  
 **応答ヘッダー** -ヘッダーは追加されません。
  
 **応答本文**-なし。
  

