---
title: 'Lync Server 2013: メディアバイパスの構成'
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
ms.openlocfilehash: 93fe9bb93ad32c0871dd51d3818d2ca788327dc5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a>Lync Server 2013 でメディアバイパスを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

このセクションでは、少なくとも1つ以上の仲介サーバーを既に公開し、構成していることを前提としています (「lync server [2013 のトポロジビルダーでの仲介サーバーの定義](lync-server-2013-define-a-mediation-server-in-topology-builder.md)」および「lync server 2013 でのトポロジの[公開](lync-server-2013-publish-the-topology.md)」または「lync server [2013](lync-server-2013-publish-the-topology.md)2013 での[フロントエンドプールまたは Standard Edition サーバーの定義と構成](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)」を

また、このセクションでは、「 [Lync Server 2013 のトポロジビルダーでゲートウェイを定義](lync-server-2013-define-a-gateway-in-topology-builder.md)する」で説明されているように、PSTN 接続を提供するために少なくとも1つのゲートウェイピアを定義していることを前提としています。 接続先のピアが SIP トランキングプロバイダーの SBC の場合は、プロバイダーが修飾プロバイダーであること、およびプロバイダーがメディアバイパスをサポートしていることを確認してください。 たとえば、多くの SIP トランキングプロバイダーは、仲介サーバーからのトラフィックの受信のみを SBC に許可します。 その場合は、対象のトランクに対してバイパスを有効にしてはなりません。 また、組織が SIP トランキングプロバイダーに内部ネットワークの IP アドレスを表示しない限り、メディアバイパスを有効にすることはできません。

<div>


> [!NOTE]  
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。 Microsoft は、認定パートナーで PSTN ゲートウェイと sbc のセットをテストしており、Cisco IP-PBX でいくつかのテストを行いました。 メディアバイパスがサポートされるのは、統合コミュニケーションのオープン相互運用性プログラム– Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>の製品およびバージョンのみです。



</div>

このセクションでは、メディアバイパスを有効にして仲介サーバーに必要な処理を減らす方法について説明します。 メディアバイパスを有効にする前に、「計画」のドキュメントの「 [planning for media バイパス In Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) 」で説明されているように、環境がメディアバイパスをサポートするために必要な条件を満たしていることを確認してください。 また、「 [Lync server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」に記載されている情報を使用して、仲介サーバーをバイパスするか、仲介サーバーをバイパスするかどうかを決定する際にサイトと地域の情報を使用するように、メディアバイパスのグローバル設定を有効にするかどうかを決定してください。

もう 1 つの高度なエンタープライズ VoIP 機能に当たる、オプションの通話受付管理 (CAC) の構成が済んでいる場合は、通話受付管理が実行する帯域幅の予約がメディア バイパスを採用する通話に適用されないようにしてください。 メディア バイパスが採用されているかどうかの検証は最初に行われます。採用されている場合は、その通話に対しては通話受付管理は使用されません。通話受付管理に対するチェックは、メディア バイパスのチェックが不合格の場合にのみ行われます。 このため、PSTN にルーティングされる特定の通話に対して 2 つの機能がともに適用されることはありません。 メディア バイパスは、通話のメディア エンドポイント間に帯域幅の制約がないことを前提にしているため、2 つの機能が両立しないという論理的結論にたどり着きます。メディア バイパスは、帯域幅制限のあるリンク上では実行できません。 このことから、PSTN の通話には次のいずれかが適用されます。 a) 仲介サーバーをメディア バイパスし、通話受付管理は通話に対して帯域幅を予約しない。または b) 通話受付管理が通話に帯域幅の予約を適用し、メディアはその通話に関わる仲介サーバーで処理される。

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>次のステップ:  トランク接続でのメディア バイパスの有効化

PSTN 接続の初期設定 (ダイヤルプラン、音声ポリシー、PSTN 使用法レコード、発信通話ルート、および変換ルール) の構成が完了したら、「 [Configure a トランク with media バイパス In Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)」の手順を使用して、メディアバイパスを有効にするプロセスを開始します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でメディアバイパスを使用してトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013 でメディアバイパスを構成して仲介サーバーを常にバイパスする](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[サイトと地域の情報を使用するように Lync Server 2013 でメディアバイパスグローバル設定を構成する](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Lync Server 2013 のグローバルメディアバイパスオプション](lync-server-2013-global-media-bypass-options.md)  


[Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

