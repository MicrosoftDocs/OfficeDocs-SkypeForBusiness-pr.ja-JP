---
title: MediationServers テーブル
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
ms.localizationpriority: medium
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers テーブルは、サポート テーブルです。 各レコードには、データベースにレコードがある呼び出しに関連する 1 つの仲介サーバーに関する情報が格納されます。
ms.openlocfilehash: 946b5750f90ed753f137e0b249af8164e3619f08
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583801"
---
# <a name="mediationservers-table"></a>MediationServers テーブル
 
MediationServers テーブルは、サポート テーブルです。 各レコードには、データベースにレコードがある呼び出しに関連する 1 つの仲介サーバーに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**MediationServerId** <br/> |int  <br/> |Primary  <br/> |この仲介サーバーを識別する一意の番号。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> | <br/> |仲介サーバー名。  <br/> |
   

