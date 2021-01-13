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
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail テーブルは、Quality of Experience データベースの他の場所で使用されるネットワーク接続の識別子にネットワーク接続の種類を対応させます。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806307"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail テーブル
 
NetworkConnectionDetail テーブルは、Quality of Experience データベースの他の場所で使用されるネットワーク接続の識別子にネットワーク接続の種類を対応させます。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |ネットワーク接続の種類の一意の識別子。  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |一意  <br/> |NetworkConnectionDetailKey に対応するネットワーク接続の種類。有効な値は次のとおりです。  <br/> 0: 有線  <br/> 1: WiFi  <br/> 2: イーサネット  <br/> 3 -- MobileBB  <br/> 4 -- その他  <br/> 5 -- トンネル  <br/> |
   

