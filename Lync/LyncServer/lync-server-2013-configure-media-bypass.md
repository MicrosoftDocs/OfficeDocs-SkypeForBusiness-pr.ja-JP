---
title: 'Lync Server 2013: メディア バイパスの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8be022e5b1b16bff432873e27ddda5f388db02f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a>Lync Server 2013 メディア バイパスの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

このセクションでは、少なくとも1つ以上の仲介サーバーを既に公開して構成していることを前提としています (「 [lync server 2013 のトポロジビルダーでの仲介サーバーの定義](lync-server-2013-define-a-mediation-server-in-topology-builder.md)」および「lync server [2013](lync-server-2013-publish-the-topology.md)での[フロントエンドプールまたは Standard Edition 2013 2013 サーバーの定義と構成](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)」で説明しています)。 [](lync-server-2013-publish-the-topology.md)

また、このセクションでは、「 [Lync Server 2013 のトポロジビルダーでゲートウェイを定義](lync-server-2013-define-a-gateway-in-topology-builder.md)する」の説明に従って、PSTN 接続を提供するために少なくとも1つのゲートウェイピアを定義していることを前提としています。 接続するピアが SIP トランキング プロバイダーの SBC の場合は、プロバイダーが認定プロバイダーであることとプロバイダーがメディア バイパスをサポートしていることを確認してください。 たとえば、多くの SIP トランキング プロバイダーが、その SBC に仲介サーバーからのトラフィックを受信することだけを許可します。 その場合は、当該のトランクに対してバイパスを有効にしないでください。 また、組織がその内部ネットワーク IP アドレスを SIP トランキング プロバイダーに公開していなければ、メディア バイパスを有効にすることはできません。

<div>


> [!NOTE]  
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。 マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。 メディアのバイパスは、統合された通信のオープンな相互運用性プログラム– Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>の製品とバージョンでのみサポートされます。



</div>

このセクションでは、メディアのバイパスを有効にして、仲介サーバーで必要な処理を軽減する方法について説明します。 メディアのバイパスを有効にする前に、計画ドキュメントの「 [Lync Server 2013 でのメディアのバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」で説明されているように、使用している環境がメディアのバイパスをサポートするために必要な条件を満たしていることを確認してください。 また、「 [Lync server 2013 でメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」に記載されている情報を使用して、仲介サーバーを無視するか、またはサイトと地域の情報を使用して、仲介サーバーをバイパスするかどうかを決定してください。

もう 1 つの高度なエンタープライズ VoIP 機能に当たる、オプションの通話受付管理 (CAC) の構成が済んでいる場合は、通話受付管理が実行する帯域幅の予約がメディア バイパスを採用する通話に適用されないようにしてください。メディア バイパスが採用されているかどうかの検証は最初に行われます。採用されている場合は、その通話に対しては通話受付管理は使用されません。通話受付管理に対するチェックは、メディア バイパスのチェックが不合格の場合にのみ行われます。このため、PSTN にルーティングされる特定の通話に対して 2 つの機能がともに適用されることはありません。メディア バイパスは、通話のメディア エンドポイント間に帯域幅の制約がないことを前提にしているため、2 つの機能が両立しないという論理的結論にたどり着きます。メディア バイパスは、帯域幅制限のあるリンク上では実行できません。このことから、PSTN の通話には次のいずれかが適用されます。a) 仲介サーバーをメディア バイパスし、通話受付管理は通話に対して帯域幅を予約しない。または b) 通話受付管理が通話に帯域幅の予約を適用し、メディアはその通話に関わる仲介サーバーで処理される。

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>次の手順: トランク接続でメディアバイパスを有効にする

PSTN 接続の初期設定 (ダイヤルプラン、音声ポリシー、PSTN 使用状況レコード、発信通話ルート、および翻訳ルール) を構成したら、「 [Lync Server 2013 でメディアバイパス](lync-server-2013-configure-a-trunk-with-media-bypass.md)を有効にする」の手順に従って、メディアのバイパスを有効にするプロセスを開始します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Lync Server 2013 のグローバルメディアバイパスオプション](lync-server-2013-global-media-bypass-options.md)  


[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

