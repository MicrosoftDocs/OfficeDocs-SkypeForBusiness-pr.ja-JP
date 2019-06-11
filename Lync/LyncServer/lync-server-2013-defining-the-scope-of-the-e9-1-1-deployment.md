---
title: 'Lync Server 2013: E9 展開のスコープを定義する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff32a71ec9b724bad9efee68784d284a71b8f385
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Lync Server 2013 での E9 展開のスコープの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-06_

Microsoft Lync Server 2013 for E9-1 を構成する前に、E9 の展開を計画する必要があります。 次のような点を検討します。

  - **E9-1-1 に関して組織にどのようなポリシーと法的義務があるか**  
    PBX (E9-1-1 用語では複数回線電話システム (MLTS) と呼ばれます) 使用時の E9-1-1 の法的義務は州ごとに異なります。 法務チームに相談して、関連する地域での Lync Server の展開に適用される可能性がある義務を理解してください。

<!-- end list -->

  - **エンタープライズ内のどの領域で E9-1-1 を有効にする必要があるか**  
    E9-1-1 は、エンタープライズ全体で有効にすることも、特定の場所だけで有効にすることもできます。たとえば、オフィスの E9-1-1 の要件が州によって異なる場合や、米国以外のサイトを除外する必要がある場合があります。

<!-- end list -->

  - **E9-1-1 をブランチ サイトにどのように展開するか**  
    E9-1-1 をブランチ サイトに展開するときは、音声の復元の概念を理解することが重要です。 一元化された電子 9-1-1 SIP trunks を使用していて、WAN の障害が発生した場合、クライアントは、場所情報サービスからの場所を取得できないか、緊急サービスサービスプロバイダに接続できない可能性があります。 Lync Server には、回復可能なデータネットワーク、各ブランチへの SIP トランクの展開、停止中のローカルゲートウェイへの緊急通話の配信など、支店の音声回復性を処理するためのいくつかの戦略が用意されています。 詳細については、「 [Lync Server 2013 でのブランチサイトの音声回復性の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。

<!-- end list -->

  - **ネットワーク外のユーザーに対し、E9-1-1 を有効にするかどうか**  
    自動的な場所の取得は、組織のネットワーク内にあるクライアントに対してのみ利用できます。そのため、組織では、Lync クライアントから発信された E9 の通話がオフプレミスでサポートされるかどうかを決定する必要があります。 たとえば、ユーザーが自宅で作業している場合や顧客サイトから作業している場合に、緊急電話をかけることができますか。 クライアントがエンタープライズネットワークの外部に配置されている場合は、ユーザーに位置情報の入力を求めるようにクライアントを構成できます。 ただし、ユーザーが指定した場所は、マスター番地の住所ガイド (MSAG) に対して prevalidated できないため、緊急サービスサービスプロバイダーディスパッチャーは、ルーティング前に発信者による場所の有効性を確認する必要があります。公衆安全応答ポイント (PSAP) への通話。
    
    <div>
    

    > [!NOTE]  
    > VPN を使用して組織のネットワークに接続しているユーザーの Lync クライアントは、内部の IP アドレス情報を取得できますが、これらのアドレスを使ってユーザーの実際の場所を特定することはできないため、VPN サブネットは位置情報サービス。

    
    </div>

<!-- end list -->

  - **米国以外のサイトに緊急通話のルーティングを提供するかどうか**  
    緊急サービスのサービス プロバイダーのサービス対象範囲外 (国外の場所など) にある会社の領域に緊急通話のルーティングを提供したい場合があります。この場合は、新しいサイトを作成し、ローカル PSTN ゲートウェイ経由で通話をルーティングする PSTN 使用法を参照する音声ポリシーをサイトに割り当てます。

</div>

<span> </span>

</div>

</div>

</div>

