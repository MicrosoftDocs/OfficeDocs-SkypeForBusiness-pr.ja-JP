---
title: MonitoredUserSiteLink テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874260"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink テーブル
 
MonitoredUserSiteLink はテーブルをサポートします。 各レコードは、ユーザーの 2 つのサイト間で 1 つのリンクを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |[UserSite テーブル](usersite.md)から参照されています。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |[UserSite テーブル](usersite.md)から参照します。  <br/> |
   

