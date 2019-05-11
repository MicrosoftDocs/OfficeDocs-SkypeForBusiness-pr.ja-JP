---
title: UserAgent テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent テーブルは、データベースに記録されているセッションに参加したさまざまなユーザー エージェントのリストを格納するサポート テーブルです。 テーブル内の各レコードが 1 つのユーザー エージェントを表す
ms.openlocfilehash: 432f5ccc26d790aff07f221a7ef9912d16c49499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907004"
---
# <a name="useragent-table"></a>UserAgent テーブル
 
UserAgent テーブルは、データベースに記録されているセッションに参加したさまざまなユーザー エージェントのリストを格納するサポート テーブルです。 テーブル内の各レコードが 1 つのユーザー エージェントを表す
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |このユーザー エージェントを識別する一意の番号です。  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |一意  <br/> |ユーザー エージェント文字列です。  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 は、仲介サーバーです。  <br/> 2 は、A/V 会議サーバーです。  <br/> 4 は、ビジネスの Skype です。  <br/> 8 は、IP 電話です。  <br/> 16 は、Live Meeting コンソールです。  <br/> 32 は、配置検証ツール (DVT) です。  <br/> 64 は、Macintosh コンピューターで Skype のビジネス サーバーです。  <br/> 128 は、ビジネスのサーバーの応答の Skype です。  <br/> 256 は、会議のお知らせサービスです。  <br/> 512 は、会議の自動応答です。  <br/> 1024 は、応答グループ アプリケーションです。  <br/> 2048 は、外側の音声コントロールです。  <br/> |
   

