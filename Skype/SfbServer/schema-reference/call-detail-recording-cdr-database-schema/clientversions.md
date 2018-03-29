---
title: ビジネス サーバー 2015 の Skype での ClientVersions テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions テーブルは、さまざまな種類のクライアントのリストを格納するサポート テーブルと、データベースに記録されているセッションに参加したバージョンです。 テーブル内の各レコードは、1 つのクライアント バージョンを表します。
ms.openlocfilehash: 488c7f4211eacb6fc496d6198258c119641ebd14
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での ClientVersions テーブル
 
ClientVersions テーブルは、さまざまな種類のクライアントのリストを格納するサポート テーブルと、データベースに記録されているセッションに参加したバージョンです。 テーブル内の各レコードは、1 つのクライアント バージョンを表します。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**バージョン Id** <br/> |**int** <br/> |Primary  <br/> |このクライアントの種類とバージョンを識別する一意の番号です。  <br/> |
|**バージョン** <br/> |**nvarchar(256)** <br/> ||バージョン名です。  <br/> |
|**顧客タイプ** <br/> |int  <br/> ||セッションで使用されているクライアントの種類を指定します。 詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

