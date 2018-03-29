---
title: ビジネス サーバー 2015 の Skype での CallPriorities テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities テーブルは、'緊急'、'緊急'、または '通常' など、可能な呼び出しの優先順位の一覧を格納する静的なテーブルです。
ms.openlocfilehash: ccd92857015e865e36cbef4147c4355369263e90
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での CallPriorities テーブル
 
CallPriorities テーブルは、'緊急'、'緊急'、または '通常' など、可能な呼び出しの優先順位の一覧を格納する静的なテーブルです。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**優先度** <br/> |nvarchar(256)  <br/> || 使用可能な値: <br/>  0 - 不明 <br/>  1-切迫感のないです。 <br/>  2-標準 <br/>  3-緊急 <br/>  4-緊急 <br/> |
   

