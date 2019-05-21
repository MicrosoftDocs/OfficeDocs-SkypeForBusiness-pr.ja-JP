---
title: NetworkConnectionDetail テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail テーブルは、ネットワーク接続の種類を、エクスペリエンスデータベースの他の場所で使用されていたネットワーク接続識別子にマップします。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294818"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail テーブル
 
NetworkConnectionDetail テーブルは、ネットワーク接続の種類を、エクスペリエンスデータベースの他の場所で使用されていたネットワーク接続識別子にマップします。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Networkconnectionのキー** <br/> |tinyint  <br/> |Primary  <br/> |ネットワーク接続の種類を表す一意の識別子です。  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |一意  <br/> |ネットワーク接続の種類。ネットワーク接続の種類キーに対応しています。 有効な値は次のとおりです。  <br/> 0--有線  <br/> 1--WiFi  <br/> 2--イーサネット  <br/> MobileBB  <br/> 4--その他  <br/> 5--トンネル  <br/> |
   

