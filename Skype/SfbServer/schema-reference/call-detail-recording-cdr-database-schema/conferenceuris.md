---
title: ビジネス サーバー 2015 の Skype での ConferenceUris テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris テーブルは、さまざまな会議をデータベースに記録されている会議セッションに参加している Uri のリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つの会議の URI を表します。
ms.openlocfilehash: 6f373774b652e9858af84dd4c16b51fcb3c5d493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887772"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での ConferenceUris テーブル
 
ConfereneUris テーブルは、さまざまな会議をデータベースに記録されている会議セッションに参加している Uri のリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つの会議の URI を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |タイム ・ スタンプ、内部のために使用します。  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |この会議の URI を識別する一意の番号です。  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||会議 URI です。  <br/> |
|**チェックサム** <br/> |int  <br/> ||ConferenceUri のチェックサムです。 使用するデータベースの検索の速度が向上します。  <br/> |
|**UriTypeId** <br/> |int  <br/> |外部  <br/> |IM 会議、または conf:audio の conf:chat など、URI の種類-オーディオ/ビデオ会議のビデオ。 詳細については、 [UriTypes テーブル](uritypes.md)のテーブルを参照してください。 <br/> |
   

