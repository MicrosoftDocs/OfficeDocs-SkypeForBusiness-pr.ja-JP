---
title: 'Lync Server 2013: DNS の概要-拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaa466792de1adcd3d048c946c7b36803fbaab63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501304"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>DNS の概要-Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-03-09_

Lync Server 2013 へのリモートアクセスの DNS レコードの要件は、証明書とポートの場合と比べて非常に簡単です。 また、Lync 2013 を実行しているクライアントを構成する方法と、フェデレーションを有効にするかどうかに応じて、多くのレコードがオプションになります。

Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を決定](lync-server-2013-determine-dns-requirements.md)する」を参照してください。

スプリットブレイン DNS が構成されていない場合の Lync 2013 クライアントの自動構成の構成の詳細については、「 [Lync Server 2013 の DNS 要件を決定](lync-server-2013-determine-dns-requirements.md)する」の「スプリットブレイン dns なしの自動構成」セクションを参照してください。

次の表に、単一統合エッジ トポロジの図に示される単一統合エッジ トポロジのサポートに必要な DNS レコードの概要を示します。 特定の DNS レコードは、Lync 2013 クライアントの自動構成にのみ必要であることに注意してください。 グループポリシーオブジェクト (Gpo) を使用して Lync クライアントを構成することを計画している場合は、関連付けられたレコードは必要ありません。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要: エッジサーバーのネットワークアダプターの要件

ルーティングに関する問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、既定のゲートウェイが、外部インターフェイスに関連付けられているネットワークアダプター上でのみ設定されていることを確認します。 たとえば、拡張統合エッジシナリオの図のように、 [拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散の場合、Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) では、既定のゲートウェイが外部ファイアウォールをポイントすることになります。

それぞれのエッジ サーバーでは、2 つのネットワーク アダプターを次のように構成できます。

  - **ネットワーク アダプター 1 - ノード 1 (内部インターフェイス)**
    
    172.25.33.10 が割り当てられた内部インターフェイス。
    
    デフォルト ゲートウェイは定義されません。
    
    Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。

  - **ネットワーク アダプター 1 - ノード 2 (内部インターフェイス)**
    
    172.25.33.11 が割り当てられた内部インターフェイス。
    
    デフォルト ゲートウェイは定義されません。
    
    Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。

  - **ネットワーク アダプター 2 ノード 1 (外部インターフェイス)**
    
    このネットワークアダプターには3つのプライベート IP アドレスが割り当てられます。たとえば、アクセスエッジサービスの131.107.155.10、Web 会議エッジサービスの131.107.155.20、音声ビデオエッジサービスの 131.107.155.30) のようになります。
    
    アクセスエッジサービスのパブリック IP アドレスは、デフォルトゲートウェイをパブリックルーター (131.107.155.1) に設定したプライマリアドレスです。
    
    Web 会議エッジサービスおよび音声ビデオエッジサービスのプライベート IP アドレスは、Windows Server の**ローカルエリア接続プロパティ**の**インターネットプロトコルバージョン 4 (tcp/IPv4)** および**インターネットプロトコルバージョン 6 (tcp/IPv6)** のプロパティの **[詳細設定**] セクションにある追加の ip アドレスです。
    
    <div>
    

    > [!NOTE]  
    > お勧めはできませんが、3 つのエッジ サービス インターフェイスすべてに 1 つの IP アドレスを使用できます。 これによって IP アドレスを節約できますが、サービスごとに異なるポート番号が必要です。 既定のポート番号は 443/TCP で、リモート ファイアウォールの大部分がトラフィックを許可します。 アクセスエッジサービスのポート値 (たとえば、アクセスエッジサービスの 5061/TCP、Web 会議エッジサービスの 444/tcp、および音声ビデオエッジサービスの 443/TCP) を変更すると、遅延しているファイアウォールが 5061/TCP および 444/TCP 経由のトラフィックを許可しないリモートユーザーに対して問題が発生する可能性があります。 また、3 つの異なる IP アドレスを使用すると、IP アドレスのフィルター処理が可能になるのでトラブルシューティングが容易になります。

    
    </div>

  - **ネットワーク アダプター 2 ノード 2 (外部インターフェイス)**
    
    このネットワークアダプターには3つのプライベート IP アドレスが割り当てられます。たとえば、アクセスエッジサービスの131.107.155.11、Web 会議エッジサービスのます (たとえば、音声ビデオエッジサービスの 131.107.155.31) のようになります。
    
    アクセスエッジサービスのパブリック IP アドレスは、デフォルトゲートウェイをパブリックルーター (131.107.155.1) に設定したプライマリアドレスです。
    
    Web 会議エッジサービスおよび音声ビデオエッジサービスのプライベート IP アドレスは、Windows Server の**ローカルエリア接続プロパティ**の**インターネットプロトコルバージョン 4 (tcp/IPv4)** および**インターネットプロトコルバージョン 6 (tcp/IPv6)** のプロパティの **[詳細設定**] セクションにある追加の ip アドレスです。

