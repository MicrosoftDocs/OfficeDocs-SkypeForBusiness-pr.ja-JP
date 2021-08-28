---
title: NetworkConnectionDetail テーブル
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
ms.localizationpriority: medium
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail テーブルは、Quality of Experience データベースの他の場所で使用されるネットワーク接続の識別子にネットワーク接続の種類を対応させます。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: d6e8bf04c8426a6278528de90f383c9867f92c8b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626449"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail テーブル
 
NetworkConnectionDetail テーブルは、Quality of Experience データベースの他の場所で使用されるネットワーク接続の識別子にネットワーク接続の種類を対応させます。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |ネットワーク接続の種類の一意の識別子。  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |一意  <br/> |NetworkConnectionDetailKey に対応するネットワーク接続の種類。有効な値は次のとおりです。  <br/> 0: 有線  <br/> 1: WiFi  <br/> 2: イーサネット  <br/> 3 -- MobileBB  <br/> 4 -- その他  <br/> 5 -- Tunnel  <br/> |
   

