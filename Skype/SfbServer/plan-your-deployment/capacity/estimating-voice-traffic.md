---
title: Skype for Business Server の音声使用状況とトラフィックの見積もり
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 次の指標を使用して、各サイトのユーザー トラフィックと、そのトラフィックをサポートするために必要なポート数を推定できます。
ms.openlocfilehash: c631361a7ef6d4706632f59366adac3384a6d255
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827687"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Skype for Business Server の音声使用状況とトラフィックの見積もり
 
次の指標を使用して、各サイトのユーザー トラフィックと、そのトラフィックをサポートするために必要なポート数を推定できます。
  
> **軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。
> 
> **中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。
> 
> **重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。
    
その後のポート数によって、必要な仲介サーバーとゲートウェイの数が決まれます。 ほとんどの組織が 2 ポートから最大 960 ポートの範囲の展開を検討している公衆交換電話網 (PSTN) ゲートウェイ。 (ゲートウェイはさらに大きくなりますが、主にテレフォニー サービス プロバイダーによって使用されます)。
  
たとえば、10,000 名のユーザーを擁する、中度のトラフィックの組織の場合、1000 ポートが必要となります。 必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。
  

