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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 度テーブルは、"緊急"、"緊急"、"標準" などの、可能な呼び出しの優先順位の一覧を保存する静的テーブルです。
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815445"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の CallPriorities 度表
 
CallPriorities 度テーブルは、"緊急"、"緊急"、"標準" などの、可能な呼び出しの優先順位の一覧を保存する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**優先順位 Id** <br/> |tinyint  <br/> |Primary  <br/> ||
|**[Priority]** <br/> |nvarchar(256)  <br/> || 許可される値: <br/>  0-不明 <br/>  1-緊急以外 <br/>  2-標準 <br/>  3-緊急 <br/>  4-緊急 <br/> |
   

