---
title: MonitoredRegionLink テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink テーブルは、サポート テーブルです。各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
ms.openlocfilehash: 0efac1d496889645ffb52db5c419397337ebf9f2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858104"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink テーブル
 
MonitoredRegionLink テーブルは、サポート テーブルです。各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |主/プライマリ、外部  <br/> |Region テーブル [から参照されます](region.md)。  <br/> |
|**Region2Key** <br/> |int  <br/> |主/プライマリ、外部  <br/> |Region テーブル [から参照されます](region.md)。  <br/> |
   

