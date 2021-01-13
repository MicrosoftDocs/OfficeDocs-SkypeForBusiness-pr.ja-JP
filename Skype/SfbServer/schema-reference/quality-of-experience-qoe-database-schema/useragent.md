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
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent テーブルは、データベースに記録されたセッションに参加したさまざまなユーザー エージェントのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのユーザー エージェントを表します。
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799937"
---
# <a name="useragent-table"></a>UserAgent テーブル
 
UserAgent テーブルは、データベースに記録されたセッションに参加したさまざまなユーザー エージェントのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのユーザー エージェントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |このユーザー エージェントを識別する一意の番号。  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |一意  <br/> |ユーザー エージェント文字列。  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 は仲介サーバーです。  <br/> 2 は音声ビデオ会議サーバーです。  <br/> 4 は Skype for Business です。  <br/> 8 は IP 電話です。  <br/> 16 は Live Meeting コンソールです。  <br/> 32 は展開検証ツール (DVT) です。  <br/> 64 は Macintosh コンピューター上の Skype for Business Server です。  <br/> 128 は Skype for Business Server Attendant です。  <br/> 256 は会議アナウンス サービスです。  <br/> 512 は会議自動応答。  <br/> 1024 は応答グループ アプリケーションです。  <br/> 2048 は音声コントロールの外部です。  <br/> |
   

