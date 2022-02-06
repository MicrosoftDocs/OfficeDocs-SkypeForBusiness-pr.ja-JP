---
title: ConferenceUris テーブル (Skype for Business Server 2015)
ms.reviewer: null
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris テーブルは、データベースに記録されている会議セッションに参加したさまざまな会議 URI の一覧を格納する補助的なテーブルです。このテーブルの個々のレコードが、1 つの会議 URI を表します。
---

# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>ConferenceUris テーブル (Skype for Business Server 2015)
 
ConfereneUris テーブルは、データベースに記録されている会議セッションに参加したさまざまな会議 URI の一覧を格納する補助的なテーブルです。このテーブルの個々のレコードが、1 つの会議 URI を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |日付型  <br/> |Primary  <br/> |タイム スタンプ (社内使用向け)。  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |この会議 URI を識別する一意の番号。  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||会議 URI。  <br/> |
|**チェックサム** <br/> |int  <br/> ||ConferenceUri のチェックサム。データベース検索の速度を速めるために使用されます。  <br/> |
|**UriTypeId** <br/> |int  <br/> |外部  <br/> |IM 会議の conf:chat、オーディオ/ビデオ会議用の conf:audio-video などの URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) の表を参照してください。 <br/> |
   

