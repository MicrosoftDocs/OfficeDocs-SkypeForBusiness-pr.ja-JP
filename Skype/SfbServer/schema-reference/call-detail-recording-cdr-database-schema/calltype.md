---
title: CallType テーブル (Skype for Business Server 2015)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。
---

# <a name="calltype-table-in-skype-for-business-server-2015"></a>CallType テーブル (Skype for Business Server 2015)
 
CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 有効な値は次のとおりです。 <br/>  0 -- 不明 <br/>  1 - インスタント メッセージング <br/>  2 -- アプリケーション共有 <br/>  3 -- オーディオ <br/>  4 - オーディオとビデオ <br/>  5 - ファイル転送 <br/> |
   

