---
title: Tenants テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Tenants テーブルは、各種テナントの一覧を格納しているサポート テーブルです。 テーブル内の各レコードが 1 つのテナントを表します。
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831717"
---
# <a name="tenants-table"></a>Tenants テーブル
 
Tenants テーブルは、各種テナントの一覧を格納しているサポート テーブルです。テーブル内の各レコードが 1 つのテナントを表します。
  
> [!NOTE]
> 内部設置型展開では、CDR は組み込みのテナント ID を使用して、パブリック IM 接続、フェデレーション、匿名など、さまざまな認証の種類を示します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |このテナント ID を識別する一意の番号。  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || 有効な値は次のとおりです。 <br/>  00000000-0000-0000-0000-0000000000000 - Enterprise <br/>  00000000-0000-0000-0000-000000000001 - フェデレーション <br/>  00000000-0000-0000-0000-000000000002 - 匿名 <br/>  00000000-0000-0000-0000-000000000003 - パブリック IM 接続 <br/> |
   

