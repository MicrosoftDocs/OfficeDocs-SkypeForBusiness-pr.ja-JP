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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: サブネットの表はサポートテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのサブネットを表します。
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294636"
---
# <a name="subnet-table"></a>Subnet テーブル
 
サブネットの表はサポートテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのサブネットを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |プライマリ、外部  <br/> |サブネットの IP の整数表現。  <br/> |
|**ネット** <br/> |int  <br/> ||サブネット マスク。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |外部  <br/> |[Usersite テーブル](usersite.md)から参照されます。  <br/> |
|**サブネットの説明** <br/> |nvarchar (512)  <br/> ||サブネットの説明。  <br/> |
   

