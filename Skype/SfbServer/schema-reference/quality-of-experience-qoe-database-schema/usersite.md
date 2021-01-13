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
description: UserSite テーブルはサポート テーブルです。 各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799917"
---
# <a name="usersite-table"></a>UserSite テーブル
 
UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |ユーザー サイトを示す一意の番号です。  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |一意  <br/> |ユーザー サイトの名前。  <br/> |
|**RegionKey** <br/> |int  <br/> |外部  <br/> |Region テーブル [から参照されます](region.md)。  <br/> |
   

