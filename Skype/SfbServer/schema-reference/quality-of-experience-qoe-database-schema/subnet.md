---
title: Subnet テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: サブネット テーブルはサポート テーブルです。 各レコードは、ネットワーク構成設定で定義されている 1 つのサブネットを表します。
ms.openlocfilehash: f659d73bbdd654365697a9f853fbb48162e1bba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907067"
---
# <a name="subnet-table"></a>Subnet テーブル
 
サブネット テーブルはサポート テーブルです。 各レコードは、ネットワーク構成設定で定義されている 1 つのサブネットを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |サブネット ip アドレスの整数表現。  <br/> |
|**サブネット マスク** <br/> |int  <br/> ||サブネット マスク。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |外部  <br/> |[UserSite テーブル](usersite.md)から参照されています。  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||サブネットの説明です。  <br/> |
   

