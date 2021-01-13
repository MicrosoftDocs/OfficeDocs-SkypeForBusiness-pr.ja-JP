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
description: MediationServers テーブルはサポート テーブルです。 各レコードには、データベース内のレコードを持つ呼び出しに関係する 1 つの仲介サーバーに関する情報が格納されます。
ms.openlocfilehash: e498409087ee5cf41b32b29ec5f66a147290e1ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814767"
---
# <a name="mediationservers-table"></a>MediationServers テーブル
 
MediationServers テーブルはサポート テーブルです。 各レコードには、データベース内のレコードを持つ呼び出しに関係する 1 つの仲介サーバーに関する情報が格納されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**MediationServerId** <br/> |int  <br/> |Primary  <br/> |この仲介サーバーを識別する一意の番号。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> | <br/> |仲介サーバー名。  <br/> |
   

