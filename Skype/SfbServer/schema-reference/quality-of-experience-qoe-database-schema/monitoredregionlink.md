---
title: MonitoredRegionLink テーブル
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
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink テーブルは、サポート テーブルです。各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
ms.openlocfilehash: 991cc3b6ce2f442ad13c350d2e37cc7c9d592d40d16da51932975a4907040569
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321629"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink テーブル
 
MonitoredRegionLink テーブルは、サポート テーブルです。各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |整数  <br/> |主/プライマリ、外部  <br/> |Region テーブル [から参照されます](region.md)。  <br/> |
|**Region2Key** <br/> |整数  <br/> |主/プライマリ、外部  <br/> |Region テーブル [から参照されます](region.md)。  <br/> |
   

