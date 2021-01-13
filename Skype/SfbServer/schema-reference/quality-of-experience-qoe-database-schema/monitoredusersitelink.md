---
title: MonitoredUserSiteLink テーブル
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink テーブルはサポート テーブルです。 各レコードは、2 つのユーザー サイト間の 1 つのリンクを表します。
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806357"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink テーブル
 
MonitoredUserSiteLink テーブルはサポート テーブルです。各レコードは、2 つのユーザー サイト間の 1 つのリンクを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主/プライマリ、外部  <br/> |[UserSite テーブルから参照されます](usersite.md)。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主/プライマリ、外部  <br/> |[UserSite テーブルからの参照](usersite.md)。  <br/> |
   

