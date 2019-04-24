---
title: PayloadDescription テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 320542593479e3051992e8079abfdf9f54b0efc0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212187"
---
# <a name="payloaddescription-table"></a>PayloadDescription テーブル
 
PayloadDescription はテーブルをサポートします。 各レコードは、オーディオまたはビデオのセッションで使用される 1 つのコーデックを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |コーデックを識別する一意の番号です。  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |一意  <br/> |コーデックの名前です。  <br/> |
   

