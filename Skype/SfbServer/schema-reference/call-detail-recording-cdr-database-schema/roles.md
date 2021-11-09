---
title: Roles テーブル
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles テーブルは、会議で使用可能な役割 (参加者、発表者など) のリストを格納する静的なテーブルです。
ms.openlocfilehash: 67faf16a478a8ca1f4c2f3bc21bd5d4a6f28909f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842649"
---
# <a name="roles-table"></a>Roles テーブル
 
Roles テーブルは、会議で使用可能な役割 (参加者、発表者など) のリストを格納する静的なテーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**役割** <br/> |nvarchar(256)  <br/> || 有効な値は次のとおりです。 <br/>  0 - 不明 <br/>  1 - 発表者 <br/>  2 - 参加者 <br/> |
   

