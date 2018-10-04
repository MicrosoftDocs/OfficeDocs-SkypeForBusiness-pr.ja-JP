---
title: Skype のビジネス サーバーの音声の使用率とトラフィックを見積もる
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
ms.openlocfilehash: e69c559c4ed56010dac3a81a97837f1131e62a2e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25376008"
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
  

