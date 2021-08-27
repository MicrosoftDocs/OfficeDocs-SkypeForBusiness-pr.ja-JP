---
title: TraceRoute テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute テーブルには、通話からのルーティング情報が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 2cecfb0fe941404668d6eedd7c146fdc92aaadd1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578561"
---
# <a name="traceroute-table"></a>TraceRoute テーブル
 
TraceRoute テーブルには、通話からのルーティング情報が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |通話が開始された日時。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |同じ日付の同じ時刻に開始された可能性がある複数の通話を区別するために使用される一意の識別子。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主/プライマリ、外部  <br/> |通話で使用されたビデオ回線の種類を表します。有効な値は次のとおりです。  <br/> 0 - オーディオ  <br/> 1 - ビデオ  <br/> 2 - パノラマ ビデオ  <br/> 3 - アプリケーション/デスクトップ共有  <br/> |
|**FromCaller** <br/> |ビット  <br/> |Primary  <br/> |通話を発信したエンドポイント。  <br/> |
|**ホップ** <br/> |int  <br/> ||ネットワーク ホップ/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |外部  <br/> |IP アドレスの一意の識別子。 IP アドレス情報は [IPAddress テーブルに格納されます](ipaddress.md)。  <br/> |
|**RTT** <br/> |int  <br/> ||ラウンド トリップ時間。ラウンド トリップ時間は、音声パケットが宛先に到達してから受信通知を送り返すまでにかかる時間を測定します。  <br/> |
   

