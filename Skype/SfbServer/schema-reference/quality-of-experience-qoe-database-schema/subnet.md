---
title: Subnet テーブル
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: サブネットの表はサポートテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのサブネットを表します。
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805205"
---
# <a name="subnet-table"></a>Subnet テーブル
 
サブネットの表はサポートテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのサブネットを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |プライマリ、外部  <br/> |サブネットの IP の整数表現。  <br/> |
|**ネット** <br/> |int  <br/> ||サブネット マスク。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |外部  <br/> |[Usersite テーブル](usersite.md)から参照されます。  <br/> |
|**サブネットの説明** <br/> |nvarchar (512)  <br/> ||サブネットの説明。  <br/> |
   

