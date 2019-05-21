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
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris テーブルは、データベースに記録された会議セッションに参加しているさまざまな会議の Uri のリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つの会議 URI を表します。
ms.openlocfilehash: 60f9952fa1fcc5b1a1a651c44beaed894a387b81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296393"
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
   

