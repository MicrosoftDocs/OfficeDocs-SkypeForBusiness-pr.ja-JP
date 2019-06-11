---
title: 'Lync Server 2013: 通話受付管理のベスト プラクティス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89be654a01615c750ce4f49f866e9339bc7e261
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 の通話受付管理のベスト プラクティス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-22_

パフォーマンスを向上させて展開を容易にするには、通話受付制御を展開するときに、次のベストプラクティスを適用します。

  - Wan が、現在および予想されるメディアトラフィックに適切にプロビジョニングされていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > 帯域幅の制限に合わせてバッファーを考慮することをお勧めします。 使用される帯域幅の合計に影響を与える競合状態などのシナリオがあります。また、帯域幅の制限を超えた場合に発生する可能性があります。 たとえば、メディアトラフィックが帯域幅の上限に近づいている間に2つの呼び出しが開始された場合、一方の呼び出しが最初に開始されるために、一方の通話が拒否されることがあります。

    
    </div>

  - ネットワーク使用量と通話の詳細レコードを監視して、最適な CAC settings を選択し、ネットワークの使用量の変化に応じて CAC 設定を更新できるようにします。

  - CAC 帯域幅ポリシーを使用して QoS の設定を補完します。

  - ブロックされた通話を PSTN に再ルーティングする場合は、PSTN の機能と容量を確認します。 詳細については、「 [Lync Server 2013 での送信ボイスルーティングの計画](lync-server-2013-planning-outbound-voice-routing.md)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > [キャパシティ] は、PSTN の潜在的な再ルーティングをサポートするために開く必要があるポートの数です。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

