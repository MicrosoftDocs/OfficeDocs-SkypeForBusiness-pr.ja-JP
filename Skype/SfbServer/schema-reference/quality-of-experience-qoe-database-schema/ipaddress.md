---
title: IPAddress テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress テーブルは、パフォーマンスの高いデータベースの別の場所で使用されている一意の IP アドレス識別子に IP アドレスをマッピングします。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809545"
---
# <a name="ipaddress-table"></a>IPAddress テーブル
 
IPAddress テーブルは、パフォーマンスの高いデータベースの別の場所で使用されている一意の IP アドレス識別子に IP アドレスをマッピングします。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |指定した IP アドレスの一意の識別子。  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |一意  <br/> |IpAddressKey にマップされる固有の IP アドレス (たとえば、189.168.1.1)。 これは IPv4 または IPv6 アドレスのいずれかになります。  <br/> |
   

