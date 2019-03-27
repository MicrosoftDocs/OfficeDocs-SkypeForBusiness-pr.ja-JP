---
title: MediationServers テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers はテーブルをサポートします。 各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つの仲介サーバーに関する情報を格納します。
ms.openlocfilehash: 77173fbb81bc2046a1906c61456f607ec7f2b5b3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877071"
---
# <a name="mediationservers-table"></a>MediationServers テーブル
 
MediationServers はテーブルをサポートします。 各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つの仲介サーバーに関する情報を格納します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**MediationServerId** <br/> |int  <br/> |Primary  <br/> |この仲介サーバーを識別する一意の番号です。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> | <br/> |仲介サーバーの名前です。  <br/> |
   

