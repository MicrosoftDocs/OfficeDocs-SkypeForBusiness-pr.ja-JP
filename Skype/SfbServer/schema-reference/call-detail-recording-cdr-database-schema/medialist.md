---
title: MediaList テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。
ms.openlocfilehash: 00667806e5099db35cce29b07248569faf09ee24
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767495"
---
# <a name="medialist-table"></a>MediaList テーブル
 
MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |値: 1 ~ 7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || MediaID 値と Media 値の静的マッピング: <br/>  1 -- IM <br/>  2 - ファイル転送 <br/>  3 - リモート アシスタンス <br/>  4 - アプリケーション共有 <br/>  5 -- 音声 <br/>  6 -- ビデオ <br/>  7 - アプリの招待 <br/> |
   
LcsCDR.SessionDetailsView.MediaTypes の値のモダリティの種類を決定する場合は、次の Join スニペットを使用する必要があります。 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
