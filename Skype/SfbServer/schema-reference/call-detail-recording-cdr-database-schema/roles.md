---
title: Roles テーブル
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
ms.openlocfilehash: a9f35c510eaca054dd504db4045686cb4eeaac4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="roles-table"></a>Roles テーブル
 
ロール」テーブルは、出席者と発表者など、可能な会議の役割の一覧を格納する静的なテーブルです。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**[役割]** <br/> |nvarchar(256)  <br/> || 使用可能な値: <br/>  0 - 不明 <br/>  1-プレゼンター <br/>  2-出席者 <br/> |
   

