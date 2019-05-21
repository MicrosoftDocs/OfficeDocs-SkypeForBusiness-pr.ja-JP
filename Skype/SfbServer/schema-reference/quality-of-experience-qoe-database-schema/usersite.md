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
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite テーブルは、サポートされているテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのユーザーサイトを表します。
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294573"
---
# <a name="usersite-table"></a>UserSite テーブル
 
UserSite テーブルは、サポートされているテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのユーザーサイトを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |ユーザーサイトを識別する一意の番号です。  <br/> |
|**UserSiteName** <br/> |nvarchar(128  <br/> |一意  <br/> |ユーザーサイトの名前。  <br/> |
|**RegionKey** <br/> |int  <br/> |外部  <br/> |[Region テーブル](region.md)から参照されます。  <br/> |
   

