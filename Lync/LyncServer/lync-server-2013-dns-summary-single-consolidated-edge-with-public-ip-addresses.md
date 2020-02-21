---
title: DNS の概要-パブリック IP アドレスを使用する単一統合エッジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 622cb9811e33762bf40c05dfa5e5f0ab644b51aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>DNS の概要-Lync Server 2013 でのパブリック IP アドレスを使用する単一統合エッジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-03-09_

Lync Server 2013 へのリモートアクセスの DNS レコードの要件は、証明書とポートの場合と比べて非常に簡単です。 また、Lync 2013 を実行しているクライアントを構成する方法と、フェデレーションを有効にするかどうかに応じて、多くのレコードがオプションになります。

Lync 2013 DNS の要件の詳細については、「 [Lync Server 2013 の dns 要件を決定](lync-server-2013-determine-dns-requirements.md)する」を参照してください。

スプリットブレイン DNS が構成されていない場合に、Lync 2013 を実行しているクライアントの自動構成の詳細については、「 [Lync Server 2013 の DNS 要件を決定する](lync-server-2013-determine-dns-requirements.md)」の「スプリットブレイン dns なしの自動構成」を参照してください。

次の表に、単一統合エッジ トポロジの図に示される単一統合エッジ トポロジのサポートに必要な DNS レコードの概要を示します。 特定の DNS レコードは、Lync 2013 および Lync 2010 クライアントの自動構成にのみ必要であることに注意してください。 グループポリシーオブジェクト (Gpo) を使用して Lync クライアントを構成することを計画している場合は、関連付けられている自動構成レコードは必要ありません。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要: エッジサーバーのネットワークアダプターの要件

ルーティングに関する問題を回避するには、エッジサーバーに少なくとも2つのネットワークアダプターがあり、既定のゲートウェイが、外部インターフェイスに関連付けられているネットワークアダプター上でのみ設定されていることを確認します。 たとえば、パブリック ip アドレスを使用する単一の統合エッジトポロジ図に示すように、 [Lync Server 2013 のパブリック ip アドレスを使用する単一統合エッジ](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)トポロジでは、既定のゲートウェイは、パブリック ip アドレスを提供できるインターネット境界またはファイアウォールの外部ルーターを指します。 エッジサーバーインターフェイスのネットワーク関係は、NAT 関係ではなくルート関係です。

エッジ サーバーの 2 つのネットワーク アダプターは、次のように構成できます。

  - **ネットワーク アダプター 1 (内部インターフェイス)**
    
    172.25.33.10 が割り当てられた内部インターフェイス。
    
    デフォルト ゲートウェイは定義されません。
    
    Lync Server 2013 または Lync Server 2013 クライアントを実行しているサーバーが含まれるネットワーク (たとえば、172.25.33.0 から 192.168.10.0) に、エッジの内部インターフェイスを含むネットワークからのルートがあることを確認します。

  - **ネットワーク アダプター 2 (外部インターフェイス)**
    
    3 つのパブリック IP アドレスがこのネットワーク アダプターに割り当てられます (例: アクセス エッジ用の 131.107.155.10、Web 会議エッジ用の 131.107.155.20、音声ビデオ用の 131.107.155.30)。
    
    <div>
    

    > [!NOTE]
    > 推奨はされませんが、1 つの IP アドレスを 3 つのエッジ サービス インターフェイスのすべてで使用することもできます。この場合、IP アドレスの節約になりますが、サービスごとに別々のポート番号が必要です。既定のポート番号は 443/TCP であり、このトラフィックはほとんどのリモート ファイアウォールで許可されます。ポートの各値を (たとえば) アクセス エッジ用の 5061/TCP、Web 会議エッジ用の 444/TCP、および AV エッジ用の 443/TCP に変更すると、リモート ユーザーを隔てるファイアウォールで 5061/TCP および 444/TCP 経由のトラフィックが許可されないという問題が発生する可能性があります。また、3 つの異なる IP アドレスを使用すると、IP アドレスのフィルター処理が可能になるのでトラブルシューティングが容易になります。

    
    </div>
    
    アクセス エッジのパブリック IP アドレスは、デフォルト ゲートウェイをパブリック ルーター (131.107.155.1) に設定した、プライマリ アドレスです。
    
    Web 会議および A/V エッジのパブリック IP アドレスは、Windows Server の**ローカル エリアの接続プロパティ**にある **インターネット プロトコル バージョン 4 (TCP/IPv4)** および**インターネット プロトコル バージョン 6 (TCP/IPv6)** のプロパティの [**詳細**] セクションで指定される追加の IP アドレスです。

<div>


> [!TIP]
> 2つのネットワークアダプターを使用してエッジサーバーを構成するには、2つのオプションのいずれかを使用します。 もう1つの方法は、エッジサーバーの内部側と外部側に3つのネットワークアダプターを使用する方法です。 このオプションの主な利点は、エッジサーバーサービスごとに別個のネットワークアダプターがあり、トラブルシューティングを行う際により簡潔なデータ収集を行うことができるということです。



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a>パブリック IP アドレスを持つ単一統合トポロジ エッジで必要な DNS レコード (例)

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
<td><p>131.107.155.10</p></td>
<td><p>アクセス エッジ外部インターフェイス (Contoso)。必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Web 会議エッジ外部インターフェイス</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30)</p></td>
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
<td><p>SIP アクセス エッジ外部インターフェイス。"許可済み SIP ドメイン" (以前のリリースでは拡張フェデレーション) と呼ばれるフェデレーション パートナーの自動 DNS 検出で必要です。必要に応じて、Lync が有効なユーザーのいるすべての SIP ドメインに対して繰り返します。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>統合エッジ内部インターフェイス</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> 前の表に記載されているレコードは、 <EM>.net</EM>内線番号または<EM>.com</EM>拡張子のどちらかを使用して表示され、スプリットブレイン DNS を使用していない場合にどの領域を含める必要があるかを強調表示します。 スプリットブレイン DNS を使用している場合は、すべてのレコードが同一の領域にあり、内部と外部のどちらのバージョンであるかだけが区別されます。 詳細については、「 <A href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS 要件を決定する</A>」の「スプリットブレイン dns」を参照してください。



</div>

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



> [!IMPORTANT]
> この SRV レコードは、モビリティおよびプッシュ通知決済機関に必要です

</td>
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

