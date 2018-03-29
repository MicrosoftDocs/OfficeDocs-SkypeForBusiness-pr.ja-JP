---
title: Subnet テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a>Subnet テーブル
 
The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.
  
|**Column**|**Data Type**|**Key/Index**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primary, Foreign  <br/> |Integer representation for the subnet IP.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||サブネット マスク。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |Referenced from the [UserSite table](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||The description for the subnet.  <br/> |
   

