---
title: Subnet テーブル
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
description: Subnet テーブルは、サポート テーブルです。 それぞれのレコードは、ネットワーク構成の設定で定義された 1 つのサブネットを表します。
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831337"
---
# <a name="subnet-table"></a>Subnet テーブル
 
Subnet テーブルは、サポート テーブルです。それぞれのレコードは、ネットワーク構成の設定で定義された 1 つのサブネットを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主/プライマリ、外部  <br/> |サブネット IP の整数表現。  <br/> |
|**SubnetMask** <br/> |int  <br/> ||サブネット マスク。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |外部  <br/> |[UserSite テーブルから参照されます](usersite.md)。  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||サブネットの説明。  <br/> |
   

