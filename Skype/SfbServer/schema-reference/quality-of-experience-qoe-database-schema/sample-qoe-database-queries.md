---
title: QoE データベース クエリのサンプル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: このセクションには、エクスペリエンスの品質 (QoE) データベースのサンプル クエリが含まれています。
ms.openlocfilehash: c66d0fdc51ee3382034f5fba1e98f93a8799f312
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020598"
---
# <a name="sample-qoe-database-queries"></a>QoE データベース クエリのサンプル
 
このセクションには、エクスペリエンスの品質 (QoE) データベースのサンプル クエリが含まれています。 
  
次の例を使用して、すべてのオーディオ ストリームのジッターとパケット損失の平均を取得します。
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

ミーティング コンソールを使用する会議の数値の合計を検索するのにには、次の例を使用します。
  
```
select avg(ConversationalMOS)
from SessionView s
inner join MediaLineView m
on s.ConferenceDateTime = m.ConferenceDateTime
   and s.SessionSeq = m.SessionSeq
   and m.MediaLineLabel = 0 -- audio media line
   and s.CallerUserAgentType = 4 -- Lync
   and s.CalleeUserAgentType = 4 -- Lync
```

キャプチャ デバイス 1 台あたり ConversstionalMOS、SendingMOS および ListendingMOS を取得するのにには、次の例を使用します。
  
```
select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
from
(
   select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

   union

   select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

)as t
group by t.DeviceName
order by SampleNum desc
```