---
title: Media テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 各レコードは、ピア ツー ピア セッションで使用される 1 つのメディアの種類を表します。 セッションは 1 つで表されます、テーブル内の複数のレコード 1 つ以上のメディア タイプを使用する場合。
ms.openlocfilehash: f0525b279fbef5cc7d4a1bc2ce0fce9212636a96
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212938"
---
# <a name="media-table"></a>Media テーブル
 
各レコードは、ピア ツー ピア セッションで使用される 1 つのメディアの種類を表します。 セッションは 1 つで表されます、テーブル内の複数のレコード 1 つ以上のメディア タイプを使用する場合。
  
> [!NOTE]
> Media テーブルは、セッションのメディアの長さを計算するのにはない使用してください。 このテーブルには、セッションでのメディアの交換のシグナルの詳細が含まれています。 INVITE 要求、メディアの交換を行うし、開始時刻は、招待状が送信された時刻を示します。招待時間は必ずしもメディアの開始時刻、メディアは、sessionee がセッションを受け入れた後にのみ開始されるためです。 終了時刻は、通常、このセッションの終了時刻を意味します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |プライマリ サーバーで、外部  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**MediaId** <br/> |tinyint  <br/> |プライマリ サーバーで、外部  <br/> |このメディアの種類を識別する一意の番号です。 詳細については[メディアの表](medialist.md)を参照してください。 <br/> |
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |メディアの要求が送信された時刻は、実際のメディアではなく開始時間。 **開始時刻**には、セッションのセットアップ時間が含まれています。 <br/> |
|**EndTime** <br/> |datetime  <br/> ||これは、セッションの終了時刻です。  <br/> |
   

