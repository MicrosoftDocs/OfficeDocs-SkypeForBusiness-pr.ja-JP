---
title: UserAgent テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーエージェントのリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つのユーザーエージェントを表します。
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294587"
---
# <a name="useragent-table"></a>UserAgent テーブル
 
UserAgent テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーエージェントのリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つのユーザーエージェントを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |このユーザーエージェントを識別する一意の番号です。  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |一意  <br/> |ユーザーエージェント文字列。  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1は仲介サーバーです。  <br/> 2は、A/V 会議サーバーです。  <br/> 4は Skype for Business です。  <br/> 8は IP 電話です。  <br/> 16は Live Meeting 本体です。  <br/> 32は展開検証ツール (DVT) です。  <br/> 64は、Macintosh コンピューター上の Skype for Business Server です。  <br/> 128は、Skype for Business Server アテンダントです。  <br/> 256は会議のアナウンスメントサービスです。  <br/> 512は、会議の自動応答です。  <br/> 1024は応答グループアプリケーションです。  <br/> 2048は外部の音声制御。  <br/> |
   

