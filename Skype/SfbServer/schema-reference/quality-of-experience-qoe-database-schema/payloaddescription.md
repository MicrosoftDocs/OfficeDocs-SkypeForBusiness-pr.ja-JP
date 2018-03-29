---
title: PayloadDescription テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription はテーブルをサポートします。 各レコードは、オーディオまたはビデオのセッションで使用される 1 つのコーデックを表します。
ms.openlocfilehash: fb4acb8182db920e25305b2be72cbc19700792bb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="payloaddescription-table"></a>PayloadDescription テーブル
 
PayloadDescription はテーブルをサポートします。 各レコードは、オーディオまたはビデオのセッションで使用される 1 つのコーデックを表します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |コーデックを識別する一意の番号です。  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |一意  <br/> |コーデックの名前です。  <br/> |
   

