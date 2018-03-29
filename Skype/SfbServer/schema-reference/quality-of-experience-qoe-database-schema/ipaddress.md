---
title: Ip アドレス テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Ip アドレス テーブルは、高品質なエクスペリエンスのデータベース内で使用する一意の IP アドレス識別子を IP アドレスをマップします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a>Ip アドレス テーブル
 
Ip アドレス テーブルは、高品質なエクスペリエンスのデータベース内で使用する一意の IP アドレス識別子を IP アドレスをマップします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |指定した IP アドレスを表す一意の識別子です。  <br/> |
|**Ip アドレス** <br/> |varchar(50)  <br/> |一意  <br/> |一意の IP アドレス (たとえば、189.168.1.1)、IpAddressKey にマップします。 IPv4 または IPv6 アドレスのいずれかがあります。  <br/> |
   

