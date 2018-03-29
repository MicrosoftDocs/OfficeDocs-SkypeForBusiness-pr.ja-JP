---
title: TraceRoute テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute の表には、呼び出しからのルーティング情報が含まれています。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: e8796b164bd6a0f2809025b784ada9d12dda449b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="traceroute-table"></a>TraceRoute テーブル
 
TraceRoute の表には、呼び出しからのルーティング情報が含まれています。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |プライマリ サーバーで、外部  <br/> |日付と時刻の呼び出しを開始しました。  <br/> |
|**SessionSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |同時日付けと同時に開始した可能性がある複数の呼び出しを区別するために使用する一意の識別子。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |プライマリ サーバーで、外部  <br/> |呼び出しで使用されているビデオの線の種類を表します。 有効な値は次のとおりです。  <br/> 0 - オーディオ  <br/> 1-ビデオ  <br/> 2-パノラマ ビデオ  <br/> 3-アプリケーションとデスクトップの共有  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |呼び出しを配置するエンドポイントです。  <br/> |
|**ホップ** <br/> |int  <br/> ||ネットワーク ホップ/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |外部  <br/> |IP アドレスの一意の識別子です。 IP アドレス情報は、 [ip アドレス テーブル](ipaddress.md)に格納されます。  <br/> |
|**RTT** <br/> |int  <br/> ||ラウンドト リップ時間です。 ラウンドト リップ時間は、ボイス パケットが送信先に到達し、バックの通知を受け取ったことを送信するためにかかる時間の量を測定します。  <br/> |
   

