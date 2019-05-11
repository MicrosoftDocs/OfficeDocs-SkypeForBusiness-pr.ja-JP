---
title: MonitoredRegionLink テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink はテーブルをサポートします。 各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
ms.openlocfilehash: 125f29a25b2ee039649dd47dcc405e208d0cd254
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920153"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink テーブル
 
MonitoredRegionLink はテーブルをサポートします。 各レコードは、2 つの国/地域の間の 1 つのリンクを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |[地域テーブル](region.md)から参照されています。  <br/> |
|**Region2Key** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |[地域テーブル](region.md)から参照されています。  <br/> |
   

