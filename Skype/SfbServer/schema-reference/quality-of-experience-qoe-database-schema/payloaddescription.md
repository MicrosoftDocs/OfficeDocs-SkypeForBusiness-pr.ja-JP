---
title: PayloadDescription テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription テーブルは、サポートテーブルです。 各レコードは、オーディオセッションまたはビデオセッションで使用される1つのコーデックを表します。
ms.openlocfilehash: 3a5719d7fbfe23eb8c1457565a36df0a02617fde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807495"
---
# <a name="payloaddescription-table"></a>PayloadDescription テーブル
 
PayloadDescription テーブルは、サポートテーブルです。 各レコードは、オーディオセッションまたはビデオセッションで使用される1つのコーデックを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |コーデックを識別する一意の番号。  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |一意  <br/> |コーデック名。  <br/> |
   

