---
title: Tenants テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: テナントのテーブルは、さまざまなテナントのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのテナントを表します。
ms.openlocfilehash: 4dde1baaf553c1a0d8a0efe65d72e8326cbb3bad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tenants-table"></a>Tenants テーブル
 
テナントのテーブルは、さまざまなテナントのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのテナントを表します。
  
> [!NOTE]
> 設置型展開では、CDR は、[フェデレーション] と [匿名、パブリック IM 接続など、さまざまな認証の種類を示すためにビルドのテナント ID を使用します。 
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |このテナント ID を識別する一意の番号  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || 使用可能な値: <br/>  00000000-0000-0000-0000-000000000000 ・ エンタープライズ <br/>  連合-00000000-0000-0000-0000-000000000001 <br/>  00000000-0000-0000-0000-000000000002 - 匿名 <br/>  00000000-0000-0000-0000-000000000003 のパブリック IM 接続 <br/> |
   

