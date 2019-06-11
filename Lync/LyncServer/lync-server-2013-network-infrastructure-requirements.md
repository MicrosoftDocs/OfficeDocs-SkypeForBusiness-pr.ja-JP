---
title: Lync Server 2013 ネットワークインフラストラクチャの要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc1f74705469bf3a024d84848942eae972e0a629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 のネットワークインフラストラクチャ要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

Lync Server 2013 トポロジの各サーバーのネットワークアダプターカードは、少なくとも 1 gb/秒 (Gbps) をサポートしている必要があります。 通常、低レイテンシおよび高帯域幅のローカルエリアネットワーク (LAN) を使用して、Lync Server トポロジ内のすべてのサーバーの役割を接続する必要があります。 LAN のサイズは、トポロジーのサイズによって異なります。

  - Standard Edition のトポロジでは、サーバーは 1 Gbps のイーサネットまたは同等のネットワークに対応している必要があります。

  - フロントエンドプールトポロジでは、ほとんどのサーバーは 1 Gbps をサポートするネットワークに存在する必要があります。特に、音声/ビデオ (A/V) 会議とアプリケーション共有をサポートしている場合に適しています。

公衆交換電話網 (PSTN) 統合については、T1 回線か E1 回線、または SIP トランキングを使用して統合できます。

<div>

## <a name="audiovideo-network-requirements"></a>音声/ビデオネットワークの要件

Lync Server の展開における音声/ビデオ (A/V) のネットワーク要件には、次のようなものがあります。

  - DNS 負荷分散を使用して1つのエッジサーバーまたはエッジプールを展開する場合は、外部ファイアウォールを NAT として構成できます。 内部ファイアウォールを NAT として構成することはできません。 これらの要件の詳細については、計画ドキュメントの「 [Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。
    
    <div>
    

    > [!IMPORTANT]  
    > エッジプールを使用していて、ハードウェアロードバランサーを使っている場合は、各エッジサーバーでパブリック IP アドレスを使用する必要があります。また、nat デバイス (たとえば、ファイアウォール、または nat で接続されている他のインフラストラクチャデバイスなど) で NAT を使用することはできません。nd または outbound トラフィック)。 詳細については、「外部ユーザーアクセスの計画」の「<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">ポートの概要-ハードウェアロードバランサーでのスケール統合エッジとハードウェアロード2013バランサーの統合エッジ</A>」を参照してください。

    
    </div>

  - 組織でサービスの品質 (QoS) インフラストラクチャが使用されている場合、メディア サブシステムは、この既存のインフラストラクチャで機能するように設計されています。

  - インターネット プロトコル セキュリティ (IPsec) を使用する場合は、A/V トラフィックに使用するポート範囲に対する IPsec を無効にすることをお勧めします。 詳細については、計画ドキュメントの「 [Lync Server 2013 での IPsec の例外](lync-server-2013-ipsec-exceptions.md)」を参照してください。

最適なメディア品質を得るには、次の操作を行います。

  - 有効期間中に、1秒あたり65キロビット (Kbps) のオーディオストリームと 500 Kbps のビデオストリームのスループットをサポートするように、ネットワークリンクをプロビジョニングします。 双方向音声またはビデオセッションは、2つのストリームで構成されています。

  - このレベル上のトラフィックの予期しないスパイクや、時間の経過に伴う使用量の増加に対処するために、Lync Server メディアエンドポイントは、さまざまなネットワークの状態に対応し、オーディオとビデオの3倍のスループット (前の段落を参照) をサポートしています。許容できる品質を維持します。 ただし、この適応性が、プロビジョニングされたネットワークをサポートしているとは限りません。 [プロビジョニングされたネットワーク] では、Lync Server メディアエンドポイントがさまざまなネットワーク条件 (たとえば、一時的な高パケット損失など) を動的に処理する機能が減少します。

  - プロビジョニングが非常に困難で困難なネットワークリンクの場合は、低トラフィック量のプロビジョニングを検討することが必要になることがあります。 このシナリオでは、Lync Server メディアエンドポイントの弾力性によって、音声品質の一部が削減された場合のトラフィックボリュームとピークトラフィックレベルの違いについて説明します。 また、ヘッドルームでは、トラフィックの急激なピークを吸収できるということもあります。

  - 短期的には適切にプロビジョニングできないリンク (たとえば、非常に脆弱な WAN リンクを持つサイトなど) については、特定のユーザーのビデオを無効にすることを検討してください。

  - エンドツーエンドの遅延 (ミリ秒) の最大値である150ミリ秒 (ミリ秒) の上限になるようにネットワークをプロビジョニングします。 待ち時間は、Lync Server メディアコンポーネントが削減できない1つのネットワーク障碍であり、弱点を見つけて除去することが重要です。

  - ウイルス対策ソフトウェアを実行しているサーバーの場合は、最適なパフォーマンスと音質を実現するために、Lync Server を実行しているすべてのサーバーを例外の一覧に追加します。

</div>

<div>

## <a name="conferencing-network-requirements"></a>会議のネットワーク要件

インターネットインフォメーションサービス (IIS) サーバーから会議コンテンツをダウンロードするために使用される帯域幅は、アップロードされたコンテンツのサイズによって異なります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

