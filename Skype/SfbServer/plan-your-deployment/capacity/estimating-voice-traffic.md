---
title: 音声の使用状況とトラフィックの見積もりSkype for Business Server
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
description: 次のメトリックを使用して、各サイトのユーザー トラフィックと、そのトラフィックをサポートするために必要なポートの数を推定できます。
ms.openlocfilehash: 470590baf8ce5735b77576292fc6558d916dd3a7173b95c113b74d42f35c5224
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318840"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>音声の使用状況とトラフィックの見積もりSkype for Business Server
 
次のメトリックを使用して、各サイトのユーザー トラフィックと、そのトラフィックをサポートするために必要なポートの数を推定できます。
  
> **軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。
> 
> **中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。
> 
> **重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。
    
ポートの数によって、必要な仲介サーバーとゲートウェイの数が決定されます。 ほとんどの組織が 2 ポートから最大 960 ポートの範囲を展開すると考える公衆交換電話網 (PSTN) ゲートウェイ。 (さらに大きなゲートウェイがありますが、これらは主にテレフォニー サービス プロバイダーによって使用されます)。
  
たとえば、10,000 名のユーザーを擁する、中度のトラフィックの組織の場合、1000 ポートが必要となります。 必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。
  

