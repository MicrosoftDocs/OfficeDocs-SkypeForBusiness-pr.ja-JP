---
title: 2015 年の ClientVersions Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions テーブルはサポート テーブルで、データベースに記録されているセッションに参加したさまざまなクライアントの種類とバージョンのリストが格納されます。テーブルの各レコードは、1 つのクライアント バージョンを表します。
ms.openlocfilehash: 1cf2f237fd05937f8eea9a8c7f180ae43418fd586b59c99679770efa2205af88
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341772"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>2015 年の ClientVersions Skype for Business Server
 
ClientVersions テーブルはサポート テーブルで、データベースに記録されているセッションに参加したさまざまなクライアントの種類とバージョンのリストが格納されます。テーブルの各レコードは、1 つのクライアント バージョンを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |このクライアントの種類とバージョンを識別する一意の番号。  <br/> |
|**バージョン** <br/> |**nvarchar(256)** <br/> ||バージョン名。  <br/> |
|**ClientType** <br/> |整数  <br/> ||セッションで使用するクライアントの種類を指定します。 詳細については [、UserAgentDef テーブル](useragentdef.md) を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

