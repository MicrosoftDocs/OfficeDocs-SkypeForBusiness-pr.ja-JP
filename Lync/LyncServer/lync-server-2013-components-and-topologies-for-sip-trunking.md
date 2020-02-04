---
title: 'Lync Server 2013: SIP トランキングのコンポーネントおよびトポロジ'
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
ms.openlocfilehash: d30c589ff02717ad49ce89d0d4e3324f6fe993e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 の SIP トランキングのコンポーネントおよびトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

次の図は、Lync Server の SIP トランキングトポロジを示しています。

**SIP トランキングトポロジ**

![SIP トランキングのトポロジ](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP トランキングのトポロジ")

図に示すように、エンタープライズ ネットワークと公衆交換電話網 (PSTN) サービス プロバイダーの間の接続には、IP 仮想プライベート ネットワーク (VPN) が使用されます。このプライベート ネットワークの目的は、IP 接続を提供し、セキュリティを強化し、(必要に応じて) サービス品質 (QoS) 保証を得ることです。VPN の性質により、SIP 信号トラフィックにトランスポート層セキュリティ (TLS) を使用したり、メディア トラフィックにセキュア リアルタイム転送プロトコル (SRTP) を使用したりする必要はありません。このため、企業とサービス プロバイダーの間の接続は、IP VPN を通じてトンネリングされる可能性のある SIP 用の普通の TCP 接続と、メディア用の普通のリアルタイム転送プロトコル (RTP) (over UDP) で構成されます。VPM ルーター間のすべてのファイアウォールのポートが開いていて VPN ルーターが通信できること、および VPN ルーターの外部エッジの IP アドレスがパブリック ルーティング可能であることを確認してください。

<div>


> [!IMPORTANT]  
> フェールオーバーを含め、高可用性のサポートを提供しているかどうかを確認するには、サービス プロバイダーに問い合わせてください。 サポートしている場合、高可用性を設定する手順を確認する必要があります。 たとえば、各仲介サーバーに1つの IP アドレスと1つの SIP トランクのみを構成する必要がある場合、または各仲介サーバーに複数の SIP trunks を構成する必要がある場合は、次の手順を実行します。<BR>複数のセントラルサイトがある場合は、他のセントラルサイトとの接続を有効にする機能がサービスプロバイダーにあるかどうかも確認します。



</div>

<div>


> [!NOTE]  
> SIP トランクの場合は、スタンドアロンの仲介サーバーを展開することを強くお勧めします。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync Server 2013 での仲介サーバーの展開とピアの定義</A>」を参照してください。



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>SIP トランキングを行うための仲介サーバーのセキュリティ保護

セキュリティ上の理由から、2 つの VPN ルーター間の各接続に仮想 LAN (VLAN) を設定する必要があります。VLAN の実際の設定プロセスは、ルーターの製造元によって異なります。詳細については、ルーター ベンダーに問い合わせてください。

次のガイドラインに従うことをお勧めします。

  - 仲介サーバーと境界ネットワーク内の VPN ルーターの間に仮想 LAN (VLAN) を設定します (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます)。

  - ルーターから VLAN へのブロードキャストまたはマルチキャスト パケットの転送は許可しません。

  - ルーターからのトラフィックを仲介サーバー以外の場所にルーティングするルーティングルールはブロックします。

VPN サーバーを使用する場合、次のガイドラインに従うことをお勧めします。

  - VPN サーバーと仲介サーバーの間に VLAN をセットアップします。

  - VPN サーバーから VLAN へのブロードキャストまたはマルチキャスト パケットの転送は許可しません。

  - VPN サーバートラフィックを仲介サーバー以外の場所にルーティングするルーティングルールをブロックします。

  - Generic Routing Encapsulation (GRE) を使用して VPN 上のデータを暗号化します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

