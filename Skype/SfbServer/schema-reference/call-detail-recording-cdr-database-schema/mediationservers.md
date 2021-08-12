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
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers テーブルは、サポート テーブルです。 各レコードには、データベースにレコードがある呼び出しに関連する 1 つの仲介サーバーに関する情報が格納されます。
ms.openlocfilehash: ef980b18aece83b26619efc375f232040745a7b20d3dca4745e0ffcd60d6e57b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286256"
---
# <a name="mediationservers-table"></a>MediationServers テーブル
 
MediationServers テーブルは、サポート テーブルです。 各レコードには、データベースにレコードがある呼び出しに関連する 1 つの仲介サーバーに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**MediationServerId** <br/> |整数  <br/> |Primary  <br/> |この仲介サーバーを識別する一意の番号。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> | <br/> |仲介サーバー名。  <br/> |
   

