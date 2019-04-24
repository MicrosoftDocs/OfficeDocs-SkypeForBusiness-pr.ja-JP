---
title: Roles テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: ロール」テーブルは、出席者と発表者など、可能な会議の役割の一覧を格納する静的なテーブルです。
ms.openlocfilehash: 2b7759cc600471a8bf1b989ce429f6b2a4149ee0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212832"
---
# <a name="roles-table"></a>Roles テーブル
 
ロール」テーブルは、出席者と発表者など、可能な会議の役割の一覧を格納する静的なテーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**[役割]** <br/> |nvarchar(256)  <br/> || 使用可能な値: <br/>  0 - 不明 <br/>  1-プレゼンター <br/>  2-出席者 <br/> |
   

