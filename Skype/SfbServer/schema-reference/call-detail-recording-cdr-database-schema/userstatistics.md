---
title: UserStatistics テーブル
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics テーブルはサポート テーブルです。 テーブル内の各レコードには、システムの個々のユーザーの使用状況に関する情報が格納されます。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 01f002e1cba20200334f8696f9fb2c20c98e82c1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756450"
---
# <a name="userstatistics-table"></a>UserStatistics テーブル
 
UserStatistics テーブルはサポート テーブルです。 テーブル内の各レコードには、システムの個々のユーザーの使用状況に関する情報が格納されます。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号。  <br/> |
|**LastLogInTime** <br/> |日付型  <br/> ||ユーザーが最後にログインした時刻。  <br/> |
|**LastConfOrganizedTime** <br/> |日付型  <br/> ||ユーザーが最後に会議を開催した時刻。  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |日付型  <br/> ||ユーザーが最後に通話に失敗した時刻。  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |日付型  <br/> ||ユーザーが会議開催者として最後に通話に失敗した時刻。  <br/> |
   

