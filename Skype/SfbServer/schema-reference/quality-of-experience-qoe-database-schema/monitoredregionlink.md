---
title: MonitoredRegionLink テーブル
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink テーブルはサポートテーブルです。 各レコードは、2つの国/地域間のリンクを1つ表します。
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807815"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink テーブル
 
MonitoredRegionLink テーブルはサポートテーブルです。 各レコードは、2つの国/地域間のリンクを1つ表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |プライマリ、外部  <br/> |[Region テーブル](region.md)から参照されます。  <br/> |
|**Region2Key** <br/> |int  <br/> |プライマリ、外部  <br/> |[Region テーブル](region.md)から参照されます。  <br/> |
   

