---
title: メディア テーブル
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 各レコードは、ピアツーピア セッションで使用される 1 つのメディア種類を表します。複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。
ms.openlocfilehash: 095e1f3227bbaf3335f581acbebbddaccd6b73de33639b2a0d04302a5c104393
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322949"
---
# <a name="media-table"></a>メディア テーブル
 
各レコードは、ピアツーピア セッションで使用される 1 つのメディア種類を表します。複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。
  
> [!NOTE]
> Media テーブルを使用してセッションでのメディアの継続時間を計算することはできません。このテーブルには、セッションでのメディア交換の信号の詳細が格納されます。メディア交換は INVITE 要求によって行われ、StartTime は INVITE が送信された時刻を示します。メディアはセッション参加者がセッションを受け付けた後でのみ開始するので、招待時間は必ずしもメディアの開始時刻を意味しません。EndTime は、通常、このセッションの終了時刻を意味します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については[、「ダイアログ」の表Skype for Business Server 2015](dialogs.md)を参照してください。 <br/> |
|**SessionIdSeq** <br/> |整数  <br/> |主/プライマリ、外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については[、「ダイアログ」の表Skype for Business Server 2015](dialogs.md)を参照してください。 <br/> |
|**MediaId** <br/> |tinyint  <br/> |主/プライマリ、外部  <br/> |このメディアの種類を示す一意の番号。 詳細については [、MediaList テーブル](medialist.md) を参照してください。 <br/> |
|**StartTime** <br/> |日付型  <br/> |Primary  <br/> |メディア要求が送信された時刻です。実際にメディアが開始した時刻ではありません。**StartTime** にはセッションのセットアップ時間が含まれます。<br/> |
|**EndTime** <br/> |日付型  <br/> ||セッションの終了時刻です。  <br/> |
   

