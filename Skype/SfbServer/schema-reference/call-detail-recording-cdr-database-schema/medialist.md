---
title: MediaList テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。
ms.openlocfilehash: 72ae6dbb145c3bb284f1090b01585591e4e773bf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877518"
---
# <a name="medialist-table"></a>MediaList テーブル
 
MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |値: 1 -7  <br/> |
|**メディア** <br/> |nvarchar(256)  <br/> || MediaID 値と Media 値の固定マッピング: <br/>  1 -- IM <br/>  2-ファイル転送 <br/>  3-リモート アシスタンス <br/>  4-アプリケーションの共有 <br/>  5 -- 音声 <br/>  6 -- ビデオ <br/>  7-アプリケーションへの招待 <br/> |
   
LcsCDR.SessionDetailsView.MediaTypes の値でモダリティの種類を特定しようとしている場合は、次の Join スニペットを使用する必要があります。 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
