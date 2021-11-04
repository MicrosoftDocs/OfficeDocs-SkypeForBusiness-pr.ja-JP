---
title: MediationServers テーブル
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: 11a064f33ed4f38017cd0fb23ace687662af357f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762075"
---
# <a name="mediationservers-table"></a>MediationServers テーブル
 
MediationServers テーブルは、サポート テーブルです。 各レコードには、データベースにレコードがある呼び出しに関連する 1 つの仲介サーバーに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**MediationServerId** <br/> |int  <br/> |Primary  <br/> |この仲介サーバーを識別する一意の番号。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> | <br/> |仲介サーバー名。  <br/> |
   

