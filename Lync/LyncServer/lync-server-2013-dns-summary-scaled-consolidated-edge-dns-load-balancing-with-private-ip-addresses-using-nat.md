---
title: 'Lync Server 2013: DNS の概要-拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d01a7ea8c2f27c9cbd2a90624743dac55116c784
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>DNS の概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

Lync Server 2013 へのリモートアクセスの DNS レコードの要件は、証明書とポートの場合と比べて非常に簡単です。 また、Lync 2013 を実行しているクライアントを構成する方法と、フェデレーションを有効にするかどうかに応じて、多くのレコードがオプションになります。

Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を決定](lync-server-2013-determine-dns-requirements.md)する」を参照してください。

スプリットブレイン DNS が構成されていない場合の Lync 2013 クライアントの自動構成の構成の詳細については、「 [Lync Server 2013 の DNS 要件を決定](lync-server-2013-determine-dns-requirements.md)する」の「スプリットブレイン dns なしの自動構成」セクションを参照してください。

次の表に、単一統合エッジ トポロジの図に示される単一統合エッジ トポロジのサポートに必要な DNS レコードの概要を示します。 特定の DNS レコードは、Lync 2013 クライアントの自動構成にのみ必要であることに注意してください。 グループポリシーオブジェクト (Gpo) を使用して Lync クライアントを構成することを計画している場合は、関連付けられたレコードは必要ありません。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要: エッジサーバーのネットワークアダプターの要件

ルーティングに関する問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、既定のゲートウェイが、外部インターフェイスに関連付けられているネットワークアダプター上でのみ設定されていることを確認します。 たとえば、拡張統合エッジシナリオ図では、[拡張統合エッジ、Lync Server 2013 の NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)では、既定のゲートウェイが外部ファイアウォールを指しています。

それぞれのエッジ サーバーでは、2 つのネットワーク アダプターを次のように構成できます。

  - **ネットワーク アダプター 1 - ノード 1 (内部インターフェイス)**
    
    172.25.33.10 が割り当てられた内部インターフェイス。
    
    デフォルト ゲートウェイは定義されていません。
    
    Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。

  - **ネットワーク アダプター 1 - ノード 2 (内部インターフェイス)**
    
    172.25.33.11 が割り当てられた内部インターフェイス。
    
    デフォルト ゲートウェイは定義されません。
    
    Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。

  - **ネットワーク アダプター 2 ノード 1 (外部インターフェイス)**
    
    このネットワーク アダプターには、3 つのプライベート IP アドレスが割り当てられます。たとえば、アクセス エッジには 10.45.16.10、Web 会議エッジには 10.45.16.20、音声ビデオ エッジには 10.45.16.30 です。
    
    <div>
    

    > [!NOTE]  
    > 推奨の方法ではありませんが、単一の IP アドレスを 3 つのエッジ サービス インターフェイスすべてで使用することもできます。この方法は IP アドレスの節約にはなりますが、サービスごとにポート番号を変える必要があります。既定のポート番号は 443/TCP で、この場合にはほとんどのリモート ファイアウォールでトラフィックが許可されます。ポート番号を変更し、たとえばアクセス エッジは 5061/TCP、Web 会議エッジは 444/TCP、音声ビデオ エッジは 443/TCP に変えた場合、5061/TCP と 444/TCP のトラフィックを許可しないファイアウォールを使用しているリモート ユーザーで問題が生じる可能性があります。また、3 つの IP アドレスを別個に使用すると、IP アドレスによるフィルターを行えるため、トラブルシューティングも簡単になります。

    
    </div>
    
    アクセス エッジのパブリック IP アドレスは、デフォルト ゲートウェイを統合ルーター (10.45.16.1) に設定した、プライマリ アドレスです。
    
    Web 会議と音声ビデオ エッジのプライベート IP アドレスは、Windows Server の [**ローカル エリアの接続プロパティ**] で [**インターネット プロトコル バージョン 4 (TCP/IPv4)**] と [**インターネット プロトコル バージョン 6 (TCP/IPv6)**] のプロパティの [**詳細設定**] セクションにある追加の IP アドレスです。

  - **ネットワーク アダプター 2 ノード 2 (外部インターフェイス)**
    
    このネットワーク アダプターには、3 つのプライベート IP アドレスが割り当てられます。たとえば、アクセス エッジには 10.45.16.11、Web 会議エッジには 10.45.16.21、音声ビデオ エッジには 10.45.16.31 です。
    
    アクセス エッジのパブリック IP アドレスは、デフォルト ゲートウェイを統合ルーター (10.45.16.1) に設定した、プライマリ アドレスです。
    
    Web 会議と音声ビデオ エッジのプライベート IP アドレスは、Windows Server の [**ローカル エリアの接続プロパティ**] で [**インターネット プロトコル バージョン 4 (TCP/IPv4)**] と [**インターネット プロトコル バージョン 6 (TCP/IPv6)**] のプロパティの [**詳細設定**] セクションにある追加の IP アドレスです。

<div>


> [!TIP]  
> 2つのネットワークアダプターを使用してエッジサーバーを構成するには、2つのオプションのいずれかを使用します。 もう1つの方法は、エッジサーバーの内部側と外部側に3つのネットワークアダプターを使用する方法です。 このオプションの主な利点は、エッジサーバーサービスごとに別個のネットワークアダプターがあり、トラブルシューティングを行う際により簡潔なデータ収集を行うことができるということです。



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a>拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散に必要な DNS レコード (例)

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
<td><p>アクセス エッジ外部インターフェイス (Contoso)。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 および 131.107.155.21</p></td>
<td><p>Web 会議エッジ外部インターフェイス</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 および 131.107.155.31</p></td>
<td><p>音声ビデオ エッジ外部インターフェイス</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip の _tls</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>アクセス エッジ外部インターフェイス。 Lync 2013 および Lync 2010 クライアントを外部で動作するように自動構成するために必要です。 必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls の _tcp</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP アドレス エッジ外部インターフェイス。"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれました) という名前のフェデレーション パートナーの自動 DNS 検出に必要です。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</p></td>
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
<td><p>_sipfederationtls の _tcp</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>他の潜在的フェデレーション パートナーによるフェデレーションの自動 DNS 検出に必要な SIP アクセス エッジ外部インターフェイス。"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーションと呼ばれていました) と呼ばれます。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</p>
<div>

> [!IMPORTANT]  
> この SRV レコードは、モビリティおよびプッシュ通知決済機関に必要です


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a>DNS の概要 - パブリック インスタント メッセージング接続


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
<td><p>アクセスエッジサービスインターフェイス</p></td>
<td><p>アクセス エッジ外部インターフェイス (Contoso)。すべての SIP ドメインと Lync が有効なユーザーについて必要なだけ繰り返します。</p></td>
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
<td><p>_xmpp-サーバーの _tcp</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>アクセスエッジサービスまたはエッジプール上の XMPP プロキシの外部インターフェイス。すべての内部 SIP ドメインについて必要に応じて、グローバルポリシー、ユーザーが配置されているサイトポリシー、またはユーザーポリシーを使用して、外部アクセスポリシーを構成することにより、Lync が有効なユーザー。 許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。 詳細については、 <strong>「</strong>関連項目」を参照してください。</p></td>
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

