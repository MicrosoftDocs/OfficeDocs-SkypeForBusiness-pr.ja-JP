---
title: Skype for Business Server 2015 の ClientVersions テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions テーブルは、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1つのクライアントバージョンを表します。
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296512"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ClientVersions テーブル
 
ClientVersions テーブルは、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1つのクライアントバージョンを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |このクライアントの種類とバージョンを識別する一意の番号。  <br/> |
|**バージョン** <br/> |**nvarchar(256)** <br/> ||バージョン名。  <br/> |
|**ClientType** <br/> |int  <br/> ||セッションで使用するクライアントの種類を指定します。 詳細については、 [Useragentdef テーブル](useragentdef.md)を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

