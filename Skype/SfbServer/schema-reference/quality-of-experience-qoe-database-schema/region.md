---
title: Region テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: 領域はテーブルをサポートします。 各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。
ms.openlocfilehash: 1fcc6c0b4b2d9cbe1edc0a7127cda7f54cd079ed
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212131"
---
# <a name="region-table"></a>Region テーブル
 
領域はテーブルをサポートします。 各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**RegionKey** <br/> |int  <br/> |Primary  <br/> |国/地域を識別する一意の番号です。  <br/> |
|**RegionName** <br/> |nvarchar (128)  <br/> |一意  <br/> |国/地域の名前。  <br/> |
   

