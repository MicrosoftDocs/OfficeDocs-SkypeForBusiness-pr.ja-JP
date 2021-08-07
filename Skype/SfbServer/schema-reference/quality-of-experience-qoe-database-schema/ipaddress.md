---
title: IPAddress テーブル
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress テーブルは、IP アドレスを体感品質データベースの他の場所で使用される一意の IP アドレス識別子にマップします。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: db9405a05335974456f77d8117f9e3f64e9832750c3d2c23441a5a587ca91d7a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305099"
---
# <a name="ipaddress-table"></a>IPAddress テーブル
 
IPAddress テーブルは、IP アドレスを体感品質データベースの他の場所で使用される一意の IP アドレス識別子にマップします。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |整数  <br/> |Primary  <br/> |指定した IP アドレスの一意の識別子。  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |一意  <br/> |IpAddressKey にマップされる一意の IP アドレス (189.168.1.1 など)。これは IPv4 または IPv6 アドレスです。  <br/> |
   

