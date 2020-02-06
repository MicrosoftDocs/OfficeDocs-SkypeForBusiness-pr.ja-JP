---
title: UserSite テーブル
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite テーブルは、サポートされているテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのユーザーサイトを表します。
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805005"
---
# <a name="usersite-table"></a>UserSite テーブル
 
UserSite テーブルは、サポートされているテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのユーザーサイトを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |ユーザーサイトを識別する一意の番号です。  <br/> |
|**UserSiteName** <br/> |nvarchar(128  <br/> |一意  <br/> |ユーザーサイトの名前。  <br/> |
|**RegionKey** <br/> |int  <br/> |外部  <br/> |[Region テーブル](region.md)から参照されます。  <br/> |
   

