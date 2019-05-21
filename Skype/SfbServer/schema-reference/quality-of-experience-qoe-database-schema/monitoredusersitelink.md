---
title: MonitoredUserSiteLink テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink リンクテーブルは、サポートテーブルです。 各レコードは、2つのユーザーサイト間のリンク1つを表します。
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294853"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink テーブル
 
MonitoredUserSiteLink リンクテーブルは、サポートテーブルです。 各レコードは、2つのユーザーサイト間のリンク1つを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |プライマリ、外部  <br/> |[Usersite テーブル](usersite.md)から参照されます。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |プライマリ、外部  <br/> |[Usersite テーブル](usersite.md)から参照します。  <br/> |
   

