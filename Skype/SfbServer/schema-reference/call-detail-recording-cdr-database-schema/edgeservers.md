---
title: ビジネス サーバー 2015 の Skype での EdgeServers テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers はテーブルをサポートします。 各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つのエッジ サーバーに関する情報を格納します。
ms.openlocfilehash: 253190f23d130d12a1b4af701bf68922717d8da8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213138"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での EdgeServers テーブル
 
EdgeServers はテーブルをサポートします。 各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つのエッジ サーバーに関する情報を格納します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Primary  <br/> |このエッジ サーバーを識別する一意の番号です。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |エッジ サーバーの名前です。  <br/> |
   

