---
title: MonitoredRegionLink テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink はテーブルをサポートします。 各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
ms.openlocfilehash: 0df5cd8abe957ed952bdf656a67e1d423cc57f33
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884415"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink テーブル
 
MonitoredRegionLink はテーブルをサポートします。 各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |[地域テーブル](region.md)から参照されています。  <br/> |
|**Region2Key** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |[地域テーブル](region.md)から参照されています。  <br/> |
   

