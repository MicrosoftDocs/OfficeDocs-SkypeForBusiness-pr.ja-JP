---
title: UserSite テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite はテーブルをサポートします。 各レコードは、ネットワーク構成設定で定義されている 1 つのユーザー サイトを表します。
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a>UserSite テーブル
 
UserSite はテーブルをサポートします。 各レコードは、ネットワーク構成設定で定義されている 1 つのユーザー サイトを表します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |ユーザーのサイトを識別する一意の番号です。  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |一意  <br/> |ユーザー サイトの名前です。  <br/> |
|**RegionKey** <br/> |int  <br/> |外部  <br/> |[地域テーブル](region.md)から参照されています。  <br/> |
   

