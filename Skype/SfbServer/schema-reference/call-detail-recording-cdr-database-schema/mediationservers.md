---
title: MediationServers テーブル
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
ms.openlocfilehash: 5854e9787497316d76b7262821be8d4953532d56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="mediationservers-table"></a>MediationServers テーブル
 
MediationServers はテーブルをサポートします。 各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つの仲介サーバーに関する情報を格納します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**MediationServerId** <br/> |int  <br/> |Primary  <br/> |この仲介サーバーを識別する一意の番号です。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> | <br/> |仲介サーバーの名前です。  <br/> |
   

