---
title: NetworkConnectionDetail テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 6df2511c2dfee0158b4633be5dfa8549639cfc6d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212391"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail テーブル
 
NetworkConnectionDetail テーブルは、ネットワーク接続の種類を高品質なエクスペリエンスのデータベース内で使用するネットワーク接続 id にマップします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |ネットワーク接続の種類の一意の識別子です。  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |一意  <br/> |NetworkConnectionDetailKey に対応するネットワーク接続の種類です。 有効な値は次のとおりです。  <br/> 0--ワイヤード (有線)  <br/> 1--WiFi  <br/> 2--イーサネット  <br/> 3-MobileBB  <br/> 4-その他の  <br/> 5--トンネル  <br/> |
   

