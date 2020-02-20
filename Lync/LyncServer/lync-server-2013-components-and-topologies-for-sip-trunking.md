---
title: 'Lync Server 2013: SIP トランキングのコンポーネントとトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b81768fe055c28fb8643a267b74de4cc99bc0ff3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 での SIP トランキングのコンポーネントとトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

次の図は、Lync Server の SIP トランキングトポロジを示しています。

**SIP トランキングのトポロジ**

![SIP トランキングトポロジ](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP トランキングトポロジ")

図に示すように、エンタープライズ ネットワークと公衆交換電話網 (PSTN) サービス プロバイダーの間の接続には、IP 仮想プライベート ネットワーク (VPN) が使用されます。このプライベート ネットワークの目的は、IP 接続を提供し、セキュリティを強化し、(必要に応じて) サービス品質 (QoS) 保証を得ることです。VPN の性質により、SIP 信号トラフィックにトランスポート層セキュリティ (TLS) を使用したり、メディア トラフィックにセキュア リアルタイム転送プロトコル (SRTP) を使用したりする必要はありません。このため、企業とサービス プロバイダーの間の接続は、IP VPN を通じてトンネリングされる可能性のある SIP 用の普通の TCP 接続と、メディア用の普通のリアルタイム転送プロトコル (RTP) (over UDP) で構成されます。VPM ルーター間のすべてのファイアウォールのポートが開いていて VPN ルーターが通信できること、および VPN ルーターの外部エッジの IP アドレスがパブリック ルーティング可能であることを確認してください。

<div>


> [!IMPORTANT]  
> フェールオーバーを含め、高可用性のサポートを提供しているかどうかを確認するには、サービス プロバイダーに問い合わせてください。 サポートしている場合、高可用性を設定する手順を確認する必要があります。 たとえば、各仲介サーバーで1つの IP アドレスと1つの SIP トランクのみを構成する必要がありますか。または、各仲介サーバーで複数の SIP トランクを構成する必要がありますか。<BR>中央サイトが複数ある場合は、サービスプロバイダーが別の中央サイトとの接続を有効にできるかどうかも確認します。



</div>

<div>


> [!NOTE]  
> SIP トランキングの場合は、スタンドアロンの仲介サーバーを展開することを強くお勧めします。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync Server 2013 での仲介サーバーの展開とピアの定義</A>」を参照してください。



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>SIP トランキングを行うための仲介サーバーのセキュリティ保護

セキュリティ上の理由から、2 つの VPN ルーター間の各接続に仮想 LAN (VLAN) を設定する必要があります。 VLAN の実際の設定プロセスは、ルーターの製造元によって異なります。詳細については、ルーター ベンダーに問い合わせてください。

次のガイドラインに従うことをお勧めします。

  - 境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) の仲介サーバーと VPN ルーターの間に仮想 LAN (VLAN) を設定します。

  - ルーターから VLAN へのブロードキャストまたはマルチキャスト パケットの転送は許可しません。

  - 仲介サーバー以外の場所にルーターからのトラフィックをルーティングするすべてのルーティングルールを禁止します。

VPN サーバーを使用する場合、次のガイドラインに従うことをお勧めします。

  - VPN サーバーと仲介サーバーの間に VLAN を設定します。

  - VPN サーバーから VLAN へのブロードキャストまたはマルチキャスト パケットの転送は許可しません。

  - 仲介サーバー以外の場所に VPN サーバートラフィックをルーティングするすべてのルーティングルールを禁止します。

  - Generic Routing Encapsulation (GRE) を使用して VPN 上のデータを暗号化します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

