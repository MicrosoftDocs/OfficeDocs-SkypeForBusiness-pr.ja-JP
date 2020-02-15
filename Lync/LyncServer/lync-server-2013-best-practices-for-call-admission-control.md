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
ms.openlocfilehash: c00dbaa2f47d34f06424c9013a5b691caab56499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="52d53-102">Lync Server 2013 での通話受付管理のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="52d53-102">Best practices for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52d53-103">_**トピックの最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="52d53-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="52d53-104">パフォーマンスの向上と展開の簡略化を実現するには、通話受付管理を展開するときに次のベスト プラクティスを適用します。</span><span class="sxs-lookup"><span data-stu-id="52d53-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="52d53-105">現在のメディア トラフィックと予測されるメディア トラフィックに対して WAN が十分にプロビジョニングされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="52d53-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52d53-p101">帯域幅制限にバッファーを考慮することをお勧めします。 合計使用帯域幅に影響し、帯域幅制限の超過を招く可能性のある競合状態が発生する場合があります。 たとえば、メディア トラフィックが帯域幅制限に近づいているときに 2 つの通話を開始しようとすると、一方の通話の方が早く開始されたためにもう一方の通話が拒否されることがあります。</span><span class="sxs-lookup"><span data-stu-id="52d53-p101">We recommend that you factor in a buffer to your bandwidth limits. There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded. For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="52d53-109">最適な CAC 設定を選択し、ネットワークの使用状況の変化に合わせて CAC 設定を更新できるように、ネットワークの使用状況と通話詳細記録を監視します。</span><span class="sxs-lookup"><span data-stu-id="52d53-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="52d53-110">CAC 帯域幅ポリシーを使用して QoS 設定を補完します。</span><span class="sxs-lookup"><span data-stu-id="52d53-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="52d53-111">ブロックされた通話を PSTN に再ルーティングする場合、PSTN の機能と処理能力を確認します。</span><span class="sxs-lookup"><span data-stu-id="52d53-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="52d53-112">詳細については、「 [Lync Server 2013 で送信音声ルーティングを計画](lync-server-2013-planning-outbound-voice-routing.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52d53-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52d53-113">処理能力は、潜在的な PSTN の再ルーティングをサポートするために開く必要のあるポート数を表します。</span><span class="sxs-lookup"><span data-stu-id="52d53-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

