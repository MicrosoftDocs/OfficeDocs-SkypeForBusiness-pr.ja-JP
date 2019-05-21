---
title: Skype for Business Server 2015 の CallPriorities 度表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 度テーブルは、"緊急"、"緊急"、"標準" などの、可能な呼び出しの優先順位の一覧を保存する静的テーブルです。
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296568"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の CallPriorities 度表
 
CallPriorities 度テーブルは、"緊急"、"緊急"、"標準" などの、可能な呼び出しの優先順位の一覧を保存する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**優先順位 Id** <br/> |tinyint  <br/> |Primary  <br/> ||
|**[Priority]** <br/> |nvarchar(256)  <br/> || 許可される値: <br/>  0-不明 <br/>  1-緊急以外 <br/>  2-標準 <br/>  3-緊急 <br/>  4-緊急 <br/> |
   

