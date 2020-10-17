---
title: 'Lync Server 2013: エンタープライズ Voip の要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eeadb699c12b3f0ece883484ea8c935bfb795256
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504344"
---
# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズ Voip の要件の定義

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-07_

ここでは、トポロジ内のサイト、サイト、およびサイト間のリンクについての考慮事項について概説します。また、エンタープライズ Voip を展開するときにそれらがどのように重要であるかについても説明します。 これらの決定を行うのに役立つ詳細については、「計画」のドキュメントの「 [Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) 」を参照してください。

<div>

## <a name="sites-and-regions"></a>サイトと地域

最初に、エンタープライズ Voip を展開するトポロジ内のサイトと、それらのサイトが属するネットワーク地域を特定します。 特に、それぞれのサイトにどのようにして公衆交換電話網 (PSTN) 接続を提供するかを考慮します。 管理上の理由から、これらのサイトが属する地域が決定的要素となります。 存続可能 Branch アプライアンス (SBAs) が展開される場所、およびインターネットテレフォニーサービスプロバイダー (ITSP) に SIP トランク (ローカルまたは中央サイト) を構成できる場所を決定してください。

</div>

<div>

## <a name="network-links-between-sites"></a>サイト間のネットワーク リンク

また、中央サイトとブランチサイト間のネットワークリンクに必要な帯域幅の使用状況についても検討する必要があります。 サイト間の WAN リンクを持っている、または展開する計画がある場合は、各ブランチサイトにゲートウェイを展開して、それらのサイトのユーザーのためにローカルの直接の中向きダイヤル (DID) の終了を提供することをお勧めします。 回復可能な WAN リンクは存在するが、WAN リンクの帯域幅に制限がありそうな場合、そのリンクに通話受付管理を構成します。 回復可能な WAN リンクがない場合、ブランチサイトで1000ユーザー未満でホストされ、ローカルのトレーニングを受けた Lync Server 管理者がいない場合は、ブランチサイトで存続可能ブランチアプライアンスを展開することをお勧めします。 ブランチサイトで1000と5000のユーザーをホストし、回復可能な WAN 接続がなく、専任の Lync Server 管理者が利用できるようになっている場合は、ブランチサイトに小規模なゲートウェイを使用して存続可能ブランチサーバーを展開することをお勧めします。 メディア バイパスをサポートするゲートウェイ ピアが存在する場合は、制限のあるリンクでメディア バイパスを有効にすることも考慮してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の高度なエンタープライズ Voip 機能のネットワーク設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

