---
title: AppliedBandwidthSource テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource テーブルは、サポートテーブルです。 各レコードは1つのソースを表します。
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295112"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource テーブル
 
AppliedBandwidthSource テーブルは、サポートテーブルです。 各レコードは1つのソースを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |ソースを識別する一意の番号。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)  <br/> |一意  <br/> |これは、適用される帯域幅の上限のソースです。 帯域幅の制限の対象となる場所 (たとえば、"Policy Server"、"TURN Server"、"モダリティ" など) について説明します。  <br/> |
   

