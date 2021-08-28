---
title: UserAgent テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent テーブルは、データベースに記録されたセッションに参加したさまざまなユーザー エージェントの一覧を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのユーザー エージェントを表します
ms.openlocfilehash: 0c23582550e659f4a48661c80770c385e168ed3c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590061"
---
# <a name="useragent-table"></a>UserAgent テーブル
 
UserAgent テーブルは、データベースに記録されたセッションに参加したさまざまなユーザー エージェントの一覧を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのユーザー エージェントを表します
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |このユーザー エージェントを識別する一意の番号。  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |一意  <br/> |ユーザー エージェントの文字列。  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 は仲介サーバーです。  <br/> 2 は音声ビデオ会議サーバーです。  <br/> 4 はSkype for Business。  <br/> 8 は IP 電話。  <br/> 16 はライブ 会議コンソールです。  <br/> 32 は展開検証ツール (DVT) です。  <br/> 64 は macintosh Skype for Business Serverで使用できます。  <br/> 128 はSkype for Business Serverです。  <br/> 256 は会議アナウンスです。  <br/> 512 は会議自動応答。  <br/> 1024 は応答グループ アプリケーションです。  <br/> 2048 は外部音声コントロールです。  <br/> |
   

