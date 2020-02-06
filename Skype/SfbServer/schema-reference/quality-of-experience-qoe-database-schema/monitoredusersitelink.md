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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink リンクテーブルは、サポートテーブルです。 各レコードは、2つのユーザーサイト間のリンク1つを表します。
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807795"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink テーブル
 
MonitoredUserSiteLink リンクテーブルは、サポートテーブルです。 各レコードは、2つのユーザーサイト間のリンク1つを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |プライマリ、外部  <br/> |[Usersite テーブル](usersite.md)から参照されます。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |プライマリ、外部  <br/> |[Usersite テーブル](usersite.md)から参照します。  <br/> |
   

