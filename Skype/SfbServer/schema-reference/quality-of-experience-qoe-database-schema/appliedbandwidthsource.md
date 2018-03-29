---
title: AppliedBandwidthSource テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource はテーブルをサポートします。 各レコードは、1 つのソースを表します。
ms.openlocfilehash: e15df92423a3408e3cb8ae40a0788e1f165961df
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource テーブル
 
AppliedBandwidthSource はテーブルをサポートします。 各レコードは、1 つのソースを表します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |ソースを識別する一意の番号です。  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |一意  <br/> |これは、適用されている帯域幅のキャップのソースです。 それは、帯域幅の制限値の取得先 (ポリシー サーバー」、「サーバーを有効にする」または「モダリティ」など) について説明します。  <br/> |
   

