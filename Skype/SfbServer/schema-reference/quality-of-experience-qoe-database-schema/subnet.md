---
title: サブネット テーブル
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet テーブルは、サポート テーブルです。それぞれのレコードは、ネットワーク構成の設定で定義された 1 つのサブネットを表します。
ms.openlocfilehash: 10df067fe95f244aea2fa9987b4962efaef9fbe32fbbfbe5b0e9f6ed9f6392e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279963"
---
# <a name="subnet-table"></a>サブネット テーブル
 
Subnet テーブルは、サポート テーブルです。それぞれのレコードは、ネットワーク構成の設定で定義された 1 つのサブネットを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |整数  <br/> |主/プライマリ、外部  <br/> |サブネット IP の整数表現。  <br/> |
|**SubnetMask** <br/> |整数  <br/> ||サブネット マスク。  <br/> |
|**UserSiteKey** <br/> |整数  <br/> |外部  <br/> |[UserSite テーブルから参照されます](usersite.md)。  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||サブネットの説明。  <br/> |
   

