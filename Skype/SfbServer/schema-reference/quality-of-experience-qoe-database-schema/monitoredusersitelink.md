---
title: MonitoredUserSiteLink テーブル
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: 3cc8c11f049e98223c80756eb2dc83f1b9354ec7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768365"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink テーブル
 
MonitoredUserSiteLink テーブルはサポート テーブルです。各レコードは、2 つのユーザー サイト間の 1 つのリンクを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主/プライマリ、外部  <br/> |[UserSite テーブルから参照されます](usersite.md)。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主/プライマリ、外部  <br/> |[UserSite テーブルからの参照](usersite.md)。  <br/> |
   

