---
title: UserSite テーブル
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。
ms.openlocfilehash: d8e7ccea49d00355a3e114833518cf5e6f762674
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737483"
---
# <a name="usersite-table"></a>UserSite テーブル
 
UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |ユーザー サイトを示す一意の番号です。  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |一意  <br/> |ユーザー サイトの名前。  <br/> |
|**RegionKey** <br/> |int  <br/> |外部  <br/> |Region テーブル [から参照されます](region.md)。  <br/> |
   

