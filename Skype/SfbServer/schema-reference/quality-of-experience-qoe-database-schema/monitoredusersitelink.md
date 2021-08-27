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
ms.localizationpriority: medium
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink テーブルはサポート テーブルです。各レコードは、2 つのユーザー サイト間の 1 つのリンクを表します。
ms.openlocfilehash: a5a8802f3821fff3d08c2365d4f76655b5824606
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610574"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink テーブル
 
MonitoredUserSiteLink テーブルはサポート テーブルです。各レコードは、2 つのユーザー サイト間の 1 つのリンクを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主/プライマリ、外部  <br/> |[UserSite テーブルから参照されます](usersite.md)。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主/プライマリ、外部  <br/> |[UserSite テーブルからの参照](usersite.md)。  <br/> |
   

