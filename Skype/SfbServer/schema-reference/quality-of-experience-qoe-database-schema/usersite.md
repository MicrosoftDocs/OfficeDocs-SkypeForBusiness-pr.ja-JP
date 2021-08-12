---
title: UserSite テーブル
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。
ms.openlocfilehash: 01ab76218040d37176355d62768c6a8b8f4b7336d22ce7263c61ac9fc8c289ed
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314333"
---
# <a name="usersite-table"></a>UserSite テーブル
 
UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |整数  <br/> |Primary  <br/> |ユーザー サイトを示す一意の番号です。  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |一意  <br/> |ユーザー サイトの名前。  <br/> |
|**RegionKey** <br/> |整数  <br/> |外部  <br/> |Region テーブル [から参照されます](region.md)。  <br/> |
   

