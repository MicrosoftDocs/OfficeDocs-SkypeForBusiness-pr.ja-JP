---
title: UserStatistics テーブル
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics テーブルはサポート テーブルです。 テーブル内の各レコードには、システムの個々のユーザーの使用状況に関する情報が格納されます。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813107"
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
   

