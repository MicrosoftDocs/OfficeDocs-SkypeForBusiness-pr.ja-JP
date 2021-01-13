---
title: Skype for Business Server 2015 の EdgeServers テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers テーブルはサポート テーブルです。 各レコードには、データベースにレコードがある呼び出しに関係する 1 つのエッジ サーバーに関する情報が格納されます。
ms.openlocfilehash: 98f37ecbf976fb08ae27e080f5e9e498558131fb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813207"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の EdgeServers テーブル
 
EdgeServers テーブルはサポート テーブルです。 各レコードには、データベースにレコードがある呼び出しに関係する 1 つのエッジ サーバーに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Primary  <br/> |このエッジ サーバーを識別する一意の番号。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |エッジ サーバー名。  <br/> |
   

