---
title: CallType テーブル (Skype for Business Server 2015)
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。
ms.openlocfilehash: d5dce646dfff73d9935aba568827e21671daf4073721f8b892f369d62348e945
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296966"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>CallType テーブル (Skype for Business Server 2015)
 
CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |整数  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 有効な値は次のとおりです。 <br/>  0 -- 不明 <br/>  1 - インスタント メッセージング <br/>  2 -- アプリケーション共有 <br/>  3 -- オーディオ <br/>  4 - オーディオとビデオ <br/>  5 - ファイル転送 <br/> |
   

