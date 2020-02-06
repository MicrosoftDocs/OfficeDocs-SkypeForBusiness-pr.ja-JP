---
title: TraceRoute テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute テーブルには、通話のルーティング情報が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805115"
---
# <a name="traceroute-table"></a>TraceRoute テーブル
 
TraceRoute テーブルには、通話のルーティング情報が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |プライマリ、外部  <br/> |通話が開始された日付と時刻。  <br/> |
|**SessionSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |同じ日付と同時に開始された可能性がある複数の通話を区別するために使用される一意の識別子。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |プライマリ、外部  <br/> |通話で使用されるビデオラインの種類を表します。 有効な値は次のとおりです。  <br/> 0-音声  <br/> 1-ビデオ  <br/> 2-パノラマビデオ  <br/> 3-アプリケーション/デスクトップ共有  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |通話を発信したエンドポイント。  <br/> |
|**ホップ** <br/> |int  <br/> ||ネットワークホップ/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |外部  <br/> |IP アドレスの一意の識別子。 IP アドレス情報は、 [IPAddress テーブル](ipaddress.md)に格納されます。  <br/> |
|**RTT** <br/> |int  <br/> ||往復時間。 往復時間は、ボイスパケットがその宛先に到達し、受信した通知を返信するのにかかる時間を測定します。  <br/> |
   