<div>


> [!TIP]  
> 2つのネットワークアダプターを使用してエッジサーバーを構成するには、2つのオプションのいずれかを使用します。 もう1つの方法は、エッジサーバーの内部側と外部側に3つのネットワークアダプターを使用する方法です。 このオプションの主な利点は、エッジサーバーサービスごとに別個のネットワークアダプターがあり、トラブルシューティングを行う際により簡潔なデータ収集を行うことができるということです。



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散に必要な DNS レコード (例)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN/DNS レコード</th>
<th>IP アドレス/FQDN</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 および 131.107.155.11</p></td>
<td><p>アクセスエッジサービスの外部インターフェイス (Contoso) は、Lync が有効なユーザーを持つすべての SIP ドメインについて必要なだけ繰り返します。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 および 131.107.155.21</p></td>
<td><p>Web 会議エッジサービスの外部インターフェイス</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 および 131.107.155.31</p></td>
<td><p>音声ビデオエッジサービスの外部インターフェイス</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip _sip._tls</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>アクセスエッジサービスの外部インターフェイス。 Lync 2013 および Lync 2010 クライアントを外部で動作するように自動構成するために必要です。 必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれました) と呼ばれるフェデレーションパートナーの自動 DNS 検出に必要なアクセスエッジサービスの外部インターフェイス。 すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 および 172.25.33.11</p></td>
<td><p>統合エッジ内部インターフェイス</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>フェデレーションに必要なレコード


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN</th>
<th>IP アドレス/FQDN ホスト レコード</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>他の潜在的フェデレーションパートナーへのフェデレーションの自動 DNS 検出に必要な SIP アクセスエッジサービスの外部インターフェイス (以前のリリースでは拡張フェデレーションと呼ばれます) と呼ばれる、"許可された SIP ドメイン" と呼ばれるものです。</p>
<div>

> [!IMPORTANT]  
> プッシュ通知サービスまたは Apple プッシュ通知サービスのいずれかを使用する Lync が有効なユーザーと Microsoft Lync モバイルクライアントを含むすべての SIP ドメインについて、必要に応じて繰り返します。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>XMPP の DNS の概要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN</th>
<th>IP アドレス/FQDN ホスト レコード</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>アクセスエッジサービスまたはエッジプール上の XMPP プロキシの外部インターフェイス。必要に応じて、Lync が有効になっているすべての内部 SIP ドメインについて、グローバルポリシー、ユーザーが配置されているサイトポリシー、Lync が有効なユーザーに適用されているユーザーポリシーを使用して、外部アクセスポリシーの構成を通じて、外部アクセスポリシーの構成を通じて実行できます。 許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。 詳細については、 <strong>「</strong> 関連項目」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (例)</p></td>
<td><p>XMPP プロキシをホストしているエッジサーバーまたはエッジプールのアクセスエッジサービスの IP アドレス</p></td>
<td><p>XMPP プロキシサービスをホストするアクセスエッジサービスまたはエッジプールを指します。 通常、作成する SRV レコードはこのホスト (A または AAAA) レコードを指し示します。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

