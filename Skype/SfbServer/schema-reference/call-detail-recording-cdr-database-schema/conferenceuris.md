---
title: Skype for Business Server 2015 の ConferenceUris テーブル
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris テーブルは、データベースに記録されている会議セッションに参加したさまざまな会議 URI の一覧を格納する補助的なテーブルです。このテーブルの個々のレコードが、1 つの会議 URI を表します。
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816137"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ConferenceUris テーブル
 
ConfereneUris テーブルは、データベースに記録されている会議セッションに参加したさまざまな会議 URI の一覧を格納する補助的なテーブルです。このテーブルの個々のレコードが、1 つの会議 URI を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |日付型  <br/> |Primary  <br/> |タイム スタンプ (社内使用向け)。  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |この会議 URI を識別する一意の番号。  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||会議 URI。  <br/> |
|**チェックサム** <br/> |int  <br/> ||ConferenceUri のチェックサム。データベース検索の速度を速めるために使用されます。  <br/> |
|**UriTypeId** <br/> |int  <br/> |外部  <br/> |URI の種類 (IM 会議の conf:chat、音声ビデオ会議の conf:audio-video など)。 詳細については [、UriTypes テーブルの](uritypes.md) 表を参照してください。 <br/> |
   

