---
title: 'Lync Server 2013: E9-1-1 展開の範囲の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27d280580f4d9cae1f6240b554be760d1689daa3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504484"
---
# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Lync Server 2013 での E9-1-1 展開の範囲の定義

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-06_

E9-1-1 用に Microsoft Lync Server 2013 を構成する前に、E9-1-1 展開を計画する必要があります。 次のような点を検討します。

  - **E9-1-1 に関して組織にどのようなポリシーと法的義務があるか**  
    PBX (E9-1-1 用語では複数回線電話システム (MLTS) と呼ばれます) 使用時の E9-1-1 の法的義務は州ごとに異なります。 該当する地域での Lync Server の展開に適用される可能性のある義務については、法務チームにお問い合わせください。

<!-- end list -->

  - **エンタープライズ内のどの領域で E9-1-1 を有効にする必要があるか**  
    E9-1-1 は、エンタープライズ全体で有効にすることも、特定の場所だけで有効にすることもできます。たとえば、オフィスの E9-1-1 の要件が州によって異なる場合や、米国以外のサイトを除外する必要がある場合があります。

<!-- end list -->

  - **E9-1-1 をブランチ サイトにどのように展開するか**  
    E9-1-1 をブランチ サイトに展開するときは、音声の復元の概念を理解することが重要です。 集中管理された電子 9-1-1 SIP トランクを使用していて、WAN の障害が発生した場合、サインインしているクライアントが場所情報サービスからの場所を取得したり、緊急サービスサービスプロバイダーに接続したりすることができない場合があります。 Lync Server には、回復可能なデータネットワークがある場合、各ブランチに SIP トランクを展開する場合、停止時にローカルゲートウェイに緊急電話をかける場合など、ブランチオフィスの音声の復元を処理するためのいくつかの戦略が用意されています。 詳細については、「 [Lync Server 2013 でのブランチサイトの音声の復元の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。

<!-- end list -->

  - **ネットワーク外のユーザーに対し、E9-1-1 を有効にするかどうか**  
    自動的な位置情報の取得に対応しているのは、組織のネットワークの内部にあるクライアントだけです。このため、社外にある Lync クライアントからの E9-1-1 通話をサポートするかどうかを組織で決定する必要があります。たとえば、自宅や顧客サイトで作業をしているユーザーが緊急通話を行えるようにするかどうかを決定します。クライアントがエンタープライズ ネットワークの外部にある場合に、ユーザーに位置情報の入力を求めるようにクライアントを構成することはできます。しかし、ユーザーが入力する場所は事前に主要道路住所案内 (MSAG) と照合できないので、緊急サービスのサービス プロバイダー ディスパッチャーは通話を緊急情報受信センター (PSAP) にルーティングする前に、場所の有効性を発信者と口頭で確認する必要があります。
    
    <div>
    

    > [!NOTE]  
    > VPN を使用して組織のネットワークに接続するユーザーの Lync クライアントは、内部 IP アドレス情報を取得できますが、これらのアドレスを使用してユーザーの実際の場所を特定することはできないため、VPN サブネットは場所情報サービスから除外する必要があります。

    
    </div>

<!-- end list -->

  - **米国以外のサイトに緊急通話のルーティングを提供するかどうか**  
    緊急サービスのサービス プロバイダーのサービス対象範囲外 (国外の場所など) にある会社の領域に緊急通話のルーティングを提供したい場合があります。この場合は、新しいサイトを作成し、ローカル PSTN ゲートウェイ経由で通話をルーティングする PSTN 使用法を参照する音声ポリシーをサイトに割り当てます。

</div>

<span> </span>

</div>

</div>

</div>

