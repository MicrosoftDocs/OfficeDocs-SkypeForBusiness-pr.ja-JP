---
title: 'Lync Server 2013: 通話受付管理のベストプラクティス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be270859304236b0704bc8cc9e1bc29f3e80fcb9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514824"
---
# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 での通話受付管理のベストプラクティス

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-22_

パフォーマンスの向上と展開の簡略化を実現するには、通話受付管理を展開するときに次のベスト プラクティスを適用します。

  - 現在のメディア トラフィックと予測されるメディア トラフィックに対して WAN が十分にプロビジョニングされていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > 帯域幅制限にバッファーを考慮することをお勧めします。 合計使用帯域幅に影響し、帯域幅制限の超過を招く可能性のある競合状態が発生する場合があります。 たとえば、メディア トラフィックが帯域幅制限に近づいているときに 2 つの通話を開始しようとすると、一方の通話の方が早く開始されたためにもう一方の通話が拒否されることがあります。

    
    </div>

  - 最適な CAC 設定を選択し、ネットワークの使用状況の変化に合わせて CAC 設定を更新できるように、ネットワークの使用状況と通話詳細記録を監視します。

  - CAC 帯域幅ポリシーを使用して QoS 設定を補完します。

  - ブロックされた通話を PSTN に再ルーティングする場合、PSTN の機能と処理能力を確認します。 詳細については、「 [Lync Server 2013 で送信音声ルーティングを計画](lync-server-2013-planning-outbound-voice-routing.md)する」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > 処理能力は、潜在的な PSTN の再ルーティングをサポートするために開く必要のあるポート数を表します。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

