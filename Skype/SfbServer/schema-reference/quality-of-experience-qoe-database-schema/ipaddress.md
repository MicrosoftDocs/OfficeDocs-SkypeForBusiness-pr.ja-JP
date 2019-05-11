---
title: Ip アドレス テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Ip アドレス テーブルは、高品質なエクスペリエンスのデータベース内で使用する一意の IP アドレス識別子を IP アドレスをマップします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: d7d3b5f9192c2385836f42f9c430da5b99752892
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920034"
---
# <a name="ipaddress-table"></a>Ip アドレス テーブル
 
Ip アドレス テーブルは、高品質なエクスペリエンスのデータベース内で使用する一意の IP アドレス識別子を IP アドレスをマップします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |指定した IP アドレスを表す一意の識別子です。  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |一意  <br/> |一意の IP アドレス (たとえば、189.168.1.1)、IpAddressKey にマップします。 IPv4 または IPv6 アドレスのいずれかがあります。  <br/> |
   

