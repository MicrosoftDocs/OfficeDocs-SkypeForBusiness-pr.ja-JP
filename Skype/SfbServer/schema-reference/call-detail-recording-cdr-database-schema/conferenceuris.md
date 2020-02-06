---
title: Skype for Business Server 2015 の ConferenceUris テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris テーブルは、データベースに記録された会議セッションに参加しているさまざまな会議の Uri のリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つの会議 URI を表します。
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815315"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ConferenceUris テーブル
 
ConfereneUris テーブルは、データベースに記録された会議セッションに参加しているさまざまな会議の Uri のリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つの会議 URI を表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Nextupdatupdat** <br/> |datetime  <br/> |Primary  <br/> |タイムスタンプ、内部使用。  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |この会議 URI を識別する一意の番号です。  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||会議の URI。  <br/> |
|**サム** <br/> |int  <br/> ||ConferenceUri のチェックサム。 データベースの検索速度を上げるために使われます。  <br/> |
|**UriTypeId** <br/> |int  <br/> |外部  <br/> |URI の種類 ("conf: IM 会議用チャット" または "conf: 音声/ビデオ会議用のオーディオビデオ" など)。 詳細については、 [UriTypes テーブル](uritypes.md)の表を参照してください。 <br/> |
   

