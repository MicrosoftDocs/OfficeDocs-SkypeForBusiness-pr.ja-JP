---
title: Skype のビジネス サーバーの音声の使用率とトラフィックを見積もる
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 次のメトリックを使用すると、各サイトおよびそのトラフィックをサポートするのにために必要なポートの数にユーザーのトラフィックを見積もる。
ms.openlocfilehash: 4475be7d233bbfa34c1d2aa8b62d578ebb985423
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197675"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Skype のビジネス サーバーの音声の使用率とトラフィックを見積もる
 
次のメトリックを使用すると、各サイトおよびそのトラフィックをサポートするのにために必要なポートの数にユーザーのトラフィックを見積もる。
  
> **軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。
> 
> **中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。
> 
> **重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。
    
ポートの数には、仲介サーバーとゲートウェイが必要になることの順番を決定します。 960 個のポートに 2 つのポートからのサイズの範囲を展開するほとんどの組織を検討している公衆交換電話網 (PSTN) ゲートウェイです。 (がさらに大きくゲートウェイがこれらの主にテレフォニー サービス プロバイダーによって使用されます)。
  
たとえば、10,000 名のユーザーを擁する中度のトラフィックの組織の場合、1000 ポートが必要となります。必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。
  

