---
title: サブネット テーブル
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet テーブルは、サポート テーブルです。それぞれのレコードは、ネットワーク構成の設定で定義された 1 つのサブネットを表します。
ms.openlocfilehash: b0c10fae89fe76c184e3aaffec4e1166c4cdb94c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768315"
---
# <a name="subnet-table"></a>サブネット テーブル
 
Subnet テーブルは、サポート テーブルです。それぞれのレコードは、ネットワーク構成の設定で定義された 1 つのサブネットを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主/プライマリ、外部  <br/> |サブネット IP の整数表現。  <br/> |
|**SubnetMask** <br/> |int  <br/> ||サブネット マスク。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |外部  <br/> |[UserSite テーブルから参照されます](usersite.md)。  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||サブネットの説明。  <br/> |
   

