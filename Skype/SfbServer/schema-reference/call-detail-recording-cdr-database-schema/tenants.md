---
title: テナント テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Tenants テーブルは、各種テナントの一覧を格納しているサポート テーブルです。テーブル内の各レコードが 1 つのテナントを表します。
ms.openlocfilehash: 37387fe3bbb4bae7b09a0898ee65373f5342c488
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863334"
---
# <a name="tenants-table"></a>テナント テーブル
 
Tenants テーブルは、各種テナントの一覧を格納しているサポート テーブルです。テーブル内の各レコードが 1 つのテナントを表します。
  
> [!NOTE]
> 内部設置型展開では、CDR は組み込みのテナント ID を使用して、パブリック IM 接続、フェデレーション、匿名など、さまざまな認証の種類を示します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |このテナント ID を識別する一意の番号。  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || 有効な値は次のとおりです。 <br/>  00000000-00000-0000-0000-00000000000 - Enterprise <br/>  000000000-00000-00000-00000-00000000001 - フェデレーション <br/>  000000000-00000-0000-0000-00000000002 - 匿名 <br/>  00000000-00000-0000-0000-00000000003 - パブリック IM 接続 <br/> |
   

