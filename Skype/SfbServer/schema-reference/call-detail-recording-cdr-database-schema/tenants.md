---
title: Tenants テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: テナントの表は、さまざまなテナントの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1つのテナントを表します。
ms.openlocfilehash: ecc83a429cb2e95426b289216f69d3a14e1826d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814855"
---
# <a name="tenants-table"></a>Tenants テーブル
 
テナントの表は、さまざまなテナントの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1つのテナントを表します。
  
> [!NOTE]
> オンプレミスの展開では、CDR はビルトインのテナント ID を使用して、パブリック IM 接続、フェデレーション、匿名など、さまざまな認証の種類を示します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**テナント** <br/> |int  <br/> |Primary  <br/> |このテナント ID を識別する一意の番号です。  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || 許可される値: <br/>  00000000-0000-0000-0000-000000000000-エンタープライズ <br/>  00000000-0000-0000-0000-000000000001-フェデレーション <br/>  00000000-0000-0000-0000-000000000002-匿名 <br/>  00000000-0000-0000-0000-000000000003-パブリック IM 接続 <br/> |
   

