---
title: 'Lync Server 2013: 組織のエンタープライズ VoIP 要件の定義'
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
ms.openlocfilehash: 8987905d2b117eb889486882b7d74ce4e52659a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 での組織のエンタープライズ VoIP 要件の定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-07_

このトピックでは、トポロジ内のサイトとサイト間のリンクについて考慮する必要がある考慮事項、およびエンタープライズ Voip を展開する際のそれらの重要性について説明します。 これらの決定を行うための詳細については、計画ドキュメントの「 [Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)」を参照してください。

<div>

## <a name="sites-and-regions"></a>サイトと地域

まず、エンタープライズボイスとそのサイトが属するネットワーク領域を展開するトポロジ内のサイトを特定します。 特に、それぞれのサイトにどのようにして公衆交換電話網 (PSTN) 接続を提供するかを考慮します。 管理上の理由から、これらのサイトが属する地域が決定的要素となります。 ゲートウェイがローカルで展開される場所を決定します。ここでは、Survivable Branch アプライアンス (SBAs) を展開し、SIP trunks (ローカルまたはセントラルサイト) をインターネットテレフォニーサービスプロバイダー (ITSP) に構成することができます。

</div>

<div>

## <a name="network-links-between-sites"></a>サイト間のネットワークリンク

また、セントラルサイトとそのブランチサイト間のネットワークリンクで想定される帯域幅の使用状況についても考慮する必要があります。 サイト間の WAN リンクがある場合、または展開を計画している場合は、各ブランチサイトにゲートウェイを展開して、それらのサイトのユーザーに対してローカル直接の内部ダイヤル (DID) の終了を提供することをお勧めします。 回復可能な WAN リンクは存在するが、WAN リンクの帯域幅に制限がありそうな場合、そのリンクに通話受付管理を構成します。 回復可能な WAN リンクを持っておらず、ブランチサイトで1000ユーザー未満のホストを使用していて、ローカルでトレーニングした Lync Server 管理者がいない場合は、ブランチサイトで Survivable Branch Appliance を展開することをお勧めします。 ブランチサイトで1000と5000の両方のユーザーをホストし、回復可能な WAN 接続を使用しておられ、Lync Server のトレーニングを利用できるようになっている場合は、ブランチサイトに小規模ゲートウェイを設定した Survivable ブランチサーバーを展開することをお勧めします。 メディア バイパスをサポートするゲートウェイ ピアが存在する場合は、制限のあるリンクでメディア バイパスを有効にすることも検討してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

