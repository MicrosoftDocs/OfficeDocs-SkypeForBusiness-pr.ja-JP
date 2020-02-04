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
ms.openlocfilehash: de1f39b32503be758e10f3fbf712acdc07bd956b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 での通話受付管理の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

テレフォニー、ビデオ、アプリケーション共有など、IP ベースの統合コミュニケーション (UC) アプリケーションでは、エンタープライズネットワークで利用可能な帯域幅は、通常、LAN 環境内の制限要素と見なされません。 ただし、サイトを相互に接続する WAN リンクでは、ネットワーク帯域幅を制限することができます。 ネットワークトラフィックの流入によって WAN リンクが受信されると、キュー、バッファリング、パケットドロップなどの現在のメカニズムが輻輳を解決するために使用されます。 トラフィック量の増加は、ネットワークの輻輳が容易になるか、必要に応じてトラフィックが破棄されるまで遅延されます。 このような状況での従来のデータトラフィックでは、受信側のクライアントで回復できます。 ユニファイドコミュニケーションなどのリアルタイムトラフィックでは、この方法でネットワークの輻輳を解決することはできません。ユニファイドコミュニケーショントラフィックは待ち時間とパケット損失の両方に影響を及ぼすためです。 WAN で渋滞すると、ユーザーにとって低品質 (QoE) が発生する可能性があります。 輻輳状態のリアルタイムトラフィックには、低品質の接続を提供するよりも、通話を拒否する方が適しています。

通話受付管理 (CAC) では、リアルタイム セッションを許容品質で確立するのに十分なネットワーク帯域幅があるかどうかを判断します。 Lync Server 2013 では、CAC はオーディオとビデオについてのみリアルタイムのトラフィックを制御しますが、データトラフィックには影響しません。 既定の WAN パスで必要な帯域幅が確保されていない場合、CAC はインターネット パスまたは公衆交換電話網 (PSTN) を利用した通話のルーティングを試みることができます。 CAC は、Lync Server でのみ使用できます。

ここでは、通話受付管理機能と CAC の計画方法を説明します。

<div>


> [!NOTE]  
> Lync Server には、通話受付制御 (CAC)、緊急サービス (E9)、メディアバイパスという3つの高度なエンタープライズ Voip 機能があります。 これら3つの機能の計画情報の概要については、「 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク設定</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 の通話受付制御の概要](lync-server-2013-overview-of-call-admission-control.md)

  - [Lync Server 2013 での通話受付管理サービス要件の定義](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [例: Lync Server 2013 での通話受付制御の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Lync Server 2013 の CAC のコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-cac.md)

  - [Lync Server 2013 の通話受付管理のベスト プラクティス](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lync Server 2013 の通話受付管理の展開チェックリスト](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

