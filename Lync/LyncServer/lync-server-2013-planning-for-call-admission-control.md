---
title: 'Lync Server 2013: 通話受付管理の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5729989334297d4a6b368808079b0a7b0f4cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 での通話受付管理の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

テレフォニー、ビデオ、アプリケーション共有など、IP ベースの統合コミュニケーション (UC) アプリケーションの場合、エンタープライズネットワークで使用可能な帯域幅は、一般に LAN 環境内の制限要因とは見なされません。 ただし、サイトを相互に接続する WAN リンクでは、ネットワーク帯域幅を制限することができます。 ネットワークトラフィックの混雑によって WAN リンクがサブスクライブされると、キュー、バッファリング、パケットドロップなどの現在のメカニズムが輻輳の解決に使用されます。 通常、このトラフィックはネットワーク輻輳が緩和されるまで、または必要に応じてトラフィックがドロップされるまで遅延します。 このような状況での従来のデータトラフィックでは、受信側のクライアントが回復できます。 ユニファイドコミュニケーションなどのリアルタイムトラフィックでは、統合コミュニケーショントラフィックが待機時間とパケット損失の両方に敏感になるため、この方法でネットワークの輻輳を解決することはできません。 WAN 上で輻輳が発生すると、ユーザーにとって QoE (Quality of Experience) が低下する可能性があります。 輻輳状態のリアルタイムトラフィックでは、低品質の接続を提供するよりも、呼び出しを拒否することをお勧めします。

通話受付管理 (CAC) は、許容できる品質のリアルタイムセッションを確立するのに十分なネットワーク帯域幅があるかどうかを判断します。 Lync Server 2013 では、CAC はオーディオとビデオに対してのみリアルタイムトラフィックを制御しますが、データトラフィックには影響を与えません。 既定の WAN パスが必要な帯域幅を持たない場合、CAC はインターネットパスまたは公衆交換電話網 (PSTN) を経由して通話をルーティングすることができます。 CAC は、Lync Server でのみ使用できます。

このセクションでは、通話受付管理機能と CAC の計画方法について説明します。

<div>


> [!NOTE]  
> Lync Server には、通話受付管理 (CAC)、緊急サービス (E9-1-1)、メディアバイパスという3つの高度なエンタープライズ Voip 機能があります。 これら3つの機能すべてに共通の計画情報の概要については、「 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク設定</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での通話受付管理の概要](lync-server-2013-overview-of-call-admission-control.md)

  - [Lync Server 2013 での通話受付管理の要件の定義](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [例: Lync Server 2013 での通話受付管理の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Lync Server 2013 の CAC のコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-cac.md)

  - [Lync Server 2013 での通話受付管理のベストプラクティス](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lync Server 2013 での通話受付管理の展開チェックリスト](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

