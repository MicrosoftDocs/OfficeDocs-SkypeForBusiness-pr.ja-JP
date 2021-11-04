---
title: CallType テーブル (Skype for Business Server 2015)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 05bfcf5b13735a460f8122fc6b1ce5eeddf94b97
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743193"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>CallType テーブル (Skype for Business Server 2015)
 
CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 有効な値は次のとおりです。 <br/>  0 -- 不明 <br/>  1 - インスタント メッセージング <br/>  2 -- アプリケーション共有 <br/>  3 -- オーディオ <br/>  4 - オーディオとビデオ <br/>  5 - ファイル転送 <br/> |
   

