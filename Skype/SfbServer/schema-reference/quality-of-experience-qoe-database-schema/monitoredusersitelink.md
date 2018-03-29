---
title: MonitoredUserSiteLink テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink はテーブルをサポートします。 各レコードは、ユーザーの 2 つのサイト間で 1 つのリンクを表します。
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink テーブル
 
MonitoredUserSiteLink はテーブルをサポートします。 各レコードは、ユーザーの 2 つのサイト間で 1 つのリンクを表します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |[UserSite テーブル](usersite.md)から参照されています。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |[UserSite テーブル](usersite.md)から参照します。  <br/> |
   

