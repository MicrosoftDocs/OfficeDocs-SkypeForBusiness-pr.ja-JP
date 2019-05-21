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
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: テナントの表は、さまざまなテナントの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1つのテナントを表します。
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295770"
---
# <a name="tenants-table"></a>Tenants テーブル
 
テナントの表は、さまざまなテナントの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1つのテナントを表します。
  
> [!NOTE]
> オンプレミスの展開では、CDR はビルトインのテナント ID を使用して、パブリック IM 接続、フェデレーション、匿名など、さまざまな認証の種類を示します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**テナント** <br/> |int  <br/> |Primary  <br/> |このテナント ID を識別する一意の番号です。  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || 許可される値: <br/>  00000000-0000-0000-0000-000000000000-エンタープライズ <br/>  00000000-0000-0000-0000-000000000001-フェデレーション <br/>  00000000-0000-0000-0000-000000000002-匿名 <br/>  00000000-0000-0000-0000-000000000003-パブリック IM 接続 <br/> |
   

