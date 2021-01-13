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
description: MonitoredRegionLink テーブルは、サポート テーブルです。 各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806347"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink テーブル
 
MonitoredRegionLink テーブルは、サポート テーブルです。各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |主/プライマリ、外部  <br/> |Region テーブル [から参照されます](region.md)。  <br/> |
|**Region2Key** <br/> |int  <br/> |主/プライマリ、外部  <br/> |Region テーブル [から参照されます](region.md)。  <br/> |
   

