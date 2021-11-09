---
title: 2015 年の CallPriorities Skype for Business Server
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities テーブルは、"緊急"、"緊急"、"標準" などの呼び出しの優先順位の一覧を格納する静的テーブルです。
ms.openlocfilehash: ed31d55852f0b685429bd7fbf70cff1bf81d63ae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845140"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>2015 年の CallPriorities Skype for Business Server
 
CallPriorities テーブルは、"緊急"、"緊急"、"標準" などの呼び出しの優先順位の一覧を格納する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**優先度** <br/> |nvarchar(256)  <br/> || 有効な値は次のとおりです。 <br/>  0 - 不明 <br/>  1 - 緊急でない <br/>  2 -- 通常 <br/>  3 -- 至急 <br/>  4 -- 緊急 <br/> |
   

