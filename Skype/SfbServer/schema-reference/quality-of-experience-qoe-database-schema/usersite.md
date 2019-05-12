---
title: UserSite テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite はテーブルをサポートします。 各レコードは、ネットワーク構成設定で定義されている 1 つのユーザー サイトを表します。
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906954"
---
# <a name="usersite-table"></a>UserSite テーブル
 
UserSite はテーブルをサポートします。 各レコードは、ネットワーク構成設定で定義されている 1 つのユーザー サイトを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |ユーザーのサイトを識別する一意の番号です。  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |一意  <br/> |ユーザー サイトの名前です。  <br/> |
|**RegionKey** <br/> |int  <br/> |外部  <br/> |[地域テーブル](region.md)から参照されています。  <br/> |
   

