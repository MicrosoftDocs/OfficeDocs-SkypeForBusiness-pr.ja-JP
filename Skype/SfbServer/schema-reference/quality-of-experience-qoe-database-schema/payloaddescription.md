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
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription テーブルは、サポートテーブルです。 各レコードは、オーディオセッションまたはビデオセッションで使用される1つのコーデックを表します。
ms.openlocfilehash: 41819c8329802b224bd3848334eddbc9de6935f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294811"
---
# <a name="payloaddescription-table"></a>PayloadDescription テーブル
 
PayloadDescription テーブルは、サポートテーブルです。 各レコードは、オーディオセッションまたはビデオセッションで使用される1つのコーデックを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |コーデックを識別する一意の番号。  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |一意  <br/> |コーデック名。  <br/> |
   

