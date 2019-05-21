---
title: UserStatistics テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics テーブルは、サポートテーブルです。 テーブルの各レコードには、個々のユーザーによるシステムの使用状況に関する情報が格納されます。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295693"
---
# <a name="userstatistics-table"></a>UserStatistics テーブル
 
UserStatistics テーブルは、サポートテーブルです。 テーブルの各レコードには、個々のユーザーによるシステムの使用状況に関する情報が格納されます。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primary  <br/> |このユーザーを識別する一意の番号です。  <br/> |
|**最終ログイン時間** <br/> |datetime  <br/> ||前回ユーザーがログインした日時。  <br/> |
|**Lastconforizedtime** <br/> |datetime  <br/> ||ユーザーが最後に会議を開催した日時。  <br/> |
|**Lastcallオーガナイザー Ercallfailuretime** <br/> |datetime  <br/> ||前回ユーザーが通話の失敗を経験した日時。  <br/> |
|**Lastconforガント Izercallfailuretime** <br/> |datetime  <br/> ||前回ユーザーが会議開催者として通話の失敗を経験した時刻。  <br/> |
   

