---
title: UserSite テーブル
ms.reviewer: ''
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
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885889"
---
# <a name="usersite-table"></a>UserSite テーブル
 
UserSite はテーブルをサポートします。 各レコードは、ネットワーク構成設定で定義されている 1 つのユーザー サイトを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |ユーザーのサイトを識別する一意の番号です。  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |一意  <br/> |ユーザー サイトの名前です。  <br/> |
|**RegionKey** <br/> |int  <br/> |外部  <br/> |[地域テーブル](region.md)から参照されています。  <br/> |
   

