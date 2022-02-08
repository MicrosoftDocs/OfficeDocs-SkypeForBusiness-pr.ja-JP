---
title: 2015 年の ClientVersions Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions テーブルはサポート テーブルで、データベースに記録されているセッションに参加したさまざまなクライアントの種類とバージョンのリストが格納されます。テーブルの各レコードは、1 つのクライアント バージョンを表します。
ms.openlocfilehash: dd9afc6addef78bf255e6237f1b29f5cac4ee071
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386326"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>2015 年の ClientVersions Skype for Business Server
 
ClientVersions テーブルはサポート テーブルで、データベースに記録されているセッションに参加したさまざまなクライアントの種類とバージョンのリストが格納されます。テーブルの各レコードは、1 つのクライアント バージョンを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |このクライアントの種類とバージョンを識別する一意の番号。  <br/> |
|**バージョン** <br/> |**nvarchar(256)** <br/> ||バージョン名。  <br/> |
|**ClientType** <br/> |int  <br/> ||セッションで使用するクライアントの種類を指定します。 詳細については [、UserAgentDef テーブル](useragentdef.md) を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

