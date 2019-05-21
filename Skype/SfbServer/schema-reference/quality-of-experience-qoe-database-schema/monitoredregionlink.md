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
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink テーブルはサポートテーブルです。 各レコードは、2つの国/地域間のリンクを1つ表します。
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294874"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink テーブル
 
MonitoredRegionLink テーブルはサポートテーブルです。 各レコードは、2つの国/地域間のリンクを1つ表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |プライマリ、外部  <br/> |[Region テーブル](region.md)から参照されます。  <br/> |
|**Region2Key** <br/> |int  <br/> |プライマリ、外部  <br/> |[Region テーブル](region.md)から参照されます。  <br/> |
   

