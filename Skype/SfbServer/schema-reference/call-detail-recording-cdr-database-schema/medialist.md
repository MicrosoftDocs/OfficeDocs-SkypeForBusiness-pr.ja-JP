---
title: MediaList テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。
ms.openlocfilehash: 308a9eee57089a02b8e3ff9924e0d9d34162f33e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295984"
---
# <a name="medialist-table"></a>MediaList テーブル
 
MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |値: 1 -7  <br/> |
|**メディア** <br/> |nvarchar(256)  <br/> || MediaID 値と Media 値の固定マッピング: <br/>  1 -- IM <br/>  2-ファイル送信 <br/>  3-リモートアシスタンス <br/>  4-アプリケーション共有 <br/>  5 -- 音声 <br/>  6 -- ビデオ <br/>  7-アプリの招待 <br/> |
   
LcsCDR.SessionDetailsView.MediaTypes の値でモダリティの種類を特定しようとしている場合は、次の Join スニペットを使用する必要があります。 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
