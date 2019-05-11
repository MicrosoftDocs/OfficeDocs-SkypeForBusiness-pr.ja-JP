---
title: キャッシュのクリア
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '概要: は、品質のダッシュ ボードを呼び出すためのデータ API の一部では、キャッシュのクリア操作について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 918709d87545289e46c6bef49aafb0f1d37b2950
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930806"
---
# <a name="clear-cache"></a>キャッシュのクリア
 
**の概要:** 品質のダッシュ ボードを呼び出すためのデータ API の一部では、キャッシュのクリア操作について説明します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。
  
キャッシュのクリアの操作は、品質のダッシュ ボードを呼び出すためのデータ API の一部です。
  
## <a name="clear-cache"></a>キャッシュのクリア

キャッシュのクリアの操作は、クエリとデータのサーバー上のキャッシュを削除します。 キャッシュがリセットし、紹介最新データ QoE キューブから後で新しい要求をします。
  

|**メソッド**|**URI を要求します。**|**HTTP のバージョン**|
|:-----|:-----|:-----|
|投稿  <br/> |https://\<ポータル\>/QoEDataService/ClearCache  <br/> |HTTP 1.1/  <br/> |
   
 **URI パラメーター**を [なし] です。
  
 **要求ヘッダー**の追加のヘッダーではありません。
  
 **リクエストの本文**の [なし] です。
  
 **応答**- 応答には、HTTP ステータス コード、応答ヘッダーのセットが含まれています。
  
 **ステータス コード**が正常終了した操作では、ステータス コード 200 (OK) を返します。
  
 **応答ヘッダー**の追加のヘッダーではありません。
  
 **応答本体**がないです。
  

