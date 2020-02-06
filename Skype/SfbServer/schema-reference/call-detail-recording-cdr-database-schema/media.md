---
title: Media テーブル
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 各レコードは、ピアツーピアセッションで使用される1つのメディアの種類を表します。 複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。
ms.openlocfilehash: b96f1e9fccf2ac3416e505eb19a54a5e227bb01f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815045"
---
# <a name="media-table"></a>Media テーブル
 
各レコードは、ピアツーピアセッションで使用される1つのメディアの種類を表します。 複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。
  
> [!NOTE]
> メディアテーブルを使って、セッションのメディアの再生時間を計算することはできません。 この表には、セッションでのメディア交換の信号の詳細が含まれています。 メディア交換は INVITE 要求によって実行され、StartTime は招待が送信された時間を示します。この招待は、セッションの開始時刻を意味するわけではありません。これは、セッションを開始した後にのみメディアが開始されるためです。 通常、EndTime はこのセッションの終了時刻を示します。 
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**MediaId** <br/> |tinyint  <br/> |プライマリ、外部  <br/> |このメディアの種類を識別する一意の番号です。 詳細については、 [Medialist の表](medialist.md)を参照してください。 <br/> |
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |これは、実際のメディアの開始時刻ではなく、メディア要求が送信された時刻です。 **StartTime**には、セッションのセットアップ時間が含まれます。 <br/> |
|**EndTime** <br/> |datetime  <br/> ||これはセッションの終了時刻です。  <br/> |
   

