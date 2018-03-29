---
title: NetworkConnectionDetail テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail テーブルは、ネットワーク接続の種類を高品質なエクスペリエンスのデータベース内で使用するネットワーク接続 id にマップします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail テーブル
 
NetworkConnectionDetail テーブルは、ネットワーク接続の種類を高品質なエクスペリエンスのデータベース内で使用するネットワーク接続 id にマップします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |ネットワーク接続の種類の一意の識別子です。  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |一意  <br/> |NetworkConnectionDetailKey に対応するネットワーク接続の種類です。 有効な値は次のとおりです。  <br/> 0--ワイヤード (有線)  <br/> 1--WiFi  <br/> 2--イーサネット  <br/> 3-MobileBB  <br/> 4-その他の  <br/> 5--トンネル  <br/> |
   

