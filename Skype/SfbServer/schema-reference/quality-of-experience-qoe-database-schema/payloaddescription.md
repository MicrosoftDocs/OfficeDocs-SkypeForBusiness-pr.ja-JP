---
title: PayloadDescription テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription テーブルは、サポート テーブルです。各レコードが、音声セッションまたはビデオ セッションで使用される 1 つのコーデックを表します。
ms.openlocfilehash: dedbf806c6cda1ce174e1a3282b81a409b63bced
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610564"
---
# <a name="payloaddescription-table"></a>PayloadDescription テーブル
 
PayloadDescription テーブルは、サポート テーブルです。各レコードが、音声セッションまたはビデオ セッションで使用される 1 つのコーデックを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |コーデックを識別する一意の番号。  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |一意  <br/> |コーデック名。  <br/> |
   

