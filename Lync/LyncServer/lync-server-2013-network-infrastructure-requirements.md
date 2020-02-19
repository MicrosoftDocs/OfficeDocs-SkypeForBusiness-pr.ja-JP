---
title: Lync Server 2013 のネットワークインフラストラクチャの要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea383a77ff8d6089e2a01d7fb00df434f6d805e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 のネットワークインフラストラクチャ要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

Lync Server 2013 トポロジ内の各サーバーのネットワークアダプターカードは、少なくとも 1 Gbps (ギガビット/秒) をサポートしている必要があります。 通常、Lync Server トポロジ内のすべてのサーバーの役割は、低遅延および高帯域幅のローカルエリアネットワーク (LAN) を使用して接続する必要があります。 LAN のサイズは、トポロジのサイズに依存します。

  - Standard Edition のトポロジでは、サーバーは 1 Gbps のイーサネットまたは同等のものをサポートするネットワーク内に存在する必要があります。

  - フロントエンドプールトポロジでは、特に音声ビデオ (A/V) 会議とアプリケーション共有をサポートする場合、多くのサーバーが 1 Gbps を超えるネットワークに存在する必要があります。

公衆交換電話網 (PSTN) 統合については、T1 回線または E1 回線、あるいは SIP トランキングを使用することにより、統合を実行できます。

<div>

## <a name="audiovideo-network-requirements"></a>音声ビデオのネットワーク要件

Lync Server 展開での音声/ビデオ (A/V) のネットワーク要件には、次のようなものがあります。

  - DNS 負荷分散を使用して単一のエッジサーバーまたはエッジプールを展開する場合は、外部ファイアウォールを NAT として構成できます。 内部ファイアウォールは、NAT として構成できません。 これらの要件の詳細については、「計画」のドキュメントの「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)する」を参照してください。
    
    <div>
    

    > [!IMPORTANT]  
    > エッジプールがあり、ハードウェアロードバランサーを使用している場合は、各エッジサーバーでパブリック IP アドレスを使用する必要があり、nat デバイスのサーバーまたはプール (たとえば、ファイアウォール、または nat デバイスやその他のインフラストラクチャデバイス) で NAT を使用できません。nd または発信トラフィック)。 詳細については、「Planning for External User Access documentation」の「 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary-拡張統合エッジ (Lync Server 2013)</A> 」を参照してください。

    
    </div>

  - 組織でサービスの品質 (QoS) インフラストラクチャが使用されている場合、メディア サブシステムは、この既存のインフラストラクチャで機能するように設計されています。

  - インターネット プロトコル セキュリティ (IPsec) を使用する場合は、A/V トラフィックに使用されるポート範囲に対する IPsec を無効にすることをお勧めします。 詳細については、「計画」のドキュメントの「 [IPsec 例外 (Lync Server 2013](lync-server-2013-ipsec-exceptions.md) )」を参照してください。

最適なメディア品質を確保するには、以下の操作を行います。

  - ストリームが有効になっている場合は、ピーク利用期間に音声ストリームにつき 65 Kbps (キロビット/秒) およびビデオ ストリームにつき 500 Kbps のスループットをサポートするようにネットワーク リンクのプロビジョニングを行います。双方向の音声またはビデオ セッションは、2 つのストリームから構成されます。

  - 時間の経過とともに、このレベル以上のトラフィックに予期しないスパイクが発生し、使用率が増加した場合、Lync Server のメディアエンドポイントは、さまざまなネットワークの状態に適応し、オーディオとビデオのスループット (前の段落を参照) の3倍の負荷をサポートすることができます。許容できる品質を維持します。 ただし、その場合は、この適応性により、プロビジョニング不足のネットワークがサポートされると想定しないでください。 一部のプロビジョニングされたネットワークでは、Lync Server のメディアエンドポイントがさまざまなネットワークの状態 (たとえば、一時的な高パケット損失など) を動的に処理する機能が低下しています。

  - プロビジョニングが非常に高価で困難なネットワークリンクの場合は、低音量のトラフィックのプロビジョニングを検討する必要があります。 このシナリオでは、Lync Server media エンドポイントの弾力性が、トラフィックボリュームとピーク時のトラフィックレベルの違いを吸収します。これにより、音声品質の一部が減少します。 また、トラフィックの急激なピークを吸収するには、ヘッドルームが減少しています。

  - 短期間では正しくプロビジョニングできないリンク (貧弱な WAN リンクを備えたサイトなど) の場合は、特定ユーザーについてはビデオを無効にすることを検討してください。

  - ピーク負荷でエンドツーエンドの最大遅延 (待ち時間) 150 ミリ秒 (ms) を保証するようにネットワークのプロビジョニングを行います。 待機時間は、Lync Server メディアコンポーネントによって削減できないネットワーク障害の1つであり、脆弱なポイントを見つけて除去することが重要です。

  - ウイルス対策ソフトウェアを実行しているサーバーでは、最適なパフォーマンスと音声品質を提供するために、Lync Server を実行しているすべてのサーバーを例外リストに含めます。

</div>

<div>

## <a name="conferencing-network-requirements"></a>会議のネットワーク要件

インターネットインフォメーションサービス (IIS) サーバーから会議コンテンツをダウンロードするために使用される帯域幅は、アップロードされるコンテンツのサイズによって異なります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

